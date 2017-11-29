---
title: "Porady: kwerenda zwraca zagnieżdżonych kolekcji"
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
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f3aeb615dda2bdfbac192c06b9fb7d938abbda7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a><span data-ttu-id="96fca-102">Porady: kwerenda zwraca zagnieżdżonych kolekcji</span><span class="sxs-lookup"><span data-stu-id="96fca-102">How to: Execute a Query that Returns Nested Collections</span></span>
<span data-ttu-id="96fca-103">Oznacza to, jak uruchamiać polecenia względem modelu koncepcyjnego przy użyciu <xref:System.Data.EntityClient.EntityCommand> obiekt i jak można pobrać wyników zagnieżdżoną kolekcję przy użyciu <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="96fca-103">This shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the nested collection results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="96fca-104">Aby uruchomić kod w tym przykładzie</span><span class="sxs-lookup"><span data-stu-id="96fca-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="96fca-105">Dodaj [modelu sprzedaży AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) do projektu i konfigurowanie projektu do [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96fca-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="96fca-106">Aby uzyskać więcej informacji, zobacz [porady: Użyj Kreatora modelu danych jednostki](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="96fca-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="96fca-107">Na stronie kodu aplikacji, Dodaj następujący `using` instrukcje (`Imports` w języku Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="96fca-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="96fca-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="96fca-108">Example</span></span>  
 <span data-ttu-id="96fca-109">A *zagnieżdżone kolekcji* jest kolekcją, która znajduje się w innej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="96fca-109">A *nested collection* is a collection that is inside another collection.</span></span> <span data-ttu-id="96fca-110">Poniższy kod pobiera kolekcję `Contacts` i zagnieżdżonych kolekcji `SalesOrderHeaders` skojarzonych z poszczególnymi `Contact`.</span><span class="sxs-lookup"><span data-stu-id="96fca-110">The following code retrieves a collection of `Contacts` and the nested collections of `SalesOrderHeaders` that are associated with each `Contact`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="96fca-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96fca-111">See Also</span></span>  
 [<span data-ttu-id="96fca-112">Dostawca EntityClient Entity Framework</span><span class="sxs-lookup"><span data-stu-id="96fca-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)