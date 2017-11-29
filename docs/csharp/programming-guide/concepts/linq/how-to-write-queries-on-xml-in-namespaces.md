---
title: "Porady: Pisanie zapytań na kod XML w przestrzeni nazw (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 194e12f88f7c22c365a18bc2dd42a3dd26b5c569
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a><span data-ttu-id="5fea8-102">Porady: Pisanie zapytań na kod XML w przestrzeni nazw (C#)</span><span class="sxs-lookup"><span data-stu-id="5fea8-102">How to: Write Queries on XML in Namespaces (C#)</span></span>
<span data-ttu-id="5fea8-103">Aby napisać zapytanie na języku XML, który znajduje się w przestrzeni nazw, należy użyć <xref:System.Xml.Linq.XName> obiektów, które mają poprawną przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="5fea8-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="5fea8-104">Język C#, najbardziej typowym podejściem jest zainicjowanie <xref:System.Xml.Linq.XNamespace> przy użyciu ciągu, który zawiera identyfikator URI, następnie za pomocą dodanie przeciążenia operatora łączenia przestrzeni nazw z nazwą lokalną.</span><span class="sxs-lookup"><span data-stu-id="5fea8-104">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>  
  
 <span data-ttu-id="5fea8-105">Pierwszy zestaw przykłady w tym temacie przedstawiono sposób tworzenia drzewo XML w domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="5fea8-105">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="5fea8-106">Drugi zestaw pokazano, jak utworzyć drzewo XML w przestrzeni nazw z prefiksem.</span><span class="sxs-lookup"><span data-stu-id="5fea8-106">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fea8-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="5fea8-107">Example</span></span>  
 <span data-ttu-id="5fea8-108">Poniższy przykład tworzy drzewo XML, który znajduje się w domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="5fea8-108">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="5fea8-109">Następnie pobierania kolekcję elementów.</span><span class="sxs-lookup"><span data-stu-id="5fea8-109">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="5fea8-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="5fea8-110">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="5fea8-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="5fea8-111">Example</span></span>  
 <span data-ttu-id="5fea8-112">W języku C# możesz pisać zapytania w taki sam sposób, niezależnie od tego, czy pisania zapytania na drzewo XML, który używa przestrzeni nazw z prefiksem lub drzewo XML z domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="5fea8-112">In C#, you write queries in the same way regardless of whether you are writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>  
  
 <span data-ttu-id="5fea8-113">Poniższy przykład tworzy drzewo XML, który znajduje się w przestrzeni nazw z prefiksem.</span><span class="sxs-lookup"><span data-stu-id="5fea8-113">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="5fea8-114">Następnie pobierania kolekcję elementów.</span><span class="sxs-lookup"><span data-stu-id="5fea8-114">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="5fea8-115">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="5fea8-115">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fea8-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5fea8-116">See Also</span></span>  
 [<span data-ttu-id="5fea8-117">Praca z przestrzeni nazw XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5fea8-117">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)