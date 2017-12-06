---
title: Partial (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5129ef7737b1b07317d47f8d18e9aceb668bf05a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="partial-visual-basic"></a><span data-ttu-id="34e83-102">Partial (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34e83-102">Partial (Visual Basic)</span></span>
<span data-ttu-id="34e83-103">Wskazuje, że Deklaracja typu jest częściową definicją typu.</span><span class="sxs-lookup"><span data-stu-id="34e83-103">Indicates that a type declaration is a partial definition of the type.</span></span>  
  
 <span data-ttu-id="34e83-104">Definicja typu między kilka deklaracji można podzielić przy użyciu `Partial` — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="34e83-104">You can divide the definition of a type among several declarations by using the `Partial` keyword.</span></span> <span data-ttu-id="34e83-105">Możesz użyć tyle częściowe deklaracje można dowolnie, dowolną liczbę plików innego źródła można dowolnie.</span><span class="sxs-lookup"><span data-stu-id="34e83-105">You can use as many partial declarations as you want, in as many different source files as you want.</span></span> <span data-ttu-id="34e83-106">Jednak wszystkie deklaracje muszą być w tym samym zestawie i tego samego obszaru nazw.</span><span class="sxs-lookup"><span data-stu-id="34e83-106">However, all the declarations must be in the same assembly and the same namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34e83-107">Obsługa języka Visual Basic *metody częściowe*, które są zazwyczaj stosowane w klas częściowych.</span><span class="sxs-lookup"><span data-stu-id="34e83-107">Visual Basic supports *partial methods*, which are typically implemented in partial classes.</span></span> <span data-ttu-id="34e83-108">Aby uzyskać więcej informacji, zobacz [metody częściowe](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) i [Sub — instrukcja](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-108">For more information, see [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e83-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="34e83-109">Syntax</span></span>  
  
```  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a><span data-ttu-id="34e83-110">Części</span><span class="sxs-lookup"><span data-stu-id="34e83-110">Parts</span></span>  
  
|<span data-ttu-id="34e83-111">Termin</span><span class="sxs-lookup"><span data-stu-id="34e83-111">Term</span></span>|<span data-ttu-id="34e83-112">Definicja</span><span class="sxs-lookup"><span data-stu-id="34e83-112">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="34e83-113">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-113">Optional.</span></span> <span data-ttu-id="34e83-114">Lista atrybutów, które są stosowane do tego typu.</span><span class="sxs-lookup"><span data-stu-id="34e83-114">List of attributes that apply to this type.</span></span> <span data-ttu-id="34e83-115">Musisz ją ująć [lista atrybutów](../../../visual-basic/language-reference/statements/attribute-list.md) w nawiasy (`< >`).</span><span class="sxs-lookup"><span data-stu-id="34e83-115">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets (`< >`).</span></span>|  
|`accessmodifier`|<span data-ttu-id="34e83-116">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-116">Optional.</span></span> <span data-ttu-id="34e83-117">Określa, jaki kod mogą uzyskiwać dostęp do tego typu.</span><span class="sxs-lookup"><span data-stu-id="34e83-117">Specifies what code can access this type.</span></span> <span data-ttu-id="34e83-118">Zobacz [poziomy w języku Visual Basic dostępu](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-118">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="34e83-119">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-119">Optional.</span></span> <span data-ttu-id="34e83-120">Zobacz [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>|  
|`MustInherit`|<span data-ttu-id="34e83-121">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-121">Optional.</span></span> <span data-ttu-id="34e83-122">Zobacz [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-122">See [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>|  
|`NotInheritable`|<span data-ttu-id="34e83-123">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-123">Optional.</span></span> <span data-ttu-id="34e83-124">Zobacz [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-124">See [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span></span>|  
|`name`|<span data-ttu-id="34e83-125">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="34e83-125">Required.</span></span> <span data-ttu-id="34e83-126">Nazwa tego typu.</span><span class="sxs-lookup"><span data-stu-id="34e83-126">Name of this type.</span></span> <span data-ttu-id="34e83-127">Musi być zgodna z nazwą zdefiniowaną w innych częściowe deklaracje tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="34e83-127">Must match the name defined in all other partial declarations of the same type.</span></span>|  
|`Of`|<span data-ttu-id="34e83-128">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-128">Optional.</span></span> <span data-ttu-id="34e83-129">Określa, że jest typem ogólnym.</span><span class="sxs-lookup"><span data-stu-id="34e83-129">Specifies that this is a generic type.</span></span> <span data-ttu-id="34e83-130">Zobacz [typy ogólne w Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-130">See [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>|  
|`typelist`|<span data-ttu-id="34e83-131">Wymagane w przypadku użycia [z](../../../visual-basic/language-reference/statements/of-clause.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-131">Required if you use [Of](../../../visual-basic/language-reference/statements/of-clause.md).</span></span> <span data-ttu-id="34e83-132">Zobacz [typu listy](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-132">See [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>|  
|`Inherits`|<span data-ttu-id="34e83-133">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-133">Optional.</span></span> <span data-ttu-id="34e83-134">Zobacz [Inherits — instrukcja](../../../visual-basic/language-reference/statements/inherits-statement.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-134">See [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).</span></span>|  
|`classname`|<span data-ttu-id="34e83-135">Wymagane w przypadku użycia `Inherits`.</span><span class="sxs-lookup"><span data-stu-id="34e83-135">Required if you use `Inherits`.</span></span> <span data-ttu-id="34e83-136">Nazwa klasy lub interfejsu, w którym ta klasa dziedziczy.</span><span class="sxs-lookup"><span data-stu-id="34e83-136">The name of the class or interface from which this class derives.</span></span>|  
|`Implements`|<span data-ttu-id="34e83-137">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-137">Optional.</span></span> <span data-ttu-id="34e83-138">Zobacz [implementuje instrukcji](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-138">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>|  
|`interfacenames`|<span data-ttu-id="34e83-139">Wymagane w przypadku użycia `Implements`.</span><span class="sxs-lookup"><span data-stu-id="34e83-139">Required if you use `Implements`.</span></span> <span data-ttu-id="34e83-140">Nazwy interfejsów, które implementuje tego typu.</span><span class="sxs-lookup"><span data-stu-id="34e83-140">The names of the interfaces this type implements.</span></span>|  
|`variabledeclarations`|<span data-ttu-id="34e83-141">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-141">Optional.</span></span> <span data-ttu-id="34e83-142">Instrukcje, które deklaruje dodatkowe zmienne i zdarzenia dla typu.</span><span class="sxs-lookup"><span data-stu-id="34e83-142">Statements which declare additional variables and events for the type.</span></span>|  
|`proceduredeclarations`|<span data-ttu-id="34e83-143">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="34e83-143">Optional.</span></span> <span data-ttu-id="34e83-144">Instrukcje, które deklaruje i zdefiniować dodatkowe procedury dla typu.</span><span class="sxs-lookup"><span data-stu-id="34e83-144">Statements which declare and define additional procedures for the type.</span></span>|  
|<span data-ttu-id="34e83-145">`End Class`lub`End Structure`</span><span class="sxs-lookup"><span data-stu-id="34e83-145">`End Class` or `End Structure`</span></span>|<span data-ttu-id="34e83-146">Kończy się tym częściowego `Class` lub `Structure` definicji.</span><span class="sxs-lookup"><span data-stu-id="34e83-146">Ends this partial `Class` or `Structure` definition.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34e83-147">Uwagi</span><span class="sxs-lookup"><span data-stu-id="34e83-147">Remarks</span></span>  
 <span data-ttu-id="34e83-148">Visual Basic używa definicje klas częściowego do oddzielania wygenerowanego kodu z utworzonymi przez użytkownika kodu w plikach źródłowych oddzielne.</span><span class="sxs-lookup"><span data-stu-id="34e83-148">Visual Basic uses partial-class definitions to separate generated code from user-authored code in separate source files.</span></span> <span data-ttu-id="34e83-149">Na przykład **projektanta formularzy systemu Windows** definiuje częściowej klasy formantów, takich jak <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="34e83-149">For example, the **Windows Form Designer** defines partial classes for controls such as <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="34e83-150">Wygenerowany kod w tych kontrolek nie należy modyfikować.</span><span class="sxs-lookup"><span data-stu-id="34e83-150">You should not modify the generated code in these controls.</span></span>  
  
 <span data-ttu-id="34e83-151">Wszystkie reguły dla klasy, struktury, interfejsu i Tworzenie modułu, takich jak te dotyczące użycia modyfikator i dziedziczenie, zastosować podczas tworzenia typu częściowego.</span><span class="sxs-lookup"><span data-stu-id="34e83-151">All the rules for class, structure, interface, and module creation, such as those for modifier usage and inheritance, apply when creating a partial type.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="34e83-152">Najlepsze praktyki</span><span class="sxs-lookup"><span data-stu-id="34e83-152">Best Practices</span></span>  
  
-   <span data-ttu-id="34e83-153">W normalnych okolicznościach nie należy rozdzielić opracowania jednego typu w deklaracjach dwóch lub więcej.</span><span class="sxs-lookup"><span data-stu-id="34e83-153">Under normal circumstances, you should not split the development of a single type across two or more declarations.</span></span> <span data-ttu-id="34e83-154">W związku z tym w większości przypadków nie trzeba `Partial` — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="34e83-154">Therefore, in most cases you do not need the `Partial` keyword.</span></span>  
  
-   <span data-ttu-id="34e83-155">Aby zwiększyć czytelność, co z częściowa deklaracja typu powinna zawierać `Partial` — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="34e83-155">For readability, every partial declaration of a type should include the `Partial` keyword.</span></span> <span data-ttu-id="34e83-156">Kompilator umożliwia co najwyżej jeden częściowa deklaracja na pominięcie słowa kluczowego. co najmniej dwa pominięcia go kompilator sygnalizuje wystąpił błąd.</span><span class="sxs-lookup"><span data-stu-id="34e83-156">The compiler allows at most one partial declaration to omit the keyword; if two or more omit it the compiler signals an error.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="34e83-157">Zachowanie</span><span class="sxs-lookup"><span data-stu-id="34e83-157">Behavior</span></span>  
  
-   <span data-ttu-id="34e83-158">**Unia deklaracji.**</span><span class="sxs-lookup"><span data-stu-id="34e83-158">**Union of Declarations.**</span></span> <span data-ttu-id="34e83-159">Kompilator traktuje typ jako Unii wszystkie częściowe deklaracje.</span><span class="sxs-lookup"><span data-stu-id="34e83-159">The compiler treats the type as the union of all its partial declarations.</span></span> <span data-ttu-id="34e83-160">Każdy modyfikator z każdej definicji częściowej ma zastosowanie do wszystkich typu, a każdy element członkowski z każdej definicji częściowej jest dostępny dla wszystkich typu.</span><span class="sxs-lookup"><span data-stu-id="34e83-160">Every modifier from every partial definition applies to the entire type, and every member from every partial definition is available to the entire type.</span></span>  
  
-   <span data-ttu-id="34e83-161">**Promocja typu nie jest dozwolona dla typów częściowych w modułach.**</span><span class="sxs-lookup"><span data-stu-id="34e83-161">**Type Promotion Not Allowed For Partial Types in Modules.**</span></span> <span data-ttu-id="34e83-162">Jeśli jest częściową definicją wewnątrz modułu, promocja typu tego typu jest automatycznie bezcelowe.</span><span class="sxs-lookup"><span data-stu-id="34e83-162">If a partial definition is inside a module, type promotion of that type is automatically defeated.</span></span> <span data-ttu-id="34e83-163">W takim przypadku zestawu definicji częściowej może spowodować nieoczekiwane wyniki, a nawet błędy kompilatora.</span><span class="sxs-lookup"><span data-stu-id="34e83-163">In such a case, a set of partial definitions can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="34e83-164">Aby uzyskać więcej informacji, zobacz [promocja typu](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="34e83-164">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
     <span data-ttu-id="34e83-165">Kompilator scala definicji częściowej tylko wtedy, gdy ich w pełni kwalifikowanej ścieżki są identyczne.</span><span class="sxs-lookup"><span data-stu-id="34e83-165">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
 <span data-ttu-id="34e83-166">`Partial` — Słowo kluczowe może być używana w tych sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="34e83-166">The `Partial` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="34e83-167">Class — instrukcja</span><span class="sxs-lookup"><span data-stu-id="34e83-167">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="34e83-168">Structure — instrukcja</span><span class="sxs-lookup"><span data-stu-id="34e83-168">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a><span data-ttu-id="34e83-169">Przykład</span><span class="sxs-lookup"><span data-stu-id="34e83-169">Example</span></span>  
 <span data-ttu-id="34e83-170">Poniższy przykład dzieli definicji klasy `sampleClass` do dwóch deklaracji, z których każdy definiuje innej `Sub` procedury.</span><span class="sxs-lookup"><span data-stu-id="34e83-170">The following example splits the definition of class `sampleClass` into two declarations, each of which defines a different `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrKeywords#3](../../../visual-basic/language-reference/codesnippet/VisualBasic/partial_1.vb)]  
  
 <span data-ttu-id="34e83-171">Dwie definicje częściowe w poprzednim przykładzie można w tym samym pliku źródłowego lub w dwóch plikach innego źródła.</span><span class="sxs-lookup"><span data-stu-id="34e83-171">The two partial definitions in the preceding example could be in the same source file or in two different source files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e83-172">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="34e83-172">See Also</span></span>  
 [<span data-ttu-id="34e83-173">Class — instrukcja</span><span class="sxs-lookup"><span data-stu-id="34e83-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="34e83-174">Structure — instrukcja</span><span class="sxs-lookup"><span data-stu-id="34e83-174">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="34e83-175">Promocja typu</span><span class="sxs-lookup"><span data-stu-id="34e83-175">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)  
 [<span data-ttu-id="34e83-176">Shadows</span><span class="sxs-lookup"><span data-stu-id="34e83-176">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="34e83-177">Typy ogólne w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="34e83-177">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="34e83-178">Metody częściowe</span><span class="sxs-lookup"><span data-stu-id="34e83-178">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)