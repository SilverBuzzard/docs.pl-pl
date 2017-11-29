---
title: "LINQ do XML-Przegląd klasy (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bf666100-5392-4968-97f4-f6b9d3287d7b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0dc4307c3cf87fa9b5cb38bdaa9d9bf77adf1424
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-classes-overview-c"></a><span data-ttu-id="4878e-102">LINQ do XML-Przegląd klasy (C#)</span><span class="sxs-lookup"><span data-stu-id="4878e-102">LINQ to XML Classes Overview (C#)</span></span>
<span data-ttu-id="4878e-103">Ten temat zawiera listę [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] klas w <xref:System.Xml.Linq> przestrzeni nazw oraz krótki opis każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="4878e-103">This topic provides a list of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>  
  
## <a name="linq-to-xml-classes"></a><span data-ttu-id="4878e-104">LINQ do XML klas</span><span class="sxs-lookup"><span data-stu-id="4878e-104">LINQ to XML Classes</span></span>  
  
### <a name="xattribute-class"></a><span data-ttu-id="4878e-105">Klasa XAttribute</span><span class="sxs-lookup"><span data-stu-id="4878e-105">XAttribute Class</span></span>  
 <span data-ttu-id="4878e-106"><xref:System.Xml.Linq.XAttribute>reprezentuje atrybut XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-106"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="4878e-107">Aby uzyskać szczegółowe informacje i przykłady, zobacz [XAttribute Przegląd klasy (C#)](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4878e-107">For detailed information and examples, see [XAttribute Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md).</span></span>  
  
### <a name="xcdata-class"></a><span data-ttu-id="4878e-108">Klasa XCData</span><span class="sxs-lookup"><span data-stu-id="4878e-108">XCData Class</span></span>  
 <span data-ttu-id="4878e-109"><xref:System.Xml.Linq.XCData>reprezentuje węzeł tekstowy CDATA.</span><span class="sxs-lookup"><span data-stu-id="4878e-109"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>  
  
### <a name="xcomment-class"></a><span data-ttu-id="4878e-110">Klasa XComment</span><span class="sxs-lookup"><span data-stu-id="4878e-110">XComment Class</span></span>  
 <span data-ttu-id="4878e-111"><xref:System.Xml.Linq.XComment>reprezentuje komentarz XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-111"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>  
  
### <a name="xcontainer-class"></a><span data-ttu-id="4878e-112">Klasa XContainer</span><span class="sxs-lookup"><span data-stu-id="4878e-112">XContainer Class</span></span>  
 <span data-ttu-id="4878e-113"><xref:System.Xml.Linq.XContainer>jest to abstrakcyjna klasa podstawowa dla wszystkich węzłów, które mogą mieć węzłów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="4878e-113"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="4878e-114">Następujące klasy pochodzi od <xref:System.Xml.Linq.XContainer> klasy:</span><span class="sxs-lookup"><span data-stu-id="4878e-114">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a><span data-ttu-id="4878e-115">Klasa XDeclaration</span><span class="sxs-lookup"><span data-stu-id="4878e-115">XDeclaration Class</span></span>  
 <span data-ttu-id="4878e-116"><xref:System.Xml.Linq.XDeclaration>reprezentuje deklaracji XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-116"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="4878e-117">Deklaracja XML służy do deklarowania wersji XML i kodowania dokumentu.</span><span class="sxs-lookup"><span data-stu-id="4878e-117">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="4878e-118">Ponadto deklaracja XML określa, czy dokument XML jest autonomiczny.</span><span class="sxs-lookup"><span data-stu-id="4878e-118">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="4878e-119">Jeśli dokument jest autonomicznym, nie ma żadnych deklaracji znaczników zewnętrznych, w zewnętrznej definicji DTD lub w jednostce parametru zewnętrzne odwołanie z podzestawu wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="4878e-119">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>  
  
