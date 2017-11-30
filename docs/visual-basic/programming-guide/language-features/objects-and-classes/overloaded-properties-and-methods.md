---
title: "Przeciążone właściwości i metody (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a872540716941ccd0dbb8b058508b89ce26a988
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="af9fe-102">Przeciążone właściwości i metody (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af9fe-102">Overloaded Properties and Methods (Visual Basic)</span></span>
<span data-ttu-id="af9fe-103">Przeciążanie jest tworzenie więcej niż jednej procedury, wystąpienie konstruktora lub właściwości w klasie z tej samej nazwie, ale argument różnych typów.</span><span class="sxs-lookup"><span data-stu-id="af9fe-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="af9fe-104">Przeciążanie użycia</span><span class="sxs-lookup"><span data-stu-id="af9fe-104">Overloading Usage</span></span>  
 <span data-ttu-id="af9fe-105">Przeciążanie jest szczególnie przydatna w przypadku, gdy model obiektu mówią, że zostanie zastosowana identycznych nazw dla procedur, które działają na różnych typach danych.</span><span class="sxs-lookup"><span data-stu-id="af9fe-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="af9fe-106">Na przykład klasa służąca do wyświetlania kilku różnych typów danych może mieć `Display` procedur, które wyglądają następująco:</span><span class="sxs-lookup"><span data-stu-id="af9fe-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 <span data-ttu-id="af9fe-107">Bez przeładowania, będzie potrzebny do tworzenia unikatowych nazw dla każdej procedury, mimo że robią to samo, jak pokazano w następnym:</span><span class="sxs-lookup"><span data-stu-id="af9fe-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 <span data-ttu-id="af9fe-108">Przeciążanie ułatwia używać właściwości lub metody, ponieważ umożliwia wybór typów danych, które mogą być używane.</span><span class="sxs-lookup"><span data-stu-id="af9fe-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="af9fe-109">Na przykład przeciążone `Display` omówionych wcześniej można wywołać metody za pomocą dowolnego z następujących wierszy kodu:</span><span class="sxs-lookup"><span data-stu-id="af9fe-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 <span data-ttu-id="af9fe-110">W czasie wykonywania [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Określ prawidłowe procedury na podstawie typów danych parametrów wywołania.</span><span class="sxs-lookup"><span data-stu-id="af9fe-110">At run time, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="af9fe-111">Przeciążanie reguły</span><span class="sxs-lookup"><span data-stu-id="af9fe-111">Overloading Rules</span></span>  
 <span data-ttu-id="af9fe-112">Przeciążonego elementu członkowskiego klasy można utworzyć przez dodanie dwóch lub więcej właściwości lub metody o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="af9fe-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="af9fe-113">Z wyjątkiem przeciążone elementy członkowskie pochodnej każdy przeciążonego elementu członkowskiego musi mieć listy różnych parametrów, a następujące elementy nie może pełnić funkcji różnego przeciążania właściwość lub procedura:</span><span class="sxs-lookup"><span data-stu-id="af9fe-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="af9fe-114">Modyfikatory, takich jak `ByVal` lub `ByRef`, które są stosowane do elementu członkowskiego lub parametrów elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="af9fe-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="af9fe-115">Nazwy parametrów</span><span class="sxs-lookup"><span data-stu-id="af9fe-115">Names of parameters</span></span>  
  
-   <span data-ttu-id="af9fe-116">Zwracane typy procedur</span><span class="sxs-lookup"><span data-stu-id="af9fe-116">Return types of procedures</span></span>  
  
 <span data-ttu-id="af9fe-117">`Overloads` — Słowo kluczowe jest opcjonalny w przypadku przeciążania, ale jeśli występują przeciążony używa elementu członkowskiego `Overloads` — słowo kluczowe, a następnie wszystkie inne przeciążone elementy członkowskie o tej samej nazwie należy także określić słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="af9fe-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="af9fe-118">Klasy pochodne mogą przeciążania dziedziczonych członków z elementów członkowskich, które mają identyczne parametry i typy parametrów procesu nazywanego *przesłanianie według nazwy i podpisu*.</span><span class="sxs-lookup"><span data-stu-id="af9fe-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="af9fe-119">Jeśli `Overloads` — słowo kluczowe jest używana, gdy przesłanianie według nazwy i podpisu, implementacja klasy pochodnej elementu członkowskiego zamiast będzie używany do implementacji w klasie podstawowej, i inne przeciążenia dla tego elementu członkowskiego będą dostępne do wystąpień klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="af9fe-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="af9fe-120">Jeśli `Overloads` — słowo kluczowe zostanie pominięty przeciążania dziedziczonego elementu członkowskiego z elementem członkowskim, który ma identyczne parametry i typy parametrów, a następnie przeładowanie jest nazywany *przesłanianie według nazwy*.</span><span class="sxs-lookup"><span data-stu-id="af9fe-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="af9fe-121">Przesłanianie według nazwy zastępuje implementacji dziedziczonego elementu członkowskiego, a także udostępnia inne przeciążenia jest niedostępny dla wystąpień klasy pochodnej i jego decedents.</span><span class="sxs-lookup"><span data-stu-id="af9fe-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="af9fe-122">`Overloads` i `Shadows` Modyfikatory nie można używać z tej samej właściwości lub metody.</span><span class="sxs-lookup"><span data-stu-id="af9fe-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="af9fe-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="af9fe-123">Example</span></span>  
 <span data-ttu-id="af9fe-124">Poniższy przykład tworzy przeciążonych metod, które akceptują albo `String` lub `Decimal` reprezentację kwota dolara ($) i zwracany ciąg zawierający podatku.</span><span class="sxs-lookup"><span data-stu-id="af9fe-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="af9fe-125">Aby użyć w tym przykładzie do utworzenia przeciążonej metody</span><span class="sxs-lookup"><span data-stu-id="af9fe-125">To use this example to create an overloaded method</span></span>  
  
1.  <span data-ttu-id="af9fe-126">Otwórz nowy projekt i Dodaj klasę o nazwie `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="af9fe-126">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="af9fe-127">Dodaj następujący kod do `TaxClass` klasy.</span><span class="sxs-lookup"><span data-stu-id="af9fe-127">Add the following code to the `TaxClass` class.</span></span>  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  <span data-ttu-id="af9fe-128">Poniższej procedury można dodać do formularza.</span><span class="sxs-lookup"><span data-stu-id="af9fe-128">Add the following procedure to your form.</span></span>  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  <span data-ttu-id="af9fe-129">Dodawanie przycisku do formularza i wywołanie `ShowTax` procedury z `Button1_Click` zdarzeń przycisku.</span><span class="sxs-lookup"><span data-stu-id="af9fe-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="af9fe-130">Uruchom projekt i kliknij przycisk w formularzu do testowania przeciążone `ShowTax` procedury.</span><span class="sxs-lookup"><span data-stu-id="af9fe-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="af9fe-131">W czasie wykonywania kompilator wybiera odpowiednią przeciążonej funkcji zgodny z parametrami używane.</span><span class="sxs-lookup"><span data-stu-id="af9fe-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="af9fe-132">Po kliknięciu przycisku przeciążona metoda jest wywoływana najpierw z `Price` parametr, który jest ciągiem i komunikat "cena jest ciągiem.</span><span class="sxs-lookup"><span data-stu-id="af9fe-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="af9fe-133">Podatek jest $5,12" jest wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="af9fe-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="af9fe-134">`TaxAmount`jest wywoływana z `Decimal` wartość po raz drugi i komunikat, "cena jest wartości dziesiętnej.</span><span class="sxs-lookup"><span data-stu-id="af9fe-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="af9fe-135">Podatek jest $5,12" jest wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="af9fe-135">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af9fe-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="af9fe-136">See Also</span></span>  
 [<span data-ttu-id="af9fe-137">Obiekty i klasy</span><span class="sxs-lookup"><span data-stu-id="af9fe-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="af9fe-138">Przesłanianie w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af9fe-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="af9fe-139">Sub — instrukcja</span><span class="sxs-lookup"><span data-stu-id="af9fe-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="af9fe-140">Podstawowe informacje o dziedziczeniu</span><span class="sxs-lookup"><span data-stu-id="af9fe-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="af9fe-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="af9fe-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="af9fe-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="af9fe-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [<span data-ttu-id="af9fe-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="af9fe-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [<span data-ttu-id="af9fe-144">Przeciążenia</span><span class="sxs-lookup"><span data-stu-id="af9fe-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="af9fe-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="af9fe-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)