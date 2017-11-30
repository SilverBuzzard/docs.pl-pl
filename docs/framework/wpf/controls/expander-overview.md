---
title: "Przegląd Ekspander"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff0a4432f6de8458e89132bbf46bab7568a04b60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="expander-overview"></a><span data-ttu-id="de667-102">Przegląd Ekspander</span><span class="sxs-lookup"><span data-stu-id="de667-102">Expander Overview</span></span>
<span data-ttu-id="de667-103"><xref:System.Windows.Controls.Expander> Kontrola zapewnia narzędzia do udostępniania zawartości w obszarze rozwijania podobny okna, który zawiera nagłówek.</span><span class="sxs-lookup"><span data-stu-id="de667-103">An <xref:System.Windows.Controls.Expander> control provides a way to provide content in an expandable area that resembles a window and includes a header.</span></span>  
  
  
<a name="CreatinganExpanderinXAML"></a>   
## <a name="creating-a-simple-expander"></a><span data-ttu-id="de667-104">Tworzenie prostego Expander</span><span class="sxs-lookup"><span data-stu-id="de667-104">Creating a Simple Expander</span></span>  
 <span data-ttu-id="de667-105">Poniższy przykład przedstawia sposób tworzenia prostej <xref:System.Windows.Controls.Expander> formantu.</span><span class="sxs-lookup"><span data-stu-id="de667-105">The following example shows how to create a simple <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="de667-106">Ten przykład tworzy <xref:System.Windows.Controls.Expander> prawdopodobnie poprzedniej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="de667-106">This example creates an <xref:System.Windows.Controls.Expander> that looks like the previous illustration.</span></span>  
  
 [!code-xaml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="de667-107"><xref:System.Windows.Controls.ContentControl.Content%2A> i <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> z <xref:System.Windows.Controls.Expander> może również zawierać złożonych zawartości, takich jak <xref:System.Windows.Controls.RadioButton> i <xref:System.Windows.Controls.Image> obiektów.</span><span class="sxs-lookup"><span data-stu-id="de667-107">The <xref:System.Windows.Controls.ContentControl.Content%2A> and <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> of an <xref:System.Windows.Controls.Expander> can also contain complex content, such as <xref:System.Windows.Controls.RadioButton> and <xref:System.Windows.Controls.Image> objects.</span></span>  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## <a name="setting-the-direction-of-the-expanding-content-area"></a><span data-ttu-id="de667-108">Ustawienie kierunku powiększające obszaru zawartości</span><span class="sxs-lookup"><span data-stu-id="de667-108">Setting the Direction of the Expanding Content Area</span></span>  
 <span data-ttu-id="de667-109">Możesz ustawić obszar zawartości <xref:System.Windows.Controls.Expander> formant do rozszerzenia w jednym z czterech kierunków (<xref:System.Windows.Controls.ExpandDirection.Down>, <xref:System.Windows.Controls.ExpandDirection.Up>, <xref:System.Windows.Controls.ExpandDirection.Left>, lub <xref:System.Windows.Controls.ExpandDirection.Right>) przy użyciu <xref:System.Windows.Controls.ExpandDirection> właściwości.</span><span class="sxs-lookup"><span data-stu-id="de667-109">You can set the content area of an <xref:System.Windows.Controls.Expander> control to expand in one of four directions (<xref:System.Windows.Controls.ExpandDirection.Down>, <xref:System.Windows.Controls.ExpandDirection.Up>, <xref:System.Windows.Controls.ExpandDirection.Left>, or <xref:System.Windows.Controls.ExpandDirection.Right>) by using the <xref:System.Windows.Controls.ExpandDirection> property.</span></span> <span data-ttu-id="de667-110">Gdy obszar zawartości jest zwinięte, tylko <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> i jego przycisk przełącznika są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="de667-110">When the content area is collapsed, only the <xref:System.Windows.Controls.Expander><xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and its toggle button appear.</span></span> <span data-ttu-id="de667-111">A <xref:System.Windows.Controls.Button> kontrolkę wyświetlającą strzałkę kierunkową jest używany jako przycisk przełącznika aby rozwinąć lub zwinąć obszar zawartości.</span><span class="sxs-lookup"><span data-stu-id="de667-111">A <xref:System.Windows.Controls.Button> control that displays a directional arrow is used as a toggle button to expand or collapse the content area.</span></span> <span data-ttu-id="de667-112">Po rozwinięciu <xref:System.Windows.Controls.Expander> próbuje wyświetlić całej jego zawartości w obszarze przypominającej okna.</span><span class="sxs-lookup"><span data-stu-id="de667-112">When expanded, the <xref:System.Windows.Controls.Expander> tries to display all of its content in a window-like area.</span></span>  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a><span data-ttu-id="de667-113">Rozmiar element Expander w Panelu sterowania</span><span class="sxs-lookup"><span data-stu-id="de667-113">Controlling the Size of an Expander in a Panel</span></span>  
 <span data-ttu-id="de667-114">Jeśli <xref:System.Windows.Controls.Expander> formant znajduje się wewnątrz kontrolkę układu, która dziedziczy <xref:System.Windows.Controls.Panel>, takich jak <xref:System.Windows.Controls.StackPanel>, nie należy określać <xref:System.Windows.FrameworkElement.Height%2A> na <xref:System.Windows.Controls.Expander> podczas <xref:System.Windows.Controls.Expander.ExpandDirection%2A> właściwość jest ustawiona na <xref:System.Windows.Controls.ExpandDirection.Down> lub <xref:System.Windows.Controls.ExpandDirection.Up>.</span><span class="sxs-lookup"><span data-stu-id="de667-114">If an <xref:System.Windows.Controls.Expander> control is inside a layout control that inherits from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.StackPanel>, do not specify a <xref:System.Windows.FrameworkElement.Height%2A> on the <xref:System.Windows.Controls.Expander> when the <xref:System.Windows.Controls.Expander.ExpandDirection%2A> property is set to <xref:System.Windows.Controls.ExpandDirection.Down> or <xref:System.Windows.Controls.ExpandDirection.Up>.</span></span> <span data-ttu-id="de667-115">Podobnie, nie należy określać <xref:System.Windows.FrameworkElement.Width%2A> na <xref:System.Windows.Controls.Expander> podczas <xref:System.Windows.Controls.Expander.ExpandDirection%2A> właściwość jest ustawiona na <xref:System.Windows.Controls.ExpandDirection.Left> lub <xref:System.Windows.Controls.ExpandDirection.Right>.</span><span class="sxs-lookup"><span data-stu-id="de667-115">Similarly, do not specify a <xref:System.Windows.FrameworkElement.Width%2A> on the <xref:System.Windows.Controls.Expander> when the <xref:System.Windows.Controls.Expander.ExpandDirection%2A> property is set to <xref:System.Windows.Controls.ExpandDirection.Left> or <xref:System.Windows.Controls.ExpandDirection.Right>.</span></span>  
  
 <span data-ttu-id="de667-116">Podczas ustawiania rozmiaru wymiaru na <xref:System.Windows.Controls.Expander> kontroli w kierunku, czy jest wyświetlana zawartość rozwinięte, <xref:System.Windows.Controls.Expander> przejmuje kontrolę nad obszarem jest używany przez zawartość i wyświetla obramowanie.</span><span class="sxs-lookup"><span data-stu-id="de667-116">When you set a size dimension on an <xref:System.Windows.Controls.Expander> control in the direction that the expanded content is displayed, the <xref:System.Windows.Controls.Expander> takes control of the area that is used by the content and displays a border around it.</span></span> <span data-ttu-id="de667-117">Pokazuje obramowania, nawet wtedy, gdy zawartość jest zwinięty.</span><span class="sxs-lookup"><span data-stu-id="de667-117">The border shows even when the content is collapsed.</span></span> <span data-ttu-id="de667-118">Rozmiar obszaru zawartości rozwinięte ustawia wymiary rozmiaru zawartości <xref:System.Windows.Controls.Expander>, lub jeśli użytkownik chce przewijanie możliwości, na <xref:System.Windows.Controls.ScrollViewer> który umieszcza zawartości.</span><span class="sxs-lookup"><span data-stu-id="de667-118">To set the size of the expanded content area, set size dimensions on the content of the <xref:System.Windows.Controls.Expander>, or if you want scrolling capability, on the <xref:System.Windows.Controls.ScrollViewer> that encloses the content.</span></span>  
  
 <span data-ttu-id="de667-119">Gdy <xref:System.Windows.Controls.Expander> formant jest ostatnim elementem w <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] automatycznie ustawia <xref:System.Windows.Controls.Expander> wymiarów równą pozostałej części <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="de667-119">When an <xref:System.Windows.Controls.Expander> control is the last element in a <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] automatically sets the <xref:System.Windows.Controls.Expander> dimensions to equal the remaining area of the <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="de667-120">Aby zapobiec to domyślne zachowanie, ustaw <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> właściwość <xref:System.Windows.Controls.DockPanel> do obiektu `false`, lub upewnij się, że <xref:System.Windows.Controls.Expander> nie jest ostatnim elementem w <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="de667-120">To prevent this default behavior, set the <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> property on the <xref:System.Windows.Controls.DockPanel> object to `false`, or make sure that the <xref:System.Windows.Controls.Expander> is not the last element in a <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
