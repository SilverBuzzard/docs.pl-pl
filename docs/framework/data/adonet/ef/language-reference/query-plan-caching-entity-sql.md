---
title: Plan zapytania buforowania (jednostka SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90b0c685-5ef2-461b-98b4-c3c0a2b253c7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 814b4451d5e08d5f9df4d370b2127d971f3fdd1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="query-plan-caching-entity-sql"></a><span data-ttu-id="edc03-102">Plan zapytania buforowania (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="edc03-102">Query Plan Caching (Entity SQL)</span></span>
<span data-ttu-id="edc03-103">Zawsze, gdy podejmowana jest próba mógł wykonać zapytania, potoku zapytanie wyszukuje pamięci podręcznej planu zapytania Czy dokładne kwerendy jest już skompilowane i dostępne.</span><span class="sxs-lookup"><span data-stu-id="edc03-103">Whenever an attempt to execute a query is made, the query pipeline looks up its query plan cache to see whether the exact query is already compiled and available.</span></span> <span data-ttu-id="edc03-104">Jeśli tak, używany jest buforowany plan zamiast tworzenia nowej.</span><span class="sxs-lookup"><span data-stu-id="edc03-104">If so, it reuses the cached plan rather than building a new one.</span></span> <span data-ttu-id="edc03-105">Jeśli dopasowanie nie zostanie znaleziony w pamięci podręcznej planu zapytania, zapytanie jest skompilowany i pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="edc03-105">If a match is not found in the query plan cache, the query is compiled and cached.</span></span> <span data-ttu-id="edc03-106">Zapytanie jest identyfikowany przez jego [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tekstu i parametru kolekcji (nazwy i typy).</span><span class="sxs-lookup"><span data-stu-id="edc03-106">A query is identified by its [!INCLUDE[esql](../../../../../../includes/esql-md.md)] text and parameter collection (names and types).</span></span> <span data-ttu-id="edc03-107">Wszystkie porównywania tekstu jest rozróżniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="edc03-107">All text comparisons are case-sensitive.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="edc03-108">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="edc03-108">Configuration</span></span>  
 <span data-ttu-id="edc03-109">Buforowanie plan zapytania jest konfigurowany za pomocą <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="edc03-109">Query plan caching is configurable through the <xref:System.Data.EntityClient.EntityCommand>.</span></span>  
  
 <span data-ttu-id="edc03-110">Aby włączyć lub wyłączyć zapytania planu buforowanie za pośrednictwem <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, ustawić tę właściwość na `true` lub `false`.</span><span class="sxs-lookup"><span data-stu-id="edc03-110">To enable or disable query plan caching through <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, set this property to `true` or `false`.</span></span> <span data-ttu-id="edc03-111">Wyłączenie buforowania planu dla poszczególnych zapytań dynamicznych, które prawdopodobnie nie można użyć więcej niż jeden raz — do poprawia wydajność.</span><span class="sxs-lookup"><span data-stu-id="edc03-111">Disabling plan caching for individual dynamic queries that are unlikely to be used more then once improves performance.</span></span>  
  
 <span data-ttu-id="edc03-112">Można włączyć zapytania planu buforowanie za pośrednictwem <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.</span><span class="sxs-lookup"><span data-stu-id="edc03-112">You can enable query plan caching through <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.</span></span>  
  
## <a name="recommended-practice"></a><span data-ttu-id="edc03-113">Zalecana praktyka</span><span class="sxs-lookup"><span data-stu-id="edc03-113">Recommended Practice</span></span>  
 <span data-ttu-id="edc03-114">Zapytania dynamiczne należy unikać, ogólnie.</span><span class="sxs-lookup"><span data-stu-id="edc03-114">Dynamic queries should be avoided, in general.</span></span> <span data-ttu-id="edc03-115">W poniższym przykładzie zapytanie dynamicznej jest narażony na ataki, z powodu danych wejściowych użytkownika bezpośrednio, bez żadnych sprawdzania poprawności.</span><span class="sxs-lookup"><span data-stu-id="edc03-115">The following dynamic query example is vulnerable to SQL injection attacks, because it takes user input directly without any validation.</span></span>  
  
 `"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp WHERE sp.EmployeeID = " + employeeTextBox.Text;`  
  
 <span data-ttu-id="edc03-116">Jeśli używasz dynamicznie generowanym zapytania, rozważ wyłączenie buforowanie planu zapytania, aby uniknąć zużycie pamięci niepotrzebne wpisy w pamięci podręcznej, które prawdopodobnie nie zostanie ponownie.</span><span class="sxs-lookup"><span data-stu-id="edc03-116">If you do use dynamically generated queries, consider disabling query plan caching to avoid unnecessary memory consumption for cache entries that are unlikely to be reused.</span></span>  
  
 <span data-ttu-id="edc03-117">Planu zapytania, buforowanie na zapytania statycznych i sparametryzowanych zapytań zapewniają korzyści wydajności.</span><span class="sxs-lookup"><span data-stu-id="edc03-117">Query plan caching on static queries and parameterized queries can provide performance benefits.</span></span> <span data-ttu-id="edc03-118">Poniżej przedstawiono przykład statyczne kwerendy:</span><span class="sxs-lookup"><span data-stu-id="edc03-118">The following is an example of a static query:</span></span>  
  
```  
"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp";  
```  
  
 <span data-ttu-id="edc03-119">Dla zapytania do dopasowania poprawnie przez pamięć podręczną planu zapytania one spełniać następujące wymagania:</span><span class="sxs-lookup"><span data-stu-id="edc03-119">For queries to be matched properly by the query plan cache, they should comply with the following requirements:</span></span>  
  
-   <span data-ttu-id="edc03-120">Tekst zapytania powinien być stałe wzorzec, najlepiej ciągiem stałym lub zasobu.</span><span class="sxs-lookup"><span data-stu-id="edc03-120">Query text should be a constant pattern, preferably a constant string or a resource.</span></span>  
  
-   <span data-ttu-id="edc03-121"><xref:System.Data.EntityClient.EntityParameter>lub <xref:System.Data.Objects.ObjectParameter> powinny być używane wszędzie tam, gdzie muszą być przekazywane wartości dostarczone przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="edc03-121"><xref:System.Data.EntityClient.EntityParameter> or <xref:System.Data.Objects.ObjectParameter> should be used wherever a user-supplied value must be passed.</span></span>  
  
 <span data-ttu-id="edc03-122">Należy unikać następujące wzorców zapytań, które niepotrzebnie zużywają miejsca w pamięci podręcznej planu zapytania:</span><span class="sxs-lookup"><span data-stu-id="edc03-122">You should avoid the following query patterns, which unnecessarily consume slots in the query plan cache:</span></span>  
  
-   <span data-ttu-id="edc03-123">Zmiany do rozróżniania wielkości liter w tekście.</span><span class="sxs-lookup"><span data-stu-id="edc03-123">Changes to letter case in the text.</span></span>  
  
-   <span data-ttu-id="edc03-124">Zmiany biały znak.</span><span class="sxs-lookup"><span data-stu-id="edc03-124">Changes to white space.</span></span>  
  
-   <span data-ttu-id="edc03-125">Zmiany w wartości literału.</span><span class="sxs-lookup"><span data-stu-id="edc03-125">Changes to literal values.</span></span>  
  
-   <span data-ttu-id="edc03-126">Zmiany tekstu wewnątrz komentarzy.</span><span class="sxs-lookup"><span data-stu-id="edc03-126">Changes to text inside comments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edc03-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="edc03-127">See Also</span></span>  
 [<span data-ttu-id="edc03-128">Omówienie SQL jednostki</span><span class="sxs-lookup"><span data-stu-id="edc03-128">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)