---
title: "Ograniczanie dostępności metody dostępu (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accesibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4905885323f59d8b8b2654a5331e02054334398
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a><span data-ttu-id="84518-102">Ograniczanie dostępności metody dostępu (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="84518-102">Restricting Accessor Accessibility (C# Programming Guide)</span></span>
<span data-ttu-id="84518-103">[Uzyskać](../../../csharp/language-reference/keywords/get.md) i [ustawić](../../../csharp/language-reference/keywords/set.md) fragmenty właściwość lub indeksator są nazywane *metody dostępu*.</span><span class="sxs-lookup"><span data-stu-id="84518-103">The [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) portions of a property or indexer are called *accessors*.</span></span> <span data-ttu-id="84518-104">Domyślnie te metody dostępu mają taką samą widoczność lub poziom dostępu: te właściwości lub indeksatora, do którego należą.</span><span class="sxs-lookup"><span data-stu-id="84518-104">By default these accessors have the same visibility, or access level: that of the property or indexer to which they belong.</span></span> <span data-ttu-id="84518-105">Aby uzyskać więcej informacji, zobacz [poziomów ułatwień dostępu](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="84518-105">For more information, see [accessibility levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> <span data-ttu-id="84518-106">Jednak czasami jest przydatne w celu ograniczenia dostępu do jednej z tych metod dostępu.</span><span class="sxs-lookup"><span data-stu-id="84518-106">However, it is sometimes useful to restrict access to one of these accessors.</span></span> <span data-ttu-id="84518-107">Zazwyczaj polega to na ograniczanie dostępności `set` akcesor przy zachowaniu `get` akcesor publicznie.</span><span class="sxs-lookup"><span data-stu-id="84518-107">Typically, this involves restricting the accessibility of the `set` accessor, while keeping the `get` accessor publicly accessible.</span></span> <span data-ttu-id="84518-108">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="84518-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_1.cs)]  
  
 <span data-ttu-id="84518-109">W tym przykładzie właściwość o nazwie `Name` definiuje `get` i `set` metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="84518-109">In this example, a property called `Name` defines a `get` and `set` accessor.</span></span> <span data-ttu-id="84518-110">`get` Akcesor odbiera poziom dostępności właściwość, `public` w takim przypadku podczas `set` akcesor jawnie jest ograniczony przez zastosowanie [chronione](../../../csharp/language-reference/keywords/protected.md) modyfikator dostępu do Metoda dostępu samej siebie.</span><span class="sxs-lookup"><span data-stu-id="84518-110">The `get` accessor receives the accessibility level of the property itself, `public` in this case, while the `set` accessor is explicitly restricted by applying the [protected](../../../csharp/language-reference/keywords/protected.md) access modifier to the accessor itself.</span></span>  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a><span data-ttu-id="84518-111">Ograniczenia dotyczące modyfikatorów dostępu</span><span class="sxs-lookup"><span data-stu-id="84518-111">Restrictions on Access Modifiers on Accessors</span></span>  
 <span data-ttu-id="84518-112">Za pomocą modyfikatorów dostępu na właściwości i indeksatorów podlega następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="84518-112">Using the accessor modifiers on properties or indexers is subject to these conditions:</span></span>  
  
-   <span data-ttu-id="84518-113">Nie można używać modyfikatorów dostępu na interfejs lub jawnego [interfejsu](../../../csharp/language-reference/keywords/interface.md) implementacja elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="84518-113">You cannot use accessor modifiers on an interface or an explicit [interface](../../../csharp/language-reference/keywords/interface.md) member implementation.</span></span>  
  
-   <span data-ttu-id="84518-114">Modyfikatory dostępu można użyć tylko wtedy, gdy właściwość lub indeksator ma zarówno atrybut `set` i `get` metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="84518-114">You can use accessor modifiers only if the property or indexer has both `set` and `get` accessors.</span></span> <span data-ttu-id="84518-115">W takim przypadku modyfikator jest dozwolony na tylko jedna z dwóch metod dostępu.</span><span class="sxs-lookup"><span data-stu-id="84518-115">In this case, the modifier is permitted on one only of the two accessors.</span></span>  
  
-   <span data-ttu-id="84518-116">Jeśli właściwość lub indeksator ma [zastąpienia](../../../csharp/language-reference/keywords/override.md) modyfikator, modyfikator dostępu muszą być zgodne akcesor przesłoniętej metody dostępu, jeśli istnieje.</span><span class="sxs-lookup"><span data-stu-id="84518-116">If the property or indexer has an [override](../../../csharp/language-reference/keywords/override.md) modifier, the accessor modifier must match the accessor of the overridden accessor, if any.</span></span>  
  
-   <span data-ttu-id="84518-117">Poziom dostępności w metodzie dostępu musi być bardziej restrykcyjny niż poziom dostępności na właściwość lub indeksator samej siebie.</span><span class="sxs-lookup"><span data-stu-id="84518-117">The accessibility level on the accessor must be more restrictive than the accessibility level on the property or indexer itself.</span></span>  
  
## <a name="access-modifiers-on-overriding-accessors"></a><span data-ttu-id="84518-118">Modyfikatory dostępu na zastępowanie metody dostępu</span><span class="sxs-lookup"><span data-stu-id="84518-118">Access Modifiers on Overriding Accessors</span></span>  
 <span data-ttu-id="84518-119">Aby zastąpić właściwość lub indeksator, przesłoniętej metody dostępu muszą być dostępne dla zastępowanie kodu.</span><span class="sxs-lookup"><span data-stu-id="84518-119">When you override a property or indexer, the overridden accessors must be accessible to the overriding code.</span></span> <span data-ttu-id="84518-120">Ponadto poziom dostępności zarówno właściwości/indeksatora i który metody dostępu muszą być zgodne odpowiednie właściwości/indeksatora przesłoniętych i metody dostępu.</span><span class="sxs-lookup"><span data-stu-id="84518-120">Also, the accessibility level of both the property/indexer, and that of the accessors must match the corresponding overridden property/indexer and the accessors.</span></span> <span data-ttu-id="84518-121">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="84518-121">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_2.cs)]  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="84518-122">Implementowanie interfejsów</span><span class="sxs-lookup"><span data-stu-id="84518-122">Implementing Interfaces</span></span>  
 <span data-ttu-id="84518-123">Gdy używasz metody dostępu do zaimplementowania interfejsu metodzie dostępu nie mogą mieć modyfikatora dostępu.</span><span class="sxs-lookup"><span data-stu-id="84518-123">When you use an accessor to implement an interface, the accessor may not have an access modifier.</span></span> <span data-ttu-id="84518-124">Jednak jeśli implementuje interfejs za pomocą jedną metodę dostępu, takich jak `get`, inne metody dostępu może mieć modyfikatora dostępu, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="84518-124">However, if you implement the interface using one accessor, such as `get`, the other accessor can have an access modifier, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_3.cs)]  
  
