---
title: 'Porady: pobieranie płytkiej wartości elementu (C#)'
ms.date: 07/20/2015
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
ms.openlocfilehash: 2555b2f17120e4dce670a9fef9fc6a126a47e935
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180655"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a>Porady: pobieranie płytkiej wartości elementu (C#)
W tym temacie przedstawiono sposób pobieranie płytkiej wartości elementu. Płytkiej wartości jest wartość określonego elementu, w przeciwieństwie do głębokiego wartość, która zawiera wartości wszystkie elementy potomne połączonych w jeden ciąg.  
  
 Podczas pobierania wartości elementu przy użyciu obu rzutowania lub <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości pobrania głębokiego wartości. Aby pobieranie płytkiej wartości, można użyć `ShallowValue` metodę rozszerzenia, jak pokazano w poniższym przykładzie. Trwa pobieranie płytkiej wartości jest przydatne w przypadku, gdy chcesz wybrać elementy, na podstawie ich zawartości.  
  
 Poniższy przykład deklaruje metodę rozszerzenia, która pobiera płytkiej wartości elementu. Następnie używa metody rozszerzenia w zapytaniu, aby wyświetlić listę wszystkich elementów, które zawierają obliczoną wartość.  
  
## <a name="example"></a>Przykład  
 W następującym pliku tekstowym Report.xml, jest źródłem w tym przykładzie.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a>Zobacz też

- [LINQ do XML osi (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
