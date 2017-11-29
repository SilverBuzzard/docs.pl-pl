---
title: '&lt;knownCertificates&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e1ce8be4dfa71685933512c1c0db36000ce93c12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="1539c-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="1539c-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="1539c-103">Reprezentuje kolekcję certyfikatów X.509, które są dostarczane do uwierzytelnienia poświadczeń zabezpieczenia wydawanych z zabezpieczeń tokenu usługi (STS).</span><span class="sxs-lookup"><span data-stu-id="1539c-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="1539c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1539c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1539c-105">\<zachowania ></span><span class="sxs-lookup"><span data-stu-id="1539c-105">\<behaviors></span></span>  
<span data-ttu-id="1539c-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1539c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1539c-107">\<zachowanie ></span><span class="sxs-lookup"><span data-stu-id="1539c-107">\<behavior></span></span>  
<span data-ttu-id="1539c-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="1539c-108">\<serviceCredentials></span></span>  
<span data-ttu-id="1539c-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1539c-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="1539c-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="1539c-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1539c-111">Składnia</span><span class="sxs-lookup"><span data-stu-id="1539c-111">Syntax</span></span>  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1539c-112">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="1539c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1539c-113">W poniższych sekcjach opisano atrybuty i elementy podrzędne, elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="1539c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1539c-114">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="1539c-114">Attributes</span></span>  
 <span data-ttu-id="1539c-115">Brak.</span><span class="sxs-lookup"><span data-stu-id="1539c-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1539c-116">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="1539c-116">Child Elements</span></span>  
  
|<span data-ttu-id="1539c-117">Element</span><span class="sxs-lookup"><span data-stu-id="1539c-117">Element</span></span>|<span data-ttu-id="1539c-118">Opis</span><span class="sxs-lookup"><span data-stu-id="1539c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1539c-119">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="1539c-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="1539c-120">Dodaje certyfikat X.509 do kolekcji.</span><span class="sxs-lookup"><span data-stu-id="1539c-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1539c-121">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="1539c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1539c-122">Element</span><span class="sxs-lookup"><span data-stu-id="1539c-122">Element</span></span>|<span data-ttu-id="1539c-123">Opis</span><span class="sxs-lookup"><span data-stu-id="1539c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1539c-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1539c-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="1539c-125">Określa token wydany jako poświadczenie usługi.</span><span class="sxs-lookup"><span data-stu-id="1539c-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1539c-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1539c-126">Remarks</span></span>  
 <span data-ttu-id="1539c-127">Wystawiony token scenariusz ma trzy etapy.</span><span class="sxs-lookup"><span data-stu-id="1539c-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="1539c-128">Podczas pierwszego etapu klienta próby uzyskania dostępu do usługi jest określane *secure token service*.</span><span class="sxs-lookup"><span data-stu-id="1539c-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="1539c-129">Bezpieczne usługi tokenu następnie uwierzytelnia klientów i następnie wystawia token, zwykle tokenu zabezpieczeń potwierdzenia Markup Language (SAML) klienta.</span><span class="sxs-lookup"><span data-stu-id="1539c-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="1539c-130">Klient następnie wróci do usługi z tokenem.</span><span class="sxs-lookup"><span data-stu-id="1539c-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="1539c-131">Usługa sprawdza, czy token dla danych, które umożliwia usłudze uwierzytelnienia tokenu, a w związku z tym klientem.</span><span class="sxs-lookup"><span data-stu-id="1539c-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="1539c-132">W celu uwierzytelnienia tokenu certyfikat używa bezpiecznego tokenu usługi musi być znane z usługą.</span><span class="sxs-lookup"><span data-stu-id="1539c-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="1539c-133">[ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element jest repozytorium dla wszystkich certyfikatów bezpiecznego tokenu usługi.</span><span class="sxs-lookup"><span data-stu-id="1539c-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="1539c-134">Aby dodać certyfikaty, należy użyć [ \<knownCertificates > elementu](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="1539c-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="1539c-135">Wstaw [ \<Dodaj >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) dla każdego certyfikatu, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="1539c-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="1539c-136">Domyślnie certyfikaty musi pochodzić od bezpiecznego usługi tokenu.</span><span class="sxs-lookup"><span data-stu-id="1539c-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="1539c-137">Te "znane" certyfikatów, upewnij się, że tylko prawnie klientów dostępu do usługi.</span><span class="sxs-lookup"><span data-stu-id="1539c-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="1539c-138">Aby przejrzeć warunki wymagane do klienta może zostać uwierzytelniony przez usługi federacyjnej, jak również więcej informacji na temat używania tego elementu konfiguracji, zobacz [porady: Konfigurowanie poświadczeń usługi federacyjnej](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="1539c-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="1539c-139">Aby uzyskać więcej informacji o scenariuszach obejmujących Federację, zobacz [Federacja i wystawione tokeny](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="1539c-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="1539c-140">Na przykład, który pokazuje, jak można wypełnić kolekcji w konfiguracji, zobacz [ \<Dodaj >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="1539c-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1539c-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1539c-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="1539c-142">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="1539c-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="1539c-143">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1539c-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="1539c-144">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="1539c-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="1539c-145">Porady: Konfigurowanie poświadczeń usługi federacyjnej</span><span class="sxs-lookup"><span data-stu-id="1539c-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="1539c-146">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="1539c-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="1539c-147">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="1539c-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="1539c-148">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="1539c-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="1539c-149">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="1539c-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)