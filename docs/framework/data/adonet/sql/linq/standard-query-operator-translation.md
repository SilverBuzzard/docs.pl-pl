---
title: Translacja Operator zapytania standardowe
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1156608e9e1aa63a2404d5394c0c4211eea60693
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="standard-query-operator-translation"></a><span data-ttu-id="bffad-102">Translacja Operator zapytania standardowe</span><span class="sxs-lookup"><span data-stu-id="bffad-102">Standard Query Operator Translation</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bffad-103">wykonuje translację standardowych operatorów zapytań do poleceń SQL.</span><span class="sxs-lookup"><span data-stu-id="bffad-103"> translates Standard Query Operators to SQL commands.</span></span> <span data-ttu-id="bffad-104">Procesor zapytań bazy danych określa semantyki wykonywania tłumaczenia SQL.</span><span class="sxs-lookup"><span data-stu-id="bffad-104">The query processor of the database determines the execution semantics of SQL translation.</span></span>  
  
 <span data-ttu-id="bffad-105">Standardowe operatory zapytań są zdefiniowane w odniesieniu do *sekwencji*.</span><span class="sxs-lookup"><span data-stu-id="bffad-105">Standard Query Operators are defined against *sequences*.</span></span> <span data-ttu-id="bffad-106">Sekwencja jest *uporządkowane* i opiera się na tożsamości odwołania dla każdego elementu w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bffad-106">A sequence is *ordered* and relies on reference identity for each element of the sequence.</span></span> <span data-ttu-id="bffad-107">Aby uzyskać więcej informacji, zobacz [standardowe operatory zapytań — omówienie](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="bffad-107">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
 <span data-ttu-id="bffad-108">SQL dotyczy przede wszystkim *nieuporządkowane zestawy wartości*.</span><span class="sxs-lookup"><span data-stu-id="bffad-108">SQL deals primarily with *unordered sets of values*.</span></span> <span data-ttu-id="bffad-109">Kolejność jest zwykle jawnie stwierdzono, operacja, która jest stosowana do końcowego wyniku zapytania, a nie na pośrednich wyników przetwarzania końcowego.</span><span class="sxs-lookup"><span data-stu-id="bffad-109">Ordering is typically an explicitly stated, post-processing operation that is applied to the final result of a query rather than to intermediate results.</span></span> <span data-ttu-id="bffad-110">Tożsamość jest definiowany przez wartości.</span><span class="sxs-lookup"><span data-stu-id="bffad-110">Identity is defined by values.</span></span> <span data-ttu-id="bffad-111">Z tego powodu zapytania SQL są zrozumiałe radzenia sobie z multisets (*torebki*) zamiast *ustawia*.</span><span class="sxs-lookup"><span data-stu-id="bffad-111">For this reason, SQL queries are understood to deal with multisets (*bags*) instead of *sets*.</span></span>  
  
 <span data-ttu-id="bffad-112">Następuje opisano różnice między standardowych operatorów zapytań i ich tłumaczenia SQL dla dostawcy programu SQL Server dla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffad-112">The following paragraphs describe the differences between the Standard Query Operators and their SQL translation for the SQL Server provider for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
## <a name="operator-support"></a><span data-ttu-id="bffad-113">Obsługa — operator</span><span class="sxs-lookup"><span data-stu-id="bffad-113">Operator Support</span></span>  
  
### <a name="concat"></a><span data-ttu-id="bffad-114">concat</span><span class="sxs-lookup"><span data-stu-id="bffad-114">Concat</span></span>  
 <span data-ttu-id="bffad-115"><xref:System.Linq.Enumerable.Concat%2A> Metody jest zdefiniowany dla uporządkowanych multisets, których kolejność odbiornika oraz kolejność argumentu są takie same.</span><span class="sxs-lookup"><span data-stu-id="bffad-115">The <xref:System.Linq.Enumerable.Concat%2A> method is defined for ordered multisets where the order of the receiver and the order of the argument are the same.</span></span> <span data-ttu-id="bffad-116"><xref:System.Linq.Enumerable.Concat%2A>działa jako `UNION ALL` za pośrednictwem multisets następuje wspólnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="bffad-116"><xref:System.Linq.Enumerable.Concat%2A> works as `UNION ALL` over the multisets followed by the common order.</span></span>  
  
 <span data-ttu-id="bffad-117">Ostatnim krokiem jest kolejnością SQL przed wyniki są tworzone.</span><span class="sxs-lookup"><span data-stu-id="bffad-117">The final step is ordering in SQL before results are produced.</span></span> <span data-ttu-id="bffad-118"><xref:System.Linq.Enumerable.Concat%2A>Nie zachowuj Kolejność argumentów.</span><span class="sxs-lookup"><span data-stu-id="bffad-118"><xref:System.Linq.Enumerable.Concat%2A> does not preserve the order of its arguments.</span></span> <span data-ttu-id="bffad-119">W celu zapewnienia odpowiedniej kolejności, musisz jawnie kolejność wyników <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="bffad-119">To ensure appropriate ordering, you must explicitly order the results of <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
