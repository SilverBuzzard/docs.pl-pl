---
title: "Wytyczne dotyczące projektowania typu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b24a934285f88386daa764c5b28bd82cf5d39a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="type-design-guidelines"></a><span data-ttu-id="181ee-102">Wytyczne dotyczące projektowania typu</span><span class="sxs-lookup"><span data-stu-id="181ee-102">Type Design Guidelines</span></span>
<span data-ttu-id="181ee-103">Z punktu widzenia środowiska CLR, dostępne są tylko dwie kategorie typów — odwołanie typy i wartość — ale dyskusji dotyczących framework projektu na potrzeby możemy podział typy bardziej logiczne, grup, każda z własne zasady określonego projektu.</span><span class="sxs-lookup"><span data-stu-id="181ee-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="181ee-104">Klasy są generalnie w przypadku typów referencyjnych.</span><span class="sxs-lookup"><span data-stu-id="181ee-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="181ee-105">Tworzą one zbiorczego rodzaje w większości platform.</span><span class="sxs-lookup"><span data-stu-id="181ee-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="181ee-106">Klasy należnych firmie ich popularne zaawansowanej zestaw zorientowane obiektowo funkcje, których obsługują oraz ogólne możliwości ich zastosowania.</span><span class="sxs-lookup"><span data-stu-id="181ee-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="181ee-107">Klasy podstawowe i klasy abstrakcyjne są specjalne logiczne grupy związane z rozszerzeń.</span><span class="sxs-lookup"><span data-stu-id="181ee-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="181ee-108">Interfejsy są typy, które może być zaimplementowany przez typy wartości i typy referencyjne.</span><span class="sxs-lookup"><span data-stu-id="181ee-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="181ee-109">W związku z tym można służą jako katalogów głównych polimorficznych hierarchii typów referencyjnych i typów wartości.</span><span class="sxs-lookup"><span data-stu-id="181ee-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="181ee-110">Ponadto interfejsy może służyć do symulowania dziedziczenie wielokrotne, który nie jest obsługiwany natywnie przez środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="181ee-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="181ee-111">Struktury są generalnie w przypadku typów wartości i powinna być zarezerwowana dla małych, prostych typów, podobnie jak w nim elementów podstawowych języka.</span><span class="sxs-lookup"><span data-stu-id="181ee-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="181ee-112">Typy wyliczeniowe są szczególnych przypadkach typów wartości używane do definiowania krótkie zestawy wartości, takich jak dni tygodnia, kolory konsoli i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="181ee-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="181ee-113">Klasy statyczne są przeznaczone do kontenerów dla statycznych elementów członkowskich typów.</span><span class="sxs-lookup"><span data-stu-id="181ee-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="181ee-114">Często są używane do zapewnienia skróty do innych operacji.</span><span class="sxs-lookup"><span data-stu-id="181ee-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="181ee-115">Delegatów, wyjątki atrybuty, tablic i kolekcje są wszystkie szczególnych przypadkach typy referencyjne przeznaczonych do określonych celów i wskazówki dotyczące ich projektowania i użycia w innym miejscu, omówiono w książce.</span><span class="sxs-lookup"><span data-stu-id="181ee-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="181ee-116">**CZY ✓** upewnij się, że każdy typ jest dobrze zdefiniowany zestaw elementów członkowskich powiązane, nie tylko losowe kolekcji funkcji niepowiązanych.</span><span class="sxs-lookup"><span data-stu-id="181ee-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="181ee-117">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="181ee-117">In This Section</span></span>  
 [<span data-ttu-id="181ee-118">Wybór między klasy i struktury</span><span class="sxs-lookup"><span data-stu-id="181ee-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="181ee-119">Projekt klasy abstrakcyjnej</span><span class="sxs-lookup"><span data-stu-id="181ee-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="181ee-120">Projekt klasy statyczne</span><span class="sxs-lookup"><span data-stu-id="181ee-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="181ee-121">Projekt interfejsu</span><span class="sxs-lookup"><span data-stu-id="181ee-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="181ee-122">Projektowanie struktury</span><span class="sxs-lookup"><span data-stu-id="181ee-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="181ee-123">Projekt wyliczenia</span><span class="sxs-lookup"><span data-stu-id="181ee-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="181ee-124">Zagnieżdżone typy</span><span class="sxs-lookup"><span data-stu-id="181ee-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="181ee-125">*Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*</span><span class="sxs-lookup"><span data-stu-id="181ee-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="181ee-126">*Drukowane uprawnieniami wariancji x edukacji, Inc. z [Framework zaleceń dotyczących projektowania: konwencje, Idioms i wzorce dla bibliotek .NET wielokrotnego użytku, wydanie 2](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina i Abrams Brada opublikowane 22 Oct 2008 przez Professional Addison-Wesley jako część serii rozwoju systemu Windows firmy Microsoft.*</span><span class="sxs-lookup"><span data-stu-id="181ee-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="181ee-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="181ee-127">See Also</span></span>  
 [<span data-ttu-id="181ee-128">Wytyczne dotyczące projektowania Framework</span><span class="sxs-lookup"><span data-stu-id="181ee-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)