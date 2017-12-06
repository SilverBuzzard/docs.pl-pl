---
title: "HScrollBar i VScrollBar — Informacje o formantach (Formularze systemu Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 80ec592bf83969ae57495b0df2af110b5622ea11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="46f61-102">HScrollBar i VScrollBar — Informacje o formantach (Formularze systemu Windows)</span><span class="sxs-lookup"><span data-stu-id="46f61-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="46f61-103">Formularze systemu Windows <xref:System.Windows.Forms.ScrollBar> formantów służą do zapewniania nawigację za pośrednictwem długą listę elementów lub duża ilość informacji, albo przewijanie w poziomie lub pionie w aplikacji lub kontrolki.</span><span class="sxs-lookup"><span data-stu-id="46f61-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="46f61-104">Paski przewijania są wspólnego elementu interfejsu systemu Windows, więc <xref:System.Windows.Forms.ScrollBar> kontroli jest często używana z formantami, które nie pochodzą z <xref:System.Windows.Forms.ScrollableControl> klasy.</span><span class="sxs-lookup"><span data-stu-id="46f61-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="46f61-105">Podobnie wielu deweloperów wybierz uwzględnienie <xref:System.Windows.Forms.ScrollBar> sterowania w przypadku tworzenia własne kontrolki użytkownika.</span><span class="sxs-lookup"><span data-stu-id="46f61-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="46f61-106"><xref:System.Windows.Forms.HScrollBar> (Poziomy) i <xref:System.Windows.Forms.VScrollBar> formantów (pionową) działać niezależnie od innych kontrolek i mieć własny zestaw zdarzeń, właściwości i metod.</span><span class="sxs-lookup"><span data-stu-id="46f61-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <span data-ttu-id="46f61-107"><xref:System.Windows.Forms.ScrollBar>formanty nie są takie same, jak paski przewijania wbudowanych, które są dołączone do pól tekstowych, pola listy, pola kombi lub formularze MDI ( <xref:System.Windows.Forms.TextBox> formant ma <xref:System.Windows.Forms.TextBox.ScrollBars%2A> właściwości, aby pokazać lub ukryć paski przewijania, które są dołączone do formantu).</span><span class="sxs-lookup"><span data-stu-id="46f61-107"><xref:System.Windows.Forms.ScrollBar> controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="46f61-108"><xref:System.Windows.Forms.ScrollBar> Steruje użyciem <xref:System.Windows.Forms.ScrollBar.Scroll> zdarzenia do monitorowania przepływu suwaka (nazywane czasami stronie przycisku suwaka) na pasku przewijania.</span><span class="sxs-lookup"><span data-stu-id="46f61-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="46f61-109">Przy użyciu <xref:System.Windows.Forms.ScrollBar.Scroll> zdarzeń zapewnia dostęp do wartości paska przewijania, jak przeciągania.</span><span class="sxs-lookup"><span data-stu-id="46f61-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="46f61-110">Value — właściwość</span><span class="sxs-lookup"><span data-stu-id="46f61-110">Value Property</span></span>  
 <span data-ttu-id="46f61-111"><xref:System.Windows.Forms.ScrollBar.Value%2A> Właściwości (która domyślnie wynosi 0) jest `integer` wartość odpowiadającą pozycja pola przewijania na pasku przewijania.</span><span class="sxs-lookup"><span data-stu-id="46f61-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="46f61-112">Pozycja pola przewijania znajduje się na wartość minimalna, powoduje przeniesienie do lewej położenie (paski przewijania w poziomie) lub górnej pozycji (w przypadku pionowe paski przewijania).</span><span class="sxs-lookup"><span data-stu-id="46f61-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="46f61-113">Gdy pole przewijania znajduje się na wartość maksymalna, przenosi pole przewijania, do prawej krawędzi lub dolną pozycję.</span><span class="sxs-lookup"><span data-stu-id="46f61-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="46f61-114">Podobnie wartość środek między dolnej i górnej części zakresu umieszcza wiodące krawędzi pola przewijania w środku paska przewijania.</span><span class="sxs-lookup"><span data-stu-id="46f61-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="46f61-115">Oprócz za pomocą kliknięć myszą, aby zmienić wartość paska przewijania, użytkownika można również przeciągnij suwak do dowolnego punktu przy pasku.</span><span class="sxs-lookup"><span data-stu-id="46f61-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="46f61-116">Wartość wynikową zależy pozycja pola przewijania, ale jest zawsze w zakresie <xref:System.Windows.Forms.ScrollBar.Minimum%2A> do <xref:System.Windows.Forms.ScrollBar.Maximum%2A> właściwości ustawione przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="46f61-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="46f61-117">LargeChange i SmallChange właściwości</span><span class="sxs-lookup"><span data-stu-id="46f61-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="46f61-118">Gdy użytkownik naciśnie klawisz PAGE UP lub PAGE DOWN lub kliknie śledzenia pasek przewijania po obu stronach pole przewijania <xref:System.Windows.Forms.ScrollBar.Value%2A> zmiany właściwości zgodnie z wartością <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="46f61-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="46f61-119">Gdy użytkownik naciśnie jedną strzałkę kluczy lub kliknie jeden z przycisków paska przewijania, <xref:System.Windows.Forms.ScrollBar.Value%2A> zmiany właściwości zgodnie z wartością <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="46f61-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f61-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="46f61-120">See Also</span></span>  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [<span data-ttu-id="46f61-121">Dodawanie do formularzy systemu Windows dla programu .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="46f61-121">Additions to Windows Forms for the .NET Framework 2.0</span></span>](http://msdn.microsoft.com/en-us/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [<span data-ttu-id="46f61-122">Formanty do użycia w formularzach systemu Windows</span><span class="sxs-lookup"><span data-stu-id="46f61-122">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)