### <a name="intersect-except-union"></a><span data-ttu-id="bffad-120">INTERSECT, z wyjątkiem przypadków Unii</span><span class="sxs-lookup"><span data-stu-id="bffad-120">Intersect, Except, Union</span></span>  
 <span data-ttu-id="bffad-121"><xref:System.Linq.Enumerable.Intersect%2A> i <xref:System.Linq.Enumerable.Except%2A> metody są jasno określone tylko dla zestawów.</span><span class="sxs-lookup"><span data-stu-id="bffad-121">The <xref:System.Linq.Enumerable.Intersect%2A> and <xref:System.Linq.Enumerable.Except%2A> methods are well defined only on sets.</span></span> <span data-ttu-id="bffad-122">Semantyka dla multisets jest niezdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="bffad-122">The semantics for multisets is undefined.</span></span>  
  
 <span data-ttu-id="bffad-123"><xref:System.Linq.Enumerable.Union%2A> Metody określone dla multisets nieuporządkowaną złączeniem multisets (efektywnie wynik klauzuli UNION ALL w języku SQL).</span><span class="sxs-lookup"><span data-stu-id="bffad-123">The <xref:System.Linq.Enumerable.Union%2A> method is defined for multisets as the unordered concatenation of the multisets (effectively the result of the UNION ALL clause in SQL).</span></span>  
  
