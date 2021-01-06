---
title: Kubernetes-WCF 开发人员 gRPC
description: 在 Kubernetes 群集中运行 ASP.NET Core gRPC 服务。
ms.date: 12/15/2020
ms.openlocfilehash: 0b457d6fa982b5f5b983194d4aedbff0eb782f36
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938049"
---
# <a name="kubernetes"></a><span data-ttu-id="2247b-103">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="2247b-103">Kubernetes</span></span>

<span data-ttu-id="2247b-104">尽管可以在 Docker 主机上手动运行容器，但对于可靠的生产系统，更好的做法是使用容器业务流程引擎来管理群集中多个服务器上运行的多个实例。</span><span class="sxs-lookup"><span data-stu-id="2247b-104">Although it's possible to run containers manually on Docker hosts, for reliable production systems it's better to use a container orchestration engine to manage multiple instances running across several servers in a cluster.</span></span> <span data-ttu-id="2247b-105">提供各种容器业务流程引擎，包括 Kubernetes、Docker Swarm 和 Apache Mesos。</span><span class="sxs-lookup"><span data-stu-id="2247b-105">There are various container orchestration engines available, including Kubernetes, Docker Swarm, and Apache Mesos.</span></span> <span data-ttu-id="2247b-106">但在这些引擎中，Kubernetes 的使用幅度远远超出最大，因此，本章将重点介绍这一点。</span><span class="sxs-lookup"><span data-stu-id="2247b-106">But of these engines, Kubernetes is far and away the most widely used, so it will be the focus of this chapter.</span></span>

<span data-ttu-id="2247b-107">Kubernetes 包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="2247b-107">Kubernetes includes the following functionality:</span></span>

- <span data-ttu-id="2247b-108">**计划** 在群集内的多个节点上运行容器，确保可用资源的平衡使用，在存在中断的情况下使容器保持运行，并处理对新版本的映像或新配置的滚动更新。</span><span class="sxs-lookup"><span data-stu-id="2247b-108">**Scheduling** runs containers on multiple nodes within a cluster, ensuring balanced usage of the available resource, keeping containers running if there are outages, and handling rolling updates to new versions of images or new configurations.</span></span>
- <span data-ttu-id="2247b-109">**运行状况检查** 监视容器，以确保继续服务。</span><span class="sxs-lookup"><span data-stu-id="2247b-109">**Health checks** monitor containers to ensure continued service.</span></span>
- <span data-ttu-id="2247b-110">**DNS & 服务发现** 处理群集中服务之间的路由。</span><span class="sxs-lookup"><span data-stu-id="2247b-110">**DNS & service discovery** handles routing between services within a cluster.</span></span>
- <span data-ttu-id="2247b-111">**入口** 公开选定的服务，通常在这些服务的实例之间提供负载平衡。</span><span class="sxs-lookup"><span data-stu-id="2247b-111">**Ingress** exposes selected services externally and generally provides load-balancing across instances of those services.</span></span>
- <span data-ttu-id="2247b-112">**资源管理** 将存储等外部资源附加到容器。</span><span class="sxs-lookup"><span data-stu-id="2247b-112">**Resource management** attaches external resources like storage to containers.</span></span>

<span data-ttu-id="2247b-113">本章详细介绍如何将 ASP.NET Core gRPC 服务和使用该服务的网站部署到 Kubernetes 群集中。</span><span class="sxs-lookup"><span data-stu-id="2247b-113">This chapter will detail how to deploy an ASP.NET Core gRPC service and a website that consumes the service into a Kubernetes cluster.</span></span> <span data-ttu-id="2247b-114">使用的示例应用程序可在 GitHub 上的 [dotnet/grpc/for wcf 开发人员](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) 存储库中找到。</span><span class="sxs-lookup"><span data-stu-id="2247b-114">The sample application used is available in the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="kubernetes-terminology"></a><span data-ttu-id="2247b-115">Kubernetes 术语</span><span class="sxs-lookup"><span data-stu-id="2247b-115">Kubernetes terminology</span></span>

