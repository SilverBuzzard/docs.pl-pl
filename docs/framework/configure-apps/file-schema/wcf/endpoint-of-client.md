---
title: '&lt;endpoint&gt; w &lt;client&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
caps.latest.revision: "22"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 87c83826d45942deb682087ad717070bd1ea4471
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltendpointgt-of-ltclientgt"></a><span data-ttu-id="62628-102">&lt;endpoint&gt; w &lt;client&gt;</span><span class="sxs-lookup"><span data-stu-id="62628-102">&lt;endpoint&gt; of &lt;client&gt;</span></span>
<span data-ttu-id="62628-103">Określa kontrakt, powiązanie i właściwości adresu punktu końcowego kanału, który jest używany przez klientów nawiązywania połączenia z usługą punktów końcowych na serwerze.</span><span class="sxs-lookup"><span data-stu-id="62628-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="62628-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="62628-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="62628-105">\<Klient ></span><span class="sxs-lookup"><span data-stu-id="62628-105">\<client></span></span>  
<span data-ttu-id="62628-106">\<punkt końcowy ></span><span class="sxs-lookup"><span data-stu-id="62628-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62628-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="62628-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   contract="String"   endpointConfiguration="String"   kind="String"  
   name="String"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62628-108">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="62628-108">Attributes and Elements</span></span>  
 <span data-ttu-id="62628-109">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="62628-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62628-110">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="62628-110">Attributes</span></span>  
  
|<span data-ttu-id="62628-111">Atrybut</span><span class="sxs-lookup"><span data-stu-id="62628-111">Attribute</span></span>|<span data-ttu-id="62628-112">Opis</span><span class="sxs-lookup"><span data-stu-id="62628-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62628-113">adres</span><span class="sxs-lookup"><span data-stu-id="62628-113">address</span></span>|<span data-ttu-id="62628-114">Atrybut wymaganych parametrów.</span><span class="sxs-lookup"><span data-stu-id="62628-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="62628-115">Określa adres punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="62628-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="62628-116">Wartość domyślna to ciąg pusty.</span><span class="sxs-lookup"><span data-stu-id="62628-116">The default is an empty string.</span></span> <span data-ttu-id="62628-117">Adres musi być bezwzględnym identyfikatorem URI.</span><span class="sxs-lookup"><span data-stu-id="62628-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="62628-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="62628-118">behaviorConfiguration</span></span>|<span data-ttu-id="62628-119">Ciąg zawierający nazwę zachowania zachowania, które ma być używany do utworzenia wystąpienia punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="62628-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="62628-120">Nazwa zachowania musi być w zakresie w punkcie, który usługa została zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="62628-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="62628-121">Wartość domyślna to ciąg pusty.</span><span class="sxs-lookup"><span data-stu-id="62628-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="62628-122">powiązanie</span><span class="sxs-lookup"><span data-stu-id="62628-122">binding</span></span>|<span data-ttu-id="62628-123">Atrybut wymaganych parametrów.</span><span class="sxs-lookup"><span data-stu-id="62628-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="62628-124">Ciąg określający typ powiązania do użycia.</span><span class="sxs-lookup"><span data-stu-id="62628-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="62628-125">Typ musi mieć sekcję konfiguracji zarejestrowanych, aby można było odwoływać się.</span><span class="sxs-lookup"><span data-stu-id="62628-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="62628-126">Ten typ jest zarejestrowany przez nazwę sekcji zamiast nazwą typu powiązania.</span><span class="sxs-lookup"><span data-stu-id="62628-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="62628-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="62628-127">bindingConfiguration</span></span>|<span data-ttu-id="62628-128">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="62628-128">Optional.</span></span> <span data-ttu-id="62628-129">Ciąg zawierający nazwę konfiguracji powiązania ma być używany podczas tworzenia wystąpienia klasy punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="62628-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="62628-130">Konfiguracja powiązania musi należeć do zakresu na punktu, w którym zdefiniowano punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="62628-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="62628-131">Wartość domyślna to ciąg pusty.</span><span class="sxs-lookup"><span data-stu-id="62628-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="62628-132">Ten atrybut jest używany w połączeniu z `binding` do odwołania konfigurację powiązania określonych w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="62628-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="62628-133">Ustaw ten atrybut, jeśli chcesz użyć niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="62628-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="62628-134">W przeciwnym razie może być wyjątek.</span><span class="sxs-lookup"><span data-stu-id="62628-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="62628-135">kontrakt</span><span class="sxs-lookup"><span data-stu-id="62628-135">contract</span></span>|<span data-ttu-id="62628-136">Atrybut wymaganych parametrów.</span><span class="sxs-lookup"><span data-stu-id="62628-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="62628-137">Ciąg znaków wskazujący, który kontrakt jest ujawniany ten punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="62628-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="62628-138">Zestaw musi implementować typ kontraktu.</span><span class="sxs-lookup"><span data-stu-id="62628-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="62628-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="62628-139">endpointConfiguration</span></span>|<span data-ttu-id="62628-140">Ciąg określający nazwę standardowego punktu końcowego, który jest uporządkowany według `kind` atrybut, który odwołuje się do informacji dodatkowej konfiguracji tego standardowego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="62628-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="62628-141">Taką samą nazwę, muszą być zdefiniowane w `<standardEndpoints>` sekcji.</span><span class="sxs-lookup"><span data-stu-id="62628-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="62628-142">rodzaj</span><span class="sxs-lookup"><span data-stu-id="62628-142">kind</span></span>|<span data-ttu-id="62628-143">Ciąg określający typ stosowanego standardowego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="62628-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="62628-144">Typ musi być zarejestrowana w `<extensions>` sekcji lub w pliku machine.config. Jeśli nie określono żadnej wartości, jest tworzona wspólnego punktu końcowego kanału.</span><span class="sxs-lookup"><span data-stu-id="62628-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="62628-145">nazwa</span><span class="sxs-lookup"><span data-stu-id="62628-145">name</span></span>|<span data-ttu-id="62628-146">Opcjonalny atrybut ciągu.</span><span class="sxs-lookup"><span data-stu-id="62628-146">Optional string attribute.</span></span> <span data-ttu-id="62628-147">Ten atrybut jest unikatowym identyfikatorem dla danego kontraktu punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="62628-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="62628-148">Można określić wielu klientów dla danego typu kontraktu.</span><span class="sxs-lookup"><span data-stu-id="62628-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="62628-149">Każda definicja należy zróżnicować przez unikatową nazwę.</span><span class="sxs-lookup"><span data-stu-id="62628-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="62628-150">W przypadku pominięcia tego atrybutu odpowiedniego punkt końcowy jest używany jako domyślny punkt końcowy skojarzone z określonym typem kontraktu.</span><span class="sxs-lookup"><span data-stu-id="62628-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="62628-151">Wartość domyślna to ciąg pusty.</span><span class="sxs-lookup"><span data-stu-id="62628-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="62628-152">`name` Atrybut powiązania jest używany w celu eksportu definicji za pośrednictwem WSDL.</span><span class="sxs-lookup"><span data-stu-id="62628-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62628-153">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="62628-153">Child Elements</span></span>  
  