### <a name="take-skip"></a><span data-ttu-id="bffad-124">Take, Skip</span><span class="sxs-lookup"><span data-stu-id="bffad-124">Take, Skip</span></span>  
 <span data-ttu-id="bffad-125"><xref:System.Linq.Enumerable.Take%2A>i <xref:System.Linq.Enumerable.Skip%2A> metody są jasno określone tylko przed *uporządkowane zestawy*.</span><span class="sxs-lookup"><span data-stu-id="bffad-125"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods are well defined only against *ordered sets*.</span></span> <span data-ttu-id="bffad-126">Semantyka nieuporządkowaną zestawów lub multisets jest nieokreślona.</span><span class="sxs-lookup"><span data-stu-id="bffad-126">The semantics for unordered sets or multisets are undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bffad-127"><xref:System.Linq.Enumerable.Take%2A>i <xref:System.Linq.Enumerable.Skip%2A> mają pewne ograniczenia, gdy są one używane w kwerendach do programu SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="bffad-127"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="bffad-128">Aby uzyskać więcej informacji, zobacz wpis "Pomiń i podjąć wyjątków w programie SQL Server 2000" w [Rozwiązywanie problemów](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="bffad-128">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
 <span data-ttu-id="bffad-129">Ze względu na ograniczenia dotyczące kolejności w programie SQL [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] próbuje przenieść kolejność argument tych metod do wyniku metody.</span><span class="sxs-lookup"><span data-stu-id="bffad-129">Because of limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of these methods to the result of the method.</span></span> <span data-ttu-id="bffad-130">Na przykład, należy wziąć pod uwagę następujące [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapytania:</span><span class="sxs-lookup"><span data-stu-id="bffad-130">For example, consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query:</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
 [!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]  
  
 <span data-ttu-id="bffad-131">Wygenerowany SQL dla tego kodu przenosi kolejność w celu ich w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="bffad-131">The generated SQL for this code moves the ordering to the end, as follows:</span></span>  
  
```  
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 <span data-ttu-id="bffad-132">Staje się oczywiste, że wszystkie określona kolejność musi być spójna kiedy <xref:System.Linq.Enumerable.Take%2A> i <xref:System.Linq.Enumerable.Skip%2A> są połączone.</span><span class="sxs-lookup"><span data-stu-id="bffad-132">It becomes obvious that all the specified ordering must be consistent when <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are chained together.</span></span> <span data-ttu-id="bffad-133">W przeciwnym razie wyniki są niezdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="bffad-133">Otherwise, the results are undefined.</span></span>  
  
 <span data-ttu-id="bffad-134">Zarówno <xref:System.Linq.Enumerable.Take%2A> i <xref:System.Linq.Enumerable.Skip%2A> są dobrze zdefiniowany dla ujemna, stałych argumentów całkowitych na podstawie specyfikacji standardowe — Operator zapytań.</span><span class="sxs-lookup"><span data-stu-id="bffad-134">Both <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are well-defined for non-negative, constant integral arguments based on the Standard Query Operator specification.</span></span>  
  
### <a name="operators-with-no-translation"></a><span data-ttu-id="bffad-135">Operatory bez translacji</span><span class="sxs-lookup"><span data-stu-id="bffad-135">Operators with No Translation</span></span>  
 <span data-ttu-id="bffad-136">Następujących metod nie są tłumaczone przez [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffad-136">The following methods are not translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="bffad-137">Najczęstszą przyczyną jest różnica między nieuporządkowaną multisets i sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bffad-137">The most common reason is the difference between unordered multisets and sequences.</span></span>  
  
|<span data-ttu-id="bffad-138">Operatory</span><span class="sxs-lookup"><span data-stu-id="bffad-138">Operators</span></span>|<span data-ttu-id="bffad-139">Decyzja</span><span class="sxs-lookup"><span data-stu-id="bffad-139">Rationale</span></span>|  
|---------------|---------------|  
|<span data-ttu-id="bffad-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span><span class="sxs-lookup"><span data-stu-id="bffad-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span></span>|<span data-ttu-id="bffad-141">Zapytania SQL działają na multisets nie znajduje się w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bffad-141">SQL queries operate on multisets, not on sequences.</span></span> <span data-ttu-id="bffad-142">`ORDER BY`musi być ostatniej zastosowana wyniki.</span><span class="sxs-lookup"><span data-stu-id="bffad-142">`ORDER BY` must be the last clause applied to the results.</span></span> <span data-ttu-id="bffad-143">Z tego powodu nie istnieje żadne ogólnego przeznaczenia Translacja te dwie metody.</span><span class="sxs-lookup"><span data-stu-id="bffad-143">For this reason, there is no general-purpose translation for these two methods.</span></span>|  
|<xref:System.Linq.Enumerable.Reverse%2A>|<span data-ttu-id="bffad-144">Tłumaczenie tej metody jest możliwość uporządkowany zestaw, ale nie jest obecnie translacji przez [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffad-144">Translation of this method is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|<span data-ttu-id="bffad-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="bffad-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span></span>|<span data-ttu-id="bffad-146">Tłumaczenie z tych metod jest możliwe w dla zestawu uporządkowanych, ale nie jest obecnie translacji przez [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffad-146">Translation of these methods is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|<span data-ttu-id="bffad-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="bffad-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span></span>|<span data-ttu-id="bffad-148">Zapytania SQL działają na multisets na nie można indeksować sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bffad-148">SQL queries operate on multisets, not on indexable sequences.</span></span>|  
|<span data-ttu-id="bffad-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A>(przeciążenia z arg domyślne)</span><span class="sxs-lookup"><span data-stu-id="bffad-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload with default arg)</span></span>|<span data-ttu-id="bffad-150">Ogólnie rzecz biorąc wartości domyślnej nie można określić dla dowolnego spójnej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="bffad-150">In general, a default value cannot be specified for an arbitrary tuple.</span></span> <span data-ttu-id="bffad-151">Wartości null dla krotek są możliwe w niektórych przypadkach za pomocą sprzężeń zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="bffad-151">Null values for tuples are possible in some cases through outer joins.</span></span>|  
  
## <a name="expression-translation"></a><span data-ttu-id="bffad-152">Wyrażenie tłumaczenia</span><span class="sxs-lookup"><span data-stu-id="bffad-152">Expression Translation</span></span>  
  
### <a name="null-semantics"></a><span data-ttu-id="bffad-153">Semantyka wartości null</span><span class="sxs-lookup"><span data-stu-id="bffad-153">Null semantics</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bffad-154">nie nakłada semantykę porównania wartości null na SQL.</span><span class="sxs-lookup"><span data-stu-id="bffad-154"> does not impose null comparison semantics on SQL.</span></span> <span data-ttu-id="bffad-155">Operatory porównania składniowo są przekształcane na ich odpowiedniki SQL.</span><span class="sxs-lookup"><span data-stu-id="bffad-155">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="bffad-156">Z tego powodu semantykę odzwierciedlają semantyki SQL są definiowane przez ustawienia serwera lub połączenia.</span><span class="sxs-lookup"><span data-stu-id="bffad-156">For this reason, the semantics reflect SQL semantics that are defined by server or connection settings.</span></span> <span data-ttu-id="bffad-157">Na przykład dwie wartości null są traktowane jako nierówne w domyślnych ustawień programu SQL Server, ale można zmienić ustawienia, aby zmienić semantykę.</span><span class="sxs-lookup"><span data-stu-id="bffad-157">For example, two null values are considered unequal under default SQL Server settings, but you can change the settings to change the semantics.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bffad-158">nie należy wziąć pod uwagę ustawienia serwera podczas tłumaczy zapytania.</span><span class="sxs-lookup"><span data-stu-id="bffad-158"> does not consider server settings when it translates queries.</span></span>  
  
 <span data-ttu-id="bffad-159">Przetłumaczono porównanie z wartością literału null do odpowiedniej wersji programu SQL (`is null` lub `is not null`).</span><span class="sxs-lookup"><span data-stu-id="bffad-159">A comparison with the literal null is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>  
  
 <span data-ttu-id="bffad-160">Wartość `null` w sortowaniu jest zdefiniowany przez program SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bffad-160">The value of `null` in collation is defined by SQL Server.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bffad-161">nie powoduje zmiany sortowania.</span><span class="sxs-lookup"><span data-stu-id="bffad-161"> does not change the collation.</span></span>  
  
### <a name="aggregates"></a><span data-ttu-id="bffad-162">Agregaty</span><span class="sxs-lookup"><span data-stu-id="bffad-162">Aggregates</span></span>  
 <span data-ttu-id="bffad-163">Metoda agregacji standardowe — Operator zapytań <xref:System.Linq.Enumerable.Sum%2A> oblicza od zera dla pustej sekwencji lub sekwencję, która zawiera tylko wartości null.</span><span class="sxs-lookup"><span data-stu-id="bffad-163">The Standard Query Operator aggregate method <xref:System.Linq.Enumerable.Sum%2A> evaluates to zero for an empty sequence or for a sequence that contains only nulls.</span></span> <span data-ttu-id="bffad-164">W [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], semantykę SQL pozostaną bez zmian, i <xref:System.Linq.Enumerable.Sum%2A> daje w wyniku `null` zamiast zero sekwencji, który zawiera tylko wartości null lub pustej sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bffad-164">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged, and <xref:System.Linq.Enumerable.Sum%2A> evaluates to `null` instead of zero for an empty sequence or for a sequence that contains only nulls.</span></span>  
  
 <span data-ttu-id="bffad-165">Ograniczenia SQL pośrednich wyników dotyczą wartości zagregowanych w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffad-165">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="bffad-166"><xref:System.Linq.Enumerable.Sum%2A> 32-bitowej liczby całkowitej ilości nie jest obliczana przy użyciu 64-bitowych wyników.</span><span class="sxs-lookup"><span data-stu-id="bffad-166">The <xref:System.Linq.Enumerable.Sum%2A> of 32-bit integer quantities is not computed by using 64-bit results.</span></span> <span data-ttu-id="bffad-167">Przepełnienie mogą wystąpić w przypadku [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczenie <xref:System.Linq.Enumerable.Sum%2A>nawet w przypadku wdrożenia standardowego — Operator zapytań nie spowoduje przepełnienie w odpowiedniej sekwencji w pamięci.</span><span class="sxs-lookup"><span data-stu-id="bffad-167">Overflow might occur for a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Sum%2A>, even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>  
  
 <span data-ttu-id="bffad-168">Podobnie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczenie <xref:System.Linq.Enumerable.Average%2A> liczby całkowitej wartości jest obliczana jako `integer`, nie jako `double`.</span><span class="sxs-lookup"><span data-stu-id="bffad-168">Likewise, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Average%2A> of integer values is computed as an `integer`, not as a `double`.</span></span>  
  
### <a name="entity-arguments"></a><span data-ttu-id="bffad-169">Argumenty jednostki</span><span class="sxs-lookup"><span data-stu-id="bffad-169">Entity Arguments</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bffad-170">Włącza typy jednostek, które mają być używane w <xref:System.Linq.Enumerable.GroupBy%2A> i <xref:System.Linq.Enumerable.OrderBy%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="bffad-170"> enables entity types to be used in the <xref:System.Linq.Enumerable.GroupBy%2A> and <xref:System.Linq.Enumerable.OrderBy%2A> methods.</span></span> <span data-ttu-id="bffad-171">W tłumaczeniu wartości tych operatorów Użyj argumentu typu jest uważana za równoważne określenie wszystkich elementów członkowskich tego typu.</span><span class="sxs-lookup"><span data-stu-id="bffad-171">In the translation of these operators, the use of an argument of a type is considered to be the equivalent to specifying all members of that type.</span></span> <span data-ttu-id="bffad-172">Na przykład następujący kod jest równoważne:</span><span class="sxs-lookup"><span data-stu-id="bffad-172">For example, the following code is equivalent:</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
 [!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]  
  
### <a name="equatable--comparable-arguments"></a><span data-ttu-id="bffad-173">Equatable / można porównywać argumentów</span><span class="sxs-lookup"><span data-stu-id="bffad-173">Equatable / Comparable Arguments</span></span>  
 <span data-ttu-id="bffad-174">Równość argumentów jest wymagane w celu wykonania następujących metod:</span><span class="sxs-lookup"><span data-stu-id="bffad-174">Equality of arguments is required in the implementation of the following methods:</span></span>  
  
 <xref:System.Linq.Enumerable.Contains%2A>  
  
 <xref:System.Linq.Enumerable.Skip%2A>  
  
 <xref:System.Linq.Enumerable.Union%2A>  
  
 <xref:System.Linq.Enumerable.Intersect%2A>  
  
 <xref:System.Linq.Enumerable.Except%2A>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bffad-175">obsługuje równości i porównania dla *płaskiej* argumentów, ale nie dla argumentów, które są lub zawierać sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bffad-175"> supports equality and comparison for *flat* arguments, but not for arguments that are or contain sequences.</span></span> <span data-ttu-id="bffad-176">Płaski argument jest typu, które mogą być mapowane na wiersz SQL.</span><span class="sxs-lookup"><span data-stu-id="bffad-176">A flat argument is a type that can be mapped to a SQL row.</span></span> <span data-ttu-id="bffad-177">Rzutowania typów jednostek, które można ustalić statycznie nie może zawierać sekwencję jest traktowany jako płaska argument.</span><span class="sxs-lookup"><span data-stu-id="bffad-177">A projection of one or more entity types that can be statically determined not to contain a sequence is considered a flat argument.</span></span>  
  
 <span data-ttu-id="bffad-178">Poniżej przedstawiono przykłady płaskiej argumentów:</span><span class="sxs-lookup"><span data-stu-id="bffad-178">Following are examples of flat arguments:</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
 [!code-vb[DLinqSQOTranslation#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]  
  
 <span data-ttu-id="bffad-179">Poniżej przedstawiono przykłady argumentów płaski (hierarchiczna).</span><span class="sxs-lookup"><span data-stu-id="bffad-179">The following are examples of non-flat (hierarchical) arguments.</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
 [!code-vb[DLinqSQOTranslation#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]  
  
### <a name="visual-basic-function-translation"></a><span data-ttu-id="bffad-180">Tłumaczenie funkcji języka Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bffad-180">Visual Basic Function Translation</span></span>  
 <span data-ttu-id="bffad-181">Następujące funkcje pomocnicze, które są używane przez kompilator Visual Basic są tłumaczone na odpowiednich operatory SQL i funkcje:</span><span class="sxs-lookup"><span data-stu-id="bffad-181">The following helper functions that are used by the Visual Basic compiler are translated to corresponding SQL operators and functions:</span></span>  
  
 `CompareString`  
  
 `DateTime.Compare`  
  
 `Decimal.Compare`  
  
 `IIf (in Microsoft.VisualBasic.Interaction)`  
  
 <span data-ttu-id="bffad-182">Metody konwersji:</span><span class="sxs-lookup"><span data-stu-id="bffad-182">Conversion methods:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="bffad-183">ToBoolean</span><span class="sxs-lookup"><span data-stu-id="bffad-183">ToBoolean</span></span>|<span data-ttu-id="bffad-184">Tosbyte —</span><span class="sxs-lookup"><span data-stu-id="bffad-184">ToSByte</span></span>|<span data-ttu-id="bffad-185">Tobyte —</span><span class="sxs-lookup"><span data-stu-id="bffad-185">ToByte</span></span>|<span data-ttu-id="bffad-186">Tochar —</span><span class="sxs-lookup"><span data-stu-id="bffad-186">ToChar</span></span>|  
|<span data-ttu-id="bffad-187">ToCharArrayRankOne</span><span class="sxs-lookup"><span data-stu-id="bffad-187">ToCharArrayRankOne</span></span>|<span data-ttu-id="bffad-188">ToDate</span><span class="sxs-lookup"><span data-stu-id="bffad-188">ToDate</span></span>|<span data-ttu-id="bffad-189">Todecimal —</span><span class="sxs-lookup"><span data-stu-id="bffad-189">ToDecimal</span></span>|<span data-ttu-id="bffad-190">Todouble —</span><span class="sxs-lookup"><span data-stu-id="bffad-190">ToDouble</span></span>|  
|<span data-ttu-id="bffad-191">ToInteger</span><span class="sxs-lookup"><span data-stu-id="bffad-191">ToInteger</span></span>|<span data-ttu-id="bffad-192">ToUInteger</span><span class="sxs-lookup"><span data-stu-id="bffad-192">ToUInteger</span></span>|<span data-ttu-id="bffad-193">ToLong</span><span class="sxs-lookup"><span data-stu-id="bffad-193">ToLong</span></span>|<span data-ttu-id="bffad-194">ToULong</span><span class="sxs-lookup"><span data-stu-id="bffad-194">ToULong</span></span>|  
|<span data-ttu-id="bffad-195">ToShort</span><span class="sxs-lookup"><span data-stu-id="bffad-195">ToShort</span></span>|<span data-ttu-id="bffad-196">ToUShort</span><span class="sxs-lookup"><span data-stu-id="bffad-196">ToUShort</span></span>|<span data-ttu-id="bffad-197">Tosingle —</span><span class="sxs-lookup"><span data-stu-id="bffad-197">ToSingle</span></span>|<span data-ttu-id="bffad-198">ToString</span><span class="sxs-lookup"><span data-stu-id="bffad-198">ToString</span></span>|  
  
## <a name="inheritance-support"></a><span data-ttu-id="bffad-199">Obsługa dziedziczenia</span><span class="sxs-lookup"><span data-stu-id="bffad-199">Inheritance Support</span></span>  
  
### <a name="inheritance-mapping-restrictions"></a><span data-ttu-id="bffad-200">Ograniczenia dotyczące mapowania dziedziczenia</span><span class="sxs-lookup"><span data-stu-id="bffad-200">Inheritance Mapping Restrictions</span></span>  
 <span data-ttu-id="bffad-201">Aby uzyskać więcej informacji, zobacz [porady: hierarchii dziedziczenia mapy](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="bffad-201">For more information, see [How to: Map Inheritance Hierarchies](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span></span>  
  
### <a name="inheritance-in-queries"></a><span data-ttu-id="bffad-202">Dziedziczenie w zapytaniach</span><span class="sxs-lookup"><span data-stu-id="bffad-202">Inheritance in Queries</span></span>  
 <span data-ttu-id="bffad-203">C# rzutowania są obsługiwane tylko w projekcji.</span><span class="sxs-lookup"><span data-stu-id="bffad-203">C# casts are supported only in projection.</span></span> <span data-ttu-id="bffad-204">Rzutowania, które są używane w innym miejscu, nie są tłumaczone i są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="bffad-204">Casts that are used elsewhere are not translated and are ignored.</span></span> <span data-ttu-id="bffad-205">Jako uzupełnienie SQL funkcji nazwy, SQL naprawdę przeprowadza tylko operacje odpowiednikiem środowisko uruchomieniowe języka wspólnego (CLR) <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="bffad-205">Aside from SQL function names, SQL really only performs the equivalent of the common language runtime (CLR) <xref:System.Convert>.</span></span> <span data-ttu-id="bffad-206">Oznacza to, że SQL można zmienić wartości typu jeden do innego.</span><span class="sxs-lookup"><span data-stu-id="bffad-206">That is, SQL can change the value of one type to another.</span></span> <span data-ttu-id="bffad-207">Nie ma odpowiednika z rzutowania, ponieważ nie istnieje żadne koncepcji reinterpreting tej samej usługi bits, jak inny typ CLR.</span><span class="sxs-lookup"><span data-stu-id="bffad-207">There is no equivalent of CLR cast because there is no concept of reinterpreting the same bits as those of another type.</span></span> <span data-ttu-id="bffad-208">Właśnie dlatego C# rzutowania działa tylko lokalnie.</span><span class="sxs-lookup"><span data-stu-id="bffad-208">That is why a C# cast works only locally.</span></span> <span data-ttu-id="bffad-209">Nie jest on zdalny.</span><span class="sxs-lookup"><span data-stu-id="bffad-209">It is not remoted.</span></span>  
  
 <span data-ttu-id="bffad-210">Operatory, `is` i `as`i `GetType` — metoda nie są ograniczone do `Select` operatora.</span><span class="sxs-lookup"><span data-stu-id="bffad-210">The operators, `is` and `as`, and the `GetType` method are not restricted to the `Select` operator.</span></span> <span data-ttu-id="bffad-211">Ich użyciem w innych operatorów zapytań również.</span><span class="sxs-lookup"><span data-stu-id="bffad-211">They can be used in other query operators also.</span></span>  
  
## <a name="sql-server-2008-support"></a><span data-ttu-id="bffad-212">Obsługa programu SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="bffad-212">SQL Server 2008 Support</span></span>  
 <span data-ttu-id="bffad-213">LINQ do SQL w programie .NET Framework 3.5 z dodatkiem SP1, obsługuje mapowanie Nowa data i czas typy programu Microsoft SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="bffad-213">Starting with the .NET Framework 3.5 SP1, LINQ to SQL supports mapping to new date and time types introduced with SQL Server 2008.</span></span> <span data-ttu-id="bffad-214">Istnieją jednak pewne ograniczenia w składniku LINQ to SQL operatorów zapytań, używane podczas pracy z wartościami mapowane na te nowe typy.</span><span class="sxs-lookup"><span data-stu-id="bffad-214">But, there are some limitations to the LINQ to SQL query operators that you can use when operating against values mapped to these new types.</span></span>  
  
### <a name="unsupported-query-operators"></a><span data-ttu-id="bffad-215">Operatory kwerend nieobsługiwana</span><span class="sxs-lookup"><span data-stu-id="bffad-215">Unsupported Query Operators</span></span>  
 <span data-ttu-id="bffad-216">Następujące operatory zapytań nie są obsługiwane w wartości mapowane na nowe typy Data i godzina programu SQL Server: `DATETIME2`, `DATE`, `TIME`, i `DATETIMEOFFSET`.</span><span class="sxs-lookup"><span data-stu-id="bffad-216">The following query operators are not supported on values mapped to the new SQL Server date and time types: `DATETIME2`, `DATE`, `TIME`, and `DATETIMEOFFSET`.</span></span>  
  
-   `Aggregate`  
  
-   `Average`  
  
-   `LastOrDefault`  
  
-   `OfType`  
  
-   `Sum`  
  
 <span data-ttu-id="bffad-217">Aby uzyskać więcej informacji dotyczących mapowania do tych typów Data i godzina programu SQL Server, zobacz [mapowanie typu środowiska CLR SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="bffad-217">For more information about mapping to these SQL Server date and time types, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
## <a name="sql-server-2005-support"></a><span data-ttu-id="bffad-218">Obsługa programu SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="bffad-218">SQL Server 2005 Support</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bffad-219">nie obsługuje następujące funkcje programu SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="bffad-219"> does not support the following SQL Server 2005 features:</span></span>  
  
-   <span data-ttu-id="bffad-220">Procedury składowane napisane dla SQL CLR.</span><span class="sxs-lookup"><span data-stu-id="bffad-220">Stored procedures written for SQL CLR.</span></span>  
  
-   <span data-ttu-id="bffad-221">Typ zdefiniowany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bffad-221">User-defined type.</span></span>  
  
-   <span data-ttu-id="bffad-222">Funkcje zapytań języka XML.</span><span class="sxs-lookup"><span data-stu-id="bffad-222">XML query features.</span></span>  
  
## <a name="sql-server-2000-support"></a><span data-ttu-id="bffad-223">Obsługa programu SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="bffad-223">SQL Server 2000 Support</span></span>  
 <span data-ttu-id="bffad-224">Następujące [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] ograniczenia (w porównaniu do [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)]) mają wpływ na [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obsługuje.</span><span class="sxs-lookup"><span data-stu-id="bffad-224">The following [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] limitations (compared to [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)]) affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
### <a name="cross-apply-and-outer-apply-operators"></a><span data-ttu-id="bffad-225">Zastosuj Cross i zewnętrznych zastosować operatory</span><span class="sxs-lookup"><span data-stu-id="bffad-225">Cross Apply and Outer Apply Operators</span></span>  
 <span data-ttu-id="bffad-226">Operatory te nie są dostępne w [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffad-226">These operators are not available in [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bffad-227">próbuje szereg modyfikacji oprogramowania należy zastąpić odpowiednie sprzężenia.</span><span class="sxs-lookup"><span data-stu-id="bffad-227"> tries a series of rewrites to replace them with appropriate joins.</span></span>  
  
 <span data-ttu-id="bffad-228">`Cross Apply`i `Outer Apply` są generowane dla nawigacji relacji.</span><span class="sxs-lookup"><span data-stu-id="bffad-228">`Cross Apply` and `Outer Apply` are generated for relationship navigations.</span></span> <span data-ttu-id="bffad-229">Zbiór zapytań, dla których są możliwe takich modyfikacji oprogramowania nie jest dobrze zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="bffad-229">The set of queries for which such rewrites are possible is not well defined.</span></span> <span data-ttu-id="bffad-230">Z tego powodu minimalny zbiór zapytań, które jest obsługiwana w przypadku [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] zestaw nie jest związana z nawigacji relacji.</span><span class="sxs-lookup"><span data-stu-id="bffad-230">For this reason, the minimal set of queries that is supported for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] is the set that does not involve relationship navigation.</span></span>  
  
### <a name="text--ntext"></a><span data-ttu-id="bffad-231">tekst / ntext</span><span class="sxs-lookup"><span data-stu-id="bffad-231">text / ntext</span></span>  
 <span data-ttu-id="bffad-232">Typy danych `text`  /  `ntext` nie można używać w pewnych operacji zapytania względem `varchar(max)`  /  `nvarchar(max)`, które są obsługiwane przez [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffad-232">Data types `text` / `ntext` cannot be used in certain query operations against `varchar(max)` / `nvarchar(max)`, which are supported by [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)].</span></span>  
  
 <span data-ttu-id="bffad-233">Nie rozwiązanie jest dostępne dla tego ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="bffad-233">No resolution is available for this limitation.</span></span> <span data-ttu-id="bffad-234">W szczególności nie można użyć `Distinct()` na dowolny wynik, który zawiera elementy członkowskie, które są mapowane na `text` lub `ntext` kolumn.</span><span class="sxs-lookup"><span data-stu-id="bffad-234">Specifically, you cannot use `Distinct()` on any result that contains members that are mapped to `text` or `ntext` columns.</span></span>  
  
### <a name="behavior-triggered-by-nested-queries"></a><span data-ttu-id="bffad-235">Zachowanie wyzwalane przez zapytania zagnieżdżone</span><span class="sxs-lookup"><span data-stu-id="bffad-235">Behavior Triggered by Nested Queries</span></span>  
 [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]<span data-ttu-id="bffad-236">(za pośrednictwem SP4) integratora ma specyfikę wyzwalane przez zapytania zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="bffad-236"> (through SP4) binder has some idiosyncrasies that are triggered by nested queries.</span></span> <span data-ttu-id="bffad-237">Zestaw zapytania SQL, który uruchamia te idiosyncrasies nie jest dobrze zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="bffad-237">The set of SQL queries that triggers these idiosyncrasies is not well defined.</span></span> <span data-ttu-id="bffad-238">Z tego powodu nie można zdefiniować zestawu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapytania, które mogą spowodować wyjątków programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bffad-238">For this reason, you cannot define the set of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries that might cause SQL Server exceptions.</span></span>  
  
### <a name="skip-and-take-operators"></a><span data-ttu-id="bffad-239">SKIP i Take operatorów</span><span class="sxs-lookup"><span data-stu-id="bffad-239">Skip and Take Operators</span></span>  
 <span data-ttu-id="bffad-240"><xref:System.Linq.Enumerable.Take%2A>i <xref:System.Linq.Enumerable.Skip%2A> mają pewne ograniczenia, gdy są one używane w zapytaniach przed [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffad-240"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span></span> <span data-ttu-id="bffad-241">Aby uzyskać więcej informacji, zobacz wpis "Pomiń i podjąć wyjątków w programie SQL Server 2000" w [Rozwiązywanie problemów](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="bffad-241">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="object-materialization"></a><span data-ttu-id="bffad-242">Obiekt Materialization</span><span class="sxs-lookup"><span data-stu-id="bffad-242">Object Materialization</span></span>  
 <span data-ttu-id="bffad-243">Materialization tworzy obiekty CLR z wierszy zwracanych przez co najmniej jednego zapytania SQL.</span><span class="sxs-lookup"><span data-stu-id="bffad-243">Materialization creates CLR objects from rows that are returned by one or more SQL queries.</span></span>  
  
-   <span data-ttu-id="bffad-244">Następujące wywołania są *wykonywane lokalnie* jako część materialization:</span><span class="sxs-lookup"><span data-stu-id="bffad-244">The following calls are *executed locally* as a part of materialization:</span></span>  
  
    -   <span data-ttu-id="bffad-245">Konstruktorów</span><span class="sxs-lookup"><span data-stu-id="bffad-245">Constructors</span></span>  
  
    -   <span data-ttu-id="bffad-246">`ToString`metody w projekcji</span><span class="sxs-lookup"><span data-stu-id="bffad-246">`ToString` methods in projections</span></span>  
  
    -   <span data-ttu-id="bffad-247">Rzutowania typów w projekcji</span><span class="sxs-lookup"><span data-stu-id="bffad-247">Type casts in projections</span></span>  
  
-   <span data-ttu-id="bffad-248">Metody, które należy wykonać <xref:System.Linq.Enumerable.AsEnumerable%2A> metody są *wykonywane lokalnie*.</span><span class="sxs-lookup"><span data-stu-id="bffad-248">Methods that follow the <xref:System.Linq.Enumerable.AsEnumerable%2A> method are *executed locally*.</span></span> <span data-ttu-id="bffad-249">Ta metoda nie powoduje natychmiastowego wykonania.</span><span class="sxs-lookup"><span data-stu-id="bffad-249">This method does not cause immediate execution.</span></span>  
  
-   <span data-ttu-id="bffad-250">Można użyć `struct` jako zwracany typ wyniku zapytania lub elementem członkowskim typu wyniku.</span><span class="sxs-lookup"><span data-stu-id="bffad-250">You can use a `struct` as the return type of a query result or as a member of the result type.</span></span> <span data-ttu-id="bffad-251">Jednostek muszą być klasy.</span><span class="sxs-lookup"><span data-stu-id="bffad-251">Entities are required to be classes.</span></span> <span data-ttu-id="bffad-252">Typy anonimowe są zmaterializowany jako wystąpień klasy, ale nazwanego struktur (z systemem innym niż jednostek) może być używana w projekcji.</span><span class="sxs-lookup"><span data-stu-id="bffad-252">Anonymous types are materialized as class instances, but named structs (non-entities) can be used in projection.</span></span>  
  
-   <span data-ttu-id="bffad-253">Członek zwracany typ wyniku zapytania mogą być typu <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="bffad-253">A member of the return type of a query result can be of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="bffad-254">Jest on zmaterializowany jako kolekcja lokalna.</span><span class="sxs-lookup"><span data-stu-id="bffad-254">It is materialized as a local collection.</span></span>  
  
-   <span data-ttu-id="bffad-255">Następujące metody powodują *materialization natychmiastowego* sekwencji, które metody są stosowane do:</span><span class="sxs-lookup"><span data-stu-id="bffad-255">The following methods cause the *immediate materialization* of the sequence that the methods are applied to:</span></span>  
  
    -   <xref:System.Linq.Enumerable.ToList%2A>  
  
    -   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
    -   <xref:System.Linq.Enumerable.ToArray%2A>  
  
## <a name="see-also"></a><span data-ttu-id="bffad-256">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bffad-256">See Also</span></span>  
 [<span data-ttu-id="bffad-257">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="bffad-257">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="bffad-258">Zwracanym lub Pomiń elementy w sekwencji</span><span class="sxs-lookup"><span data-stu-id="bffad-258">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 [<span data-ttu-id="bffad-259">Łączenie dwóch sekwencji</span><span class="sxs-lookup"><span data-stu-id="bffad-259">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 [<span data-ttu-id="bffad-260">Zwraca różnicy pomiędzy dwoma sekwencji</span><span class="sxs-lookup"><span data-stu-id="bffad-260">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 [<span data-ttu-id="bffad-261">Zwraca część wspólną dwóch sekwencji zestawu</span><span class="sxs-lookup"><span data-stu-id="bffad-261">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 [<span data-ttu-id="bffad-262">Zwraca złożenie dwóch sekwencji zestawu</span><span class="sxs-lookup"><span data-stu-id="bffad-262">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)