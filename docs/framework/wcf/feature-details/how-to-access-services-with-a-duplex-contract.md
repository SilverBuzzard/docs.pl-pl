---
title: "Instrukcje: Uzyskiwanie dostępu do usług za pomocą kontraktu dwukierunkowego"
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
helpviewer_keywords: duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4c273e674fb7cb0f2801d9858d598baab5973a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="361ab-102">Instrukcje: Uzyskiwanie dostępu do usług za pomocą kontraktu dwukierunkowego</span><span class="sxs-lookup"><span data-stu-id="361ab-102">How to: Access Services with a Duplex Contract</span></span>
<span data-ttu-id="361ab-103">Jedna funkcja [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] jest możliwość tworzenia usługi, który korzysta ze wzorca komunikacji dupleksowej.</span><span class="sxs-lookup"><span data-stu-id="361ab-103">One feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="361ab-104">Ten wzorzec umożliwia usługi do komunikacji z klientem za pośrednictwem wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="361ab-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="361ab-105">W tym temacie przedstawiono kroki, aby utworzyć [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta w klasie klienta, który implementuje interfejs wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="361ab-105">This topic shows the steps to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client in a client class that implements the callback interface.</span></span>  
  
 <span data-ttu-id="361ab-106">Dwa powiązania udostępnia adres IP klienta do usługi.</span><span class="sxs-lookup"><span data-stu-id="361ab-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="361ab-107">Klienta należy użyć zabezpieczeń, aby upewnić się, że go tylko łączy się z usługami go relacji zaufania.</span><span class="sxs-lookup"><span data-stu-id="361ab-107">The client should use security to ensure that it connects only to services it trusts.</span></span>  
  
 <span data-ttu-id="361ab-108">Samouczek dotyczący tworzenia podstawowego [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usługi i klienta, zobacz [Wprowadzenie — samouczek](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="361ab-108">For a tutorial on creating a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service and client, see [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
### <a name="to-access-a-duplex-service"></a><span data-ttu-id="361ab-109">Dostęp do usługi dupleksu</span><span class="sxs-lookup"><span data-stu-id="361ab-109">To access a duplex service</span></span>  
  
1.  <span data-ttu-id="361ab-110">Utwórz usługę, która zawiera dwa interfejsy.</span><span class="sxs-lookup"><span data-stu-id="361ab-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="361ab-111">Pierwszy interfejs dla usługi, druga jest przeznaczona dla wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="361ab-111">The first interface is for the service, the second is for the callback.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="361ab-112">Tworzenie usługi duplex, zobacz [porady: tworzenie kontraktu dwukierunkowego](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="361ab-112"> creating a duplex service, see [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
2.  <span data-ttu-id="361ab-113">Uruchom usługę.</span><span class="sxs-lookup"><span data-stu-id="361ab-113">Run the service.</span></span>  
  
3.  <span data-ttu-id="361ab-114">Użyj [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) do generowania kontraktów (interfejsy) dla klienta.</span><span class="sxs-lookup"><span data-stu-id="361ab-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="361ab-115">Aby dowiedzieć się, jak to zrobić, zobacz [porady: Tworzenie klienta](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="361ab-115">For information about how to do this, see  [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
4.  <span data-ttu-id="361ab-116">Zaimplementuj interfejs wywołania zwrotnego w klasie klienta, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="361ab-116">Implement the callback interface in the client class, as shown in the following example.</span></span>  
  
    ```csharp  
    public class CallbackHandler : ICalculatorDuplexCallback  
    {  
        public void Result(double result)  
        {  
            Console.WriteLine("Result ({0})", result);  
        }  
        public void Equation(string equation)  
        {  
            Console.WriteLine("Equation({0})", equation);  
        }  
    }  
    ```  
  
    ```vb  
    Public Class CallbackHandler   
    Implements ICalculatorDuplexCallback  
       Public Sub Result (ByVal result As Double)  
          Console.WriteLine("Result ({0})", result)  
       End Sub  
        Public Sub Equation(ByVal equation As String)  
            Console.Writeline("Equation({0})", equation)  
        End Sub  
    End Class  
    ```  
  
5.  <span data-ttu-id="361ab-117">Utworzenie wystąpienia <xref:System.ServiceModel.InstanceContext> klasy.</span><span class="sxs-lookup"><span data-stu-id="361ab-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="361ab-118">Konstruktor wymaga wystąpienia klasy klienta.</span><span class="sxs-lookup"><span data-stu-id="361ab-118">The constructor requires an instance of the client class.</span></span>  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  <span data-ttu-id="361ab-119">Utwórz wystąpienie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta przy użyciu konstruktora, który wymaga <xref:System.ServiceModel.InstanceContext> obiektu.</span><span class="sxs-lookup"><span data-stu-id="361ab-119">Create an instance of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="361ab-120">Drugi parametr konstruktora jest nazwa punktu końcowego znalezione w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="361ab-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  <span data-ttu-id="361ab-121">Wywołanie metody [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="361ab-121">Call the methods of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client as required.</span></span>  
  
## <a name="example"></a><span data-ttu-id="361ab-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="361ab-122">Example</span></span>  
 <span data-ttu-id="361ab-123">Poniższy przykładowy kod przedstawia sposób tworzenia klasy klienta, który uzyskuje dostęp do kontraktu dwukierunkowego.</span><span class="sxs-lookup"><span data-stu-id="361ab-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="361ab-124">Zabezpieczenia.NET Framework</span><span class="sxs-lookup"><span data-stu-id="361ab-124">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="361ab-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="361ab-125">See Also</span></span>  
 [<span data-ttu-id="361ab-126">Wprowadzenie — samouczek</span><span class="sxs-lookup"><span data-stu-id="361ab-126">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="361ab-127">Porady: tworzenie kontraktu dwukierunkowego</span><span class="sxs-lookup"><span data-stu-id="361ab-127">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="361ab-128">Narzędzie do obsługi metadanych elementu ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="361ab-128">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="361ab-129">Porady: Tworzenie klienta</span><span class="sxs-lookup"><span data-stu-id="361ab-129">How to: Create a Client</span></span>](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="361ab-130">Porady: używanie elementu ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="361ab-130">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)