---
title: x:Property — dyrektywa
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: 34f982c30a345f95c7a1c7e70de8c5cc4de62cbb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508189"
---
# <a name="xproperty-directive"></a>x:Property — dyrektywa
Deklaruje właściwości w znaczniku XAML.  
  
## <a name="xaml-object-element-usage"></a>Użycie elementu obiektu języka XAML  
  
```  
<object x:Class="className">  
  <x:Members>  
    <x:Property Name="propertyName" Type="propertyType/>  
    additionalProperties  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a>Wartości XAML  
  
|||  
|-|-|  
|`className`|Nazwa klasy zapasowy lub częściowe klasy dla trybu produkcyjnego XAML.|  
|`propertyName`|Nazwa elementu członkowskiego jest zdefiniowana właściwość.|  
|`propertyType`|Wpisz nazwę (lub inną formę ciągu właściwa dla struktury), który określa typ tej właściwości.|  
  
## <a name="remarks"></a>Uwagi  
 W implementacji usług programu .NET Framework XAML. `x:Property` nie ma bezpośredniego typu kopii, ale jest obsługiwany przez <xref:System.Windows.Markup.PropertyDefinition> klasy. W postaci strumienia węzłów XAML `x:Property` element jest reprezentowany jako składową o nazwie `Property`, z przestrzeni nazw XAML dla języka XAML. Element członkowski `Property` przechowywania atrybutów podaną przez znaczników.  
  
 Znaczenie `Name` i `Type` nie są przypisane na poziomie usług programu .NET Framework XAML. Są one przechowywane w początkowej strumień węzłów XAML jako wartości parametrów, należy interpretować później zgodnie z zasadami, które mogą zostać nałożone przez określonych platform. Znaczenie może być wyrównane do nazwy XAML i typu XAML, co oznacza, lub może być tylko prawidłowe w systemie typów zapasowy, w zależności od implementacji.  
  
 Do obsługi praktyczne wykorzystanie `x:Members` jako środek do określania definicje elementów członkowskich w znaczniku, elementy członkowskie muszą być skojarzone z klasy, który może być modyfikowany. Zamierzony modelu jest fakt, że `x:Members` istnieje jako element członkowski typu, który określa `x:Class`. Mechanizm kojarzenia typów i elementów członkowskich lub do tworzenia definicji dynamicznego elementu członkowskiego nie jest obsługiwane na poziomie usług programu .NET Framework XAML. To pole pozostanie do poszczególnych struktur, które mają modeli aplikacji, które obsługują definicje elementów członkowskich z XAML. Zwykle akcji kompilacji MSBUILD, które znaczników kompilacji XAML, a następnie zintegrować go z kodem lub zestawy czyste z XAML produktu są wymagane do obsługi tej funkcji.  
  
## <a name="xproperty-for-windows-workflow-foundation"></a>x: Property dla programu Windows Workflow Foundation  
 Dla programu Windows Workflow Foundation `x:Property` definiuje elementy niestandardowe działanie składające się wyłącznie w XAML lub XAML — definicja dynamiczne elementy członkowskie w Projektancie działanie z kodem. `x:Class` musi być także określona w elemencie głównym produkcji XAML. To nie jest wymagane na poziomie usług programu .NET Framework XAML, ale staje się to wymagane, gdy produkcji XAML jest ładowany przez akcje kompilacji MSBUILD, które obsługują niestandardowych działań i Windows Workflow Foundation XAML ogólnie rzecz biorąc. Windows Workflow Foundation nie używa czystego Nazwa typu XAML jako jego wartość przeznaczone dla `x:Property` `Type` atrybutu i zamiast tego używa konwencji, który nie jest udokumentowany w tym miejscu. Aby uzyskać więcej informacji, zobacz [dynamicznego tworzenia działania](https://msdn.microsoft.com/library/dd807392.aspx).
