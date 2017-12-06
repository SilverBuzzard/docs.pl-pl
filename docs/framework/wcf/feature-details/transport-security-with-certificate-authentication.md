---
title: "Zabezpieczanie transportu przy użyciu uwierzytelniania certyfikatów"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
caps.latest.revision: "20"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: abff650bd7c0e613524e4903cc754b7ff4200328
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="transport-security-with-certificate-authentication"></a><span data-ttu-id="91359-102">Zabezpieczanie transportu przy użyciu uwierzytelniania certyfikatów</span><span class="sxs-lookup"><span data-stu-id="91359-102">Transport Security with Certificate Authentication</span></span>
<span data-ttu-id="91359-103">W tym temacie omówiono przy użyciu certyfikatów X.509 do uwierzytelniania klienta i serwera, korzystając z zabezpieczeń transportu.</span><span class="sxs-lookup"><span data-stu-id="91359-103">This topic discusses using X.509 certificates for server and client authentication when using transport security.</span></span> <span data-ttu-id="91359-104">Aby uzyskać więcej informacji na temat X.509 Zobacz certyfikaty [certyfikatów kluczy publicznych X.509](http://msdn.microsoft.com/library/bb540819\(VS.85\).aspx).</span><span class="sxs-lookup"><span data-stu-id="91359-104">For more information about X.509 certificates see [X.509 Public Key Certificates](http://msdn.microsoft.com/library/bb540819\(VS.85\).aspx).</span></span> <span data-ttu-id="91359-105">Certyfikaty muszą być wystawiane przez urząd certyfikacji, który jest często wystawcy certyfikatów innych firm.</span><span class="sxs-lookup"><span data-stu-id="91359-105">Certificates must be issued by a certification authority, which is often a third-party issuer of certificates.</span></span> <span data-ttu-id="91359-106">W domenie systemu Windows Server usługi certyfikatów Active Directory może służyć do wystawiania certyfikatów dla komputerów klienckich w domenie.</span><span class="sxs-lookup"><span data-stu-id="91359-106">On a Windows Server domain, Active Directory Certificate Services can be used to issue certificates to client computers on the domain.</span></span> <span data-ttu-id="91359-107">Aby uzyskać więcej informacji, zobacz [usług certyfikatów systemu Windows 2008 R2](http://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="91359-107">For more information see [Windows 2008 R2 Certificate Services](http://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409).</span></span> <span data-ttu-id="91359-108">W tym scenariuszu usługi jest obsługiwane w obszarze Internet usługi informacyjne (IIS), której skonfigurowano protokołem SSL Secure Sockets Layer ().</span><span class="sxs-lookup"><span data-stu-id="91359-108">In this scenario, the service is hosted under Internet Information Services (IIS) which is configured with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="91359-109">Usługa jest skonfigurowana z certyfikatem SSL (X.509), aby umożliwić klientom zweryfikowanie tożsamości serwera.</span><span class="sxs-lookup"><span data-stu-id="91359-109">The service is configured with an SSL (X.509) certificate to allow clients to verify the identity of the server.</span></span> <span data-ttu-id="91359-110">Klient jest konfigurowane również certyfikatu X.509, który umożliwia usłudze do weryfikacji tożsamości klienta.</span><span class="sxs-lookup"><span data-stu-id="91359-110">The client is also configured with an X.509 certificate that allows the service to verify the identity of the client.</span></span> <span data-ttu-id="91359-111">Certyfikat serwera musi być uważany za zaufany przez klienta i certyfikat klienta musi być uważany za zaufany przez serwer.</span><span class="sxs-lookup"><span data-stu-id="91359-111">The server’s certificate must be trusted by the client and the client’s certificate must be trusted by the server.</span></span> <span data-ttu-id="91359-112">Rzeczywiste mechanika jak usługa i klient sprawdza tożsamość siebie nawzajem wykracza poza zakres tego tematu.</span><span class="sxs-lookup"><span data-stu-id="91359-112">The actual mechanics of how the service and client verifies each other’s identity is beyond the scope of this topic.</span></span> <span data-ttu-id="91359-113">Aby uzyskać więcej informacji, zobacz [podpisu cyfrowego w witrynie Wikipedia](http://go.microsoft.com/fwlink/?LinkId=253157).</span><span class="sxs-lookup"><span data-stu-id="91359-113">For more information see [Digital Signature on Wikipedia](http://go.microsoft.com/fwlink/?LinkId=253157).</span></span>  
  
 <span data-ttu-id="91359-114">W tym scenariuszu implementuje wzorzec komunikat żądania/odpowiedzi, jak pokazano na poniższym diagramie.</span><span class="sxs-lookup"><span data-stu-id="91359-114">This scenario implements a request/reply message pattern as illustrated by the following diagram.</span></span>  
  
 <span data-ttu-id="91359-115">![Bezpiecznego transferu za pomocą certyfikatów](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span><span class="sxs-lookup"><span data-stu-id="91359-115">![Secure transfer using certificates](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="91359-116">za pomocą certyfikatu usługi, zobacz [Praca z certyfikatami](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) i [porady: Konfigurowanie portu z certyfikatem SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="91359-116"> using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span> <span data-ttu-id="91359-117">W poniższej tabeli opisano różne charakterystyki scenariusza.</span><span class="sxs-lookup"><span data-stu-id="91359-117">The following table describes the various characteristics of the scenario.</span></span>  
  
|<span data-ttu-id="91359-118">Cechy</span><span class="sxs-lookup"><span data-stu-id="91359-118">Characteristic</span></span>|<span data-ttu-id="91359-119">Opis</span><span class="sxs-lookup"><span data-stu-id="91359-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="91359-120">Tryb zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="91359-120">Security Mode</span></span>|<span data-ttu-id="91359-121">Transportu</span><span class="sxs-lookup"><span data-stu-id="91359-121">Transport</span></span>|  
|<span data-ttu-id="91359-122">Współdziałanie</span><span class="sxs-lookup"><span data-stu-id="91359-122">Interoperability</span></span>|<span data-ttu-id="91359-123">Z istniejących klientów usługi sieci Web i usług.</span><span class="sxs-lookup"><span data-stu-id="91359-123">With existing Web service clients and services.</span></span>|  
|<span data-ttu-id="91359-124">Uwierzytelnianie (serwer)</span><span class="sxs-lookup"><span data-stu-id="91359-124">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="91359-125">Uwierzytelnianie (klient)</span><span class="sxs-lookup"><span data-stu-id="91359-125">Authentication (Client)</span></span>|<span data-ttu-id="91359-126">Tak (za pomocą certyfikatu SSL)</span><span class="sxs-lookup"><span data-stu-id="91359-126">Yes (using an SSL certificate)</span></span><br /><br /> <span data-ttu-id="91359-127">Tak (za pomocą certyfikatu X.509)</span><span class="sxs-lookup"><span data-stu-id="91359-127">Yes (using an X.509 certificate)</span></span>|  
|<span data-ttu-id="91359-128">Integralność danych</span><span class="sxs-lookup"><span data-stu-id="91359-128">Data Integrity</span></span>|<span data-ttu-id="91359-129">Tak</span><span class="sxs-lookup"><span data-stu-id="91359-129">Yes</span></span>|  
|<span data-ttu-id="91359-130">Poufność danych</span><span class="sxs-lookup"><span data-stu-id="91359-130">Data Confidentiality</span></span>|<span data-ttu-id="91359-131">Tak</span><span class="sxs-lookup"><span data-stu-id="91359-131">Yes</span></span>|  
|<span data-ttu-id="91359-132">Transportu</span><span class="sxs-lookup"><span data-stu-id="91359-132">Transport</span></span>|<span data-ttu-id="91359-133">HTTPS</span><span class="sxs-lookup"><span data-stu-id="91359-133">HTTPS</span></span>|  
|<span data-ttu-id="91359-134">Powiązanie</span><span class="sxs-lookup"><span data-stu-id="91359-134">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a><span data-ttu-id="91359-135">Skonfiguruj usługę</span><span class="sxs-lookup"><span data-stu-id="91359-135">Configure the Service</span></span>  
 <span data-ttu-id="91359-136">Ponieważ usługę w tym scenariuszu jest obsługiwany w środowisku usług IIS, jest on skonfigurowany z pliku web.config.</span><span class="sxs-lookup"><span data-stu-id="91359-136">Since the service in this scenario is hosted under IIS, it is configured with a web.config file.</span></span> <span data-ttu-id="91359-137">Następujący plik web.config przedstawiono sposób konfigurowania <xref:System.ServiceModel.WSHttpBinding> Aby użyć zabezpieczeń transportu i poświadczeń klienta X.509.</span><span class="sxs-lookup"><span data-stu-id="91359-137">The following web.config shows how to configure the <xref:System.ServiceModel.WSHttpBinding> to use transport security and X.509 client credentials.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>              
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>            
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a><span data-ttu-id="91359-138">Konfigurowanie klienta</span><span class="sxs-lookup"><span data-stu-id="91359-138">Configure the Client</span></span>  
 <span data-ttu-id="91359-139">Klienta można skonfigurować w kodzie, lub w pliku app.config.</span><span class="sxs-lookup"><span data-stu-id="91359-139">The client can be configured in code or in an app.config file.</span></span> <span data-ttu-id="91359-140">Poniższy przykład pokazuje, jak skonfigurować klienta w kodzie.</span><span class="sxs-lookup"><span data-stu-id="91359-140">The following example shows how to configure the client in code.</span></span>  
  
```vb  
// Create the binding.  
WSHttpBinding myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name   
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.   
EndpointAddress ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator   
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
CalculatorClient cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 <span data-ttu-id="91359-141">Klient może również skonfigurować w pliku App.config, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="91359-141">Alternatively you can configure the client in an App.config file as shown in the following example:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "   
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="Binding1"   
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="91359-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="91359-142">See Also</span></span>  
 [<span data-ttu-id="91359-143">Przegląd zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="91359-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="91359-144">Model zabezpieczeń systemu Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="91359-144">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)