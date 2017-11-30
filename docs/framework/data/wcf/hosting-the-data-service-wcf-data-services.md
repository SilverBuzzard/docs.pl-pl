---
title: "Hosting usług danych (usługi danych WCF)"
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
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a11e7e499f705f4aace791320057e04205db58c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="hosting-the-data-service-wcf-data-services"></a><span data-ttu-id="ac60f-102">Hosting usług danych (usługi danych WCF)</span><span class="sxs-lookup"><span data-stu-id="ac60f-102">Hosting the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="ac60f-103">Za pomocą [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], można utworzyć usługi, która opisuje dane jako [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] źródła danych.</span><span class="sxs-lookup"><span data-stu-id="ac60f-103">By using [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you can create a service that exposes data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="ac60f-104">Ta usługa danych jest zdefiniowany jako klasa, która dziedziczy <xref:System.Data.Services.DataService%601>.</span><span class="sxs-lookup"><span data-stu-id="ac60f-104">This data service is defined as a class that inherits from <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="ac60f-105">Ta klasa udostępnia funkcje wymagane do przetwarzania komunikatów żądań, przeprowadzania aktualizacji w źródle danych oraz do generowania wiadomości odpowiedzi, co jest wymagane przez [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac60f-105">This class provides the functionality required to process request messages, perform updates against the data source, and generate responses messages, as required by [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span> <span data-ttu-id="ac60f-106">Jednak usługa danych nie można powiązać i nasłuchiwania gniazda sieci dla przychodzących żądań HTTP.</span><span class="sxs-lookup"><span data-stu-id="ac60f-106">However, a data service cannot bind to and listen on a network socket for incoming HTTP requests.</span></span> <span data-ttu-id="ac60f-107">Dla tej funkcji wymagane usługi danych zależy od składnika hostingu.</span><span class="sxs-lookup"><span data-stu-id="ac60f-107">For this required functionality, the data service relies on a hosting component.</span></span>  
  
 <span data-ttu-id="ac60f-108">Hosta usługi danych wykonuje następujące zadania w imieniu usług danych:</span><span class="sxs-lookup"><span data-stu-id="ac60f-108">The data service host performs the following tasks on behalf of the data service:</span></span>  
  
-   <span data-ttu-id="ac60f-109">Nasłuchuje żądań i kieruje te żądania do usługi danych.</span><span class="sxs-lookup"><span data-stu-id="ac60f-109">Listens for requests and routes these requests to the data service.</span></span>  
  
-   <span data-ttu-id="ac60f-110">Tworzy wystąpienie usługi danych dla każdego żądania.</span><span class="sxs-lookup"><span data-stu-id="ac60f-110">Creates an instance of the data service for each request.</span></span>  
  
-   <span data-ttu-id="ac60f-111">Żądania przez usługę danych procesów żądania przychodzącego.</span><span class="sxs-lookup"><span data-stu-id="ac60f-111">Requests that the data service process the incoming request.</span></span>  
  
-   <span data-ttu-id="ac60f-112">Wysyła odpowiedź w imieniu usług danych.</span><span class="sxs-lookup"><span data-stu-id="ac60f-112">Sends the response on behalf of the data service.</span></span>  
  
 <span data-ttu-id="ac60f-113">Aby uprościć hosting usług danych, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] został zaprojektowany do integrowania z usługi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ac60f-113">To simplify hosting a data service, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] is designed to integrate with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="ac60f-114">Usługi danych udostępnia domyślną implementację WCF, która służy jako hosta usługi danych w [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ac60f-114">The data service provides a default WCF implementation that serves as the data service host in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="ac60f-115">W związku z tym można hosta usługi danych w jednym z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="ac60f-115">Therefore, you can host a data service in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ac60f-116">W [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ac60f-116">In an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>  
  
-   <span data-ttu-id="ac60f-117">W zarządzanej aplikacji obsługującej usługi hostowania samoobsługowego WCF.</span><span class="sxs-lookup"><span data-stu-id="ac60f-117">In a managed application that supports self-hosted WCF services.</span></span>  
  
-   <span data-ttu-id="ac60f-118">W niektórych innych niestandardowych hosta usługi danych.</span><span class="sxs-lookup"><span data-stu-id="ac60f-118">In some other custom data service host.</span></span>  
  
## <a name="hosting-a-data-service-in-an-aspnet-application"></a><span data-ttu-id="ac60f-119">Hosting w aplikacji ASP.NET usługi danych</span><span class="sxs-lookup"><span data-stu-id="ac60f-119">Hosting a Data Service in an ASP.NET Application</span></span>  
 <span data-ttu-id="ac60f-120">Jeśli używasz **Dodaj nowy element** okna dialogowego w programie Visual Studio, aby zdefiniować usługę danych w aplikacji ASP.NET, narzędzie wygeneruje dwa nowe pliki w projekcie.</span><span class="sxs-lookup"><span data-stu-id="ac60f-120">When you use the **Add New Item** dialog in Visual Studio to define a data service in an ASP.NET application, the tool generates two new files in the project.</span></span> <span data-ttu-id="ac60f-121">Pierwszy plik ma `.svc` rozszerzenia i powoduje, że środowisko uruchomieniowe WCF sposobu utworzenia wystąpienia usługi danych.</span><span class="sxs-lookup"><span data-stu-id="ac60f-121">The first file has a `.svc` extension and instructs the WCF runtime how to instantiate the data service.</span></span> <span data-ttu-id="ac60f-122">Poniżej przedstawiono przykład tego pliku w usłudze danych Northwind próbki utworzone po zakończeniu [szybkiego startu](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):</span><span class="sxs-lookup"><span data-stu-id="ac60f-122">The following is an example of this file for the Northwind sample data service created when you complete the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):</span></span>  
  
