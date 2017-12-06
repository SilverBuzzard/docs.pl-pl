---
title: "Rozwój za pomocą My (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: My.MyWpfExtension.Windows
helpviewer_keywords:
- My object
- My namespace
- My feature
- Visual Basic, programming in
ms.assetid: f1d04509-5e46-4551-9f9f-94334a121fca
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2cf51e1f6292a61c071fe6d92f5fcbce4be84ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="development-with-my-visual-basic"></a><span data-ttu-id="2f267-102">Rozwój za pomocą My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f267-102">Development with My (Visual Basic)</span></span>
<span data-ttu-id="2f267-103">Visual Basic udostępnia nowe funkcje do szybkiego opracowywania aplikacji poprawy wydajności i łatwości użycia, dostarczając zasilania.</span><span class="sxs-lookup"><span data-stu-id="2f267-103">Visual Basic provides new features for rapid application development that improve productivity and ease of use while delivering power.</span></span> <span data-ttu-id="2f267-104">Jedną z tych funkcji, o nazwie `My`, zapewnia dostęp do informacji i domyślnego wystąpienia obiektów, które odnoszą się do aplikacji i jej środowisko wykonawcze.</span><span class="sxs-lookup"><span data-stu-id="2f267-104">One of these features, called `My`, provides access to information and default object instances that are related to the application and its run-time environment.</span></span> <span data-ttu-id="2f267-105">Te informacje jest zorganizowana w formacie, który jest identyfikowana za pomocą funkcji IntelliSense i logicznie nakreślono zgodnie z użytku.</span><span class="sxs-lookup"><span data-stu-id="2f267-105">This information is organized in a format that is discoverable through IntelliSense and logically delineated according to use.</span></span>  
  
 <span data-ttu-id="2f267-106">Członkowie najwyższego poziomu `My` są widoczne jako obiekty.</span><span class="sxs-lookup"><span data-stu-id="2f267-106">Top-level members of `My` are exposed as objects.</span></span> <span data-ttu-id="2f267-107">Każdy obiekt działa podobnie do przestrzeni nazw lub klasy z `Shared` elementów członkowskich który udostępnia zestaw elementów członkowskich pokrewne.</span><span class="sxs-lookup"><span data-stu-id="2f267-107">Each object behaves similarly to a namespace or a class with `Shared` members, and it exposes a set of related members.</span></span>  
  
 <span data-ttu-id="2f267-108">W poniższej tabeli przedstawiono najwyższego poziomu `My` obiektów i ich relacji między nimi.</span><span class="sxs-lookup"><span data-stu-id="2f267-108">This table shows the top-level `My` objects and their relationship to each other.</span></span>  
  
 <span data-ttu-id="2f267-109">![Model obiektów Mój](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span><span class="sxs-lookup"><span data-stu-id="2f267-109">![Object Model for My](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f267-110">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="2f267-110">In This Section</span></span>  
 [<span data-ttu-id="2f267-111">Wykonywanie zadań z My.Application, My.Computer oraz My.User</span><span class="sxs-lookup"><span data-stu-id="2f267-111">Performing Tasks with My.Application, My.Computer, and My.User</span></span>](../../../visual-basic/developing-apps/development-with-my/performing-tasks-with-my-application-my-computer-and-my-user.md)  
 <span data-ttu-id="2f267-112">W tym artykule opisano trzy centralnego `My` obiektów, `My.Application`, `My.Computer`, i `My.User`, które zapewniają dostęp do informacji i funkcji</span><span class="sxs-lookup"><span data-stu-id="2f267-112">Describes the three central `My` objects, `My.Application`, `My.Computer`, and `My.User`, which provide access to information and functionality</span></span>  
  
 [<span data-ttu-id="2f267-113">Domyślne wystąpienia obiektu zapewniane przez My.Forms i My.WebServices</span><span class="sxs-lookup"><span data-stu-id="2f267-113">Default Object Instances Provided by My.Forms and My.WebServices</span></span>](../../../visual-basic/developing-apps/development-with-my/default-object-instances-provided-by-my-forms-and-my-webservices.md)  
 <span data-ttu-id="2f267-114">W tym artykule opisano `My.Forms` i `My.WebServices` obiektów, które zapewniają dostęp do formularzy, źródła danych i usług XML sieci Web używanych przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="2f267-114">Describes the `My.Forms` and `My.WebServices` objects, which provide access to forms, data sources, and XML Web services used by your application.</span></span>  
  
 [<span data-ttu-id="2f267-115">Szybkie opracowywanie aplikacji przy użyciu My.Resources i My.Settings</span><span class="sxs-lookup"><span data-stu-id="2f267-115">Rapid Application Development with My.Resources and My.Settings</span></span>](../../../visual-basic/developing-apps/development-with-my/rapid-application-development-with-my-resources-and-my-settings.md)  
 <span data-ttu-id="2f267-116">W tym artykule opisano `My.Resources` i `My.Settings` obiektów, które zapewniają dostęp do zasobów aplikacji i ustawień.</span><span class="sxs-lookup"><span data-stu-id="2f267-116">Describes the `My.Resources` and `My.Settings` objects, which provide access to an application's resources and settings.</span></span>  
  
 [<span data-ttu-id="2f267-117">Omówienie modelu aplikacji Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f267-117">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="2f267-118">W tym artykule opisano [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] modelu zamykania uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2f267-118">Describes the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Application Startup/Shutdown model.</span></span>  
  
 [<span data-ttu-id="2f267-119">Jak Moje zależy od typu projektu</span><span class="sxs-lookup"><span data-stu-id="2f267-119">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="2f267-120">Zwraca szczegółowe informacje, na którym `My` funkcje są dostępne w różnych typach projektów.</span><span class="sxs-lookup"><span data-stu-id="2f267-120">Gives details on which `My` features are available in different project types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f267-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2f267-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="2f267-122">My.Forms — obiekt</span><span class="sxs-lookup"><span data-stu-id="2f267-122">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [<span data-ttu-id="2f267-123">My.WebServices — obiekt</span><span class="sxs-lookup"><span data-stu-id="2f267-123">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [<span data-ttu-id="2f267-124">Jak Moje zależy od typu projektu</span><span class="sxs-lookup"><span data-stu-id="2f267-124">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)