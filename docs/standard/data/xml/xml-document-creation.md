---
title: Tworzenie dokumentu XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b76140fb7d79b1e191c0451cd7556963130d224a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2018
ms.locfileid: "45646184"
---
# <a name="xml-document-creation"></a>Tworzenie dokumentu XML
Istnieją dwa sposoby tworzenia dokumentu XML. Jednym ze sposobów jest utworzenie **XmlDocument** bez parametrów. Innym sposobem jest utworzenie **XmlDocument** i przekazać go tabeli XmlNameTable jako parametr. Poniższy przykład pokazuje, jak utworzyć nowy, pusty **XmlDocument** przy użyciu bez parametrów.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 Po utworzeniu dokumentu, będzie można go załadować z danymi z ciągu, przesyłać strumieniowo, adres URL, czytnika tekstu lub **XmlReader** pochodne klasy przy użyciu **obciążenia** metody. Istnieje również innej metody load, **działanie metody LoadXML** metody, która odczytuje XML z ciągu. Aby uzyskać więcej informacji na temat różnych **obciążenia** metod, zobacz [wczytywanie dokumentu XML do modelu DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 Brak klasy o nazwie **tabeli XmlNameTable**. Ta klasa znajduje się tabela obiektów string rozproszone obiekty. Ta tabela zawiera skuteczne dla analizatora XML do użycia tego samego obiektu ciągu dla elementu wszystkie powtórzone i nazw atrybutów w dokumencie XML. **Tabeli XmlNameTable** zostało automatycznie utworzone po dokumentu jest tworzony, jak pokazano powyżej i jest ładowany z nazwy atrybutu i elementu podczas ładowania dokumentu. Jeśli masz już dokumentu za pomocą nazwy tabeli, a te nazwy może przydać się w innym dokumencie, można utworzyć nowego dokumentu przy użyciu **obciążenia** metody, która przyjmuje **tabeli XmlNameTable** jako parametr. Gdy dokument zostanie utworzony przy użyciu tej metody, wykorzystuje istniejące **tabeli XmlNameTable** ze wszystkimi atrybuty i elementy już załadowane do niego z innych dokumentów. Umożliwia ono wydajnie porównywania nazw elementów i atrybutów. Aby uzyskać więcej informacji na temat **tabeli XmlNameTable**, zobacz [obiektu porównanie przy użyciu tabeli XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md). Aby informacje, zobacz <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>Zobacz także

- [Model DOM (XML Document Object Model)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
