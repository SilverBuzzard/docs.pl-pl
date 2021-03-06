---
title: Programowanie protokołów podłączanych
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- WebResponse class, pluggable protocols
- sending data, pluggable protocols
- network resources, pluggable protocols
- Internet, pluggable protocols
- programming pluggable protocols
- pluggable protocols, programming
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
ms.openlocfilehash: 74dd44e704836b209366a7975d08a43375318e90
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190791"
---
# <a name="programming-pluggable-protocols"></a>Programowanie protokołów podłączanych
Abstrakcyjna <xref:System.Net.WebRequest> i <xref:System.Net.WebResponse> klasy zapewniają base podłączanych protokołów. Przez wyprowadzanie klasy związane z Protokołem z <xref:System.Net.WebRequest> i <xref:System.Net.WebResponse>, aplikacja może dane żądania z zasobem internetowym i uzyskać odpowiedzi bez protokołu używanego do określania.  
  
 Aby można było utworzyć związane z protokołem <xref:System.Net.WebRequest>, należy zarejestrować jego metody Create. Używa się statycznej <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> metody <xref:System.Net.WebRequest> zarejestrować <xref:System.Net.WebRequest> zależne do obsługi zestawu żądań do określonego schematu Internet, schemat i serwer lub do schematu, serwera i ścieżki.  
  
 W większości przypadków będzie wysyłać i odbierać dane przy użyciu metod i właściwości <xref:System.Net.WebRequest> klasy. Jednak jeśli potrzebujesz dostępu do właściwości specyficznych dla protokołu, użytkownik może rzutowanie typu <xref:System.Net.WebRequest> do określonego wystąpienia klasy pochodnej.  
  
 Aby móc korzystać z protokołów podłączanych swoje <xref:System.Net.WebRequest> elementy podrzędne należy podać transakcji żądań i odpowiedzi domyślnej, która nie wymaga ustawiania właściwości specyficzne dla protokołu. Na przykład <xref:System.Net.HttpWebRequest> klasy, która implementuje <xref:System.Net.WebRequest> klasy do obsługi protokołu HTTP, zapewnia `GET` żądanie domyślnie i zwraca <xref:System.Net.HttpWebResponse> zawierający Strumień zwrócony z serwera sieci Web.  
  
## <a name="see-also"></a>Zobacz też  
 [Wyprowadzanie z elementu WebRequest](../../../docs/framework/network-programming/deriving-from-webrequest.md)  
 [Wyprowadzanie z elementu WebResponse](../../../docs/framework/network-programming/deriving-from-webresponse.md)  
 [Programowanie dla sieci w programie .NET Framework](../../../docs/framework/network-programming/index.md)  
 [Instrukcje: rzutowanie elementu WebRequest w celu uzyskania dostępu do właściwości specyficznych dla protokołu](../../../docs/framework/network-programming/how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)
