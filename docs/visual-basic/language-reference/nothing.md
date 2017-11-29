---
title: Nothing (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6932fee01ec6f39f67fb1a26a9a5b5cbd47d9767
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="nothing-visual-basic"></a><span data-ttu-id="04531-102">Nothing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04531-102">Nothing (Visual Basic)</span></span>
<span data-ttu-id="04531-103">Reprezentuje wartość domyślną każdego typu danych.</span><span class="sxs-lookup"><span data-stu-id="04531-103">Represents the default value of any data type.</span></span> <span data-ttu-id="04531-104">Typy odwołań, wartością domyślną jest `null` odwołania.</span><span class="sxs-lookup"><span data-stu-id="04531-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="04531-105">Dla typów wartości wartość domyślna zależy od tego, czy typ wartości jest null.</span><span class="sxs-lookup"><span data-stu-id="04531-105">For value types, the default value depends on whether the value type is nullable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04531-106">Dla typów wartości nie przyjmujące wartości `Nothing` w języku Visual Basic różni się od `null` w języku C#.</span><span class="sxs-lookup"><span data-stu-id="04531-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="04531-107">W języku Visual Basic, jeśli wartość zmiennej typu niedopuszczający wartości null do `Nothing`, zmienna jest ustawiona na wartość domyślną dla deklarowanym typem.</span><span class="sxs-lookup"><span data-stu-id="04531-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="04531-108">W języku C#, jeśli przypisano zmienną typu niedopuszczające wartości do `null`, występuje błąd kompilacji.</span><span class="sxs-lookup"><span data-stu-id="04531-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04531-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="04531-109">Remarks</span></span>  
 <span data-ttu-id="04531-110">`Nothing`reprezentuje wartość domyślna typu danych.</span><span class="sxs-lookup"><span data-stu-id="04531-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="04531-111">Wartość domyślna zależy od tego, czy zmienna jest typem wartości lub typu referencyjnego.</span><span class="sxs-lookup"><span data-stu-id="04531-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>  
  
 <span data-ttu-id="04531-112">Zmienna *typu wartości* bezpośrednio zawiera wartość.</span><span class="sxs-lookup"><span data-stu-id="04531-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="04531-113">Typy wartości obejmują wszystkie typy danych numerycznych, `Boolean`, `Char`, `Date`, wszystkie struktury i wszystkie wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="04531-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="04531-114">Zmienna *zawierają odwołania do typu* zawiera odwołanie do wystąpienia obiektu w pamięci.</span><span class="sxs-lookup"><span data-stu-id="04531-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="04531-115">Typy odwołań obejmują klas, tablic obiektów delegowanych i ciągów.</span><span class="sxs-lookup"><span data-stu-id="04531-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="04531-116">Aby uzyskać więcej informacji, zobacz [typów wartości i typy referencyjne](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="04531-116">For more information, see [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
 <span data-ttu-id="04531-117">Jeśli zmienna jest wartością typu, zachowanie `Nothing` zależy od tego, czy zmienna jest typem danych wartości null.</span><span class="sxs-lookup"><span data-stu-id="04531-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="04531-118">Do reprezentowania typu wartości null, należy dodać `?` modyfikator nazwy typu.</span><span class="sxs-lookup"><span data-stu-id="04531-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="04531-119">Przypisywanie `Nothing` do wartości null zmiennej ustawia wartość `null`.</span><span class="sxs-lookup"><span data-stu-id="04531-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="04531-120">Aby uzyskać dodatkowe informacje i przykłady, zobacz [typy dopuszczające wartości zerowe wartości](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="04531-120">For more information and examples, see [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>  
  
 <span data-ttu-id="04531-121">Jeśli zmienna jest typ wartości, który nie dopuszcza, przypisywanie `Nothing` do ustawia ją na wartość domyślną dla deklarowanym typem.</span><span class="sxs-lookup"><span data-stu-id="04531-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="04531-122">Ten typ zawiera elementy członkowskie zmiennej, są ustawione wartości domyślne.</span><span class="sxs-lookup"><span data-stu-id="04531-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="04531-123">Poniższy przykład przedstawia to dla typów skalarnych.</span><span class="sxs-lookup"><span data-stu-id="04531-123">The following example illustrates this for scalar types.</span></span>  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 <span data-ttu-id="04531-124">Jeśli zmienna jest typu referencyjnego, przypisywanie `Nothing` do zmiennej ustawia ją na `null` odwołanie typu zmienną.</span><span class="sxs-lookup"><span data-stu-id="04531-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="04531-125">Zmienna, która ma ustawioną wartość `null` odwołania nie jest skojarzony z żadnym obiektem.</span><span class="sxs-lookup"><span data-stu-id="04531-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="04531-126">W poniższym przykładzie pokazano to.</span><span class="sxs-lookup"><span data-stu-id="04531-126">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 <span data-ttu-id="04531-127">Podczas sprawdzania, czy odwołanie (lub wartość null, wpisz) zmienna jest `null`, nie używaj `= Nothing` lub `<> Nothing`.</span><span class="sxs-lookup"><span data-stu-id="04531-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="04531-128">Zawsze używaj `Is Nothing` lub `IsNot Nothing`.</span><span class="sxs-lookup"><span data-stu-id="04531-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>  
  
 <span data-ttu-id="04531-129">Ciągi w Visual Basic, pusty ciąg równa `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="04531-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="04531-130">W związku z tym `"" = Nothing` ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="04531-130">Therefore, `"" = Nothing` is true.</span></span>  
  
 <span data-ttu-id="04531-131">W poniższym przykładzie przedstawiono porównanie, które używają `Is` i `IsNot` operatorów.</span><span class="sxs-lookup"><span data-stu-id="04531-131">The following example shows comparisons that use the `Is` and `IsNot` operators.</span></span>  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 <span data-ttu-id="04531-132">Jeśli zmienna jest zadeklarowana bez użycia `As` klauzuli i ustaw ją na `Nothing`, zmienna ma typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="04531-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="04531-133">Na przykład jest `Dim something = Nothing`.</span><span class="sxs-lookup"><span data-stu-id="04531-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="04531-134">Błąd kompilacji w takim przypadku występuje podczas `Option Strict` znajduje się na i `Option Infer` jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="04531-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>  
  
 <span data-ttu-id="04531-135">Po przypisaniu `Nothing` zmiennej obiektu nie odwołuje się do dowolnego wystąpienia obiektu.</span><span class="sxs-lookup"><span data-stu-id="04531-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="04531-136">Jeśli zmienna była wcześniej określone wystąpienie, ustawieniem dla niego `Nothing` nie kończy się wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="04531-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="04531-137">Wystąpienie zostanie zakończony i skojarzone z nim zasoby pamięci są wydawane tylko wtedy, gdy moduł garbage collector (GC) wykrywa, że nie ma żadnych aktywnych odwołań pozostałych.</span><span class="sxs-lookup"><span data-stu-id="04531-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>  
  
 <span data-ttu-id="04531-138">`Nothing`różni się od <xref:System.DBNull> obiektu, który reprezentuje niezainicjowanej wariantu lub kolumną nieistniejącą bazy danych.</span><span class="sxs-lookup"><span data-stu-id="04531-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04531-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="04531-139">See Also</span></span>  
 [<span data-ttu-id="04531-140">Dim — instrukcja</span><span class="sxs-lookup"><span data-stu-id="04531-140">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="04531-141">Okres istnienia obiektów: Sposób obiekty są tworzone i niszczone</span><span class="sxs-lookup"><span data-stu-id="04531-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [<span data-ttu-id="04531-142">Okres istnienia w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04531-142">Lifetime in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="04531-143">Is — Operator</span><span class="sxs-lookup"><span data-stu-id="04531-143">Is Operator</span></span>](../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="04531-144">IsNot — Operator</span><span class="sxs-lookup"><span data-stu-id="04531-144">IsNot Operator</span></span>](../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="04531-145">Typy dopuszczające wartości zerowe wartości</span><span class="sxs-lookup"><span data-stu-id="04531-145">Nullable Value Types</span></span>](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)