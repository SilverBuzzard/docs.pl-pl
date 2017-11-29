---
title: '&lt;transportConfigurationTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b048b160f337897765fa4fcff73a4906534ab08b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="52116-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="52116-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="52116-103">Reprezentuje kolekcję elementów konfiguracji, które określa rodzaj danego transportu.</span><span class="sxs-lookup"><span data-stu-id="52116-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="52116-104">Może to służyć do dodawania niestandardowych protokołów WAS.</span><span class="sxs-lookup"><span data-stu-id="52116-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="52116-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="52116-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="52116-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="52116-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="52116-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="52116-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52116-108">Składnia</span><span class="sxs-lookup"><span data-stu-id="52116-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52116-109">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="52116-109">Attributes and Elements</span></span>  
 <span data-ttu-id="52116-110">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="52116-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52116-111">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="52116-111">Attributes</span></span>  
  
|<span data-ttu-id="52116-112">Atrybut</span><span class="sxs-lookup"><span data-stu-id="52116-112">Attribute</span></span>|<span data-ttu-id="52116-113">Opis</span><span class="sxs-lookup"><span data-stu-id="52116-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52116-114">nazwa</span><span class="sxs-lookup"><span data-stu-id="52116-114">name</span></span>|<span data-ttu-id="52116-115">Nazwa transportu</span><span class="sxs-lookup"><span data-stu-id="52116-115">The name of the transport</span></span>|  
|<span data-ttu-id="52116-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="52116-116">transportConfigurationType</span></span>|<span data-ttu-id="52116-117">Typ, który implementuje transportu</span><span class="sxs-lookup"><span data-stu-id="52116-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52116-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="52116-118">Child Elements</span></span>  
  
|<span data-ttu-id="52116-119">Element</span><span class="sxs-lookup"><span data-stu-id="52116-119">Element</span></span>|<span data-ttu-id="52116-120">Opis</span><span class="sxs-lookup"><span data-stu-id="52116-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52116-121">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="52116-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="52116-122">Dodaje element konfiguracji, który identyfikuje typ danego transportu.</span><span class="sxs-lookup"><span data-stu-id="52116-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52116-123">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="52116-123">Parent Elements</span></span>  
  
|<span data-ttu-id="52116-124">Element</span><span class="sxs-lookup"><span data-stu-id="52116-124">Element</span></span>|<span data-ttu-id="52116-125">Opis</span><span class="sxs-lookup"><span data-stu-id="52116-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52116-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="52116-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="52116-127">Definiuje typ, który usługę hostingu środowiskowego dla danego transportu.</span><span class="sxs-lookup"><span data-stu-id="52116-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52116-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="52116-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="52116-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="52116-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)