---
title: 'Porady: modyfikowanie pliku konfiguracji komputera, aby włączyć obsługę protokołu IPv6'
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: 32aa1c3fa50d5c0486da4ef6799c77ead605b504
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187260"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a>Porady: modyfikowanie pliku konfiguracji komputera, aby włączyć obsługę protokołu IPv6
Poniższy przykład kodu pokazuje, jak zmodyfikować plik konfiguracji komputera, *machine.config*, aby włączyć obsługę protokołu IPv6. *Machine.config* plik jest przechowywany w *%Windir%\Microsoft.NET\Framework* folder w katalogu, w którym zainstalowano Windows. Ma osobnej *machine.config* plików w folderach w ramach *%Windir%\Microsoft.NET\Framework* dla każdej wersji programu .NET Framework zainstalowanej na komputerze (na przykład *C:\ WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).  
  
 Ustawienia te można również wprowadzić w pliku konfiguracyjnym aplikacji. Ma on priorytet nad plikiem konfiguracyjnym komputera.  
  
 Dla programu .NET Framework w wersji 1.1 i starszych wartość **włączony protokół ipv6** konfiguracji przełącznik określa czy członkowie <xref:System.Net.Dns?displayProperty=nameWithType> klasy zwracać adresów IPv6.  
  
 Dla programu .NET Framework w wersji 2.0 lub nowszej, jeśli Windows obsługuje protokół IPv6, a następnie wszystkie elementy członkowskie <xref:System.Net.Dns?displayProperty=nameWithType> klasy (na przykład <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> metoda), będzie zwracać adresów IPv6 z jednym z ograniczeń. Przestarzali członkowie <xref:System.Net.Dns?displayProperty=nameWithType> klasy (na przykład <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> metoda) odczytuje i rozpoznać wartości w pliku konfiguracji.  
  
> [!NOTE]
>  .NET Framework w wersji 2.0 lub nowszej domyślnie był włączony protokół IPv6. Dla programu .NET Framework w wersji 1.1 i starsze wersje protokołu IPv6 jest domyślnie wyłączona.  
  
## <a name="example"></a>Przykład  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Adresowanie IPv6](../../../docs/framework/network-programming/ipv6-addressing.md)  
 [Schemat ustawień sieci](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [\<Protokół IPv6 >, Element (ustawienia sieci)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
