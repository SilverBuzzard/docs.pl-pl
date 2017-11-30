---
title: ISTNIEJE (jednostka SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a8e483124205d986ad7a44b47815ed6aa2845744
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="exists-entity-sql"></a><span data-ttu-id="c4a62-102">ISTNIEJE (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="c4a62-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="c4a62-103">Określa, czy kolekcja jest pusta.</span><span class="sxs-lookup"><span data-stu-id="c4a62-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4a62-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c4a62-104">Syntax</span></span>  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4a62-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c4a62-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c4a62-106">Dowolne prawidłowe wyrażenie, które zwraca kolekcję.</span><span class="sxs-lookup"><span data-stu-id="c4a62-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="c4a62-107">NIE</span><span class="sxs-lookup"><span data-stu-id="c4a62-107">NOT</span></span>  
 <span data-ttu-id="c4a62-108">Określa, czy wynik EXISTS można zanegowane.</span><span class="sxs-lookup"><span data-stu-id="c4a62-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4a62-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c4a62-109">Return Value</span></span>  
 <span data-ttu-id="c4a62-110">`true`Jeśli kolekcja nie jest pusty; w przeciwnym razie `false`.</span><span class="sxs-lookup"><span data-stu-id="c4a62-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4a62-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c4a62-111">Remarks</span></span>  
 <span data-ttu-id="c4a62-112">EXISTS jest jednym z [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ustawić operatorów.</span><span class="sxs-lookup"><span data-stu-id="c4a62-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="c4a62-113">Wszystkie [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatory zestawów są oceniane od lewej do prawej.</span><span class="sxs-lookup"><span data-stu-id="c4a62-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="c4a62-114">Pierwszeństwo informacji dla [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorów, zobacz [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c4a62-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4a62-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="c4a62-115">Example</span></span>  
 <span data-ttu-id="c4a62-116">Następujące zapytanie SQL jednostki używa operatora EXISTS do określenia, czy kolekcja jest pusta.</span><span class="sxs-lookup"><span data-stu-id="c4a62-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="c4a62-117">Kwerenda jest oparta na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c4a62-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c4a62-118">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="c4a62-118">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c4a62-119">Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c4a62-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="c4a62-120">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="c4a62-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="c4a62-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c4a62-121">See Also</span></span>  
 [<span data-ttu-id="c4a62-122">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="c4a62-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)