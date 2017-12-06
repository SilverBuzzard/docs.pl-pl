---
title: "Porady: zwijanie i ukrywanie fragmentów kodu (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56a31f0c8af9b84e87ebe1e5191d72d19be8340f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="0d40c-102">Porady: zwijanie i ukrywanie fragmentów kodu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d40c-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="0d40c-103">`#Region` Dyrektywy umożliwia zwijanie i ukrywanie fragmentów kodu w [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] plików.</span><span class="sxs-lookup"><span data-stu-id="0d40c-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files.</span></span> <span data-ttu-id="0d40c-104">`#Region` Dyrektywy pozwala określić blok kodu, który można rozwinąć lub Zwiń, korzystając z [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] edytora kodu.</span><span class="sxs-lookup"><span data-stu-id="0d40c-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] code editor.</span></span> <span data-ttu-id="0d40c-105">Możliwość selektywnego ukrywanie kodu sprawia, że pliki można zarządzać i czytelne.</span><span class="sxs-lookup"><span data-stu-id="0d40c-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="0d40c-106">Aby uzyskać więcej informacji, zobacz [Tworzenie konspektu](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="0d40c-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="0d40c-107">`#Region`dyrektywy obsługuje semantyki blok kodu `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="0d40c-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="0d40c-108">Oznacza to nie może zaczynać się jeden blok, a kończyć się w innym; rozpoczęcia i zakończenia musi być w tym samym bloku.</span><span class="sxs-lookup"><span data-stu-id="0d40c-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="0d40c-109">`#Region`dyrektywy nie są obsługiwane w funkcjach.</span><span class="sxs-lookup"><span data-stu-id="0d40c-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="0d40c-110">Zwijanie i ukrywanie sekcji kodu</span><span class="sxs-lookup"><span data-stu-id="0d40c-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="0d40c-111">Umieść sekcji kodu między `#Region` i `#End Region` instrukcje, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="0d40c-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     <span data-ttu-id="0d40c-112">`#Region` Bloku można używać wiele razy w pliku kodu, w związku z tym użytkownicy mogą definiować własne bloki procedur i klasy, które z kolei może zostać zwinięty.</span><span class="sxs-lookup"><span data-stu-id="0d40c-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="0d40c-113">`#Region`bloki mogą być zagnieżdżone w innych `#Region` bloków.</span><span class="sxs-lookup"><span data-stu-id="0d40c-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d40c-114">Ukrywanie kodu nie uniemożliwia jej kompilowany i nie ma wpływu na `#If...#End If` instrukcje.</span><span class="sxs-lookup"><span data-stu-id="0d40c-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d40c-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d40c-115">See Also</span></span>  
 [<span data-ttu-id="0d40c-116">Kompilacja warunkowa</span><span class="sxs-lookup"><span data-stu-id="0d40c-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="0d40c-117">#Region — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="0d40c-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="0d40c-118">#If... Then... #Else — dyrektywy</span><span class="sxs-lookup"><span data-stu-id="0d40c-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="0d40c-119">Tworzenie konspektu</span><span class="sxs-lookup"><span data-stu-id="0d40c-119">Outlining</span></span>](/visualstudio/ide/outlining)