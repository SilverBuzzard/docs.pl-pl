---
title: Architektura WCF i międzynarodowe nazwy domen
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: a0d4a5b4fe5dd3bc7cf41c8c6ad320dd83861aec
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187926"
---
# <a name="wcf-and-internationalized-domain-names"></a>Architektura WCF i międzynarodowe nazwy domen
Dodano obsługę do obsługi usług WCF za pomocą nazw międzynarodowych domen (IDN). Międzynarodowa nazwa domeny jest nazwa domeny, który zawiera znaki spoza zestawu ASCII. Ta obsługa obejmuje możliwość hostowanie usługi WCF przy użyciu nazwy IDN i klienta programu WCF na komunikowanie się z usługą sieci web o nazwie IDN.  
  
## <a name="systemuri-and-idn"></a>System.Uri i IDN  
 <xref:System.Uri> ma dwie właściwości <xref:System.Uri.Host%2A> i <xref:System.Uri.DnsSafeHost%2A>. Te właściwości zawierają wartości Unicode lub Punycode, w zależności od ustawień konfiguracji IDN.  
  
 IDN jest włączone w pliku konfiguracji aplikacji przy użyciu następujący kod XML  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 \<Idn > element zawiera atrybut włączony, którą można ustawić na jeden z następujących wartości:  
  
1.  "None"  
  
2.  "AllExceptIntranet"  
  
3.  "Wszystkie"  
  
 Gdy ustawienie IDN ma wartość "None", nie konwersje są wykonywane przez Uri.Host lub Uri.DnsSafeHost. Jeśli ustawienie IDN jest równa "All", identyfikator uri. Host pozostaje Unicode i identyfikatora uri. DnsSafeHost jest konwertowana na ciąg Punycode. Jeśli ustawienie IDN, jest równa "AllExceptIntranet", identyfikator uri. DnsSafeHost jest konwertowana na ciąg Punycode w przypadku adresów internetowych i pozostaje Unicode dla adresów w sieci intranet. To ustawienie jest ważne dla poprawnego rozpoznawania nazw DNS. Należy pamiętać, że to ustawienie nie jest wymagane do skonfigurowania dla systemu Windows 8 i nowszych wersji.  
  
> [!WARNING]
>  Powinno nigdy trwale kodować adresu przy użyciu Punycode. Usługi WCF przekonwertuje go na podstawie ustawień konfiguracji, które należy zastosować.  
  
> [!WARNING]
>  Podczas dodawania znaków Unicode do applicationHost.exe.config, Zapisz plik przy użyciu kodowania UTF-8.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Uri?displayProperty=nameWithType>
