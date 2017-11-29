---
title: '&lt;peer&gt; w &lt;clientCredentials&gt;, element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f26321afdbe53c4ab3750eae4a7a730bcb5ae4e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="1001b-102">&lt;peer&gt; w &lt;clientCredentials&gt;, element</span><span class="sxs-lookup"><span data-stu-id="1001b-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="1001b-103">Określa poświadczenia używane podczas uwierzytelniania klientów peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1001b-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="1001b-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1001b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1001b-105">\<zachowania ></span><span class="sxs-lookup"><span data-stu-id="1001b-105">\<behaviors></span></span>  
<span data-ttu-id="1001b-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1001b-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="1001b-107">\<zachowanie ></span><span class="sxs-lookup"><span data-stu-id="1001b-107">\<behavior></span></span>  
<span data-ttu-id="1001b-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="1001b-108">\<clientCredentials></span></span>  
<span data-ttu-id="1001b-109">\<peer ></span><span class="sxs-lookup"><span data-stu-id="1001b-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1001b-110">Składnia</span><span class="sxs-lookup"><span data-stu-id="1001b-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1001b-111">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="1001b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1001b-112">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="1001b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1001b-113">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="1001b-113">Attributes</span></span>  
 <span data-ttu-id="1001b-114">Brak.</span><span class="sxs-lookup"><span data-stu-id="1001b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1001b-115">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="1001b-115">Child Elements</span></span>  
  
|<span data-ttu-id="1001b-116">Element</span><span class="sxs-lookup"><span data-stu-id="1001b-116">Element</span></span>|<span data-ttu-id="1001b-117">Opis</span><span class="sxs-lookup"><span data-stu-id="1001b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1001b-118">\<certyfikat ></span><span class="sxs-lookup"><span data-stu-id="1001b-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="1001b-119">Określa certyfikat X.509 do użycia podczas podpisywania i szyfrowania wiadomości dla klientów peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1001b-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="1001b-120">.</span><span class="sxs-lookup"><span data-stu-id="1001b-120">.</span></span>|  
|[<span data-ttu-id="1001b-121">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1001b-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="1001b-122">Określa opcje uwierzytelniania dla klientów typu peer.</span><span class="sxs-lookup"><span data-stu-id="1001b-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="1001b-123">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1001b-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="1001b-124">Określa opcje uwierzytelnienia dla nadawców wiadomości.</span><span class="sxs-lookup"><span data-stu-id="1001b-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1001b-125">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="1001b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1001b-126">Element</span><span class="sxs-lookup"><span data-stu-id="1001b-126">Element</span></span>|<span data-ttu-id="1001b-127">Opis</span><span class="sxs-lookup"><span data-stu-id="1001b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1001b-128">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="1001b-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="1001b-129">Określa poświadczenia używane do uwierzytelniania klienta do usługi.</span><span class="sxs-lookup"><span data-stu-id="1001b-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1001b-130">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1001b-130">Remarks</span></span>  
 <span data-ttu-id="1001b-131">Ten element konfiguracji Określa poświadczenia używane przez węzeł elementu równorzędnego do samodzielnego uwierzytelnienia w innych węzłach w sieci, a także ustawienia uwierzytelniania, używane do uwierzytelniania innych węzłów równorzędnych węzła równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="1001b-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="1001b-132">Aby uzyskać więcej informacji, zobacz [uwierzytelniania wiadomości kanał elementu równorzędnego](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) i [zabezpieczanie aplikacji kanałów równorzędnych](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="1001b-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1001b-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1001b-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="1001b-134">Sieci peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="1001b-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="1001b-135">Zabezpieczanie klientów</span><span class="sxs-lookup"><span data-stu-id="1001b-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="1001b-136">Uwierzytelnianie wiadomości kanału równorzędnego</span><span class="sxs-lookup"><span data-stu-id="1001b-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="1001b-137">Niestandardowe uwierzytelnianie kanału równorzędnego</span><span class="sxs-lookup"><span data-stu-id="1001b-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="1001b-138">Zabezpieczanie aplikacji kanałów równorzędnych</span><span class="sxs-lookup"><span data-stu-id="1001b-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="1001b-139">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="1001b-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)