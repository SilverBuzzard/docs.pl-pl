---
title: "Porady: Przechwytywanie danych usługi wiadomości (usługi danych WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6c18664eaa154fbc048c77cb359d0926f04b7e52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="8ab67-102">Porady: Przechwytywanie danych usługi wiadomości (usługi danych WCF)</span><span class="sxs-lookup"><span data-stu-id="8ab67-102">How to: Intercept Data Service Messages (WCF Data Services)</span></span>
<span data-ttu-id="8ab67-103">Z [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], mogą przechwycić komunikaty żądania, aby mogli dodawać niestandardowej logiki do operacji.</span><span class="sxs-lookup"><span data-stu-id="8ab67-103">With [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="8ab67-104">Do przechwycenia wiadomości, używasz metody oparte na atrybutach specjalnie w usłudze danych.</span><span class="sxs-lookup"><span data-stu-id="8ab67-104">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="8ab67-105">Aby uzyskać więcej informacji, zobacz [Interceptory](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8ab67-105">For more information, see [Interceptors](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="8ab67-106">W przykładzie w tym temacie użyto usługę Northwind przykładowych danych.</span><span class="sxs-lookup"><span data-stu-id="8ab67-106">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="8ab67-107">Ta usługa jest utworzone po zakończeniu [szybkiego startu usługi danych WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8ab67-107">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="8ab67-108">Aby zdefiniować interceptor zapytań wymaga dla zestawu jednostek zlecenia</span><span class="sxs-lookup"><span data-stu-id="8ab67-108">To define a query interceptor for the Orders entity set</span></span>  
  
1.  <span data-ttu-id="8ab67-109">W projekcie usługi danych Northwind Otwórz plik Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="8ab67-109">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="8ab67-110">Na stronie kodu `Northwind` klasy, Dodaj następujący `using` instrukcji (`Imports` w języku Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="8ab67-110">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3.  <span data-ttu-id="8ab67-111">W `Northwind` klasy, zdefiniuj metody operację usługi o nazwie `OnQueryOrders` w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8ab67-111">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="8ab67-112">Aby zdefiniować interceptora zmian, dla zestawu jednostek produktów</span><span class="sxs-lookup"><span data-stu-id="8ab67-112">To define a change interceptor for the Products entity set</span></span>  
  
1.  <span data-ttu-id="8ab67-113">W projekcie usługi danych Northwind Otwórz plik Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="8ab67-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="8ab67-114">W `Northwind` klasy, zdefiniuj metody operację usługi o nazwie `OnChangeProducts` w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8ab67-114">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="8ab67-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="8ab67-115">Example</span></span>  
 <span data-ttu-id="8ab67-116">W tym przykładzie definiuje metody interceptora zapytań dla `Orders` zestaw jednostek, który zwraca wartość wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="8ab67-116">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="8ab67-117">Wyrażenie nie zawiera delegata filtrujące żądany `Orders` oparte na powiązanych `Customers` zawierających nazwę określonego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="8ab67-117">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="8ab67-118">Nazwa z kolei jest określana na podstawie użytkownika żądającego.</span><span class="sxs-lookup"><span data-stu-id="8ab67-118">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="8ab67-119">W tym przykładzie przyjęto założenie, że usługa danych jest obsługiwana w aplikacji sieci Web ASP.NET, która używa usług WCF i czy jest włączone uwierzytelnianie.</span><span class="sxs-lookup"><span data-stu-id="8ab67-119">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="8ab67-120"><xref:System.Web.HttpContext> Klasa służy do pobierania zasady bieżącego żądania.</span><span class="sxs-lookup"><span data-stu-id="8ab67-120">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="8ab67-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="8ab67-121">Example</span></span>  
 <span data-ttu-id="8ab67-122">W tym przykładzie definiuje metodę interceptora zmian `Products` zestawu jednostek.</span><span class="sxs-lookup"><span data-stu-id="8ab67-122">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="8ab67-123">Ta metoda sprawdza dane wejściowe do usługi <xref:System.Data.Services.UpdateOperations.Add> lub <xref:System.Data.Services.UpdateOperations.Change> operacji i zgłasza wyjątek, jeśli wprowadzono zmiany, aby wycofane produktu.</span><span class="sxs-lookup"><span data-stu-id="8ab67-123">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="8ab67-124">Ponadto pozwala na blokowanie usunięcie produktów jako nieobsługiwanej operacji.</span><span class="sxs-lookup"><span data-stu-id="8ab67-124">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="8ab67-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8ab67-125">See Also</span></span>  
 [<span data-ttu-id="8ab67-126">Porady: Definiowanie operacji usługi</span><span class="sxs-lookup"><span data-stu-id="8ab67-126">How to: Define a Service Operation</span></span>](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)  
 [<span data-ttu-id="8ab67-127">Definiowanie usługi danych WCF</span><span class="sxs-lookup"><span data-stu-id="8ab67-127">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)