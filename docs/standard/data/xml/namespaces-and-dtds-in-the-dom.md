---
title: "Obszary nazw i elementów DTD w modelu DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e9b55c4-76ad-4f54-8d96-7ce4b4cf1e05
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 87a03883622ba63a8d999907305356905b36bf1c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="namespaces-and-dtds-in-the-dom"></a><span data-ttu-id="12205-102">Obszary nazw i elementów DTD w modelu DOM</span><span class="sxs-lookup"><span data-stu-id="12205-102">Namespaces and DTDs in the DOM</span></span>
<span data-ttu-id="12205-103">Obsługa definicje (elementów DTD) complicate przestrzeni nazw typu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="12205-103">Document type definitions (DTDs) complicate namespace support.</span></span> <span data-ttu-id="12205-104">Na przykład następujący kod XML zawiera zawierające dwukropki w nazwach atrybutów domyślnych.</span><span class="sxs-lookup"><span data-stu-id="12205-104">For example, the following XML contains default attributes containing colons in their names.</span></span>  
  
```xml  
<!ATTLIST item x:id CDATA #IMPLIED>  
```  
  
 <span data-ttu-id="12205-105">Poniżej przedstawiono możliwe rozwiązania, jeśli ta konstrukcja jest dozwolone:</span><span class="sxs-lookup"><span data-stu-id="12205-105">The following are possible resolutions if this construct is allowed:</span></span>  
  
-   <span data-ttu-id="12205-106">`x:` Jest traktowany jako prefiks przestrzeni nazw, ale ten prefiks musi być rozpoznawalna przy użyciu `xmlns:x` deklaracji przestrzeni nazw musi również istnieć gdzieś w definicji DTD.</span><span class="sxs-lookup"><span data-stu-id="12205-106">The `x:` is treated as a namespace prefix, but this prefix must be resolvable using an `xmlns:x` namespace declaration, which must also exist somewhere in the DTD.</span></span> <span data-ttu-id="12205-107">Istnieje błąd mapowania prefiks na inną w dokumencie wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="12205-107">It is an error to map this prefix to something different in the instance document.</span></span>  
  
-   <span data-ttu-id="12205-108">`x:` Jest traktowany jako prefiks przestrzeni nazw, ale ten prefiks jest zawsze rozwiązane w kontekście elementów wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="12205-108">The `x:` is treated as a namespace prefix, but this prefix is always resolved in the context of the instance elements.</span></span> <span data-ttu-id="12205-109">Oznacza to, że prefiks faktycznie można zamapować na inną przestrzeń nazw Uniform Resource Identifier (URI), w zależności od zakresu przestrzeni nazw, w którym `item` element jest wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="12205-109">This means the prefix could actually map to different namespace Uniform Resource Identifiers (URIs), depending on the namespace scope in which the `item` element appears.</span></span> <span data-ttu-id="12205-110">To zachowanie jest bardziej przewidywalne od rozdzielczości, podany w starszych punktor, ale ma inne konsekwencje skomplikowane, ponieważ wymaga ona materializować domyślne atrybuty.</span><span class="sxs-lookup"><span data-stu-id="12205-110">This behavior is more predictable than the resolution given in the earlier bullet, but it has other complicated ramifications because it requires the default attributes be materialized.</span></span>  
  
-   <span data-ttu-id="12205-111">Dwukropkiem jest ignorowany, ponieważ jest on DTD, a nazwa atrybutu jest `x:y`, bez prefiksu i bez identyfikatora URI przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="12205-111">The colon is ignored because it is in a DTD, and the name of the attribute is `x:y`, no prefix and no namespace URI.</span></span>  
  
-   <span data-ttu-id="12205-112">Dwukropkiem w domyślny atrybut zgłasza wyjątek, informujący o tym, że dwukropków w nazwach wewnątrz DTD nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="12205-112">The colon in the default attribute throws an exception, saying that colons in names inside a DTD are not supported.</span></span> <span data-ttu-id="12205-113">Powoduje to przewidywalne zachowanie, ale oznacza, że nie można załadować wiele sieci World Wide Web konsorcjum W3C opublikowane elementów DTD.</span><span class="sxs-lookup"><span data-stu-id="12205-113">This results in a predictable behavior, but means you cannot load many of the World Wide Web Consortium (W3C) published DTDs.</span></span>  
  
-   <span data-ttu-id="12205-114">Gdy użytkownik zażąda weryfikacji DTD, obsługa przestrzeni nazw w całym dokumencie jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="12205-114">When the user requests DTD validation, namespace support for the entire document is turned off.</span></span> <span data-ttu-id="12205-115">Dzięki temu można załadować definicji DTD W3C i powoduje przewidywalne zachowanie.</span><span class="sxs-lookup"><span data-stu-id="12205-115">This makes it possible to load W3C DTDs and results in a predictable behavior.</span></span>  
  
 <span data-ttu-id="12205-116">Kod XML w programie Microsoft .NET Framework implementuje drugą opcją maksymalną zgodność W3C.</span><span class="sxs-lookup"><span data-stu-id="12205-116">The XML in the Microsoft .NET Framework implements the second option for maximum W3C compatibility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12205-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="12205-117">See Also</span></span>  
 [<span data-ttu-id="12205-118">Modelu obiektu dokumentu XML modelu DOM)</span><span class="sxs-lookup"><span data-stu-id="12205-118">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)