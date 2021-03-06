---
title: '&lt;Kryteria znajdowania&gt;'
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 38941e4afb0cfa4fea8657c90c1105a5ab771d49
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144209"
---
# <a name="ltfindcriteriagt"></a>&lt;Kryteria znajdowania&gt;
Element konfiguracji, który dostarcza zestaw kryteriów używanych przez aplikację kliencką do wyszukiwania usługi odkrywania. Kryteria mogą być grupowane w kryteriach wyszukiwania (Określanie usług szukasz) i Znajdź kryteriów zakończenia (ile wyszukiwanie powinno trwać).  
  
 \<system.ServiceModel>  
\<standardEndpoints >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|czas trwania|Wartość przedziału czasu, który określa maksymalny czas oczekiwania na odpowiedzi z usług w sieci. Domyślny czas trwania wynosi 20 sekund.|  
|maxResults|Liczba całkowita określająca maksymalną liczbę odpowiedzi zaczekać z usług w sieci lub Internetu. Jeśli maksymalna odpowiedzi są odbierane przed wartość określoną w `duration` atrybut upłynie zakończenia operacji wyszukiwania.|  
|scopeMatchBy|Identyfikator URI, który określa algorytm dopasowania do użycia podczas dopasowywania zakresów w wiadomości sondy z tym punktem końcowym.<br /><br /> Istnieje pięć obsługiwanych reguł dopasowania do zakresu. Jeśli nie określisz regułę dopasowania w zakresie `ScopeMatchByPrefix` jest używany. Aby uzyskać więcej informacji na temat tego, zobacz <xref:System.ServiceModel.Discovery.FindCriteria>.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<contractTypeNames >](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|Kolekcja elementów konfiguracji, które zawierają nazwy typu kontraktu usługi przepływu pracy.|  
|\<Rozszerzenia > z \<kryteria znajdowania >|Kolekcja obiektów elementu XML, które udostępniają rozszerzenia.|  
|[\<zakresy >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Kolekcja obiektów zawierających bezwzględne identyfikatory URI, które są używane podczas operacji wyszukiwania, aby zlokalizować określonej usługi lub usług.<br /><br /> Jeśli zostanie znaleziony określonej usługi, udanych dopasowań stało się między usługą identyfikatora URI i zakres identyfikatora URI, a czasami za pomocą reguł zakresu, obsługujące komplikacji dopasowania.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<standardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Zawiera ustawienia wymagane przez aplikację do uczestnictwa w procesie odnajdowania usług jako klient.|  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
