---
title: 'Porady: znajdowanie poprzednich elementów równorzędnych (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
ms.openlocfilehash: d2bd34db7bd839e50ec3e77819230f5f6410b73e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787125"
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a>Porady: znajdowanie poprzednich elementów równorzędnych (XPath-LINQ to XML) (C#)
W tym temacie porównano XPath `preceding-sibling` osi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] podrzędnych <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> osi.  
  
 Wyrażenie XPath jest:  
  
 `preceding-sibling::*`  
  
 Należy pamiętać, że wyniki zarówno <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> i <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> znajdują się w kolejności dokumentu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład umożliwia znalezienie `FullAddress` elementu, a następnie pobierze poprzednich elementów przy użyciu `preceding-sibling` osi.  
  
 W tym przykładzie użyto następujący dokument XML: [przykładowy plik XML: Klienci i zamówienia (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
  
XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();  
  
// XPath expression  
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
  
## <a name="see-also"></a>Zobacz też

- [LINQ to XML dla użytkowników metody XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
