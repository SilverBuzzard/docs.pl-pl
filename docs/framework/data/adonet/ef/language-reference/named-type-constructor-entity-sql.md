---
title: Konstruktor typu nazwanego (jednostka SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 72a19094beb03982448a102a4c7362a026d9e611
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="c5925-102">Konstruktor typu nazwanego (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="c5925-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="c5925-103">Używany do tworzenia wystąpień typów nominalnego modelu koncepcyjnego, takich jak jednostki lub typów złożonych.</span><span class="sxs-lookup"><span data-stu-id="c5925-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5925-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c5925-104">Syntax</span></span>  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="c5925-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="c5925-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="c5925-106">Wartość, która jest identyfikatorem prostej lub ujętego w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="c5925-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="c5925-107">Aby uzyskać więcej informacji, zobacz [identyfikatorów](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="c5925-107">For more information see, [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="c5925-108">Atrybuty typu, które są rozpatrywane w tej samej kolejności występującym w deklaracji typu.</span><span class="sxs-lookup"><span data-stu-id="c5925-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5925-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c5925-109">Return Value</span></span>  
 <span data-ttu-id="c5925-110">Wystąpienia nazwane typy złożone i typy jednostek.</span><span class="sxs-lookup"><span data-stu-id="c5925-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5925-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c5925-111">Remarks</span></span>  
 <span data-ttu-id="c5925-112">W poniższych przykładach pokazano, jak utworzyć nominalnego i złożone typy:</span><span class="sxs-lookup"><span data-stu-id="c5925-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="c5925-113">Poniższe wyrażenie tworzy wystąpienie `Person` typu:</span><span class="sxs-lookup"><span data-stu-id="c5925-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="c5925-114">Poniższe wyrażenie powoduje utworzenie wystąpienia typu złożonego:</span><span class="sxs-lookup"><span data-stu-id="c5925-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="c5925-115">Poniższe wyrażenie tworzy wystąpienie typu złożonego zagnieżdżone:</span><span class="sxs-lookup"><span data-stu-id="c5925-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="c5925-116">Poniższe wyrażenie tworzy wystąpienie obiektu z zagnieżdżony typ złożony:</span><span class="sxs-lookup"><span data-stu-id="c5925-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="c5925-117">Poniższy przykład pokazuje, jak zainicjować właściwość typu złożonego do wartości null:`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="c5925-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5925-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="c5925-118">Example</span></span>  
 <span data-ttu-id="c5925-119">Następujące zapytanie SQL jednostki używa konstruktora typu o nazwie do utworzenia wystąpienia typu modelu koncepcyjnego.</span><span class="sxs-lookup"><span data-stu-id="c5925-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="c5925-120">Kwerenda jest oparta na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c5925-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c5925-121">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="c5925-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c5925-122">Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c5925-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="c5925-123">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="c5925-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="c5925-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c5925-124">See Also</span></span>  
 [<span data-ttu-id="c5925-125">Konstruowanie typów</span><span class="sxs-lookup"><span data-stu-id="c5925-125">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="c5925-126">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="c5925-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)