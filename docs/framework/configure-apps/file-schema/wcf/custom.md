---
title: '&lt;custom&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 7d558be66b8a1e46d9743c5f8bf0bb9a8b4c349e
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838962"
---
# <a name="ltcustomgt"></a>&lt;custom&gt;
Określa ustawienia dla równorzędnej niestandardowej usługi rozpoznawania.  
  
\<system.serviceModel>  
\<powiązania >  
\<netPeerBinding>  
\<Powiązanie >  
\<Program rozpoznawania nazw >  
\<custom>  
  
## <a name="syntax"></a>Składnia  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`address`|Identyfikator URI, który określa adres punktu końcowego węzła równorzędnego, który jest hostem równorzędnej niestandardowej usługi rozpoznawania.|  
|`resolverType`|Ciąg, który określa typ równorzędnej niestandardowej usługi rozpoznawania.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<tożsamość >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Określa tożsamość mechanizmy rozpoznawania elementów równorzędnych niestandardowe skonfigurowane z tym elementem. Ten element jest typu <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<nagłówki >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Kolekcja nagłówka adres używany dla wiadomości protokołu SOAP, obsługiwane przez program rozpoznawania nazw dla równorzędnej niestandardowej.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<resolver>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|Program rozpoznawania elementów równorzędnych, który jest używany do rozpoznawania elementu równorzędnego siatki identyfikator do zbioru adresów węzłów równorzędnych reprezentujących kilka węzłów, które uczestniczą w siatce.|  
  
## <a name="remarks"></a>Uwagi  
 Ten element definiuje ustawienia podstawowe dla równorzędnej niestandardowej usługi rozpoznawania nazw, w tym adres punktu końcowego elementu równorzędnego obsługującego usługę, a także ustawienia określonego powiązania. Aby uzyskać więcej informacji na temat tworzenia niestandardowego mechanizmu, zobacz [Dodawanie niestandardowego mechanizmu do aplikacji PeerChannel](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [Mechanizmy rozpoznawania elementów równorzędnych](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [Dodawanie niestandardowego mechanizmu do aplikacji PeerChannel](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
