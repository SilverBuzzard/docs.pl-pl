---
title: "Wprowadzenie — przykład"
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
helpviewer_keywords: basic samples [WCF], getting started
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
caps.latest.revision: "60"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a5ff6af234fabf278c84a3487b9f65217d84f6e4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2017
---
# <a name="getting-started-sample"></a><span data-ttu-id="e203d-102">Wprowadzenie — przykład</span><span class="sxs-lookup"><span data-stu-id="e203d-102">Getting Started Sample</span></span>
<span data-ttu-id="e203d-103">Uruchamianie przykładowych pokazano, jak do zaimplementowania typowych usługi i typowego klienta przy użyciu [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e203d-103">The Getting Started sample demonstrates how to implement a typical service and a typical client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="e203d-104">W tym przykładzie stanowi podstawę dla wszystkich innych przykładów podstawową technologię.</span><span class="sxs-lookup"><span data-stu-id="e203d-104">This sample is the basis for all other basic technology samples.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e203d-105">Procedury i kompilacji instrukcje dotyczące instalacji dla tego przykładu znajdują się na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="e203d-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e203d-106">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="e203d-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e203d-107">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="e203d-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e203d-108">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="e203d-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e203d-109">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="e203d-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\GettingStarted\GettingStarted`  
  
 <span data-ttu-id="e203d-110">Usługa zawiera opis operacji wykonywanych w kontrakcie usługi, który ujawnia on publicznie jak metadanych.</span><span class="sxs-lookup"><span data-stu-id="e203d-110">The service describes the operations it performs in a service contract that it exposes publicly as metadata.</span></span> <span data-ttu-id="e203d-111">Usługa zawiera również kod do wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="e203d-111">The service also contains the code to implement the operations.</span></span>  
  
 <span data-ttu-id="e203d-112">Klient zawiera definicję kontraktu usługi i klasy serwera proxy, aby uzyskać dostęp do usługi.</span><span class="sxs-lookup"><span data-stu-id="e203d-112">The client contains a definition of the service contract and a proxy class for accessing the service.</span></span> <span data-ttu-id="e203d-113">Kod serwera proxy jest generowany na podstawie przy użyciu metadanych usługi [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e203d-113">The proxy code is generated from the service metadata using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
 <span data-ttu-id="e203d-114">Na [!INCLUDE[wv](../../../../includes/wv-md.md)], usługa jest obsługiwana w Windows Activation Service (WAS).</span><span class="sxs-lookup"><span data-stu-id="e203d-114">On [!INCLUDE[wv](../../../../includes/wv-md.md)], the service is hosted in the Windows Activation Service (WAS).</span></span> <span data-ttu-id="e203d-115">Na [!INCLUDE[wxp](../../../../includes/wxp-md.md)] i [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], jest obsługiwany przez usługi Internet Information Services (IIS) i programu ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e203d-115">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], it is hosted by Internet Information Services (IIS) and ASP.NET.</span></span> <span data-ttu-id="e203d-116">Hosting w usługach IIS lub WAS umożliwia usłudze aktywowany automatycznie, gdy jest on dostępny po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="e203d-116">Hosting a service in IIS or WAS allows the service to be activated automatically when it is accessed for the first time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e203d-117">Jeśli chcesz rozpocząć pracę z przykładowym obsługującego usługę w aplikacji konsoli usług IIS, zobacz [hosta samodzielnego](../../../../docs/framework/wcf/samples/self-host.md) próbki.</span><span class="sxs-lookup"><span data-stu-id="e203d-117">If you would prefer to get started with a sample that hosts the service in a console application instead of IIS, see the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span>  
  
 <span data-ttu-id="e203d-118">Usługa i klient Określ szczegóły dotyczące dostępu w pliku ustawień konfiguracji, które zapewniają elastyczność w czasie wdrażania.</span><span class="sxs-lookup"><span data-stu-id="e203d-118">The service and client specify access details in configuration file settings, which provide flexibility at the time of deployment.</span></span> <span data-ttu-id="e203d-119">Dotyczy to również definicji punktu końcowego, który określa address, binding i contract.</span><span class="sxs-lookup"><span data-stu-id="e203d-119">This includes an endpoint definition that specifies an address, binding, and contract.</span></span> <span data-ttu-id="e203d-120">Powiązanie określa szczegóły transportu i zabezpieczeń dla jak usługa ma być dostępny.</span><span class="sxs-lookup"><span data-stu-id="e203d-120">The binding specifies transport and security details for how the service is to be accessed.</span></span>  
  
 <span data-ttu-id="e203d-121">Usługa konfiguruje zachowania w czasie wykonywania Publikowanie metadanych.</span><span class="sxs-lookup"><span data-stu-id="e203d-121">The service configures a run-time behavior to publish its metadata.</span></span>  
  
 <span data-ttu-id="e203d-122">Usługa implementuje kontrakt definiuje wzorzec komunikacji żądanie odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="e203d-122">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="e203d-123">Kontrakt jest definiowana za pomocą `ICalculator` interfejsu, który udostępnia operacji matematycznych (Dodawanie, odjąć mnożenia i dzielenia).</span><span class="sxs-lookup"><span data-stu-id="e203d-123">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="e203d-124">Klient wysyła żądania do operacji matematycznych danego i odpowiedzi usługi z wynikiem.</span><span class="sxs-lookup"><span data-stu-id="e203d-124">The client makes requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="e203d-125">Implementuje usługi `ICalculator` kontraktu, który jest zdefiniowany w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="e203d-125">The service implements an `ICalculator` contract that is defined in the following code.</span></span>  
  
```vb  
' Define a service contract.  
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>  
     Public Interface ICalculator  
        <OperationContract()>  
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()>  
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()>  
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()>  
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
    End Interface  
```  
  
```csharp  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="e203d-126">Implementacji usługi jest obliczana i zwraca odpowiednie wynik, jak pokazano w poniższym przykładzie kodzie.</span><span class="sxs-lookup"><span data-stu-id="e203d-126">The service implementation calculates and returns the appropriate result, as shown in the following example code.</span></span>  
  
```vb  
' Service class which implements the service contract.  
Public Class CalculatorService  
Implements ICalculator  
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add  
Return n1 + n2  
End Function  
  
Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract  
Return n1 - n2  
End Function  
  
Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply  
Return n1 * n2  
End Function  
  
Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide  
Return n1 / n2  
End Function  
End Class  
```  
  
```csharp  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
```  
  
 <span data-ttu-id="e203d-127">Usługa przedstawia punktu końcowego w celu komunikowania się z usługą, zdefiniowane przy użyciu pliku konfiguracji (Web.config), jak pokazano w poniższym Przykładowa konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="e203d-127">The service exposes an endpoint for communicating with the service, defined using a configuration file (Web.config), as shown in the following sample configuration.</span></span>  
  
```xaml  
<services>  
    <service   
        name="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- ICalculator is exposed at the base address provided by  
         host: http://localhost/servicemodelsamples/service.svc.  -->  
       <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
       ...  
    </service>  
</services>  
```  
  
 <span data-ttu-id="e203d-128">Usługa udostępnia punkt końcowy pod adresem podstawowa podał hosta usług IIS lub WAS.</span><span class="sxs-lookup"><span data-stu-id="e203d-128">The service exposes the endpoint at the base address provided by the IIS or WAS host.</span></span> <span data-ttu-id="e203d-129">Powiązanie jest skonfigurowane z normą <xref:System.ServiceModel.WSHttpBinding>, co umożliwia komunikacji HTTP i standardowe protokoły usług sieci Web adresowanie i zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="e203d-129">The binding is configured with a standard <xref:System.ServiceModel.WSHttpBinding>, which provides HTTP communication and standard Web service protocols for addressing and security.</span></span> <span data-ttu-id="e203d-130">Kontrakt jest `ICalculator` zaimplementowanych przez usługę.</span><span class="sxs-lookup"><span data-stu-id="e203d-130">The contract is the `ICalculator` implemented by the service.</span></span>  
  
 <span data-ttu-id="e203d-131">Zgodnie z konfiguracją, usługi są dostępne w http://localhost/servicemodelsamples/service.svc przez klienta na tym samym komputerze.</span><span class="sxs-lookup"><span data-stu-id="e203d-131">As configured, the service can be accessed at http://localhost/servicemodelsamples/service.svc by a client on the same computer.</span></span> <span data-ttu-id="e203d-132">W przypadku klientów dostępu zdalnego computersto usługi należy określić w pełni kwalifikowanej nazwy domeny zamiast nazwy localhost.</span><span class="sxs-lookup"><span data-stu-id="e203d-132">For clients on remote computersto access the service, a fully-qualified domain name must be specified instead of localhost.</span></span>  
  
 <span data-ttu-id="e203d-133">Domyślnie platformę nie ujawnia metadanych.</span><span class="sxs-lookup"><span data-stu-id="e203d-133">The framework does not expose metadata by default.</span></span> <span data-ttu-id="e203d-134">W efekcie usługa włącza <xref:System.ServiceModel.Description.ServiceMetadataBehavior> i udostępnia punktu końcowego (MEX) wymiany metadanych w http://localhost/servicemodelsamples/service.svc/mex.</span><span class="sxs-lookup"><span data-stu-id="e203d-134">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> and exposes a metadata exchange (MEX) endpoint at http://localhost/servicemodelsamples/service.svc/mex.</span></span> <span data-ttu-id="e203d-135">Następująca konfiguracja pokazano to.</span><span class="sxs-lookup"><span data-stu-id="e203d-135">The following configuration demonstrates this.</span></span>  
  
```xaml  
<system.serviceModel>  
  <services>  
    <service   
        name="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- the mex endpoint is explosed at  
       http://localhost/servicemodelsamples/service.svc/mex -->  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange" />  
    </service>  
  </services>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults  
   attribute to true-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
        <serviceMetadata httpGetEnabled="True"/>  
        <serviceDebug includeExceptionDetailInFaults="False" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="e203d-136">Klient komunikuje się za pomocą typu danego kontraktu przy użyciu klasy klienta, który jest generowany przez [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e203d-136">The client communicates using a given contract type by using a client class that is generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="e203d-137">Ta wygenerowanego klienta znajduje się w pliku generatedClient.cs lub generatedClient.vb.</span><span class="sxs-lookup"><span data-stu-id="e203d-137">This generated client is contained in the file generatedClient.cs or generatedClient.vb.</span></span> <span data-ttu-id="e203d-138">Narzędzie to pobiera metadane dla danej usługi i generuje klienta do użycia przez aplikację klienta do komunikowania się przy użyciu typu danego kontraktu.</span><span class="sxs-lookup"><span data-stu-id="e203d-138">This utility retrieves metadata for a given service and generates a client for use by the client application to communicate using a given contract type.</span></span> <span data-ttu-id="e203d-139">Usługa hostowana musi być dostępny w celu generowania kodu klienta, ponieważ usługi służy do pobierania metadanych zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="e203d-139">The hosted service must be available to generate the client code, because the service is used to retrieve the updated metadata.</span></span>  
  
 <span data-ttu-id="e203d-140">Uruchom następujące polecenie w wierszu polecenia SDK w katalogu klienta można wygenerować typu serwera proxy:</span><span class="sxs-lookup"><span data-stu-id="e203d-140">Run the following command from the SDK command prompt in the client directory to generate the typed proxy:</span></span>  
  
```  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
```  
  
 <span data-ttu-id="e203d-141">Aby wygenerować klienta w Visual Basic, wpisz następujące polecenie w wierszu polecenia SDK:</span><span class="sxs-lookup"><span data-stu-id="e203d-141">To generate client in Visual Basic type the following from the SDK command prompt:</span></span>  
  
 `Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`  
  
 <span data-ttu-id="e203d-142">Za pomocą wygenerowanego klienta, klient ma dostęp do danego punktu końcowego, konfigurując odpowiednie adres i powiązanie.</span><span class="sxs-lookup"><span data-stu-id="e203d-142">By using the generated client, the client can access a given service endpoint by configuring the appropriate address and binding.</span></span> <span data-ttu-id="e203d-143">Jak usługi Klient korzysta z pliku konfiguracji (App.config) do określenia punktu końcowego, z którą chce komunikacji.</span><span class="sxs-lookup"><span data-stu-id="e203d-143">Like the service, the client uses a configuration file (App.config) to specify the endpoint with which it wants to communicate.</span></span> <span data-ttu-id="e203d-144">Konfiguracja punktu końcowego klienta składa się z adres bezwzględny dla punktu końcowego usługi, powiązanie i kontraktu, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e203d-144">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract, as shown in the following example.</span></span>  
  
```xaml  
<client>  
     <endpoint  
         address="http://localhost/servicemodelsamples/service.svc"   
         binding="wsHttpBinding"   
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />  
</client>  
```  
  
 <span data-ttu-id="e203d-145">Wdrożenie klienta tworzy klienta i korzysta z typu interfejsu do rozpoczęcia komunikacji z usługą, jak pokazano w poniższym przykładzie kodzie.</span><span class="sxs-lookup"><span data-stu-id="e203d-145">The client implementation instantiates the client and uses the typed interface to begin communicating with the service, as shown in the following example code.</span></span>  
  
```vb  
' Create a client  
Dim client As New CalculatorClient()  
  
' Call the Add service operation.  
            Dim value1 = 100.0R  
            Dim value2 = 15.99R  
            Dim result = client.Add(value1, value2)  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)  
  
' Call the Subtract service operation.  
value1 = 145.00R  
value2 = 76.54R  
result = client.Subtract(value1, value2)  
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)  
  
' Call the Multiply service operation.  
value1 = 9.00R  
value2 = 81.25R  
result = client.Multiply(value1, value2)  
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)  
  
' Call the Divide service operation.  
value1 = 22.00R  
value2 = 7.00R  
result = client.Divide(value1, value2)  
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)  
  
'Closing the client gracefully closes the connection and cleans up resources  
```  
  
```csharp  
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
// Call the Subtract service operation.  
value1 = 145.00D;  
value2 = 76.54D;  
result = client.Subtract(value1, value2);  
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
// Call the Multiply service operation.  
value1 = 9.00D;  
value2 = 81.25D;  
result = client.Multiply(value1, value2);  
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
// Call the Divide service operation.  
value1 = 22.00D;  
value2 = 7.00D;  
result = client.Divide(value1, value2);  
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
//Closing the client releases all communication resources.  
client.Close();  
```  
  
 <span data-ttu-id="e203d-146">Po uruchomieniu próbki operację żądania i odpowiedzi są wyświetlane w oknie konsoli klienta.</span><span class="sxs-lookup"><span data-stu-id="e203d-146">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e203d-147">Naciśnij klawisz ENTER w oknie klienta, aby zamknąć klienta.</span><span class="sxs-lookup"><span data-stu-id="e203d-147">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="e203d-148">Przykładowe wprowadzenie zawiera standardowy sposób, aby utworzyć usługę i klienta.</span><span class="sxs-lookup"><span data-stu-id="e203d-148">The Getting Started sample shows the standard way to create a service and client.</span></span> <span data-ttu-id="e203d-149">Druga [podstawowe](../../../../docs/framework/wcf/samples/basic-sample.md) kompilacji w tym przykładzie, aby zademonstrować funkcje określonego produktu.</span><span class="sxs-lookup"><span data-stu-id="e203d-149">The other [Basic](../../../../docs/framework/wcf/samples/basic-sample.md) build on this sample to demonstrate specific product features.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e203d-150">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="e203d-150">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e203d-151">Upewnij się, że wykonano procedurę [jednorazowego procedurę instalacji dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e203d-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e203d-152">Tworzenie wersji języka C# lub Visual Basic .NET rozwiązania, postępuj zgodnie z instrukcjami [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e203d-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="e203d-153">Aby uruchomić przykładowy w konfiguracji pojedynczej lub między komputerami, postępuj zgodnie z instrukcjami w [uruchamiania przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e203d-153">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e203d-154">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e203d-154">See Also</span></span>  
 [<span data-ttu-id="e203d-155">Porady: hostowanie usługi WCF w zarządzanej aplikacji</span><span class="sxs-lookup"><span data-stu-id="e203d-155">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [<span data-ttu-id="e203d-156">Porady: hostowanie usługi WCF w programie IIS</span><span class="sxs-lookup"><span data-stu-id="e203d-156">How to: Host a WCF Service in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)