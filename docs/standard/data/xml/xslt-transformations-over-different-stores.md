---
title: Przekształcenia XSLT w różnych magazynach
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b5ff264f9a781c95ccf9bdbabf4b29806016362
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890844"
---
# <a name="xslt-transformations-over-different-stores"></a>Przekształcenia XSLT w różnych magazynach
> [!NOTE]
>  <xref:System.Xml.Xsl.XslTransform> Klasy jest przestarzała w [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Można przeprowadzić rozszerzalny język arkusza stylów dla przekształceń przekształcenia (XSLT) przy użyciu <xref:System.Xml.Xsl.XslCompiledTransform> klasy. Zobacz [używanie klasy XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) i [Migrowanie z klasy XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) Aby uzyskać więcej informacji.  
  
 ADO.NET i XML klasy w [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] zapewnia ujednolicony model programowania w celu dostępu do danych. Tych danych jest reprezentowany jako danych XML, który jest tekst rozdzielany według tagów, oraz dane relacyjne, czyli tabelach składających się z wierszy i kolumn. Kod XML w [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] odczytuje dane XML z dowolny strumień danych do drzewa węzła XML Document Object Model (DOM), w którym dane są dostępne programowo, a ADO.NET zapewnia sposób uzyskiwania dostępu i manipulowania danymi relacyjnymi w ramach <xref:System.Data.DataSet> obiektu.  
  
 Modelu DOM języka XML zapewnia dostęp do danych w dokumentach XML i dodatkowych klas do odczytu, zapisu i nawigacja w dokumentach XML. Te klasy są obsługiwane w <xref:System.Xml> przestrzeni nazw, który również łączy modelu DOM języka XML przy użyciu usługi dostępu do danych, które są dostarczane przez ADO.NET. <xref:System.Xml.XmlDataDocument> Zapewnia relacyjnych dostęp do danych. <xref:System.Xml.XmlDataDocument> Mapuje XML w relacyjnej bazie danych w ADO.NET <xref:System.Data.DataSet>. Wszelkie [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]— na podstawie aplikacji można użyć klas w <xref:System.Xml> przestrzeń nazw w celu uzyskiwania dostępu i manipulowania dokumentów XML i dla danych relacyjnych w <xref:System.Xml.XmlDataDocument>. Ta implementacja obsługuje architektury n warstwowa zbierania i dystrybucji danych. Aby uzyskać więcej informacji, zobacz [Integracja XML z danymi relacyjnymi i ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).  
  
## <a name="see-also"></a>Zobacz także

- [Implementowanie procesora XSLT przy użyciu klasy XslTransform](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
