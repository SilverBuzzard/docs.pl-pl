---
title: Element &lt;Event&gt; (architektura .NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7ccf013398420dbeb7918f99baa922aa1bc89db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395557"
---
# <a name="lteventgt-element-net-native"></a>Element &lt;Event&gt; (architektura .NET Native)
Zastosowanie zasad wykonywania odbicia do zdarzenia.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Typ atrybutu|Opis|  
|---------------|--------------------|-----------------|  
|`Name`|Ogólne|Atrybut wymagany. Określa nazwę zdarzenia.|  
|`Browse`|Odbicie|Atrybut opcjonalny. Określa, czy wykonywania zapytania dotyczącego informacji o wyliczaniu zdarzenia, ale nie umożliwia dostępu dynamicznej w czasie wykonywania.|  
|`Dynamic`|Odbicie|Atrybut opcjonalny. Formanty środowiska uruchomieniowego dostęp do zdarzeń, aby włączyć dynamiczne programowania. Ta zasada zapewnia, że zdarzenia można obsługiwać dynamicznie w czasie wykonywania.|  
  
## <a name="name-attribute"></a>Nazwa atrybutu  
  
|Wartość|Opis|  
|-----------|-----------------|  
|*method_name*|Nazwa zdarzenia. Typ zdarzenia jest zdefiniowany przez nadrzędny [ \<typu >](../../../docs/framework/net-native/type-element-net-native.md) lub [ \<TypeInstantiation >](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elementu.|  
  
## <a name="all-other-attributes"></a>Inne atrybuty  
  
|Wartość|Opis|  
|-----------|-----------------|  
|*policy_setting*|Ustawienia do zastosowania dla tego typu zasad dla zdarzenia. Możliwe wartości to `Auto`, `Excluded`, `Included`, i `Required`. Aby uzyskać więcej informacji, zobacz [ustawienia zasad dyrektyw środowiska uruchomieniowego](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Stosuje odbicia zasady do typu i jej elementów członkowskich.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Stosuje zasady odbicia do skonstruowanego typu ogólnego i jej elementów członkowskich.|  
  
## <a name="remarks"></a>Uwagi  
 Jeśli zasady zdarzeń nie jest jawnie zdefiniowany, dziedziczy zasad wykonywania jego elementu nadrzędnego.  
  
## <a name="see-also"></a>Zobacz też  
 [Dokumentacja pliku konfiguracji dyrektyw środowiska uruchomieniowego (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Elementy dyrektyw środowiska uruchomieniowego](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [Ustawienia zasad dyrektyw środowiska uruchomieniowego](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