<a name="CreatingScrollableContent"></a>   
## <a name="creating-scrollable-content"></a><span data-ttu-id="de667-121">Tworzenie przewijanej treści</span><span class="sxs-lookup"><span data-stu-id="de667-121">Creating Scrollable Content</span></span>  
 <span data-ttu-id="de667-122">Jeśli zawartość jest zbyt duży rozmiar obszaru zawartości, może zawijać się zawartość <xref:System.Windows.Controls.Expander> w <xref:System.Windows.Controls.ScrollViewer> zapewnić przewijanej treści.</span><span class="sxs-lookup"><span data-stu-id="de667-122">If the content is too large for the size of the content area, you can wrap the content of an <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> in order to provide scrollable content.</span></span> <span data-ttu-id="de667-123"><xref:System.Windows.Controls.Expander> Formant automatycznie nie zapewnia funkcji przewijania.</span><span class="sxs-lookup"><span data-stu-id="de667-123">The <xref:System.Windows.Controls.Expander> control does not automatically provide scrolling capability.</span></span> <span data-ttu-id="de667-124">Na poniższej ilustracji pokazano <xref:System.Windows.Controls.Expander> formant, który zawiera <xref:System.Windows.Controls.ScrollViewer> formantu.</span><span class="sxs-lookup"><span data-stu-id="de667-124">The following illustration shows an <xref:System.Windows.Controls.Expander> control that contains a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 <span data-ttu-id="de667-125">**Expander w ScrollViewer**</span><span class="sxs-lookup"><span data-stu-id="de667-125">**Expander in a ScrollViewer**</span></span>  
  
 <span data-ttu-id="de667-126">![Expander z paska przewijania](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")</span><span class="sxs-lookup"><span data-stu-id="de667-126">![Expander with ScrollBar](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")</span></span>  
  
 <span data-ttu-id="de667-127">Po umieszczeniu <xref:System.Windows.Controls.Expander> kontroli w <xref:System.Windows.Controls.ScrollViewer>ustaw <xref:System.Windows.Controls.ScrollViewer> wymiaru właściwość, która odpowiada kierunek, w którym <xref:System.Windows.Controls.Expander> zawartości otwiera rozmiar <xref:System.Windows.Controls.Expander> obszar zawartości.</span><span class="sxs-lookup"><span data-stu-id="de667-127">When you place an <xref:System.Windows.Controls.Expander> control in a <xref:System.Windows.Controls.ScrollViewer>, set the <xref:System.Windows.Controls.ScrollViewer> dimension property that corresponds to the direction in which the <xref:System.Windows.Controls.Expander> content opens to the size of the <xref:System.Windows.Controls.Expander> content area.</span></span> <span data-ttu-id="de667-128">Na przykład jeśli ustawisz <xref:System.Windows.Controls.Expander.ExpandDirection%2A> właściwość <xref:System.Windows.Controls.Expander> do <xref:System.Windows.Controls.ExpandDirection.Down> (otwiera obszar zawartości w dół), ustaw <xref:System.Windows.FrameworkElement.Height%2A> właściwość <xref:System.Windows.Controls.ScrollViewer> formantu wymagane wysokość obszaru zawartości.</span><span class="sxs-lookup"><span data-stu-id="de667-128">For example, if you set the <xref:System.Windows.Controls.Expander.ExpandDirection%2A> property on the <xref:System.Windows.Controls.Expander> to <xref:System.Windows.Controls.ExpandDirection.Down> (the content area opens down), set the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> control to the required height for the content area.</span></span> <span data-ttu-id="de667-129">Jeśli zamiast tego wartość wysokości zawartości, <xref:System.Windows.Controls.ScrollViewer> to ustawienie nie jest rozpoznawane i dlatego nie zapewnia przewijanej treści.</span><span class="sxs-lookup"><span data-stu-id="de667-129">If you instead set the height dimension on the content itself, <xref:System.Windows.Controls.ScrollViewer> does not recognize this setting and therefore, does not provide scrollable content.</span></span>  
  
 <span data-ttu-id="de667-130">Poniższy przykład przedstawia sposób tworzenia <xref:System.Windows.Controls.Expander> kontroli mający złożonych zawartości i zawiera <xref:System.Windows.Controls.ScrollViewer> formantu.</span><span class="sxs-lookup"><span data-stu-id="de667-130">The following example shows how to create an <xref:System.Windows.Controls.Expander> control that has complex content and that contains a <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="de667-131">Ten przykład tworzy <xref:System.Windows.Controls.Expander> to jak na ilustracji na początku tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="de667-131">This example creates an <xref:System.Windows.Controls.Expander> that is like the illustration at the beginning of this section.</span></span>  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## <a name="using-the-alignment-properties"></a><span data-ttu-id="de667-132">Przy użyciu właściwości wyrównania</span><span class="sxs-lookup"><span data-stu-id="de667-132">Using the Alignment Properties</span></span>  
 <span data-ttu-id="de667-133">Zawartość można wyrównać przez ustawienie <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> i <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> właściwości <xref:System.Windows.Controls.Expander> formantu.</span><span class="sxs-lookup"><span data-stu-id="de667-133">You can align content by setting the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> and <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> properties on the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="de667-134">Wyrównanie ustaw te właściwości, zastosowanie do nagłówka, a także do rozwiniętego zawartości.</span><span class="sxs-lookup"><span data-stu-id="de667-134">When you set these properties, the alignment applies to the header and also to the expanded content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de667-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="de667-135">See Also</span></span>  
 <xref:System.Windows.Controls.Expander>  
 <xref:System.Windows.Controls.ExpandDirection>  
 [<span data-ttu-id="de667-136">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="de667-136">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)