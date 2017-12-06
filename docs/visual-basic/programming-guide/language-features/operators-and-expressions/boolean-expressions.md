---
title: "Wyrażenia logiczne (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 48071c6833f9841fa42311dda59d6959c0645ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="ff9ff-102">Wyrażenia logiczne (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff9ff-102">Boolean Expressions (Visual Basic)</span></span>
<span data-ttu-id="ff9ff-103">A *wyrażenie warunkowe* wyrażenie obliczane do wartości [— typ danych logicznych](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` lub `False`.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-103">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="ff9ff-104">`Boolean`wyrażenia może potrwać kilka formularzy.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-104">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="ff9ff-105">Najprostszą jest bezpośrednie porównanie wartości `Boolean` zmienną `Boolean` literal, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-105">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="ff9ff-106">Dwa znaczenie = — Operator</span><span class="sxs-lookup"><span data-stu-id="ff9ff-106">Two Meanings of the = Operator</span></span>  
 <span data-ttu-id="ff9ff-107">Zwróć uwagę, że w instrukcji przypisania `newCustomer = True` wygląda tak samo jak wyrażenia w poprzednim przykładzie, ale wykonuje różne funkcje i jest używane w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-107">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="ff9ff-108">W powyższym przykładzie wyrażenie `newCustomer = True` reprezentuje wartość logiczną i `=` logowania jest interpretowana jako operator porównania.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-108">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="ff9ff-109">W instrukcji autonomicznej `=` logowania jest interpretowana jako operatora przypisania i przypisuje wartość prawej strony, aby zmienna po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-109">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="ff9ff-110">Ilustruje to poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 <span data-ttu-id="ff9ff-111">Aby uzyskać więcej informacji, zobacz [porównania wartości](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) i [instrukcje](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff9ff-111">For further information, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) and [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="ff9ff-112">Operatory porównania</span><span class="sxs-lookup"><span data-stu-id="ff9ff-112">Comparison Operators</span></span>  
 <span data-ttu-id="ff9ff-113">Operatory porównania, takich jak `=`, `<`, `>`, `<>`, `<=`, i `>=` utworzyć na podstawie porównania ilości wyrażenie po lewej stronie operatora wyrażenie po prawej stronie wyrażenia logiczne operator i oceny wynik w postaci `True` lub `False`.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-113">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="ff9ff-114">Ilustruje to poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-114">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="ff9ff-115">Ponieważ 42 jest mniejsza niż 81, wyrażenia logicznego w poprzednim przykładzie daje w wyniku `True`.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-115">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="ff9ff-116">Aby uzyskać więcej informacji na ten rodzaj wyrażenia, zobacz [porównania wartości](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).</span><span class="sxs-lookup"><span data-stu-id="ff9ff-116">For more information on this kind of expression, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="ff9ff-117">Operatory porównania w połączeniu z operatorami logicznymi</span><span class="sxs-lookup"><span data-stu-id="ff9ff-117">Comparison Operators Combined with Logical Operators</span></span>  
 <span data-ttu-id="ff9ff-118">Przy użyciu operatorów logicznych w celu utworzenia bardziej złożonych wyrażeń logicznych można łączyć wyrażeniach porównania.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-118">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="ff9ff-119">W poniższym przykładzie pokazano użycie operatory porównania w połączeniu z operatorem logicznym.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-119">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="ff9ff-120">W powyższym przykładzie wartość wyrażenia zależy od wartości wyrażenia na każdej stronie `And` operatora.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-120">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="ff9ff-121">Jeśli oba wyrażenia są `True`, a następnie daje w wyniku wyrażenia `True`.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-121">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="ff9ff-122">Jeśli jedno z wyrażeń ma `False`, a następnie całe wyrażenie daje w wyniku `False`.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-122">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="ff9ff-123">Zwarcie operatory</span><span class="sxs-lookup"><span data-stu-id="ff9ff-123">Short-Circuiting Operators</span></span>  
 <span data-ttu-id="ff9ff-124">Operatory logiczne `AndAlso` i `OrElse` zachowują znany jako *zwarcie*.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-124">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="ff9ff-125">Short-circuiting operator najpierw sprawdza Lewy argument operacji.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-125">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="ff9ff-126">Jeśli lewy operand określa wartość wyrażenia, wykonywania programu będzie kontynuowane bez obliczania prawe wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-126">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="ff9ff-127">Ilustruje to poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-127">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 <span data-ttu-id="ff9ff-128">W powyższym przykładzie operator oblicza wyrażenie po lewej stronie, `45 < 12`.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-128">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="ff9ff-129">Ponieważ lewe wyrażenie daje w wyniku `False`, całego wyrażenia logicznego musi być `False`.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-129">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="ff9ff-130">Wykonanie programu, w związku z tym pomija wykonywanie kodu w `If` bez oceny prawe wyrażenie `testFunction(3)`.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-130">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="ff9ff-131">W tym przykładzie nie wywołuje `testFunction()` ponieważ po lewej stronie wyrażenia falsifies całego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-131">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="ff9ff-132">Podobnie jeśli wyrażenie po lewej stronie wyrażenia logicznego przy użyciu `OrElse` daje w wyniku `True`, wykonanie przechodzi do następnego wiersza kodu bez sprawdzania prawe wyrażenie, ponieważ wyrażenie po lewej stronie już został zweryfikowany całą wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-132">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="ff9ff-133">Porównanie z operatorami Circuiting krótki</span><span class="sxs-lookup"><span data-stu-id="ff9ff-133">Comparison with Non-Short-Circuiting Operators</span></span>  
 <span data-ttu-id="ff9ff-134">Z kolei obu stronach operatora logicznego są oceniane po operatorów logicznych `And` i `Or` są używane.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-134">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="ff9ff-135">Ilustruje to poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 <span data-ttu-id="ff9ff-136">Poprzednim przykładzie wywołuje `testFunction()` nawet po lewej stronie wyrażenia `False`.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-136">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="ff9ff-137">Wyrażenia w nawiasach</span><span class="sxs-lookup"><span data-stu-id="ff9ff-137">Parenthetical Expressions</span></span>  
 <span data-ttu-id="ff9ff-138">Można użyć nawiasów określających kolejność obliczania wyrażeń logicznych.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-138">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="ff9ff-139">Najpierw należy ocenić wyrażenia ujętego w nawiasy.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-139">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="ff9ff-140">Wiele poziomów zagnieżdżenia pierwszeństwo jest przyznawane najbardziej głęboko zagnieżdżone wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-140">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="ff9ff-141">Ocena będzie kontynuowana, zgodnie z regułami kolejność wykonywania działań w obrębie nawiasów.</span><span class="sxs-lookup"><span data-stu-id="ff9ff-141">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="ff9ff-142">Aby uzyskać więcej informacji, zobacz [kolejność wykonywania w języku Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="ff9ff-142">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9ff-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ff9ff-143">See Also</span></span>  
 [<span data-ttu-id="ff9ff-144">Operatory logiczne i bitowe w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff9ff-144">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="ff9ff-145">Porównania wartości</span><span class="sxs-lookup"><span data-stu-id="ff9ff-145">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="ff9ff-146">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="ff9ff-146">Statements</span></span>](../../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="ff9ff-147">Operatory porównania</span><span class="sxs-lookup"><span data-stu-id="ff9ff-147">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="ff9ff-148">Skuteczna kombinacja operatorów</span><span class="sxs-lookup"><span data-stu-id="ff9ff-148">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [<span data-ttu-id="ff9ff-149">Kolejność wykonywania w języku Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff9ff-149">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ff9ff-150">Boolean — typ danych</span><span class="sxs-lookup"><span data-stu-id="ff9ff-150">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)