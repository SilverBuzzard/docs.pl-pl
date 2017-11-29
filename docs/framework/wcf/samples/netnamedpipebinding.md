---
title: NetNamedPipeBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Net Profile Named Pipe
ms.assetid: e78e845f-c325-46e2-927d-81616f97f7d5
caps.latest.revision: "34"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ba6c85bbee3a0740568b47ea1a54db1a4327743f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="netnamedpipebinding"></a><span data-ttu-id="c5ec8-102">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="c5ec8-102">NetNamedPipeBinding</span></span>
<span data-ttu-id="c5ec8-103">W przykładzie pokazano `netNamedPipeBinding` powiązania, który zapewnia komunikację między procesami na tym samym komputerze.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-103">This sample demonstrates the `netNamedPipeBinding` binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="c5ec8-104">Nazwane potoki nie działają na komputerach.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-104">Named pipes do not work across machines.</span></span> <span data-ttu-id="c5ec8-105">Ten przykład jest oparty na [wprowadzenie](../../../../docs/framework/wcf/samples/getting-started-sample.md) Kalkulator usługi.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-105">This sample is based on The [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) calculator service.</span></span>  
  
 <span data-ttu-id="c5ec8-106">W tym przykładzie usługa jest samodzielnie hostowana.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-106">In this sample, the service is self-hosted.</span></span> <span data-ttu-id="c5ec8-107">Klient i usługa są aplikacji konsoli.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-107">Both the client and the service are console applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5ec8-108">Procedury i kompilacji instrukcje dotyczące instalacji dla tego przykładu znajdują się na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c5ec8-109">Powiązanie jest określona w plikach konfiguracji dla klienta i usługi.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-109">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="c5ec8-110">Typ powiązania jest określona w `binding` atrybutu[\<punktu końcowego >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element, jak pokazano w poniższych Przykładowa konfiguracja:</span><span class="sxs-lookup"><span data-stu-id="c5ec8-110">The binding type is specified in the `binding` attribute of the[\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element as shown in the following sample configuration:</span></span>  
  
```xml  
<endpoint address="net.pipe://localhost/ServiceModelSamples/service"  
          binding="netNamedPipeBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="c5ec8-111">Poprzedni przykład przedstawia sposób konfigurowania punktu końcowego użycia `netNamedPipeBinding` powiązania z ustawieniami domyślnymi.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-111">The previous sample shows how to configure an endpoint to use the `netNamedPipeBinding` binding with the default settings.</span></span> <span data-ttu-id="c5ec8-112">Jeśli chcesz skonfigurować `netNamedPipeBinding` powiązania i zmieniać pewne ustawienia, należy zdefiniować konfiguracji powiązania.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-112">If you want to configure the `netNamedPipeBinding` binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="c5ec8-113">Punkt końcowy musi odwoływać się Konfiguracja powiązania o nazwie z `bindingConfiguration` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-113">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span>  
  
```xml  
<endpoint address="net.pipe://localhost/ServiceModelSamples/service"  
          binding="netNamedPipeBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="c5ec8-114">W tym przykładzie ma nazwę konfiguracji powiązania `Binding1` i ma następujące definicje:</span><span class="sxs-lookup"><span data-stu-id="c5ec8-114">In this sample, the binding configuration is named `Binding1` and has the following definition:</span></span>  
  
```xml  
<bindings>  
  <!--   
        Following is the expanded configuration section for a NetNamedPipeBinding.  
        Each property is configured with the default value.  
     -->  
  <netNamedPipeBinding>  
    <binding name="Binding1"   
             closeTimeout="00:01:00"  
             openTimeout="00:01:00"   
             receiveTimeout="00:10:00"   
             sendTimeout="00:01:00"  
             transactionFlow="false"   
             transferMode="Buffered"   
             transactionProtocol="OleTransactions"  
             hostNameComparisonMode="StrongWildcard"   
             maxBufferPoolSize="524288"  
             maxBufferSize="65536"   
             maxConnections="10"   
             maxReceivedMessageSize="65536">  
      <security mode="Transport">  
        <transport protectionLevel="EncryptAndSign" />  
      </security>  
    </binding>  
  </netNamedPipeBinding>  
</bindings>  
```  
  
 <span data-ttu-id="c5ec8-115">Po uruchomieniu próbki operację żądania i odpowiedzi są wyświetlane w oknie konsoli klienta.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-115">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c5ec8-116">Naciśnij klawisz ENTER w oknie klienta, aby zamknąć klienta.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-116">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c5ec8-117">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="c5ec8-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c5ec8-118">Upewnij się, że wykonano procedurę [jednorazowego procedurę instalacji dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c5ec8-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="c5ec8-119">Tworzenie wersji języka C# lub Visual Basic .NET rozwiązania, postępuj zgodnie z instrukcjami [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c5ec8-119">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="c5ec8-120">Aby uruchomić przykład w konfiguracji jednego komputera, postępuj zgodnie z instrukcjami [uruchamiania przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c5ec8-120">To run the sample in a single machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c5ec8-121">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c5ec8-122">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="c5ec8-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c5ec8-123">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c5ec8-124">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="c5ec8-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\NamedPipe`  
  
## <a name="see-also"></a><span data-ttu-id="c5ec8-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c5ec8-125">See Also</span></span>