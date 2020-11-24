---
title: 复制现有节点
ms.date: 03/30/2017
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: b4ae24f9776456033a876e8ae4d1515d2f669fe0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830943"
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="000e2-102">复制现有节点</span><span class="sxs-lookup"><span data-stu-id="000e2-102">Copy Existing Nodes</span></span>
<span data-ttu-id="000e2-103">XML 文档对象模型 (DOM) 包含许多可用于选择节点的方法和属性，如 SelectSingleNode  、ChildNodes[int i]  、Attributes[int i]  。</span><span class="sxs-lookup"><span data-stu-id="000e2-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="000e2-104">选择节点后，可以使用适用于特定节点类型的插入方法之一将该节点插入到树中。</span><span class="sxs-lookup"><span data-stu-id="000e2-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="000e2-105">将节点插入到树中的唯一限制是在插入节点后文档的格式仍必须是正确的。</span><span class="sxs-lookup"><span data-stu-id="000e2-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="000e2-106">将现有节点插入到 DOM 树中时，该节点从其原始位置移除并添加到它的目标位置。</span><span class="sxs-lookup"><span data-stu-id="000e2-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="000e2-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="000e2-107">See also</span></span>

- [<span data-ttu-id="000e2-108">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="000e2-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
