---
title: 'Porady: kontrolowanie prefiksy Namespace (C#) (LINQ do XML)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fc8d652c54be62fdf38e0aa05fcf6a81af3f719b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a><span data-ttu-id="59fd1-102">Porady: kontrolowanie prefiksy Namespace (C#) (LINQ do XML)</span><span class="sxs-lookup"><span data-stu-id="59fd1-102">How to: Control Namespace Prefixes (C#) (LINQ to XML)</span></span>
<span data-ttu-id="59fd1-103">W tym temacie opisano, jak podczas serializowania drzewo XML można kontrolować prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="59fd1-103">This topic describes how you can control namespace prefixes when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="59fd1-104">W wielu sytuacjach nie jest potrzebne do sterowania prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="59fd1-104">In many situations, it is not necessary to control namespace prefixes.</span></span>  
  
 <span data-ttu-id="59fd1-105">Jednak niektóre narzędzia do programowania XML wymagają określonego formantu prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="59fd1-105">However, certain XML programming tools require specific control of namespace prefixes.</span></span> <span data-ttu-id="59fd1-106">Na przykład użytkownik może być manipulowanie arkusz stylów XSLT lub dokumentu XAML, który zawiera osadzony wyrażenia XPath, które odwołują się do określonego obszaru nazw prefiksów; w tym przypadku jest ważne, że dokument być serializowany z tych prefiksów.</span><span class="sxs-lookup"><span data-stu-id="59fd1-106">For example, you might be manipulating an XSLT style sheet or a XAML document that contains embedded XPath expressions that refer to specific namespace prefixes; in this case, it is important that the document be serialized with those specific prefixes.</span></span>  
  
 <span data-ttu-id="59fd1-107">Jest to najbardziej typowe przyczyny kontrolowanie prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="59fd1-107">This is the most common reason for controlling namespace prefixes.</span></span>  
  
 <span data-ttu-id="59fd1-108">Kontrolowanie prefiksy przestrzeni nazw innej typową przyczyną jest użytkownicy mają ręcznie edytować dokument XML, czy chcesz utworzyć prefiksy przestrzeni nazw, które są wygodne dla użytkownika na typ.</span><span class="sxs-lookup"><span data-stu-id="59fd1-108">Another common reason for controlling namespace prefixes is that you want users to edit the XML document manually, and you want to create namespace prefixes that are convenient for the user to type.</span></span> <span data-ttu-id="59fd1-109">Na przykład użytkownik może generować dokumentu XSD.</span><span class="sxs-lookup"><span data-stu-id="59fd1-109">For example, you might be generating an XSD document.</span></span> <span data-ttu-id="59fd1-110">Konwencje dla schematów sugerują, użyj jednej `xs` lub `xsd` jako prefiksu dla przestrzeni nazw schematu.</span><span class="sxs-lookup"><span data-stu-id="59fd1-110">Conventions for schemas suggest that you use either `xs` or `xsd` as the prefix for the schema namespace.</span></span>  
  
 <span data-ttu-id="59fd1-111">Aby kontrolować prefiksy przestrzeni nazw, należy wstawić atrybutów, które zadeklarować przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="59fd1-111">To control namespace prefixes, you insert attributes that declare namespaces.</span></span> <span data-ttu-id="59fd1-112">Deklarowanie przestrzeni nazw z prefiksów, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] podejmie próbę honorować prefiksy przestrzeni nazw podczas serializacji.</span><span class="sxs-lookup"><span data-stu-id="59fd1-112">If you declare the namespaces with specific prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will attempt to honor the namespace prefixes when serializing.</span></span>  
  
 <span data-ttu-id="59fd1-113">Aby utworzyć atrybutu, który deklaruje przestrzeni nazw z prefiksem, należy utworzyć gdzie przestrzeni nazw nazwa atrybutu jest atrybut <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, a nazwa atrybutu to prefiks przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="59fd1-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the namespace of the name of the attribute is <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, and the name of the attribute is the namespace prefix.</span></span> <span data-ttu-id="59fd1-114">Wartość atrybutu jest identyfikatorem URI przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="59fd1-114">The value of the attribute is the URI of the namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59fd1-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="59fd1-115">Example</span></span>  
 <span data-ttu-id="59fd1-116">W tym przykładzie deklaruje dwie przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="59fd1-116">This example declares two namespaces.</span></span> <span data-ttu-id="59fd1-117">Określa, że `http://www.adventure-works.com` przestrzeń nazw ma prefiks `aw`oraz że `www.fourthcoffee.com` przestrzeń nazw ma prefiks `fc`.</span><span class="sxs-lookup"><span data-stu-id="59fd1-117">It specifies that the `http://www.adventure-works.com` namespace has the prefix of `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="59fd1-118">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="59fd1-118">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59fd1-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="59fd1-119">See Also</span></span>  
 [<span data-ttu-id="59fd1-120">Praca z przestrzeni nazw XML (C#)</span><span class="sxs-lookup"><span data-stu-id="59fd1-120">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)