---
title: 'Porady: pobieranie informacji jako tylko do odczytu'
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
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9a9765d8d8330c7ad2a6e8cb25166427cdd9414a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="a3f21-102">Porady: pobieranie informacji jako tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="a3f21-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="a3f21-103">Jeśli nie chcesz zmienić dane, można zwiększyć wydajność kwerend przez wyszukiwanie wyniki tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="a3f21-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="a3f21-104">Implementowanie przetwarzania tylko do odczytu, ustawiając <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> do `false`.</span><span class="sxs-lookup"><span data-stu-id="a3f21-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3f21-105">Gdy <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> ustawiono `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> niejawnie ustawiono `false`.</span><span class="sxs-lookup"><span data-stu-id="a3f21-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3f21-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="a3f21-106">Example</span></span>  
 <span data-ttu-id="a3f21-107">Poniższy kod pobiera kolekcji tylko do odczytu, dat pracownika.</span><span class="sxs-lookup"><span data-stu-id="a3f21-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a3f21-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a3f21-108">See Also</span></span>  
 [<span data-ttu-id="a3f21-109">Pojęcia dotyczące zapytań</span><span class="sxs-lookup"><span data-stu-id="a3f21-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="a3f21-110">Zapytanie bazy danych</span><span class="sxs-lookup"><span data-stu-id="a3f21-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [<span data-ttu-id="a3f21-111">Odroczone i ładowania bezpośredniego</span><span class="sxs-lookup"><span data-stu-id="a3f21-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)