```  
<%@ ServiceHost Language="C#"   
    Factory="System.Data.Services.DataServiceHostFactory,   
            System.Data.Services, Version=4.0.0.0,   
            Culture=neutral, PublicKeyToken=b77a5c561934e089"   
    Service="NorthwindService.Northwind" %>   
```  
  
 <span data-ttu-id="ac60f-123">Ta dyrektywa określa, że aplikacją w celu utworzenia hosta usługi danych o podanej nazwie klasy usługi za pomocą <xref:System.Data.Services.DataServiceHostFactory> klasy.</span><span class="sxs-lookup"><span data-stu-id="ac60f-123">This directive tells the application to create the service host for the named data service class by using the <xref:System.Data.Services.DataServiceHostFactory> class.</span></span>  
  
 <span data-ttu-id="ac60f-124">Na stronie CodeBehind `.svc` plik zawiera klasę, która jest implementacją usługi data, zdefiniowanego w następujący sposób dla usługi danych Northwind próbki:</span><span class="sxs-lookup"><span data-stu-id="ac60f-124">The code-behind page for the `.svc` file contains the class that is the implementation of the data service itself, which is defined as follows for the Northwind sample data service:</span></span>  
  
 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
 <span data-ttu-id="ac60f-125">Ponieważ usługa danych zachowuje się jak usługi WCF, Usługa danych integruje się z [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] i jest zgodna z modelem programowania sieci Web WCF.</span><span class="sxs-lookup"><span data-stu-id="ac60f-125">Because a data service behaves like a WCF service, the data service integrates with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] and follows the WCF Web programming model.</span></span> <span data-ttu-id="ac60f-126">Aby uzyskać więcej informacji, zobacz [usługi WCF i platformy ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) i [modelu programowania protokołu HTTP sieci Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="ac60f-126">For more information, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) and [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span></span>  
  
## <a name="self-hosted-wcf-services"></a><span data-ttu-id="ac60f-127">Usług hostowania samoobsługowego WCF</span><span class="sxs-lookup"><span data-stu-id="ac60f-127">Self-Hosted WCF Services</span></span>  
 <span data-ttu-id="ac60f-128">Ponieważ zawiera implementacji programu WCF [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] obsługuje hostingu samodzielnego usługi danych jako usługa WCF.</span><span class="sxs-lookup"><span data-stu-id="ac60f-128">Because it incorporates a WCF implementation, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] support self-hosting a data service as a WCF service.</span></span> <span data-ttu-id="ac60f-129">Usługa może być własnym hostowanej w żadnym [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplikacji, takich jak aplikacji konsoli.</span><span class="sxs-lookup"><span data-stu-id="ac60f-129">A service can be self-hosted in any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application, such as a console application.</span></span> <span data-ttu-id="ac60f-130"><xref:System.Data.Services.DataServiceHost> Klasy, która dziedziczy <xref:System.ServiceModel.Web.WebServiceHost>, jest używany do utworzenia wystąpienia usługi data pod określonym adresem.</span><span class="sxs-lookup"><span data-stu-id="ac60f-130">The <xref:System.Data.Services.DataServiceHost> class, which inherits from <xref:System.ServiceModel.Web.WebServiceHost>, is used to instantiate the data service at a specific address.</span></span>  
  
 <span data-ttu-id="ac60f-131">Hostingu samodzielnego może służyć do projektowania i testowania, ponieważ jego ułatwia wdrażanie i rozwiązywanie problemów z usługi.</span><span class="sxs-lookup"><span data-stu-id="ac60f-131">Self-hosting can be used for development and testing because it can make it easier to deploy and troubleshoot the service.</span></span> <span data-ttu-id="ac60f-132">Jednak tego rodzaju hosting nie zapewnia zaawansowane funkcje obsługi i zarządzania oferowane przez [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] lub przez Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="ac60f-132">However, this kind of hosting does not provide the advanced hosting and management features provided by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] or by Internet Information Services (IIS).</span></span> <span data-ttu-id="ac60f-133">Aby uzyskać więcej informacji, zobacz [Hosting w zarządzanej aplikacji](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="ac60f-133">For more information, see [Hosting in a Managed Application](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>  
  
## <a name="defining-a-custom-data-service-host"></a><span data-ttu-id="ac60f-134">Definiowanie hosta usługi danych niestandardowych</span><span class="sxs-lookup"><span data-stu-id="ac60f-134">Defining a Custom Data Service Host</span></span>  
 <span data-ttu-id="ac60f-135">W przypadkach, w którym implementacja hosta programu WCF jest zbyt restrykcyjna również możliwość definiowania niestandardowych hosta usługi danych.</span><span class="sxs-lookup"><span data-stu-id="ac60f-135">For cases where the WCF host implementation is too restrictive, you can also define a custom host for a data service.</span></span> <span data-ttu-id="ac60f-136">Każda klasa implementująca <xref:System.Data.Services.IDataServiceHost> interfejs może służyć jako hosta usługi danych.</span><span class="sxs-lookup"><span data-stu-id="ac60f-136">Any class that implements <xref:System.Data.Services.IDataServiceHost> interface can be used as the network host for a data service.</span></span> <span data-ttu-id="ac60f-137">Niestandardowy host musi implementować <xref:System.Data.Services.IDataServiceHost> interfejsu i mieć możliwość obsługi podstawowych obowiązków hosta usługi danych:</span><span class="sxs-lookup"><span data-stu-id="ac60f-137">A custom host must implement the <xref:System.Data.Services.IDataServiceHost> interface and be able to handle the following basic responsibilities of the data service host:</span></span>  
  
-   <span data-ttu-id="ac60f-138">Ścieżka katalogu głównego usługi udostępnić usługę danych.</span><span class="sxs-lookup"><span data-stu-id="ac60f-138">Provide the data service with the service root path.</span></span>  
  
-   <span data-ttu-id="ac60f-139">Przetworzyć informacji nagłówki żądań i odpowiedzi do odpowiedniego <xref:System.Data.Services.IDataServiceHost> implementacja elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="ac60f-139">Process request and response headers information to the appropriate <xref:System.Data.Services.IDataServiceHost> member implementation.</span></span>  
  
-   <span data-ttu-id="ac60f-140">Obsługa wyjątków zgłaszanych przez usługę danych.</span><span class="sxs-lookup"><span data-stu-id="ac60f-140">Handle exceptions raised by the data service.</span></span>  
  
-   <span data-ttu-id="ac60f-141">Sprawdź poprawność parametrów w ciągu zapytania.</span><span class="sxs-lookup"><span data-stu-id="ac60f-141">Validate parameters in the query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac60f-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac60f-142">See Also</span></span>  
 [<span data-ttu-id="ac60f-143">Definiowanie usługi danych WCF</span><span class="sxs-lookup"><span data-stu-id="ac60f-143">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [<span data-ttu-id="ac60f-144">Udostępnianie danych jako usługa</span><span class="sxs-lookup"><span data-stu-id="ac60f-144">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)  
 [<span data-ttu-id="ac60f-145">Konfigurowanie usługi danych</span><span class="sxs-lookup"><span data-stu-id="ac60f-145">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)