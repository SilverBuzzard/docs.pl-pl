---
title: '&lt;mexHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4e8e9a13553e8b7463f7bb7f66c1a38dc1d4ac36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltmexhttpbindinggt"></a><span data-ttu-id="307a4-102">&lt;mexHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="307a4-102">&lt;mexHttpBinding&gt;</span></span>
<span data-ttu-id="307a4-103">Określa ustawienia dla powiązania używanego w wymianie wiadomości WS-MetadataExchange (WS-MEX) za pośrednictwem protokołu HTTP.</span><span class="sxs-lookup"><span data-stu-id="307a4-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="307a4-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="307a4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="307a4-105">\<powiązania ></span><span class="sxs-lookup"><span data-stu-id="307a4-105">\<bindings></span></span>  
<span data-ttu-id="307a4-106">\<mexHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="307a4-106">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="307a4-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="307a4-107">Syntax</span></span>  
  
```xml  
<mexHttpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="307a4-108">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="307a4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="307a4-109">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="307a4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="307a4-110">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="307a4-110">Attributes</span></span>  
  
|<span data-ttu-id="307a4-111">Atrybut</span><span class="sxs-lookup"><span data-stu-id="307a4-111">Attribute</span></span>|<span data-ttu-id="307a4-112">Opis</span><span class="sxs-lookup"><span data-stu-id="307a4-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="307a4-113">A <xref:System.TimeSpan> wartość, która określa interwał przeznaczony na zakończenie operacji zamknięcia.</span><span class="sxs-lookup"><span data-stu-id="307a4-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="307a4-114">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="307a4-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="307a4-115">Wartość domyślna to 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="307a4-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="307a4-116">Ciąg zawierający nazwę konfiguracji powiązania.</span><span class="sxs-lookup"><span data-stu-id="307a4-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="307a4-117">Wartość ta powinna być unikatowa, ponieważ jest używany jako identyfikator dla tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="307a4-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="307a4-118">Każdego powiązania ma `name` i `namespace` atrybutu niesekwencyjnego razem jednoznacznie zidentyfikować je w metadanych usługi.</span><span class="sxs-lookup"><span data-stu-id="307a4-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="307a4-119">Ponadto ta nazwa jest unikatowa wśród powiązania tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="307a4-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="307a4-120">Począwszy od [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], powiązania i zachowania nie muszą mieć nazwę.</span><span class="sxs-lookup"><span data-stu-id="307a4-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="307a4-121">Aby uzyskać więcej informacji o konfiguracji domyślnej i bez powiązania i zachowania, zobacz [uproszczony konfiguracji](../../../../../docs/framework/wcf/simplified-configuration.md) i [uproszczona konfiguracja usług WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="307a4-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="307a4-122">A <xref:System.TimeSpan> wartość, która określa interwał przeznaczony na zakończenie operacji otwarcia.</span><span class="sxs-lookup"><span data-stu-id="307a4-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="307a4-123">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="307a4-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="307a4-124">Wartość domyślna to 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="307a4-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="307a4-125">A <xref:System.TimeSpan> wartość, która określa interwał przeznaczony na zakończenie operacji odbioru.</span><span class="sxs-lookup"><span data-stu-id="307a4-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="307a4-126">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="307a4-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="307a4-127">Wartość domyślna to 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="307a4-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="307a4-128">A <xref:System.TimeSpan> wartość, która określa interwał przeznaczony na zakończenie operacji wysyłania.</span><span class="sxs-lookup"><span data-stu-id="307a4-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="307a4-129">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="307a4-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="307a4-130">Wartość domyślna to 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="307a4-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="307a4-131">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="307a4-131">Child Elements</span></span>  
 <span data-ttu-id="307a4-132">Brak.</span><span class="sxs-lookup"><span data-stu-id="307a4-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="307a4-133">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="307a4-133">Parent Elements</span></span>  
  
|<span data-ttu-id="307a4-134">Element</span><span class="sxs-lookup"><span data-stu-id="307a4-134">Element</span></span>|<span data-ttu-id="307a4-135">Opis</span><span class="sxs-lookup"><span data-stu-id="307a4-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="307a4-136">\<powiązania ></span><span class="sxs-lookup"><span data-stu-id="307a4-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="307a4-137">Ten element przetrzymuje kolekcję powiązań standardowych i niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="307a4-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="307a4-138">Uwagi</span><span class="sxs-lookup"><span data-stu-id="307a4-138">Remarks</span></span>  
 <span data-ttu-id="307a4-139">To powiązanie jest zasadniczo `WSHttpBinding` powiązania z wyłączonymi zabezpieczeniami.</span><span class="sxs-lookup"><span data-stu-id="307a4-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="307a4-140">Obsługuje większość żądania metadanych.</span><span class="sxs-lookup"><span data-stu-id="307a4-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307a4-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="307a4-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpBindingElement>  
 [<span data-ttu-id="307a4-142">Porady: Publikowanie metadanych dla usługi przy użyciu pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="307a4-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="307a4-143">Publikowanie i pobieranie metadanych za pośrednictwem powiązania niestandardowego</span><span class="sxs-lookup"><span data-stu-id="307a4-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="307a4-144">Metadane</span><span class="sxs-lookup"><span data-stu-id="307a4-144">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="307a4-145">Powiązania</span><span class="sxs-lookup"><span data-stu-id="307a4-145">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="307a4-146">Konfigurowanie powiązań dostarczanych przez System</span><span class="sxs-lookup"><span data-stu-id="307a4-146">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="307a4-147">Konfigurowanie usług Windows Communication Foundation i klientów za pomocą powiązań</span><span class="sxs-lookup"><span data-stu-id="307a4-147">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="307a4-148">\<Powiązanie ></span><span class="sxs-lookup"><span data-stu-id="307a4-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)