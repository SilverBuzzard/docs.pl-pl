---
title: '#region — C# odwołania'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: c306511ad8133d0063ccf8b70f2d34d25d2ad3fa
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244287"
---
# <a name="region-c-reference"></a>#region (odwołanie w C#)
Dyrektywa `#region` pozwala określić blok kodu, który można rozwinąć lub zwinąć przy użyciu funkcji [tworzenia konspektu](/visualstudio/ide/outlining) w edytorze kodu programu Visual Studio. W dłuższych plikach z kodem wygodniejsze jest zwinięcie lub ukrycie jednego lub kilku regionów, aby móc skupić się na tej części pliku, nad którą się obecnie pracuje. Poniższy przykład przedstawia sposób definiowania regionu:  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a>Uwagi  
 Blok `#region` musi kończyć się dyrektywą [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).  
  
 Blok `#region` nie może nakładać się na blok [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md). Blok `#region` może natomiast być zagnieżdżony w bloku `#if`, a blok `#if` może być zagnieżdżony w bloku `#region`.  
  
## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../../../csharp/language-reference/index.md)  
- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
- [Dyrektywy preprocesora C#](../../../csharp/language-reference/preprocessor-directives/index.md)
