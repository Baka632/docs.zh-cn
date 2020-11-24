---
title: 命名空间对包含元素和属性的新节点的实体引用扩展的影响
ms.date: 03/30/2017
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
ms.openlocfilehash: 8ef86f05d2b39639ad5faae792eb9b2854ff0673
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830163"
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a>命名空间对包含元素和属性的新节点的实体引用扩展的影响
由于实体声明的内容可以包含几乎所有内容，因此该内容有可能包含像 `<!ENTITY aname "<elem>test</elem>">` 这样的元素。  
  
 分析 XML 时，`&aname;` 在分析时不用其替换内容扩展。 不执行 XML 扩展的原因在于对元素的命名空间解析只有在将节点放入文档中时才发生。 在此之前，并不知道范围中存在哪个命名空间。 将节点放入文档中后，将进行命名空间解析，生成的实体内容将被分析为相应节点。  
  
> [!NOTE]
> 新创建的实体引用节点进行扩展后，该扩展永远不会再次进行。 因此，在元素的替换文本中使用的命名空间将在设置父节点时绑定。 然而，命名空间可能会对现有实体引用节点（将它们删除并插入其他位置时）或用 CloneNode  方法克隆的实体引用节点变化。  
  
## <a name="see-also"></a>请参阅

- [XML 文档对象模型 (DOM)](xml-document-object-model-dom.md)