## <a name="accessor-accessibility-domain"></a><span data-ttu-id="84518-125">Domena dostępności metody dostępu</span><span class="sxs-lookup"><span data-stu-id="84518-125">Accessor Accessibility Domain</span></span>  
 <span data-ttu-id="84518-126">Jeśli używasz modyfikatora dostępu w metodzie dostępu, [domena dostępności](../../../csharp/language-reference/keywords/accessibility-domain.md) metody dostępu jest określany przez modyfikator.</span><span class="sxs-lookup"><span data-stu-id="84518-126">If you use an access modifier on the accessor, the [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md) of the accessor is determined by this modifier.</span></span>  
  
 <span data-ttu-id="84518-127">Jeśli nie używasz modyfikatora dostępu w metodzie dostępu, domena dostępności metody dostępu jest określany przez właściwość lub indeksator poziom dostępności.</span><span class="sxs-lookup"><span data-stu-id="84518-127">If you did not use an access modifier on the accessor, the accessibility domain of the accessor is determined by the accessibility level of the property or indexer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84518-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="84518-128">Example</span></span>  
 <span data-ttu-id="84518-129">Poniższy przykład zawiera trzy klasy `BaseClass`, `DerivedClass`, i `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="84518-129">The following example contains three classes, `BaseClass`, `DerivedClass`, and `MainClass`.</span></span> <span data-ttu-id="84518-130">Istnieją dwie właściwości na `BaseClass`, `Name` i `Id` w obu klasach.</span><span class="sxs-lookup"><span data-stu-id="84518-130">There are two properties on the `BaseClass`, `Name` and `Id` on both classes.</span></span> <span data-ttu-id="84518-131">W przykładzie pokazano, jak właściwość `Id` na `DerivedClass` może być ukryty przez właściwość `Id` na `BaseClass` korzystając modyfikator dostępu ograniczające takich jak [chronione](../../../csharp/language-reference/keywords/protected.md) lub [ prywatne](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="84518-131">The example demonstrates how the property `Id` on `DerivedClass` can be hidden by the property `Id` on `BaseClass` when you use a restrictive access modifier such as [protected](../../../csharp/language-reference/keywords/protected.md) or [private](../../../csharp/language-reference/keywords/private.md).</span></span> <span data-ttu-id="84518-132">W związku z tym podczas można przypisać wartości do tej właściwości, właściwość `BaseClass` klasy jest wywoływana zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="84518-132">Therefore, when you assign values to this property, the property on the `BaseClass` class is called instead.</span></span> <span data-ttu-id="84518-133">Modyfikator dostępu przez zastąpienie [publicznego](../../../csharp/language-reference/keywords/public.md) będzie Udostępnij właściwość.</span><span class="sxs-lookup"><span data-stu-id="84518-133">Replacing the access modifier by [public](../../../csharp/language-reference/keywords/public.md) will make the property accessible.</span></span>  
  
 <span data-ttu-id="84518-134">W przykładzie pokazano także który modyfikator dostępu ograniczające, takich jak `private` lub `protected`na `set` akcesor `Name` właściwości w `DerivedClass` uniemożliwia dostęp do metody dostępu i generuje błąd podczas przypisywania do go.</span><span class="sxs-lookup"><span data-stu-id="84518-134">The example also demonstrates that a restrictive access modifier, such as `private` or `protected`, on the `set` accessor of the `Name` property in `DerivedClass` prevents access to the accessor and generates an error when you assign to it.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_4.cs)]  
  
## <a name="comments"></a><span data-ttu-id="84518-135">Komentarze</span><span class="sxs-lookup"><span data-stu-id="84518-135">Comments</span></span>  
 <span data-ttu-id="84518-136">Zwróć uwagę, że jeśli zamienisz deklaracji `new private string Id` przez `new public string Id`, uzyskać dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="84518-136">Notice that if you replace the declaration `new private string Id` by `new public string Id`, you get the output:</span></span>  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a><span data-ttu-id="84518-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="84518-137">See Also</span></span>  
 [<span data-ttu-id="84518-138">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="84518-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="84518-139">Właściwości</span><span class="sxs-lookup"><span data-stu-id="84518-139">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="84518-140">Indeksatory</span><span class="sxs-lookup"><span data-stu-id="84518-140">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="84518-141">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="84518-141">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)