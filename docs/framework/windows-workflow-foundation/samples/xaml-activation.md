---
title: Aktywacja XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f513b10c84de968d5a18b800037b512aad90399e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-activation"></a><span data-ttu-id="996d4-102">Aktywacja XAML</span><span class="sxs-lookup"><span data-stu-id="996d4-102">XAML Activation</span></span>
<span data-ttu-id="996d4-103">W tym przykładzie pokazano, jak udostępniać deklaracyjnego przepływu pracy w programie IIS.</span><span class="sxs-lookup"><span data-stu-id="996d4-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="996d4-104">Próbka jest podstawowy przepływ pracy o nazwie `EchoService` mający jednej operacji.</span><span class="sxs-lookup"><span data-stu-id="996d4-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="996d4-105">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="996d4-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="996d4-106">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="996d4-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="996d4-107">Jeśli ten katalog nie istnieje, przejdź do (stronę pobierania), aby pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="996d4-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="996d4-108">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="996d4-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="996d4-109">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="996d4-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="996d4-110">Otwórz rozwiązanie XAMLActivation.sln w [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="996d4-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="996d4-111">Skompiluj rozwiązanie, naciskając klawisz **F5**.</span><span class="sxs-lookup"><span data-stu-id="996d4-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="996d4-112">Uruchom WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="996d4-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="996d4-113">W wierszu polecenia wpisz następujące:</span><span class="sxs-lookup"><span data-stu-id="996d4-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="996d4-114">CD %SystemDrive%\Program Files\Microsoft 10.0\Common7\IDE programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="996d4-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="996d4-115">Uruchom WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="996d4-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="996d4-116">Ustaw adres usługi na WcfTestClient.exe, naciskając klawisze CTRL + SHIFT + A i ustawienie adresu usługi http://localhost:56133/Service.xamlx.</span><span class="sxs-lookup"><span data-stu-id="996d4-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="996d4-117">Operacja echo testować usługę.</span><span class="sxs-lookup"><span data-stu-id="996d4-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="996d4-118">Wdrażanie usługi w usługach IIS przy użyciu DeployToIIS.Bat w wierszu polecenia z uprawnieniami administratora.</span><span class="sxs-lookup"><span data-stu-id="996d4-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="996d4-119">Zaktualizuj adres usługi na komputerze klienckim http://localhost/XAMLActivation/Service.xamlx, a następnie testować usługę ponownie, używając WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="996d4-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>