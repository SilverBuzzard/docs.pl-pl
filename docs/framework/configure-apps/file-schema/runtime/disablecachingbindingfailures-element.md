---
title: '&lt;disablecachingbindingfailures —&gt; — Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78ca269dacc33fb441310ad00ba2548826f5403e
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610518"
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a>&lt;disablecachingbindingfailures —&gt; — Element
Określa, czy należy wyłączyć buforowanie powiązania błędy, które występują, ponieważ zestaw nie został odnaleziony przez sondowanie.  
  
 \<Konfiguracja > Element  
\<środowisko uruchomieniowe > Element  
\<disablecachingbindingfailures — >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|Włączone|Atrybut wymagany.<br /><br /> Określa, czy należy wyłączyć buforowanie powiązania błędy, które występują, ponieważ zestaw nie został odnaleziony przez sondowanie.|  
  
## <a name="enabled-attribute"></a>Atrybut włączony  
  
|Wartość|Opis|  
|-----------|-----------------|  
|0|Nie należy wyłączać buforowanie powiązania błędy, które występują, ponieważ zestaw nie został odnaleziony przez sondowanie. Jest to domyślne zachowanie powiązania, począwszy od programu .NET Framework w wersji 2.0.|  
|1|Wyłącz buforowanie powiązania błędy, które występują, ponieważ zestaw nie został odnaleziony przez sondowanie. To ustawienie zostanie przywrócony zachowanie wiązania programu .NET Framework w wersji 1.1.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
|`runtime`|Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.|  
  
## <a name="remarks"></a>Uwagi  
 Począwszy od programu .NET Framework w wersji 2.0, domyślne zachowanie ładowania zestawów jest wszystkie powiązania i podczas ładowania błędów w pamięci podręcznej. Oznacza to jeśli próba załadowania zestawu zakończy się niepowodzeniem, kolejne żądania do tego samego zestawu obciążenia nie natychmiast, bez próby zlokalizowania zestawu. Ten element wyłącza tego domyślne zachowanie dla powiązania błędy, które występują, ponieważ nie można odnaleźć zestawu w ścieżce badania. Te błędy throw <xref:System.IO.FileNotFoundException>.  
  
 Niektóre wiązania błędów ładowania nie dotyczy tego elementu i zawsze są buforowane. Te błędy występują, ponieważ zestaw został znaleziony, ale nie można go załadować. Rzuć <xref:System.BadImageFormatException> lub <xref:System.IO.FileLoadException>. Poniższa lista zawiera kilka przykładów tych błędów.  
  
-   Jeśli użytkownik podejmie próbę załadowania pliku nie jest prawidłowym zestawem, kolejne próby załadowania zestawu zakończy się niepowodzeniem, nawet wtedy, gdy nieprawidłowego pliku zostaje zastąpiona opcją poprawny zestaw.  
  
-   Jeśli użytkownik podejmie próbę załadowania zestawu, który jest zablokowany przez system plików, kolejne próby załadowania zestawu zakończy się niepowodzeniem nawet po opublikowaniu zestawu w systemie plików.  
  
-   Co najmniej wersji zestawu, który próbujesz załadować znajduje się w ścieżce badania, ale określonej wersji, którego zażądano nie znajduje się wśród nich, kolejne próby załadowania tej wersji zakończy się niepowodzeniem nawet wtedy, gdy poprawnej wersji jest przenoszony do badania ścieżki.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak wyłączyć buforowanie niepowodzenia powiązań zestawów, które występują, ponieważ zestaw nie został odnaleziony przez sondowanie.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też  
- [Schemat ustawień środowiska uruchomieniowego](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Schemat pliku konfiguracji](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Sposoby lokalizowania zestawów przez środowisko uruchomieniowe](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