<span data-ttu-id="2247b-116">Kubernetes 使用 *desired state configuration*： API 用于描述 *pod、\*\*部署* 和 *服务* 等对象，而 *控制平面* 负责实现 *群集* 中所有 *节点* 上的所需状态。</span><span class="sxs-lookup"><span data-stu-id="2247b-116">Kubernetes uses *desired state configuration*: the API is used to describe objects like *Pods*, *Deployments*, and *Services*, and the *Control Plane* takes care of implementing the desired state across all the *nodes* in a *cluster*.</span></span> <span data-ttu-id="2247b-117">Kubernetes 群集具有运行 *KUBERNETES API* 的 *主* 节点，可以通过编程方式或使用 `kubectl` 命令行工具进行通信。</span><span class="sxs-lookup"><span data-stu-id="2247b-117">A Kubernetes cluster has a *Master* node that runs the *Kubernetes API*, which you can communicate with programmatically or by using the `kubectl` command-line tool.</span></span> <span data-ttu-id="2247b-118">`kubectl` 可以通过命令行参数创建和管理对象，但它最适合包含 Kubernetes 对象的声明数据的 YAML 文件。</span><span class="sxs-lookup"><span data-stu-id="2247b-118">`kubectl` can create and manage objects through command-line arguments, but it works best with YAML files that contain declaration data for Kubernetes objects.</span></span>

### <a name="kubernetes-yaml-files"></a><span data-ttu-id="2247b-119">Kubernetes YAML 文件</span><span class="sxs-lookup"><span data-stu-id="2247b-119">Kubernetes YAML files</span></span>

<span data-ttu-id="2247b-120">每个 Kubernetes YAML 文件将至少有三个顶级属性：</span><span class="sxs-lookup"><span data-stu-id="2247b-120">Every Kubernetes YAML file will have at least three top-level properties:</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

<span data-ttu-id="2247b-121">`apiVersion`属性用于指定 (哪个版本以及该文件的目标) 。</span><span class="sxs-lookup"><span data-stu-id="2247b-121">The `apiVersion` property is used to specify which version (and which API) the file is intended for.</span></span> <span data-ttu-id="2247b-122">`kind`属性指定 YAML 表示的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="2247b-122">The `kind` property specifies the kind of object the YAML represents.</span></span> <span data-ttu-id="2247b-123">`metadata`属性包含对象属性，如 `name` 、 `namespace` 和 `labels` 。</span><span class="sxs-lookup"><span data-stu-id="2247b-123">The `metadata` property contains object properties like `name`, `namespace`, and `labels`.</span></span>

<span data-ttu-id="2247b-124">大多数 Kubernetes YAML 文件还将有一个 `spec` 描述创建对象所需的资源和配置的部分。</span><span class="sxs-lookup"><span data-stu-id="2247b-124">Most Kubernetes YAML files will also have a `spec` section that describes the resources and configuration necessary to create the object.</span></span>

### <a name="pods"></a><span data-ttu-id="2247b-125">Pod</span><span class="sxs-lookup"><span data-stu-id="2247b-125">Pods</span></span>

<span data-ttu-id="2247b-126">Pod 是 Kubernetes 中的基本执行单位。</span><span class="sxs-lookup"><span data-stu-id="2247b-126">Pods are the basic units of execution in Kubernetes.</span></span> <span data-ttu-id="2247b-127">它们可以运行多个容器，但也可用于运行单个容器。</span><span class="sxs-lookup"><span data-stu-id="2247b-127">They can run multiple containers, but they're also used to run single containers.</span></span> <span data-ttu-id="2247b-128">Pod 还包括容器所需的所有存储资源以及网络 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2247b-128">The pod also includes any storage resources required by the containers, and the network IP address.</span></span>

### <a name="services"></a><span data-ttu-id="2247b-129">服务</span><span class="sxs-lookup"><span data-stu-id="2247b-129">Services</span></span>

<span data-ttu-id="2247b-130">服务是元对象，用于描述 pod (或 pod) 集，并提供一种在群集内访问这些对象的方式，如使用群集 DNS 服务将服务名称映射到一组 pod IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2247b-130">Services are meta-objects that describe Pods (or sets of Pods) and provide a way to access them within the cluster, such as mapping a service name to a set of pod IP addresses by using the cluster DNS service.</span></span>

### <a name="deployments"></a><span data-ttu-id="2247b-131">部署</span><span class="sxs-lookup"><span data-stu-id="2247b-131">Deployments</span></span>

<span data-ttu-id="2247b-132">部署是 pod 的 *所需状态* 对象。</span><span class="sxs-lookup"><span data-stu-id="2247b-132">Deployments are the *desired state* objects for Pods.</span></span> <span data-ttu-id="2247b-133">如果手动创建 pod，则它将在终止时重新启动。</span><span class="sxs-lookup"><span data-stu-id="2247b-133">If you create a pod manually, it won't be restarted when it terminates.</span></span> <span data-ttu-id="2247b-134">部署用于告知群集哪些 pod 和这些 pod 的副本数在当前时间运行。</span><span class="sxs-lookup"><span data-stu-id="2247b-134">Deployments are used to tell the cluster which Pods, and how many replicas of those Pods, should be running at the present time.</span></span>

