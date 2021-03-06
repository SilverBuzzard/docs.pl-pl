---
title: '&lt;gcconcurrent —&gt; — Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fa802ab9d1025bd130a6265b50050284aae0150
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612390"
---
# <a name="ltgcconcurrentgt-element"></a>&lt;gcconcurrent —&gt; — Element
Określa, czy środowisko uruchomieniowe języka wspólnego uruchamia wyrzucanie elementów bezużytecznych w oddzielnym wątku.  
  
 \<Konfiguracja >  
\<runtime>  
\<gcconcurrent — >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`enabled`|Atrybut wymagany.<br /><br /> Określa, czy środowisko uruchomieniowe jednocześnie uruchamia wyrzucanie elementów bezużytecznych.|  
  
## <a name="enabled-attribute"></a>Atrybut włączony  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`false`|Nie równoczesne wyrzucanie elementów bezużytecznych.|  
|`true`|Uruchamia współbieżnego wyrzucania elementów bezużytecznych. Domyślnie włączone.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
|`runtime`|Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.|  
  
## <a name="remarks"></a>Uwagi  
 Przed .NET Framework 4 wyrzucanie elementów bezużytecznych obsługiwane współbieżne wyrzucanie elementów bezużytecznych, wykonywane wyrzucania elementów bezużytecznych w tle w oddzielnym wątku. W programie .NET Framework 4 współbieżne wyrzucanie elementów bezużytecznych została zastąpiona GC, który wykonuje wyrzucania elementów bezużytecznych w tle w oddzielnym wątku tła. Począwszy od programu .NET Framework 4.5, zbieranie w tle stały się dostępne w serwer wyrzucania elementów bezużytecznych. `<gcConcurrent>` Element kontroluje, czy środowisko uruchomieniowe wykonuje albo równolegle lub w tle wyrzucanie elementów bezużytecznych, jeśli jest dostępna lub czy wykonuje wyrzucanie elementów bezużytecznych na pierwszym planie.  
  
> [!WARNING]
>  Począwszy od programu .NET Framework 4, współbieżne wyrzucanie elementów bezużytecznych zastępuje wyrzucania elementów bezużytecznych w tle. Warunki *współbieżnych* i *tła* są używane zamiennie w dokumentacji programu .NET Framework. Aby wyłączyć wyrzucania elementów bezużytecznych w tle, należy użyć `<gcConcurrent>` elementu, zgodnie z opisem w tym artykule.  
  
 Domyślnie używa środowiska uruchomieniowego współbieżnych oraz wyrzucania elementów bezużytecznych w tle, który jest zoptymalizowany pod kątem opóźnień. Jeśli aplikacja obejmuje interakcji z użytkownikiem duże, należy pozostawić współbieżne wyrzucanie elementów bezużytecznych, włączone, aby zminimalizować czas wstrzymania aplikacji do wyrzucania elementów bezużytecznych. Jeśli ustawisz `enabled` atrybutu `<gcConcurrent>` elementu `false`, środowisko wykonawcze używa niewspółbieżnym wyrzucaniem elementów bezużytecznych, zoptymalizowaną pod kątem przepływności. Następujący plik konfiguracji wyłącza wyrzucania elementów bezużytecznych w tle.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 W przypadku `<gcConcurrentSetting>` ustawienia w pliku konfiguracji komputera, określa wartość domyślną dla wszystkich aplikacji programu .NET Framework. Ustawienie pliku konfiguracji komputera zastępuje ustawienia pliku konfiguracyjnego aplikacji.  
  
 Aby uzyskać więcej informacji na temat równolegle i wyrzucania elementów bezużytecznych w tle, zobacz sekcję "współbieżne wyrzucanie elementów bezużytecznych" w [podstawowe informacje dotyczące wyrzucania elementów bezużytecznych](../../../../../docs/standard/garbage-collection/fundamentals.md) tematu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład umożliwia współbieżne wyrzucanie elementów bezużytecznych.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też  
- [Schemat ustawień środowiska uruchomieniowego](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Schemat pliku konfiguracji](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Podstawy dotyczące odzyskiwania pamięci](../../../../../docs/standard/garbage-collection/fundamentals.md)
