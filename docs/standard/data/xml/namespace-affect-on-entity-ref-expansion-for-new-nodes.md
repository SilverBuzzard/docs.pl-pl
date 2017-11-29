---
title: "Namespace ma to wpływu na jednostki odwołanie do rozszerzenia dla nowych węzłów zawierających elementy i atrybuty"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 39110a9b44e6efbe7ad0331cfdb4fbe6078e7cfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a><span data-ttu-id="aa1c2-102">Namespace ma to wpływu na jednostki odwołanie do rozszerzenia dla nowych węzłów zawierających elementy i atrybuty</span><span class="sxs-lookup"><span data-stu-id="aa1c2-102">Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes</span></span>
<span data-ttu-id="aa1c2-103">Treść jednostki deklaracji może zawierać prawie wszystko, istnieje możliwość, że zawartość może zawierać elementu jak `<!ENTITY aname "<elem>test</elem>">`.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-103">Because the content of an entity declaration can contain almost anything, there is a possibility that the content could contain an element like `<!ENTITY aname "<elem>test</elem>">`.</span></span>  
  
 <span data-ttu-id="aa1c2-104">Podczas analizowania pliku XML `&aname;` z zawartością zamiany nie jest rozwinięty w czasie analizy.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-104">When the XML is parsed, `&aname;` is not expanded with its replacement content at parse time.</span></span> <span data-ttu-id="aa1c2-105">Rozszerzenie pliku XML nie jest wykonywana, ponieważ rozpoznawania nazw dla elementu nie może wystąpić, dopóki węzeł znajduje się w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-105">The expansion of the XML is not done because resolution of the namespace for the element cannot occur until the node is placed in the document.</span></span> <span data-ttu-id="aa1c2-106">Do tego czasu nie jest nie wie, jakiego przestrzeni nazw, który znajduje się w zakresie.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-106">Until that time, there is no knowledge of what namespace is in scope.</span></span> <span data-ttu-id="aa1c2-107">Gdy węzeł jest włączony do dokumentu, rozpoznawane przestrzeni nazw, a wynikowy jednostki zawartości jest analizowana w jego odpowiednich węzłów.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-107">When the node is put into the document, then the namespace resolution occurs, and the resulting entity content is parsed into its appropriate nodes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa1c2-108">W momencie rozszerzenia w węźle odwołania nowo utworzonej jednostki go nigdy nie wystąpi ponownie.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-108">Once the expansion occurs on a newly created entity reference node, it never reoccurs.</span></span> <span data-ttu-id="aa1c2-109">W związku z tym w czasie węzła nadrzędnego jest ustawiona, są powiązane obszarów nazw używanych w tekst zastępczy dla elementu.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-109">Therefore, the namespaces used in the replacement text for the element are bound at the time that the parent node is set.</span></span> <span data-ttu-id="aa1c2-110">Jednak można zmienić przestrzeni nazw dla istniejących węzłów odwołanie do jednostki po usunięciu i wstawić je w innej lokalizacji lub na węzłach odwołanie do jednostki, które są klonowane z **CloneNode** metody.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-110">However, the namespace can be changed for existing entity reference nodes when you remove and insert them somewhere else, or on entity reference nodes that are cloned with the **CloneNode** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1c2-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aa1c2-111">See Also</span></span>  
 [<span data-ttu-id="aa1c2-112">Modelu obiektu dokumentu XML modelu DOM)</span><span class="sxs-lookup"><span data-stu-id="aa1c2-112">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)