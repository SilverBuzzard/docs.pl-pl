---
title: Wydajność zapytań łańcuchowych (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: 9377c4e57eb19f133a1f973ea7f86c3bf72e4cf8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "43854583"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a>Wydajność zapytań łańcuchowych (LINQ to XML) (C#)
Jedną z najważniejszych zalet LINQ (i LINQ to XML) jest to, że zapytań łańcuchowych może wykonywać oraz pojedynczego zapytania większych i bardziej skomplikowane.  
  
 Łańcuchowe zapytań jest zapytanie, które używa innego zapytania jako źródło. Na przykład w poniższym kodzie prosty `query2` ma `query1` jako źródło:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    new XElement("Child", 3),  
    new XElement("Child", 4)  
);  
  
var query1 = from x in root.Elements("Child")  
             where (int)x >= 3  
             select x;  
  
var query2 = from e in query1  
             where (int)e % 2 == 0  
             select e;  
  
foreach (var i in query2)  
    Console.WriteLine("{0}", (int)i);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```  
4  
```  
  
 To zapytanie łańcuchowych zawiera ten sam profil wydajności jako iteracji przez listę połączoną.  
  
-   <xref:System.Xml.Linq.XContainer.Elements%2A> Osi jest zasadniczo ta sama wydajność co iteracji przez listę połączoną. <xref:System.Xml.Linq.XContainer.Elements%2A> jest implementowany jako iterator za pomocą odroczonego wykonania. Oznacza to, że robi jakąś pracę dodatkowo do iteracji w połączonej listy, takich jak obiekt iteratora do przydzielania i śledzeniu stanu wykonywania. Tę pracę można podzielić na dwie kategorie: prac, które odbywa się w czasie, o których iterator który jest skonfigurowany i czynności, które odbywa się podczas każdej iteracji. Praca Instalatora jest mały, stały ilość pracy i Praca wykonana podczas każdej iteracji jest proporcjonalna do liczby elementów w kolekcji źródłowej.  
  
-   W `query1`, `where` klauzuli powoduje, że zapytanie, aby wywołać <xref:System.Linq.Enumerable.Where%2A> metody. Ta metoda jest również implementowana jako iterator. Praca Instalatora składa się z tworzenia wystąpienia delegata, który będzie odwoływać się do wyrażenia lambda oraz zwykłej instalacji dla iteratora. Z każdą iteracją delegat jest wywoływana, aby wykonać predykat. Praca Instalatora i pracy wykonanej w każdej iteracji jest podobny do pracy wykonanej podczas iteracji osi.  
  
-   W `query1`, klauzula select powoduje, że zapytanie, aby wywołać <xref:System.Linq.Enumerable.Select%2A> metody. Ta metoda ma ten sam profil wydajności jako <xref:System.Linq.Enumerable.Where%2A> metody.  
  
-   W `query2`, zarówno `where` klauzuli i `select` klauzuli mieć ten sam profil wydajności, podobnie jak w `query1`.  
  
 Iteracja przez `query2` jest zatem bezpośrednio proporcjonalnie do liczby elementów w źródle pierwsze zapytanie, innymi słowy, liniowo. Odpowiedni przykład Visual Basic będą mieć ten sam profil wydajności.  
  
 Aby uzyskać więcej informacji dotyczących iteratorów, zobacz [uzyskanie](../../../../csharp/language-reference/keywords/yield.md).  
  
 Aby uzyskać bardziej szczegółowy samouczek dotyczący Łączenie łańcuchowe zapytań, zobacz [samouczek: tworzenie łańcuchów zapytań razem](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).  
  
## <a name="see-also"></a>Zobacz też

- [Wydajność (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
