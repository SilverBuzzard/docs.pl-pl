---
title: Operacje kwantyfikatora (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9bc48c69179b1f8876efaa465295e94a9a0e0fb6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="40053-102">Operacje kwantyfikatora (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40053-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="40053-103">Operacje kwantyfikatora zwracać <xref:System.Boolean> wartość, która wskazuje, czy niektóre lub wszystkie elementy w sekwencji spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="40053-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="40053-104">Na poniższej ilustracji przedstawiono dwie operacje kwantyfikatora różnych na dwóch różnych źródeł sekwencji.</span><span class="sxs-lookup"><span data-stu-id="40053-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="40053-105">Pierwszą operacją zapyta, jeśli co najmniej jeden z elementów jest znak "A", a wynik jest `true`.</span><span class="sxs-lookup"><span data-stu-id="40053-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="40053-106">Druga operacja zapyta, czy wszystkie elementy są znaków "A", a wynik jest `true`.</span><span class="sxs-lookup"><span data-stu-id="40053-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="40053-107">![Operacje kwantyfikatora LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="40053-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="40053-108">Metody — operator standardowe zapytań, które wykonują operacje kwantyfikatora są wymienione w poniższej sekcji.</span><span class="sxs-lookup"><span data-stu-id="40053-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40053-109">Metody</span><span class="sxs-lookup"><span data-stu-id="40053-109">Methods</span></span>  
  
|<span data-ttu-id="40053-110">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="40053-110">Method Name</span></span>|<span data-ttu-id="40053-111">Opis</span><span class="sxs-lookup"><span data-stu-id="40053-111">Description</span></span>|<span data-ttu-id="40053-112">Składnia wyrażeń języka Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40053-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="40053-113">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="40053-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="40053-114">Wszystkie</span><span class="sxs-lookup"><span data-stu-id="40053-114">All</span></span>|<span data-ttu-id="40053-115">Określa, czy wszystkie elementy w sekwencji spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="40053-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="40053-116">wszystkie</span><span class="sxs-lookup"><span data-stu-id="40053-116">Any</span></span>|<span data-ttu-id="40053-117">Określa, czy wszystkie elementy w sekwencji spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="40053-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="40053-118">Zawiera</span><span class="sxs-lookup"><span data-stu-id="40053-118">Contains</span></span>|<span data-ttu-id="40053-119">Określa, czy sekwencja zawiera określony element.</span><span class="sxs-lookup"><span data-stu-id="40053-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="40053-120">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="40053-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="40053-121">Przykłady składni wyrażeń zapytania</span><span class="sxs-lookup"><span data-stu-id="40053-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="40053-122">Użyj tych przykładów `Aggregate` klauzuli w języku Visual Basic w ramach warunek filtrowania w zapytaniu składnika LINQ.</span><span class="sxs-lookup"><span data-stu-id="40053-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="40053-123">W poniższym przykładzie użyto `Aggregate` klauzuli i <xref:System.Linq.Enumerable.All%2A> — metoda rozszerzenia do zwrócenia z kolekcji osoby, których zwierząt domowych są wszystkie starsze niż określony okres ważności.</span><span class="sxs-lookup"><span data-stu-id="40053-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 <span data-ttu-id="40053-124">W następnym przykładzie użyto `Aggregate` klauzuli i <xref:System.Linq.Enumerable.Any%2A> — metoda rozszerzenia do zwrócenia z kolekcji tych osób, które mają co najmniej jeden domowe, która jest starsza niż określony okres ważności.</span><span class="sxs-lookup"><span data-stu-id="40053-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="40053-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="40053-125">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="40053-126">Operatory standardowe zapytań — omówienie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40053-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="40053-127">AGGREGATE — klauzula</span><span class="sxs-lookup"><span data-stu-id="40053-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="40053-128">Porady: zapytanie o zdania zawierające określony zestaw wyrazów (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40053-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)