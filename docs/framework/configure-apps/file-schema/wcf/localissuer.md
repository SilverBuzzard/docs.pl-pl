---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: cb5afb0e73ad0a07ea43f06915f4e477d7f8f985
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841556"
---
# <a name="ltlocalissuergt"></a>&lt;localIssuer&gt;
Określa adres i powiązanie wystawcy lokalnego, można użyć do uzyskania tokenu zabezpieczającego.  
  
 \<system.ServiceModel>  
\<zachowania >  
sekcja endpointBehaviors  
\<zachowanie >  
\<clientCredentials>  
\<issuedToken >  
\<localIssuer >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|adres|Wymagany ciąg. Określa identyfikator URI wystawcy lokalnego.|  
|powiązanie|Opcjonalny ciąg. Jedno z powiązań dostarczanych przez system. Aby uzyskać listę, zobacz [powiązania System-Provided](../../../../../docs/framework/wcf/system-provided-bindings.md).|  
|bindingConfiguration|Opcjonalny ciąg. Określa konfigurację powiązania w pliku konfiguracji.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<tożsamość >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Określa informacje o tożsamości dla wystawcy lokalnego.|  
|[\<nagłówki >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Kolekcja nagłówków adresowych, które są wymagane do prawidłowego adresowania wystawcy lokalnego. Możesz użyć `add` — słowo kluczowe, aby dodać nagłówek do tej kolekcji.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<issuedToken >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Określa niestandardowy token używany do uwierzytelniania klienta do usługi.|  
  
## <a name="remarks"></a>Uwagi  
 W przypadku uzyskania wystawiony token z Usługa tokenu zabezpieczającego (STS), należy skonfigurować aplikację klienta przy użyciu adresu i powiązania do użycia do komunikowania się z usługi STS. Gdy <xref:System.ServiceModel.WSFederationHttpBinding> nie dostarcza adres URL dla usługi tokenu zabezpieczającego lub gdy adres wystawcy powiązania federacyjnego `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` lub `null`, klienta programu Windows Communication Foundation (WCF) kanału używa wartości określonych przez `address`i `binding` nawiązać połączenia z usługą STS uzyskać Wystawiony token. Aby uzyskać więcej informacji na temat konfigurowania lokalnego wystawcy, zobacz [porady: Konfigurowanie lokalnego wystawcy](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład ustawia `address`, `binding`, i `bindingConfiguration` atrybuty `localIssuer` elementu.  
  
```xml  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [Zachowania zabezpieczeń](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Instrukcje: konfigurowanie lokalnego wystawcy](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Uwierzytelnianie i tożsamość usług](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Zachowania zabezpieczeń](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Federacja i wystawione tokeny](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Zabezpieczanie usług i klientów](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Zabezpieczanie klientów](../../../../../docs/framework/wcf/securing-clients.md)  
 [Instrukcje: tworzenie klienta federacyjnego](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Federacja i wystawione tokeny](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
