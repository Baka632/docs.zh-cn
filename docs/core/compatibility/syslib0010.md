---
title: SYSLIB0010 警告
description: 了解有关生成编译时警告 SYSLIB0010 的过时信息。
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 824423d58802d4a286bfed98422341097985990f
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440603"
---
# <a name="syslib0010-unsupported-remoting-apis"></a>SYSLIB0010：不支持的远程处理 API

[.NET 远程处理](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))是一项传统技术，基础结构仅存在于 .NET Framework 中。 从 .NET 5.0 开始，以下与远程处理相关的 API 标记为已过时。 在代码中使用这些 API 会在编译时生成警告 `SYSLIB0010`。

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workarounds"></a>工作区

请考虑使用 WCF 或基于 HTTP 的 REST 服务与其他应用程序的对象或跨计算机进行通信。 有关详细信息，请参阅 [.NET Framework 技术在 .NET Core 上不可用](../porting/net-framework-tech-unavailable.md)。

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>另请参阅

- [.NET 远程处理](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))