|<span data-ttu-id="62628-154">Element</span><span class="sxs-lookup"><span data-stu-id="62628-154">Element</span></span>|<span data-ttu-id="62628-155">Opis</span><span class="sxs-lookup"><span data-stu-id="62628-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62628-156">\<nagłówki ></span><span class="sxs-lookup"><span data-stu-id="62628-156">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="62628-157">Kolekcja nagłówków adresu.</span><span class="sxs-lookup"><span data-stu-id="62628-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="62628-158">\<tożsamość ></span><span class="sxs-lookup"><span data-stu-id="62628-158">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="62628-159">Tożsamości, która umożliwia uwierzytelnianie punktu końcowego przez inne punkty końcowe, wymiana wiadomości z nim.</span><span class="sxs-lookup"><span data-stu-id="62628-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62628-160">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="62628-160">Parent Elements</span></span>  
  
|<span data-ttu-id="62628-161">Element</span><span class="sxs-lookup"><span data-stu-id="62628-161">Element</span></span>|<span data-ttu-id="62628-162">Opis</span><span class="sxs-lookup"><span data-stu-id="62628-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62628-163">\<Klient ></span><span class="sxs-lookup"><span data-stu-id="62628-163">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="62628-164">Sekcja konfiguracyjna, który definiuje listę punktów końcowych, które klient może połączyć się.</span><span class="sxs-lookup"><span data-stu-id="62628-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="62628-165">Przykład</span><span class="sxs-lookup"><span data-stu-id="62628-165">Example</span></span>  
 <span data-ttu-id="62628-166">Jest to przykład konfiguracji punktu końcowego kanału.</span><span class="sxs-lookup"><span data-stu-id="62628-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    name="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
</endpoint>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62628-167">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="62628-167">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>  
 <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 [<span data-ttu-id="62628-168">Konfiguracja klienta programu WCF</span><span class="sxs-lookup"><span data-stu-id="62628-168">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="62628-169">Klienci</span><span class="sxs-lookup"><span data-stu-id="62628-169">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)