---
title: "Instrukcje: Tworzenie podstawowego źródła danych Atom"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6e0cacc1-9b11-4665-adb7-577a62626fd6
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d395e286bb42cb8533f7a8d62a8fdd68fd2b9204
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-basic-atom-feed"></a><span data-ttu-id="6fcca-102">Instrukcje: Tworzenie podstawowego źródła danych Atom</span><span class="sxs-lookup"><span data-stu-id="6fcca-102">How to: Create a Basic Atom Feed</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="6fcca-103">Służy do tworzenia usługi, który ujawnia zespolonego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="6fcca-103"> allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="6fcca-104">W tym temacie omówiono sposób tworzenia usługi zespolonego, który ujawnia źródła zespolonego Atom.</span><span class="sxs-lookup"><span data-stu-id="6fcca-104">This topic discusses how to create a syndication service that exposes an Atom syndication feed.</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="6fcca-105">Aby utworzyć usługę zespolonego podstawowe</span><span class="sxs-lookup"><span data-stu-id="6fcca-105">To create a basic syndication service</span></span>  
  
1.  <span data-ttu-id="6fcca-106">Definiowanie kontraktu usługi przy użyciu interfejsu oznaczony atrybutem <xref:System.ServiceModel.Web.WebGetAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="6fcca-106">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="6fcca-107">Każda operacja uwidocznioną jak zespolonego źródła powinna zwrócić <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> obiektu.</span><span class="sxs-lookup"><span data-stu-id="6fcca-107">Each operation that is exposed as a syndication feed should return a <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> object.</span></span>  
  
     [!code-csharp[htAtomBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#0)]
     [!code-vb[htAtomBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="6fcca-108">Wszystkie operacje usługi, które są stosowane <xref:System.ServiceModel.Web.WebGetAttribute> są mapowane na żądania HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="6fcca-108">All service operations that apply the <xref:System.ServiceModel.Web.WebGetAttribute> are mapped to HTTP GET requests.</span></span> <span data-ttu-id="6fcca-109">Aby mapować operację na innej metody HTTP, należy użyć <xref:System.ServiceModel.Web.WebInvokeAttribute> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="6fcca-109">To map your operation to a different HTTP method, use the <xref:System.ServiceModel.Web.WebInvokeAttribute> instead.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="6fcca-110">[Porady: Tworzenie usługi HTTP sieci Web WCF podstawowe](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).</span><span class="sxs-lookup"><span data-stu-id="6fcca-110"> [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).</span></span>  
  
2.  <span data-ttu-id="6fcca-111">Implementowanie kontraktu usługi.</span><span class="sxs-lookup"><span data-stu-id="6fcca-111">Implement the service contract.</span></span>  
  
     [!code-csharp[htAtomBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#1)]
     [!code-vb[htAtomBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#1)]  
  
3.  <span data-ttu-id="6fcca-112">Utwórz <xref:System.ServiceModel.Syndication.SyndicationFeed> obiektu i dodać autora, kategoria i opis.</span><span class="sxs-lookup"><span data-stu-id="6fcca-112">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htAtomBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#2)]
     [!code-vb[htAtomBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#2)]  
  
4.  <span data-ttu-id="6fcca-113">Utwórz kilka <xref:System.ServiceModel.Syndication.SyndicationItem> obiektów.</span><span class="sxs-lookup"><span data-stu-id="6fcca-113">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htAtomBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#3)]
     [!code-vb[htAtomBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#3)]  
  
5.  <span data-ttu-id="6fcca-114">Dodaj <xref:System.ServiceModel.Syndication.SyndicationItem> obiektów do źródła danych.</span><span class="sxs-lookup"><span data-stu-id="6fcca-114">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> objects to the feed.</span></span>  
  
     [!code-csharp[htAtomBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#4)]
     [!code-vb[htAtomBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#4)]  
  
6.  <span data-ttu-id="6fcca-115">Zwróć kanału informacyjnego.</span><span class="sxs-lookup"><span data-stu-id="6fcca-115">Return the feed.</span></span>  
  
     [!code-csharp[htAtomBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#5)]
     [!code-vb[htAtomBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="6fcca-116">Do obsługi usługi</span><span class="sxs-lookup"><span data-stu-id="6fcca-116">To host the service</span></span>  
  
1.  <span data-ttu-id="6fcca-117">Utwórz <xref:System.ServiceModel.Web.WebServiceHost> obiektu.</span><span class="sxs-lookup"><span data-stu-id="6fcca-117">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>  
  
     [!code-csharp[htAtomBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#6)]
     [!code-vb[htAtomBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#6)]  
  
2.  <span data-ttu-id="6fcca-118">Otworzyć hosta usługi, załadować źródła strumieniowego z usługi, Wyświetl źródło i poczekaj, aż użytkownikowi naciśnij klawisz ENTER.</span><span class="sxs-lookup"><span data-stu-id="6fcca-118">Open the service host, load the feed from the service, display the feed, and wait for the user to press ENTER.</span></span>  
  
     [!code-csharp[htAtomBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#8)]
     [!code-vb[htAtomBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="6fcca-119">Aby wywołać GetBlog() z HTTP GET</span><span class="sxs-lookup"><span data-stu-id="6fcca-119">To call GetBlog() with an HTTP GET</span></span>  
  
1.  <span data-ttu-id="6fcca-120">Otwórz program Internet Explorer, wpisz następujący adres URL, a następnie naciśnij klawisz ENTER: http://localhost: 8000/BlogService/GetBlog</span><span class="sxs-lookup"><span data-stu-id="6fcca-120">Open Internet Explorer, type the following URL, and press ENTER: http://localhost:8000/BlogService/GetBlog</span></span>  
  
     <span data-ttu-id="6fcca-121">Adres URL zawiera adres podstawowy usługi (http://localhost: 8000/BlogService), względny adres punktu końcowego i do wywołania operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="6fcca-121">The URL contains the base address of the service (http://localhost:8000/BlogService), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="6fcca-122">Aby wywołać GetBlog() z kodu</span><span class="sxs-lookup"><span data-stu-id="6fcca-122">To call GetBlog() from code</span></span>  
  
1.  <span data-ttu-id="6fcca-123">Utwórz <xref:System.Xml.XmlReader> z adresu podstawowego i wywoływania metody.</span><span class="sxs-lookup"><span data-stu-id="6fcca-123">Create a <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htAtomBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#9)]
     [!code-vb[htAtomBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#9)]  
  
2.  <span data-ttu-id="6fcca-124">Wywołaj statycznych <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> metody, przekazując <xref:System.Xml.XmlReader> właśnie utworzony.</span><span class="sxs-lookup"><span data-stu-id="6fcca-124">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htAtomBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#10)]
     [!code-vb[htAtomBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#10)]  
  
     <span data-ttu-id="6fcca-125">To wywołanie operacji usługi i wypełnia nowy <xref:System.ServiceModel.Syndication.SyndicationFeed> z elementem formatującym zwrócony przez operację usługi.</span><span class="sxs-lookup"><span data-stu-id="6fcca-125">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3.  <span data-ttu-id="6fcca-126">Dostęp do źródła strumieniowego obiektu.</span><span class="sxs-lookup"><span data-stu-id="6fcca-126">Access the feed object.</span></span>  
  
     [!code-csharp[htAtomBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#11)]
     [!code-vb[htAtomBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="6fcca-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="6fcca-127">Example</span></span>  
 <span data-ttu-id="6fcca-128">Poniżej znajduje się pełna listy w tym przykładzie kodu.</span><span class="sxs-lookup"><span data-stu-id="6fcca-128">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htAtomBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#12)]
 [!code-vb[htAtomBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6fcca-129">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="6fcca-129">Compiling the Code</span></span>  
 <span data-ttu-id="6fcca-130">W przypadku kompilowania kodu poprzedni kod, odniesienia System.ServiceModel.dll i System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="6fcca-130">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fcca-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6fcca-131">See Also</span></span>  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>