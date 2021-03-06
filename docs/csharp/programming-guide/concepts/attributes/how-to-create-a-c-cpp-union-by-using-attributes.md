---
title: 'Porady: tworzenie Unii C-C++ za pomocą atrybutów (C#)'
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: 8b5a88656b1172407c3e5b9f5198d5acae7bf9e0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2018
ms.locfileid: "43798512"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a>Porady: tworzenie złożenia C/C++ za pomocą atrybutów (C#)
Za pomocą atrybutów można dostosować, jak struktury są ułożone w pamięci. Na przykład można utworzyć, co jest nazywane Unia w języku C/C++ za pomocą `StructLayout(LayoutKind.Explicit)` i `FieldOffset` atrybutów.  
  
## <a name="example"></a>Przykład  
 W tym segmencie kodu, wszystkie pola z `TestUnion` rozpoczynają się od tej samej lokalizacji w pamięci.  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestUnion  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public byte b;  
       }  
```  
  
## <a name="example"></a>Przykład  
 Oto inny przykład gdzie pola zaczynają się w różnych jawnie ustawić lokalizacje.  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestExplicit  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public long lg;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i1;  
  
           [System.Runtime.InteropServices.FieldOffset(4)]  
           public int i2;  
  
           [System.Runtime.InteropServices.FieldOffset(8)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(12)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(14)]  
           public byte b;  
       }  
```  
  
 Pola dwóch liczb całkowitych, `i1` i `i2`, Udostępnij te same lokalizacje pamięci jako `lg`. Tego rodzaju kontrolę nad układzie struktury jest przydatne, gdy za pomocą wywołania platformy.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Reflection>  
- <xref:System.Attribute>  
- [Przewodnik programowania w języku C#](../../../../csharp/programming-guide/index.md)  
- [Atrybuty](../../../../../docs/standard/attributes/index.md)  
- [Odbicie (C#)](../../../../csharp/programming-guide/concepts/reflection.md)  
- [Atrybuty (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md)  
- [Tworzenie atrybutów niestandardowych (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
- [Uzyskiwanie dostępu do atrybutów przy użyciu odbicia (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
