---
title: '&lt;defaultftpcachepolicy —&gt; — Element (ustawienia sieci)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: a8c71551adc2b88b5300994134eaec329a083709
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188290"
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a>&lt;defaultftpcachepolicy —&gt; — Element (ustawienia sieci)
Opisuje, czy buforowanie FTP jest aktywny i w tym artykule opisano domyślne zasady buforowania.  
  
 \<Konfiguracja >  
\<system.net>  
\<requestCaching — >  
\<defaultftpcachepolicy — >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`policyLevel`|Określa, FTP, zasady buforowania. Wartość domyślna to `Default`.|  
  
## <a name="policylevel-attribute"></a>policyLevel atrybutu  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`Default`|Zwraca buforowane zasobu, jeśli zasób jest świeże, długość zawartości jest dokładne i wygaśnięcia, modyfikowanie i atrybuty długość zawartości znajdują się.|  
|`BypassCache`|Zwraca zasobu z serwera.|  
|`CacheOnly`|Zwraca buforowane zasobu, jeśli długość zawartości jest obecna, a także odpowiada rozmiarowi wpisu.|  
|`CacheIfAvailable`|Zwraca buforowane zasobu, jeśli długość zawartości jest dostarczany i odpowiada rozmiarowi wejścia; w przeciwnym razie zasób zostanie pobrana z serwera i jest zwracany do obiektu wywołującego.|  
|`Revalidate`|Zwraca buforowane zasobu, jeśli sygnatury czasowej zasobów pamięci podręcznej jest taka sama jak sygnatura czasowa zasobu na serwerze; w przeciwnym razie zasób jest pobierane z serwera, przechowywane w pamięci podręcznej i zwracany do wywołującego.|  
|`Reload`|Pobiera zasób z serwera, jest on przechowywany w pamięci podręcznej i zwraca zasobu do obiektu wywołującego.|  
|`NoCacheNoStore`|Jeśli istnieje zasób pamięci podręcznej, został usunięty. Zasób jest pobierane z serwera i jest zwracany do obiektu wywołującego.|  
|`Revalidate`|Spełnia żądanie przy użyciu pamięci podręcznej kopię zasobu, jeśli sygnatura czasowa jest taka sama jak sygnatura czasowa zasobu na serwerze; w przeciwnym razie zasób jest pobierane z serwera, przedstawione do obiektu wywołującego i przechowywane w pamięci podręcznej.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[requestCaching —](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Określa mechanizm buforowania żądań sieci.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak określić zasady buforowania FTP `NoCacheNoStore`.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też  
- <xref:System.Net.Cache>  
- <xref:System.Net.WebRequest>  
- <xref:System.Net.Cache.RequestCacheLevel>  
- [Schemat ustawień sieci](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
