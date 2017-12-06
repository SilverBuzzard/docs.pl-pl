---
title: "Yield — Instrukcja (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99f5129d5cb43cddfb17731f337a72fae22d3626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="62e6d-102">Yield — Instrukcja (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62e6d-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="62e6d-103">Wysyła następnego elementu kolekcji do `For Each...Next` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="62e6d-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62e6d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="62e6d-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62e6d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="62e6d-105">Parameters</span></span>  
  
|<span data-ttu-id="62e6d-106">Termin</span><span class="sxs-lookup"><span data-stu-id="62e6d-106">Term</span></span>|<span data-ttu-id="62e6d-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="62e6d-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="62e6d-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="62e6d-108">Required.</span></span> <span data-ttu-id="62e6d-109">Wyrażenie, które jest umożliwiają niejawnej konwersji na typ funkcji iteracyjnej lub `Get` dostępu, który zawiera `Yield` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="62e6d-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62e6d-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="62e6d-110">Remarks</span></span>  
 <span data-ttu-id="62e6d-111">`Yield` Instrukcja zwraca jeden element w kolekcji w czasie.</span><span class="sxs-lookup"><span data-stu-id="62e6d-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="62e6d-112">`Yield` Instrukcji znajduje się w funkcji iteracyjnej lub `Get` metody dostępu wykonać niestandardowe iteracji w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="62e6d-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="62e6d-113">Korzystać z funkcji iteracyjnej przy użyciu [For Each... Następna instrukcja](../../../visual-basic/language-reference/statements/for-each-next-statement.md) lub zapytania LINQ.</span><span class="sxs-lookup"><span data-stu-id="62e6d-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="62e6d-114">Każdej iteracji `For Each` pętli wywołuje funkcję iteratora.</span><span class="sxs-lookup"><span data-stu-id="62e6d-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="62e6d-115">Gdy `Yield` instrukcji zostanie osiągnięta w funkcji iteracyjnej `expression` jest zwracany, i są przechowywane w bieżącej lokalizacji w kodzie.</span><span class="sxs-lookup"><span data-stu-id="62e6d-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="62e6d-116">Wykonanie jest uruchamiane ponownie z tej lokalizacji przy następnym wywołaniu funkcji iteratora.</span><span class="sxs-lookup"><span data-stu-id="62e6d-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="62e6d-117">Niejawna konwersja musi istnieć z typu `expression` w `Yield` instrukcji, aby zwracany typ iteratora.</span><span class="sxs-lookup"><span data-stu-id="62e6d-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="62e6d-118">Można użyć `Exit Function` lub `Return` instrukcji, aby zakończyć iterację.</span><span class="sxs-lookup"><span data-stu-id="62e6d-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="62e6d-119">"Yield" nie jest słowem zastrzeżonym i ma specjalne znaczenie tylko wtedy, gdy jest on używany w `Iterator` funkcji lub `Get` dostępu.</span><span class="sxs-lookup"><span data-stu-id="62e6d-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="62e6d-120">Aby uzyskać więcej informacji o funkcje iteracyjne i `Get` metod dostępu, zobacz [Iteratory](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="62e6d-120">For more information about iterator functions and `Get` accessors, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="62e6d-121">Funkcje iteracyjne i metody dostępu Get</span><span class="sxs-lookup"><span data-stu-id="62e6d-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="62e6d-122">Deklaracja funkcji iteracyjnej lub `Get` akcesora musi spełniać następujące wymagania:</span><span class="sxs-lookup"><span data-stu-id="62e6d-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="62e6d-123">Musi on zawierać [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modyfikator.</span><span class="sxs-lookup"><span data-stu-id="62e6d-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="62e6d-124">Zwracany typ musi być <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, lub <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="62e6d-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="62e6d-125">Nie ma żadnych `ByRef` parametrów.</span><span class="sxs-lookup"><span data-stu-id="62e6d-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="62e6d-126">Funkcji iteracyjnej nie może wystąpić w zdarzenia, konstruktora wystąpienia, statycznego konstruktora lub destruktora statycznych.</span><span class="sxs-lookup"><span data-stu-id="62e6d-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="62e6d-127">Funkcji iteracyjnej można funkcji anonimowej.</span><span class="sxs-lookup"><span data-stu-id="62e6d-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="62e6d-128">Aby uzyskać więcej informacji, zobacz [Iteratory](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="62e6d-128">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="62e6d-129">Obsługa wyjątków</span><span class="sxs-lookup"><span data-stu-id="62e6d-129">Exception Handling</span></span>  
 <span data-ttu-id="62e6d-130">A `Yield` instrukcja może być wewnątrz `Try` zablokować z [spróbuj... CATCH... Instrukcji finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="62e6d-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="62e6d-131">A `Try` bloku, który ma `Yield` instrukcja może mieć `Catch` blokuje i może mieć `Finally` bloku.</span><span class="sxs-lookup"><span data-stu-id="62e6d-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="62e6d-132">A `Yield` instrukcja nie może być wewnątrz `Catch` bloku lub `Finally` bloku.</span><span class="sxs-lookup"><span data-stu-id="62e6d-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="62e6d-133">Jeśli `For Each` treści (poza funkcją iteratora) zgłasza wyjątek, `Catch` bloku w funkcji iteracyjnej nie została wykonana, ale `Finally` wykonaniu bloku w funkcji iteracyjnej.</span><span class="sxs-lookup"><span data-stu-id="62e6d-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="62e6d-134">A `Catch` bloku wewnątrz funkcji iteracyjnej przechwytuje tylko wyjątki, które występuje wewnątrz funkcji iteracyjnej.</span><span class="sxs-lookup"><span data-stu-id="62e6d-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="62e6d-135">Realizacja techniczna</span><span class="sxs-lookup"><span data-stu-id="62e6d-135">Technical Implementation</span></span>  
 <span data-ttu-id="62e6d-136">Poniższy kod zwraca `IEnumerable (Of String)` z funkcji iteracyjnej, a następnie wykonuje iterację elementy `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="62e6d-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="62e6d-137">Wywołanie `MyIteratorFunction` treści funkcji nie jest wykonywana.</span><span class="sxs-lookup"><span data-stu-id="62e6d-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="62e6d-138">Zamiast tego wywołanie zwraca `IEnumerable(Of String)` do `elements` zmiennej.</span><span class="sxs-lookup"><span data-stu-id="62e6d-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="62e6d-139">Na iterację `For Each` pętli, <xref:System.Collections.IEnumerator.MoveNext%2A> metoda jest wywoływana dla `elements`.</span><span class="sxs-lookup"><span data-stu-id="62e6d-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="62e6d-140">To wywołanie wykonuje treści `MyIteratorFunction` aż do następnego `Yield` osiągnięciu instrukcji.</span><span class="sxs-lookup"><span data-stu-id="62e6d-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="62e6d-141">`Yield` Instrukcja zwraca wyrażenie określające nie tylko wartość `element` zmienna do użycia przez pętli, ale także <xref:System.Collections.Generic.IEnumerator%601.Current%2A> właściwości elementów, która jest `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="62e6d-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="62e6d-142">W każdej iteracji kolejnych `For Each` pętli, wykonanie treści iteratora kontynuuje działanie od miejsca przerwał, ponownie zatrzymywanie po osiągnięciu `Yield` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="62e6d-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="62e6d-143">`For Each` Pętli działanie jest kończone po zakończeniu funkcji iteracyjnej lub `Return` lub `Exit Function` osiągnięciu instrukcji.</span><span class="sxs-lookup"><span data-stu-id="62e6d-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62e6d-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="62e6d-144">Example</span></span>  
 <span data-ttu-id="62e6d-145">W poniższym przykładzie przedstawiono `Yield` instrukcji, która znajduje się wewnątrz [dla... Następny](../../../visual-basic/language-reference/statements/for-next-statement.md) pętli.</span><span class="sxs-lookup"><span data-stu-id="62e6d-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="62e6d-146">Każdej iteracji [dla każdego](../../../visual-basic/language-reference/statements/for-each-next-statement.md) treść instrukcji w `Main` tworzy wywołanie `Power` funkcji iteracyjnej.</span><span class="sxs-lookup"><span data-stu-id="62e6d-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="62e6d-147">Każde wywołanie funkcji iteracyjnej przechodzi do następnego wykonywanie `Yield` instrukcja, która występuje w ciągu następnej iteracji `For…Next` pętli.</span><span class="sxs-lookup"><span data-stu-id="62e6d-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="62e6d-148">Zwracany typ metody iteracyjnej jest <xref:System.Collections.Generic.IEnumerable%601>, typem interfejsu iteratora.</span><span class="sxs-lookup"><span data-stu-id="62e6d-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="62e6d-149">Kiedy metoda iteratora jest wywoływana, zwraca obiekt wyliczeniowy, który zawiera potęgi liczb.</span><span class="sxs-lookup"><span data-stu-id="62e6d-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="62e6d-150">Przykład</span><span class="sxs-lookup"><span data-stu-id="62e6d-150">Example</span></span>  
 <span data-ttu-id="62e6d-151">W poniższym przykładzie pokazano `Get` dostępu, który jest iteratora.</span><span class="sxs-lookup"><span data-stu-id="62e6d-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="62e6d-152">Deklaracja właściwości zawiera `Iterator` modyfikator.</span><span class="sxs-lookup"><span data-stu-id="62e6d-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 <span data-ttu-id="62e6d-153">Aby uzyskać dodatkowe przykłady, zobacz [Iteratory](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="62e6d-153">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62e6d-154">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="62e6d-154">See Also</span></span>  
 [<span data-ttu-id="62e6d-155">Iteratory</span><span class="sxs-lookup"><span data-stu-id="62e6d-155">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="62e6d-156">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="62e6d-156">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)