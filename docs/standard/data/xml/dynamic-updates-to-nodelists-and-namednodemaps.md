---
title: NodeList 和 NamedNodeMap 的动态更新
ms.date: 03/30/2017
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
ms.openlocfilehash: 2e23507000a780246c129d470b525f19b8b3b9c9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827654"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>NodeList 和 NamedNodeMap 的动态更新
由于 XmlNodeList  和 XmlNamedNodeMap  包含节点集，而 XML 文档加载到内存中并被修改，因此万维网联合会 (W3C) 规定这些包含节点集的对象必须是动态对象。 也就是说，如果基础文档更改，则这两个对象中的数据也应更改。 因此，如果 XmlNodeList  包含特定元素（例如，元素 X）的所有子元素，请在文档中的元素 X 下添加另一个元素 Q。XmlNodeList  也应将新元素 Q 添加到集合中。 反过来也一样。 如果将节点添加到 XmlNodeList  ，那么基础文档也会更新。  
  
## <a name="see-also"></a>请参阅

- [XML 文档对象模型 (DOM)](xml-document-object-model-dom.md)