### <a name="xdocument-class"></a><span data-ttu-id="4878e-120">Klasy XDocument</span><span class="sxs-lookup"><span data-stu-id="4878e-120">XDocument Class</span></span>  
 <span data-ttu-id="4878e-121"><xref:System.Xml.Linq.XDocument>reprezentuje dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-121"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="4878e-122">Aby uzyskać szczegółowe informacje i przykłady, zobacz [Przegląd klasy XDocument (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4878e-122">For detailed information and examples, see [XDocument Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
### <a name="xdocumenttype-class"></a><span data-ttu-id="4878e-123">Klasa XDocumentType</span><span class="sxs-lookup"><span data-stu-id="4878e-123">XDocumentType Class</span></span>  
 <span data-ttu-id="4878e-124"><xref:System.Xml.Linq.XDocumentType>reprezentuje dokumentu typu Definition (definicja DTD dokumentu XML).</span><span class="sxs-lookup"><span data-stu-id="4878e-124"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>  
  
### <a name="xelement-class"></a><span data-ttu-id="4878e-125">Klasy XElement — klasa</span><span class="sxs-lookup"><span data-stu-id="4878e-125">XElement Class</span></span>  
 <span data-ttu-id="4878e-126"><xref:System.Xml.Linq.XElement>reprezentuje XML element.</span><span class="sxs-lookup"><span data-stu-id="4878e-126"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="4878e-127">Aby uzyskać szczegółowe informacje i przykłady, zobacz [klasy XElement Przegląd klasy (C#)](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4878e-127">For detailed information and examples, see [XElement Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md).</span></span>  
  
### <a name="xname-class"></a><span data-ttu-id="4878e-128">Klasa XName</span><span class="sxs-lookup"><span data-stu-id="4878e-128">XName Class</span></span>  
 <span data-ttu-id="4878e-129"><xref:System.Xml.Linq.XName>reprezentuje nazwy elementów (<xref:System.Xml.Linq.XElement>) i atrybuty (<xref:System.Xml.Linq.XAttribute>).</span><span class="sxs-lookup"><span data-stu-id="4878e-129"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="4878e-130">Aby uzyskać szczegółowe informacje i przykłady, zobacz [Przegląd klasy XDocument (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4878e-130">For detailed information and examples, see [XDocument Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="4878e-131">Umożliwia nazw XML równie proste, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="4878e-131"> is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="4878e-132">Ze względu na złożoność nazwy XML są często uważane zaawansowane tematu w kodzie XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-132">Due to their complexity, XML names are often considered to be an advanced topic in XML.</span></span> <span data-ttu-id="4878e-133">Można przypuszczać, że ta złożoności pochodzi nie z przestrzeni nazw, deweloperom używany regularnie programowania, ale z prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4878e-133">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="4878e-134">Prefiksy Namespace może być przydatna, aby zmniejszyć naciśnięcia klawiszy wymagane podczas wprowadzania danych XML lub aby ułatwić XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-134">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="4878e-135">Jednak prefiksy są często tylko skrót przy użyciu pełnego przestrzeni nazw XML i nie są wymagane w większości przypadków.</span><span class="sxs-lookup"><span data-stu-id="4878e-135">However, prefixes are often just a shortcut for using the full XML namespace, and are not required in most cases.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="4878e-136">upraszcza nazw XML, rozwiązując wszystkie prefiksy do ich odpowiednich przestrzeni nazw XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-136"> simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="4878e-137">Prefiksy są dostępne, jeśli są wymagane przez <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="4878e-137">Prefixes are available, if they are required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>  
  
 <span data-ttu-id="4878e-138">Jest to możliwe, jeśli to konieczne, aby formant prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4878e-138">It is possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="4878e-139">W niektórych sytuacjach podczas pracy z innymi systemami XML, takiego jak XSLT lub XAML, należy kontrolować prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4878e-139">In some circumstances, if you are working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="4878e-140">Na przykład jeśli wyrażenie XPath, która korzysta z prefiksy przestrzeni nazw i jest osadzony w arkusz stylów XSLT, należy się upewnić, że dokument XML jest serializowany z prefiksy przestrzeni nazw, które pasują do wyrażenia XPath.</span><span class="sxs-lookup"><span data-stu-id="4878e-140">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>  
  
### <a name="xnamespace-class"></a><span data-ttu-id="4878e-141">Klasa XNamespace</span><span class="sxs-lookup"><span data-stu-id="4878e-141">XNamespace Class</span></span>  
 <span data-ttu-id="4878e-142"><xref:System.Xml.Linq.XNamespace>reprezentuje obszar nazw dla <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4878e-142"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="4878e-143">Przestrzenie nazw są składnika <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="4878e-143">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>  
  
### <a name="xnode-class"></a><span data-ttu-id="4878e-144">Klasa XNode</span><span class="sxs-lookup"><span data-stu-id="4878e-144">XNode Class</span></span>  
 <span data-ttu-id="4878e-145"><xref:System.Xml.Linq.XNode>jest klasą abstrakcyjną, reprezentujący węzły drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-145"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="4878e-146">Następujące klasy pochodzi od <xref:System.Xml.Linq.XNode> klasy:</span><span class="sxs-lookup"><span data-stu-id="4878e-146">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>  
  
-   <xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="4878e-147">Klasa XNodeDocumentOrderComparer</span><span class="sxs-lookup"><span data-stu-id="4878e-147">XNodeDocumentOrderComparer Class</span></span>  
 <span data-ttu-id="4878e-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer>zapewnia funkcje do porównania węzły ich kolejności dokumentu.</span><span class="sxs-lookup"><span data-stu-id="4878e-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>  
  
### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="4878e-149">Klasa XNodeEqualityComparer</span><span class="sxs-lookup"><span data-stu-id="4878e-149">XNodeEqualityComparer Class</span></span>  
 <span data-ttu-id="4878e-150"><xref:System.Xml.Linq.XNodeEqualityComparer>zapewnia funkcje do porównania węzły równości wartości.</span><span class="sxs-lookup"><span data-stu-id="4878e-150"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>  
  
### <a name="xobject-class"></a><span data-ttu-id="4878e-151">Klasa XObject</span><span class="sxs-lookup"><span data-stu-id="4878e-151">XObject Class</span></span>  
 <span data-ttu-id="4878e-152"><xref:System.Xml.Linq.XObject>jest abstrakcyjna klasa podstawowa dla <xref:System.Xml.Linq.XNode> i <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4878e-152"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="4878e-153">Zawiera funkcję adnotacji i zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="4878e-153">It provides annotation and event functionality.</span></span>  
  
### <a name="xobjectchange-class"></a><span data-ttu-id="4878e-154">Klasa XObjectChange</span><span class="sxs-lookup"><span data-stu-id="4878e-154">XObjectChange Class</span></span>  
 <span data-ttu-id="4878e-155"><xref:System.Xml.Linq.XObjectChange>Określa typ zdarzenia, gdy zdarzenie jest wywoływane dla <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="4878e-155"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>  
  
### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="4878e-156">Klasa XObjectChangeEventArgs</span><span class="sxs-lookup"><span data-stu-id="4878e-156">XObjectChangeEventArgs Class</span></span>  
 <span data-ttu-id="4878e-157"><xref:System.Xml.Linq.XObjectChangeEventArgs>udostępnia dane dla <xref:System.Xml.Linq.XObject.Changing> i <xref:System.Xml.Linq.XObject.Changed> zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4878e-157"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>  
  
### <a name="xprocessinginstruction-class"></a><span data-ttu-id="4878e-158">Klasa XProcessingInstruction</span><span class="sxs-lookup"><span data-stu-id="4878e-158">XProcessingInstruction Class</span></span>  
 <span data-ttu-id="4878e-159"><xref:System.Xml.Linq.XProcessingInstruction>reprezentuje instrukcji przetwarzania XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-159"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="4878e-160">Instrukcja przetwarzania komunikuje się informacji do aplikacji, która przetwarza dane XML.</span><span class="sxs-lookup"><span data-stu-id="4878e-160">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
### <a name="xtext-class"></a><span data-ttu-id="4878e-161">Klasa XText</span><span class="sxs-lookup"><span data-stu-id="4878e-161">XText Class</span></span>  
 <span data-ttu-id="4878e-162"><xref:System.Xml.Linq.XText>reprezentuje węzeł tekstowy.</span><span class="sxs-lookup"><span data-stu-id="4878e-162"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="4878e-163">W większości przypadków nie trzeba używać tej klasy.</span><span class="sxs-lookup"><span data-stu-id="4878e-163">In most cases, you do not have to use this class.</span></span> <span data-ttu-id="4878e-164">Ta klasa jest używana głównie dla zawartości mieszanej.</span><span class="sxs-lookup"><span data-stu-id="4878e-164">This class is primarily used for mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4878e-165">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4878e-165">See Also</span></span>  
 [<span data-ttu-id="4878e-166">LINQ do XML-przegląd programowania w języku (C#)</span><span class="sxs-lookup"><span data-stu-id="4878e-166">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)