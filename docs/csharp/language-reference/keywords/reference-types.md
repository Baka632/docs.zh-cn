---
description: 引用类型 - C# 参考
title: 引用类型 - C# 参考
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 075ec5ecd8f71f5cb85bab0e2baff56409709191
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899608"
---
# <a name="reference-types-c-reference"></a>引用类型（C# 参考）

C# 中有两种类型：引用类型和值类型。 引用类型的变量存储对其数据（对象）的引用，而值类型的变量直接包含其数据。 对于引用类型，两种变量可引用同一对象；因此，对一个变量执行的操作会影响另一个变量所引用的对象。 对于值类型，每个变量都具有其自己的数据副本，对一个变量执行的操作不会影响另一个变量（in、ref 和 out 参数变量除外；请参阅 [in](in-parameter-modifier.md)、[ref](ref.md) 和 [out](out-parameter-modifier.md) 参数修饰符）。

 下列关键字用于声明引用类型：

- [class](class.md)

- [interface](interface.md)

- [delegate](../builtin-types/reference-types.md)
- [record](../builtin-types/reference-types.md)

 C# 也提供了下列内置引用类型：

- [dynamic](../builtin-types/reference-types.md)

- [object](../builtin-types/reference-types.md)

- [string](../builtin-types/reference-types.md)

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 关键字](index.md)
- [指针类型](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [值类型](../builtin-types/value-types.md)
