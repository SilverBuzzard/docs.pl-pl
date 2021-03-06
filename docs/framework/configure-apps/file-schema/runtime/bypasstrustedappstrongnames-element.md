---
title: '&lt;bypasstrustedappstrongnames —&gt; — Element'
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59fe6beb359575c818131e1ae502fdebcec5096c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613755"
---
# <a name="ltbypasstrustedappstrongnamesgt-element"></a>&lt;bypasstrustedappstrongnames —&gt; — Element
Określa, czy pominąć weryfikacji silnych nazw zestawów pełnego zaufania, które są ładowane do pełnego zaufania <xref:System.AppDomain>.  
  
 \<Konfiguracja >  
\<runtime>  
\<bypasstrustedappstrongnames — >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`enabled`|Atrybut wymagany.<br /><br /> Określa, czy jest włączona funkcja obejścia, która pozwala uniknąć sprawdzania poprawności silne nazwy dla zestawów pełnego zaufania. Gdy ta funkcja jest włączona, silne nazwy nie są weryfikowane pod kątem poprawności, gdy zestaw jest ładowany. Wartość domyślna to `true`.|  
  
## <a name="enabled-attribute"></a>Atrybut włączony  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`true`|Podpisy silnej nazwy zestawów pełnego zaufania nie są weryfikowane, gdy zestawy są ładowane do pełnego zaufania <xref:System.AppDomain>. Domyślnie włączone.|  
|`false`|Podpisy silnej nazwy zestawów pełnego zaufania są weryfikowane, gdy zestawy są ładowane do pełnego zaufania <xref:System.AppDomain>. Podpis silnej nazwy jest sprawdzany tylko w przypadku poprawność podpisu; nie była porównywana do innego silnej nazwy, pod kątem dopasowania.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
|`runtime`|Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.|  
  
## <a name="remarks"></a>Uwagi  
 Funkcji pomijania silnej nazwy pozwala uniknąć konieczności weryfikacji podpisu silnej nazwy zestawów pełnego zaufania.  
  
 Funkcja pomijania ma zastosowanie do dowolnego złożenia, który jest podpisany silną nazwą i ma następujące cechy:  
  
-   W pełni zaufany, bez <xref:System.Security.Policy.StrongName> dowodów (na przykład `MyComputer` strefa dowód).  
  
-   Ładowany do w pełni zaufany <xref:System.AppDomain>.  
  
-   Ładowane z lokalizacji w obszarze <xref:System.AppDomainSetup.ApplicationBase%2A> właściwość, która <xref:System.AppDomain>.  
  
-   Nie podpisywane z opóźnieniem.  
  
> [!NOTE]
>  Jeśli funkcja pomijania została wyłączona dla wszystkich aplikacji na komputerze przy użyciu klucza rejestru, to ustawienie pliku konfiguracji nie ma wpływu. Aby uzyskać więcej informacji, zobacz [jak: Wyłączanie funkcji pomijania silnej nazwy](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak określić zachowanie, które sprawdza poprawność podpisu silnej nazwy zestawów pełnego zaufania.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też  
- [Schemat ustawień środowiska uruchomieniowego](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Schemat pliku konfiguracji](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Instrukcje: Wyłączanie funkcji pomijania silnej nazwy](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
