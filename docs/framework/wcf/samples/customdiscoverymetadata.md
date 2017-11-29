---
title: CustomDiscoveryMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5b3272b642a04821d8343cae776e48f90d266cfe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="customdiscoverymetadata"></a><span data-ttu-id="707d4-102">CustomDiscoveryMetadata</span><span class="sxs-lookup"><span data-stu-id="707d4-102">CustomDiscoveryMetadata</span></span>
<span data-ttu-id="707d4-103">W tym przykładzie pokazano, jak można wstawić niestandardowych metadanych XML do odnajdowania metadanych dla punktu końcowego wykrywalny udostępnianych przez usługę.</span><span class="sxs-lookup"><span data-stu-id="707d4-103">This sample shows how to insert custom XML metadata into the discovery metadata for a discoverable endpoint exposed by a service.</span></span> <span data-ttu-id="707d4-104">Przykładowe następnie przedstawiono, jak wyszukać usługę klienta i wyodrębnić te niestandardowe dane.</span><span class="sxs-lookup"><span data-stu-id="707d4-104">The sample then shows how a client can search for the service and extract this custom data.</span></span> <span data-ttu-id="707d4-105">W tym przykładzie składa się z dwóch projektów, usług i klientów.</span><span class="sxs-lookup"><span data-stu-id="707d4-105">This sample consists of two projects, service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="707d4-106">Usługa</span><span class="sxs-lookup"><span data-stu-id="707d4-106">Service</span></span>  
 <span data-ttu-id="707d4-107">W `main` metody próbki wskazuje, że obiekt typu <xref:System.Xml.Linq.XElement> jest wypełniana wymagane pola i jest dodawany do <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="707d4-107">In the `main` method, the sample shows that an object of type <xref:System.Xml.Linq.XElement> is populated with the desired fields and is added to the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span></span> <span data-ttu-id="707d4-108">To <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> jest dodawany do danego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="707d4-108">This <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> is added to a particular endpoint.</span></span> <span data-ttu-id="707d4-109">Gdy tego punktu końcowego zostanie wykryta, metadane odnajdywania zawiera niestandardowych danych, które zostały dodane w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="707d4-109">When that particular endpoint is discovered, the discovery metadata contains the custom data that was added here.</span></span>  
  
## <a name="client"></a><span data-ttu-id="707d4-110">Klient</span><span class="sxs-lookup"><span data-stu-id="707d4-110">Client</span></span>  
 <span data-ttu-id="707d4-111">Pokazuje przykładowe <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> wywołana metoda <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span><span class="sxs-lookup"><span data-stu-id="707d4-111">The sample shows the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method being called on a <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span></span> <span data-ttu-id="707d4-112">Powstałe w ten sposób <xref:System.ServiceModel.Discovery.FindResponse> następnie zostanie zapytany o odpowiednie i oczekiwanych elementów XML.</span><span class="sxs-lookup"><span data-stu-id="707d4-112">The resulting <xref:System.ServiceModel.Discovery.FindResponse> is then queried for the appropriate and expected XML elements.</span></span> <span data-ttu-id="707d4-113">Te elementy są następnie podane w konsoli.</span><span class="sxs-lookup"><span data-stu-id="707d4-113">These elements are then printed to the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="707d4-114">Aby użyć tego przykładu</span><span class="sxs-lookup"><span data-stu-id="707d4-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="707d4-115">Załadowanie projektu rozwiązania w [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] i skompilować projekt.</span><span class="sxs-lookup"><span data-stu-id="707d4-115">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="707d4-116">Najpierw uruchomić aplikację usługi, generowane w \service\bin\debug [katalogu podstawowego rozwiązania], a następnie uruchomić aplikacji klienckiej, generowane w \Client\bin\debug [katalogu podstawowego rozwiązania]</span><span class="sxs-lookup"><span data-stu-id="707d4-116">First run the Service application, generated in [solution base directory]\service\bin\debug, and then run the Client application, generated in [solution base directory]\Client\bin\debug</span></span>  
  
3.  <span data-ttu-id="707d4-117">Należy pamiętać, że usługa jest dostępna online klienta lokalizuje usługę i wyświetla metadane opublikowany w punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="707d4-117">Note that the service comes online, the client locates the service and prints the metadata published in the endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="707d4-118">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="707d4-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="707d4-119">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="707d4-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="707d4-120">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="707d4-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="707d4-121">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="707d4-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a><span data-ttu-id="707d4-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="707d4-122">See Also</span></span>