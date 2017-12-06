---
title: "Ustawia węzeł w przekształcenia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4d6d2f5a68ce5cef9937edc136e52efcd5366df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="node-sets-in-transformations"></a><span data-ttu-id="070eb-102">Ustawia węzeł w przekształcenia</span><span class="sxs-lookup"><span data-stu-id="070eb-102">Node Sets in Transformations</span></span>
<span data-ttu-id="070eb-103">Zestaw węzłów są jednym z cztery typy podstawowe dane, które zostaną zwrócone z wyrażenia XML Path Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="070eb-103">Node sets are one of four basic data types that are returned from XML Path Language (XPath) expressions.</span></span> <span data-ttu-id="070eb-104">Zestaw węzłów, które nieuporządkowaną zbiór węzłów bez duplikatów, utworzony w kolejności dokumentu, można przypisać do zmiennej w arkuszu stylów.</span><span class="sxs-lookup"><span data-stu-id="070eb-104">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="070eb-105"><xref:System.Xml.Xsl.XslTransform> Klasa jest przestarzała w [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="070eb-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="070eb-106">Może wykonywać rozszerzalny język arkusza stylów dla transformacji przekształcenia XSLT () przy użyciu <xref:System.Xml.Xsl.XslCompiledTransform> klasy.</span><span class="sxs-lookup"><span data-stu-id="070eb-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="070eb-107">Zobacz [za pomocą klasy XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) i [migracji z klasy XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) Aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="070eb-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="070eb-108">Zestaw węzłów są jednym z cztery typy podstawowe dane, które zostaną zwrócone z wyrażenia XPath.</span><span class="sxs-lookup"><span data-stu-id="070eb-108">Node sets are one of four basic data types that are returned from XPath expressions.</span></span> <span data-ttu-id="070eb-109">Zestaw węzłów, które nieuporządkowaną zbiór węzłów bez duplikatów, utworzony w kolejności dokumentu, można przypisać do zmiennej w arkuszu stylów.</span><span class="sxs-lookup"><span data-stu-id="070eb-109">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span> <span data-ttu-id="070eb-110">Tego zestawu węzłów jest wynikiem wyrażenia używane w XPath `select` atrybutu w transformację, zachowanie jest takie samo jako węzeł ustawić z XML modelu DOM (Document Object).</span><span class="sxs-lookup"><span data-stu-id="070eb-110">This node set, which is a result of an XPath expression used in a `select` attribute in a transformation, has the same behavior as a node set from the XML Document Object Model (DOM).</span></span> <span data-ttu-id="070eb-111">Można przejść węzła ustawić przy użyciu zestawu metod przedstawiono w [węzła ustawić nawigacji przy użyciu Element XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), w odróżnieniu od wynikowego fragmentu drzewa lub wynikowego fragmentu drzewa, który używa <xref:System.Xml.XPath.XPathNodeIterator> nawigacji.</span><span class="sxs-lookup"><span data-stu-id="070eb-111">You can navigate a node set using a set of methods shown in [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), unlike a result tree fragment or result tree fragment, which uses the <xref:System.Xml.XPath.XPathNodeIterator> for navigation.</span></span>  
  
 <span data-ttu-id="070eb-112">Poniższy przykładowy kod przedstawia sposób wykonania iteracji w węźle ustawiane podczas `variable` lub `parameter` elementu w arkuszu stylów ocenia się na zestaw węzłów.</span><span class="sxs-lookup"><span data-stu-id="070eb-112">The following code sample shows how to iterate over a node set when a `variable` or `parameter` element in a style sheet evaluates to a node set.</span></span>  
  
## <a name="style-sheet"></a><span data-ttu-id="070eb-113">Arkusz stylów</span><span class="sxs-lookup"><span data-stu-id="070eb-113">Style Sheet</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
    <xsl:variable name="x" select="bookstore/book/title"></xsl:variable>  
  
    <xsl:template match="/">  
        <xsl:for-each select="$x">  
            ******  
            <xsl:value-of select="."></xsl:value-of>  
            ******  
        </xsl:for-each>  
    </xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="input"></a><span data-ttu-id="070eb-114">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="070eb-114">Input</span></span>  
  
```xml  
<bookstore>  
   <book style="autobiography">  
      <title>Seven Years in Trenton</title>  
   </book>  
  
   <book style="autobiography">  
      <title>Seven Years in Trenton2</title>  
   </book>  
  
   <book style="textbook">  
      <title>History of Trenton Vol 3</title>  
   </book>  
</bookstore>  
```  
  
## <a name="output"></a><span data-ttu-id="070eb-115">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="070eb-115">Output</span></span>  
  
```  
******  
Seven Years in Trenton  
******  
  
******  
Seven Years in Trenton2  
******  
  
******  
History of Trenton Vol 3  
******  
```  
  
## <a name="see-also"></a><span data-ttu-id="070eb-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="070eb-116">See Also</span></span>  
 <xref:System.Xml.XPath.XPathNodeIterator>  
 [<span data-ttu-id="070eb-117">Przekształcenia XSLT przy użyciu klasy XslTransform</span><span class="sxs-lookup"><span data-stu-id="070eb-117">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [<span data-ttu-id="070eb-118">Klasa XslTransform implementuje procesorze XSLT</span><span class="sxs-lookup"><span data-stu-id="070eb-118">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)