### <a name="other-objects"></a><span data-ttu-id="2247b-135">其他对象</span><span class="sxs-lookup"><span data-stu-id="2247b-135">Other objects</span></span>

<span data-ttu-id="2247b-136">箱、服务和部署只是三个最基本的对象类型。</span><span class="sxs-lookup"><span data-stu-id="2247b-136">Pods, Services, and Deployments are just three of the most basic object types.</span></span> <span data-ttu-id="2247b-137">Kubernetes 群集管理了许多其他对象类型。</span><span class="sxs-lookup"><span data-stu-id="2247b-137">There are dozens of other object types that are managed by Kubernetes clusters.</span></span> <span data-ttu-id="2247b-138">有关详细信息，请参阅 [Kubernetes 概念](https://kubernetes.io/docs/concepts/) 文档。</span><span class="sxs-lookup"><span data-stu-id="2247b-138">For more information, see the [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) documentation.</span></span>

### <a name="namespaces"></a><span data-ttu-id="2247b-139">命名空间</span><span class="sxs-lookup"><span data-stu-id="2247b-139">Namespaces</span></span>

<span data-ttu-id="2247b-140">Kubernetes 群集旨在扩展到数百或数千个节点并运行相似的服务数量。</span><span class="sxs-lookup"><span data-stu-id="2247b-140">Kubernetes clusters are designed to scale to hundreds or thousands of nodes and to run similar numbers of services.</span></span> <span data-ttu-id="2247b-141">若要避免对象名称之间的冲突，请使用命名空间将对象组合成较大的应用程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="2247b-141">To avoid clashes between object names, namespaces are used to group objects together as part of larger applications.</span></span> <span data-ttu-id="2247b-142">Kubernetes 自己的服务在 `default` 命名空间中运行。</span><span class="sxs-lookup"><span data-stu-id="2247b-142">Kubernetes's own services run in a `default` namespace.</span></span> <span data-ttu-id="2247b-143">所有用户对象都应在其自己的命名空间中创建，以避免与群集中的默认对象或其他租户发生冲突。</span><span class="sxs-lookup"><span data-stu-id="2247b-143">All user objects should be created in their own namespaces to avoid potential clashes with default objects or other tenants in the cluster.</span></span>

## <a name="get-started-with-kubernetes"></a><span data-ttu-id="2247b-144">Kubernetes 入门</span><span class="sxs-lookup"><span data-stu-id="2247b-144">Get started with Kubernetes</span></span>

<span data-ttu-id="2247b-145">如果你运行的是适用于 Windows 的 Docker Desktop 或适用于 Mac 的 Docker Desktop，则 Kubernetes 已可用。</span><span class="sxs-lookup"><span data-stu-id="2247b-145">If you're running Docker Desktop for Windows or Docker Desktop for Mac, Kubernetes is already available.</span></span> <span data-ttu-id="2247b-146">只需在 "**设置**" 窗口的 " **Kubernetes** " 部分中将其启用：</span><span class="sxs-lookup"><span data-stu-id="2247b-146">Just enable it in the **Kubernetes** section of the **Settings** window:</span></span>

![在 Docker Desktop 中启用 Kubernetes](media/kubernetes/enable-kubernetes-docker-desktop-v2.png)

<span data-ttu-id="2247b-148">若要在 Linux 上运行本地 Kubernetes 群集，请考虑使用 [minikube](https://github.com/kubernetes/minikube)或 [MicroK8s](https://microk8s.io/) （如果 linux 分发支持 [snap](https://snapcraft.io/)）。</span><span class="sxs-lookup"><span data-stu-id="2247b-148">To run a local Kubernetes cluster on Linux, consider [minikube](https://github.com/kubernetes/minikube), or [MicroK8s](https://microk8s.io/) if your Linux distribution supports [snaps](https://snapcraft.io/).</span></span>

<span data-ttu-id="2247b-149">若要确认群集是否正在运行且可访问，请运行 `kubectl version` 以下命令：</span><span class="sxs-lookup"><span data-stu-id="2247b-149">To confirm that your cluster is running and accessible, run the `kubectl version` command:</span></span>

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"19", GitVersion:"v1.19.3", GitCommit:"1e11e4a2108024935ecfcb2912226cedeafd99df", GitTreeState:"clean", BuildDate:"2020-10-14T12:50:19Z", GoVersion:"go1.15.2", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"19", GitVersion:"v1.19.3", GitCommit:"1e11e4a2108024935ecfcb2912226cedeafd99df", GitTreeState:"clean", BuildDate:"2020-10-14T12:41:49Z", GoVersion:"go1.15.2", Compiler:"gc", Platform:"linux/amd64"}
```

<span data-ttu-id="2247b-150">在此示例中， `kubectl` CLI 和 Kubernetes 服务器都运行的是版本1.14.6。</span><span class="sxs-lookup"><span data-stu-id="2247b-150">In this example, both the `kubectl` CLI and the Kubernetes server are running version 1.14.6.</span></span> <span data-ttu-id="2247b-151">的每个版本 `kubectl` 都应支持服务器的上一个和下一个版本，因此 `kubectl` 1.14 也适用于服务器版本1.13 和1.15。</span><span class="sxs-lookup"><span data-stu-id="2247b-151">Each version of `kubectl` is supposed to support the previous and next version of the server, so `kubectl` 1.14 should work with server versions 1.13 and 1.15 as well.</span></span>

## <a name="run-services-on-kubernetes"></a><span data-ttu-id="2247b-152">在 Kubernetes 上运行服务</span><span class="sxs-lookup"><span data-stu-id="2247b-152">Run services on Kubernetes</span></span>

<span data-ttu-id="2247b-153">该示例应用程序的 `kube` 目录包含三个 YAML 文件。</span><span class="sxs-lookup"><span data-stu-id="2247b-153">The sample application has a `kube` directory that contains three YAML files.</span></span> <span data-ttu-id="2247b-154">该 `namespace.yml` 文件声明自定义命名空间： `stocks` 。</span><span class="sxs-lookup"><span data-stu-id="2247b-154">The `namespace.yml` file declares a custom namespace: `stocks`.</span></span> <span data-ttu-id="2247b-155">该 `stockdata.yml` 文件声明 gRPC 应用程序的部署和服务， `stockweb.yml` 文件声明使用 gRPC 服务的 ASP.NET CORE 5.0 MVC web 应用程序的部署和服务。</span><span class="sxs-lookup"><span data-stu-id="2247b-155">The `stockdata.yml` file declares the Deployment and the Service for the gRPC application, and the `stockweb.yml` file declares the Deployment and Service for an ASP.NET Core 5.0 MVC web application that consumes the gRPC service.</span></span>

<span data-ttu-id="2247b-156">若要将 `YAML` 文件与配合使用 `kubectl` ，请运行 `apply -f` 以下命令：</span><span class="sxs-lookup"><span data-stu-id="2247b-156">To use a `YAML` file with `kubectl`, run the `apply -f` command:</span></span>

```console
kubectl apply -f object.yml
```

<span data-ttu-id="2247b-157">`apply`此命令将检查 YAML 文件的有效性并显示从 API 收到的任何错误，但不会等待，直到创建了该文件中声明的所有对象，因为此步骤可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="2247b-157">The `apply` command will check the validity of the YAML file and display any errors received from the API, but doesn't wait until all the objects declared in the file have been created because this step can take some time.</span></span> <span data-ttu-id="2247b-158">使用 `kubectl get` 带有相关对象类型的命令检查群集中的对象创建。</span><span class="sxs-lookup"><span data-stu-id="2247b-158">Use the `kubectl get` command with the relevant object types to check on object creation in the cluster.</span></span>

### <a name="the-namespace-declaration"></a><span data-ttu-id="2247b-159">命名空间声明</span><span class="sxs-lookup"><span data-stu-id="2247b-159">The namespace declaration</span></span>

<span data-ttu-id="2247b-160">命名空间声明非常简单，只需分配 `name` ：</span><span class="sxs-lookup"><span data-stu-id="2247b-160">Namespace declaration is simple and requires only assigning a `name`:</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

<span data-ttu-id="2247b-161">使用 `kubectl` 应用 `namespace.yml` 文件，并确认已成功创建命名空间：</span><span class="sxs-lookup"><span data-stu-id="2247b-161">Use `kubectl` to apply the `namespace.yml` file and to confirm the namespace is created successfully:</span></span>

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a><span data-ttu-id="2247b-162">StockData 应用程序</span><span class="sxs-lookup"><span data-stu-id="2247b-162">The StockData application</span></span>

<span data-ttu-id="2247b-163">该 `stockdata.yml` 文件声明了两个对象：一个部署和一个服务。</span><span class="sxs-lookup"><span data-stu-id="2247b-163">The `stockdata.yml` file declares two objects: a Deployment and a Service.</span></span>

#### <a name="the-stockdata-deployment"></a><span data-ttu-id="2247b-164">StockData 部署</span><span class="sxs-lookup"><span data-stu-id="2247b-164">The StockData Deployment</span></span>

<span data-ttu-id="2247b-165">YAML 文件的部署部分 `spec` 为部署本身提供，其中包括所需的副本数，以及 `template` 部署要创建和管理的 Pod 对象的。</span><span class="sxs-lookup"><span data-stu-id="2247b-165">The Deployment part of the YAML file provides the `spec` for the deployment itself, including the number of replicas required, and a `template` for the Pod objects to be created and managed by the deployment.</span></span> <span data-ttu-id="2247b-166">请注意，部署对象由 API 管理 `apps` ，如中所指定 `apiVersion` ，而不是主 Kubernetes API。</span><span class="sxs-lookup"><span data-stu-id="2247b-166">Note that Deployment objects are managed by the `apps` API, as specified in `apiVersion`, rather than the main Kubernetes API.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 1
  template:
    metadata:
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

<span data-ttu-id="2247b-167">`spec.selector`属性用于将正在运行的 pod 与部署相匹配。</span><span class="sxs-lookup"><span data-stu-id="2247b-167">The `spec.selector` property is used to match running Pods to the Deployment.</span></span> <span data-ttu-id="2247b-168">Pod 的 `metadata.labels` 属性必须与属性匹配， `matchLabels` 否则 API 调用将失败。</span><span class="sxs-lookup"><span data-stu-id="2247b-168">The Pod's `metadata.labels` property must match the `matchLabels` property or the API call will fail.</span></span>

<span data-ttu-id="2247b-169">`template.spec`部分声明要运行的容器。</span><span class="sxs-lookup"><span data-stu-id="2247b-169">The `template.spec` section declares the container to be run.</span></span> <span data-ttu-id="2247b-170">当你使用本地 Kubernetes 群集（如 Docker Desktop 提供的群集）时，可以指定在本地生成的映像，只要它们具有版本标记即可。</span><span class="sxs-lookup"><span data-stu-id="2247b-170">When you're working with a local Kubernetes cluster, such as the one provided by Docker Desktop, you can specify images that were built locally as long as they have a version tag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2247b-171">默认情况下，Kubernetes 将始终检查并尝试请求新映像。</span><span class="sxs-lookup"><span data-stu-id="2247b-171">By default, Kubernetes will always check for and try to pull a new image.</span></span> <span data-ttu-id="2247b-172">如果在其任何已知存储库中都找不到该映像，则创建 Pod 会失败。</span><span class="sxs-lookup"><span data-stu-id="2247b-172">If it can't find the image in any of its known repositories, the Pod creation will fail.</span></span> <span data-ttu-id="2247b-173">若要使用本地映像，请将设置 `imagePullPolicy` 为 `Never` 。</span><span class="sxs-lookup"><span data-stu-id="2247b-173">To work with local images, set the `imagePullPolicy` to `Never`.</span></span>

<span data-ttu-id="2247b-174">`ports`属性指定应在 Pod 上发布的容器端口。</span><span class="sxs-lookup"><span data-stu-id="2247b-174">The `ports` property specifies which container ports should be published on the Pod.</span></span> <span data-ttu-id="2247b-175">`stockservice`映像在标准 HTTP 端口上运行服务，因此端口80已发布。</span><span class="sxs-lookup"><span data-stu-id="2247b-175">The `stockservice` image runs the service on the standard HTTP port, so port 80 is published.</span></span>

<span data-ttu-id="2247b-176">`resources`部分将资源限制应用于在 Pod 中运行的容器。</span><span class="sxs-lookup"><span data-stu-id="2247b-176">The `resources` section applies resource limits to the container running within the Pod.</span></span> <span data-ttu-id="2247b-177">这是一种很好的做法，因为它可以防止单个 Pod 消耗节点上的所有可用 CPU 或内存。</span><span class="sxs-lookup"><span data-stu-id="2247b-177">This is a good practice because it prevents an individual Pod from consuming all the available CPU or memory on a node.</span></span>

> [!NOTE]
> <span data-ttu-id="2247b-178">ASP.NET Core 5.0 经过优化和优化，可在资源受限的容器中运行。</span><span class="sxs-lookup"><span data-stu-id="2247b-178">ASP.NET Core 5.0 has been optimized and tuned to run in resource-limited containers.</span></span> <span data-ttu-id="2247b-179">`dotnet/core/aspnet`Docker 映像设置环境变量，以告知 `dotnet` 运行时它在容器中。</span><span class="sxs-lookup"><span data-stu-id="2247b-179">The `dotnet/core/aspnet` Docker image sets an environment variable to tell the `dotnet` runtime that it's in a container.</span></span>

#### <a name="the-stockdata-service"></a><span data-ttu-id="2247b-180">StockData 服务</span><span class="sxs-lookup"><span data-stu-id="2247b-180">The StockData Service</span></span>

<span data-ttu-id="2247b-181">YAML 文件的服务部分声明了向群集中的 pod 提供访问权限的服务。</span><span class="sxs-lookup"><span data-stu-id="2247b-181">The Service part of the YAML file declares the service that provides access to the Pods within the cluster.</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

<span data-ttu-id="2247b-182">`spec` `selector` `Pods` 在这种情况下，服务使用属性来匹配运行，在此示例中，查找具有标签的 pod `run: stockdata` 。</span><span class="sxs-lookup"><span data-stu-id="2247b-182">The Service `spec` uses the `selector` property to match running `Pods`, in this case looking for Pods that have a label `run: stockdata`.</span></span> <span data-ttu-id="2247b-183">匹配的 pod 上指定的已 `port` 命名的服务发布。</span><span class="sxs-lookup"><span data-stu-id="2247b-183">The specified `port` on matching Pods is published by the named service.</span></span> <span data-ttu-id="2247b-184">命名空间中运行的其他盒 `stocks` 可以使用作为地址访问此服务上的 HTTP `http://stockdata` 。</span><span class="sxs-lookup"><span data-stu-id="2247b-184">Other Pods running in the `stocks` namespace can access HTTP on this service by using `http://stockdata` as the address.</span></span> <span data-ttu-id="2247b-185">在其他命名空间中运行的 pod 可以使用 `http://stockdata.stocks` 主机名。</span><span class="sxs-lookup"><span data-stu-id="2247b-185">Pods running in other namespaces can use the `http://stockdata.stocks` host name.</span></span> <span data-ttu-id="2247b-186">您可以通过使用 [网络策略](https://kubernetes.io/docs/concepts/services-networking/network-policies/)来控制跨命名空间的服务访问。</span><span class="sxs-lookup"><span data-stu-id="2247b-186">You can control cross-namespace service access by using [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span></span>

#### <a name="deploy-the-stockdata-application"></a><span data-ttu-id="2247b-187">部署 StockData 应用程序</span><span class="sxs-lookup"><span data-stu-id="2247b-187">Deploy the StockData application</span></span>

<span data-ttu-id="2247b-188">使用 `kubectl` 应用 `stockdata.yml` 文件，并确认已创建部署和服务：</span><span class="sxs-lookup"><span data-stu-id="2247b-188">Use `kubectl` to apply the `stockdata.yml` file and confirm that the Deployment and Service were created:</span></span>

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a><span data-ttu-id="2247b-189">StockWeb 应用程序</span><span class="sxs-lookup"><span data-stu-id="2247b-189">The StockWeb application</span></span>

<span data-ttu-id="2247b-190">该 `stockweb.yml` 文件声明 MVC 应用程序的部署和服务。</span><span class="sxs-lookup"><span data-stu-id="2247b-190">The `stockweb.yml` file declares the Deployment and Service for the MVC application.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a><span data-ttu-id="2247b-191">环境变量</span><span class="sxs-lookup"><span data-stu-id="2247b-191">Environment variables</span></span>

<span data-ttu-id="2247b-192">`env`部署对象的部分指定要在运行映像的容器中设置的环境变量 `stockweb:1.0.0` 。</span><span class="sxs-lookup"><span data-stu-id="2247b-192">The `env` section of the Deployment object specifies environment variables to be set in the container that's running the `stockweb:1.0.0` images.</span></span>

<span data-ttu-id="2247b-193">此 **`StockData__Address`** 环境变量将映射到 `StockData:Address` 配置设置，感谢 EnvironmentVariables 配置提供程序。</span><span class="sxs-lookup"><span data-stu-id="2247b-193">The **`StockData__Address`** environment variable will map to the `StockData:Address` configuration setting thanks to the EnvironmentVariables configuration provider.</span></span> <span data-ttu-id="2247b-194">此设置在名称之间使用双下划线分隔部分。</span><span class="sxs-lookup"><span data-stu-id="2247b-194">This setting uses double underscores between names to separate sections.</span></span> <span data-ttu-id="2247b-195">该地址使用 `stockdata` 在同一 Kubernetes 命名空间中运行的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="2247b-195">The address uses the service name of the `stockdata` Service, which is running in the same Kubernetes namespace.</span></span>

<span data-ttu-id="2247b-196">**`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** 环境变量设置一个 <xref:System.AppContext> 开关，该开关可为启用未加密的 HTTP/2 连接 <xref:System.Net.Http.HttpClient> 。</span><span class="sxs-lookup"><span data-stu-id="2247b-196">The **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** environment variable sets an <xref:System.AppContext> switch that enables unencrypted HTTP/2 connections for <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="2247b-197">此环境变量的作用与在代码中设置开关相同，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2247b-197">This environment variable does the same thing as setting the switch in code, as shown here:</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="2247b-198">如果使用交换机的环境变量，则可以轻松地根据运行应用程序的上下文来更改上下文。</span><span class="sxs-lookup"><span data-stu-id="2247b-198">If you use an environment variable for the switch, you can easily change the context depending on the context in which the application is running.</span></span>

#### <a name="service-types"></a><span data-ttu-id="2247b-199">服务类型</span><span class="sxs-lookup"><span data-stu-id="2247b-199">Service types</span></span>

<span data-ttu-id="2247b-200">`type: NodePort`属性用于使 web 应用程序可以从群集外部访问。</span><span class="sxs-lookup"><span data-stu-id="2247b-200">The `type: NodePort` property is used to make the web application accessible from outside the cluster.</span></span> <span data-ttu-id="2247b-201">此属性类型会导致 Kubernetes 将服务上的端口80发布到群集外部网络套接字上的任意端口。</span><span class="sxs-lookup"><span data-stu-id="2247b-201">This property type causes Kubernetes to publish port 80 on the Service to an arbitrary port on the cluster's external network sockets.</span></span> <span data-ttu-id="2247b-202">您可以使用命令查找分配的端口 `kubectl get service` 。</span><span class="sxs-lookup"><span data-stu-id="2247b-202">You can find the assigned port by using the `kubectl get service` command.</span></span>

<span data-ttu-id="2247b-203">不 `stockdata` 能从群集外部访问该服务，因此它使用默认类型 `ClusterIP` 。</span><span class="sxs-lookup"><span data-stu-id="2247b-203">The `stockdata` Service shouldn't be accessible from outside the cluster, so it uses the default type, `ClusterIP`.</span></span>

<span data-ttu-id="2247b-204">生产系统最有可能使用集成的负载均衡器向外部使用者公开公共应用程序。</span><span class="sxs-lookup"><span data-stu-id="2247b-204">Production systems will most likely use an integrated load balancer to expose public applications to external consumers.</span></span> <span data-ttu-id="2247b-205">以这种方式公开的服务应使用 `LoadBalancer` 类型。</span><span class="sxs-lookup"><span data-stu-id="2247b-205">Services exposed in this way should use the `LoadBalancer` type.</span></span>

<span data-ttu-id="2247b-206">有关服务类型的详细信息，请参阅 [Kubernetes 发布服务](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) 文档。</span><span class="sxs-lookup"><span data-stu-id="2247b-206">For more information on Service types, see the [Kubernetes Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) documentation.</span></span>

#### <a name="deploy-the-stockweb-application"></a><span data-ttu-id="2247b-207">部署 StockWeb 应用程序</span><span class="sxs-lookup"><span data-stu-id="2247b-207">Deploy the StockWeb application</span></span>

<span data-ttu-id="2247b-208">使用 `kubectl` 应用 `stockweb.yml` 文件，并确认已创建部署和服务：</span><span class="sxs-lookup"><span data-stu-id="2247b-208">Use `kubectl` to apply the `stockweb.yml` file and confirm that the Deployment and Service were created:</span></span>

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

<span data-ttu-id="2247b-209">此命令的输出 `get service` 显示 HTTP 端口已发布到 `32564` 外部网络上的端口。</span><span class="sxs-lookup"><span data-stu-id="2247b-209">The output of the `get service` command shows that the HTTP port has been published to port `32564` on the external network.</span></span> <span data-ttu-id="2247b-210">对于 Docker Desktop，此 IP 地址将为 localhost。</span><span class="sxs-lookup"><span data-stu-id="2247b-210">For Docker Desktop, this IP address will be localhost.</span></span> <span data-ttu-id="2247b-211">可以通过浏览到来访问应用程序 `http://localhost:32564` 。</span><span class="sxs-lookup"><span data-stu-id="2247b-211">You can access the application by browsing to `http://localhost:32564`.</span></span>

### <a name="test-the-application"></a><span data-ttu-id="2247b-212">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="2247b-212">Test the application</span></span>

<span data-ttu-id="2247b-213">StockWeb 应用程序显示从简单的请求-答复服务中检索到的 NASDAQ 股票列表。</span><span class="sxs-lookup"><span data-stu-id="2247b-213">The StockWeb application displays a list of NASDAQ stocks that are retrieved from a simple request-reply service.</span></span> <span data-ttu-id="2247b-214">对于此演示，每行还显示返回它的服务实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2247b-214">For this demonstration, each line also shows the unique ID of the Service instance that returned it.</span></span>

![StockWeb 屏幕快照](media/kubernetes/stockweb-screenshot.png)

<span data-ttu-id="2247b-216">如果服务的副本数 `stockdata` 增加，则可能希望 **服务器** 值从行更改为行，但事实上，始终从同一实例返回所有100记录。</span><span class="sxs-lookup"><span data-stu-id="2247b-216">If the number of replicas of the `stockdata` Service were increased, you might expect the **Server** value to change from line to line, but in fact all 100 records are always returned from the same instance.</span></span> <span data-ttu-id="2247b-217">如果每隔几秒刷新一次页面，则服务器 ID 保持不变。</span><span class="sxs-lookup"><span data-stu-id="2247b-217">If you refresh the page every few seconds, the server ID remains the same.</span></span> <span data-ttu-id="2247b-218">为何发生这种情况？</span><span class="sxs-lookup"><span data-stu-id="2247b-218">Why does this happen?</span></span> <span data-ttu-id="2247b-219">此处提供两个因素。</span><span class="sxs-lookup"><span data-stu-id="2247b-219">There are two factors at play here.</span></span>

<span data-ttu-id="2247b-220">首先，Kubernetes 服务发现系统默认使用轮循机制负载平衡。</span><span class="sxs-lookup"><span data-stu-id="2247b-220">First, the Kubernetes Service discovery system uses round-robin load balancing by default.</span></span> <span data-ttu-id="2247b-221">第一次查询 DNS 服务器时，它将返回服务的第一个匹配的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2247b-221">The first time the DNS server is queried, it will return the first matching IP address for the Service.</span></span> <span data-ttu-id="2247b-222">下一次，它将返回列表中的下一个 IP 地址，依此类推，直到结束。</span><span class="sxs-lookup"><span data-stu-id="2247b-222">The next time, it will return the next IP address in the list, and so on, until the end.</span></span> <span data-ttu-id="2247b-223">此时，它会循环返回到开始。</span><span class="sxs-lookup"><span data-stu-id="2247b-223">At that point, it loops back to the start.</span></span>

<span data-ttu-id="2247b-224">其次， `HttpClient` 用于 StockWeb 应用程序的 gRPC 客户端的由 [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)创建和管理，该客户端的单个实例用于每次调用页面。</span><span class="sxs-lookup"><span data-stu-id="2247b-224">Second, the `HttpClient` used for the StockWeb application's gRPC client is created and managed by the [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), and a single instance of this client is used for every call to the page.</span></span> <span data-ttu-id="2247b-225">客户端只进行一次 DNS 查找，因此所有请求都将路由到相同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2247b-225">The client only does one DNS lookup, so all requests are routed to the same IP address.</span></span> <span data-ttu-id="2247b-226">由于 `HttpClientHandler` 出于性能方面的原因，已缓存的多个请求都将使用相同的 IP 地址，直到缓存的 DNS 条目过期，或由于某种原因释放了处理程序实例。</span><span class="sxs-lookup"><span data-stu-id="2247b-226">And because the `HttpClientHandler` is cached for performance reasons, multiple requests in quick succession will *all* use the same IP address, until the cached DNS entry expires or the handler instance is disposed for some reason.</span></span>

<span data-ttu-id="2247b-227">结果是，默认情况下，对 gRPC 服务的请求不会在群集中该服务的所有实例间平衡。</span><span class="sxs-lookup"><span data-stu-id="2247b-227">The result is that by default requests to a gRPC Service aren't balanced across all instances of that Service in the cluster.</span></span> <span data-ttu-id="2247b-228">不同的使用者将使用不同的实例，但这不能保证请求的良好分布或资源的平衡使用。</span><span class="sxs-lookup"><span data-stu-id="2247b-228">Different consumers will use different instances, but that doesn't guarantee a good distribution of requests or a balanced use of resources.</span></span>

<span data-ttu-id="2247b-229">下一章 [服务网格](service-mesh.md)将解决此问题。</span><span class="sxs-lookup"><span data-stu-id="2247b-229">The next chapter, [Service meshes](service-mesh.md), will address this problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2247b-230">[上一页](docker.md)
>[下一页](service-mesh.md)</span><span class="sxs-lookup"><span data-stu-id="2247b-230">[Previous](docker.md)
[Next](service-mesh.md)</span></span>
