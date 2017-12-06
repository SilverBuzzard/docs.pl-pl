---
title: "Użycie obiektów DrawingVisual"
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
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ee46c41d6f0f42bbb9f50bd5862f6eb076b34bb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="using-drawingvisual-objects"></a><span data-ttu-id="fe4c3-102">Użycie obiektów DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="fe4c3-102">Using DrawingVisual Objects</span></span>
<span data-ttu-id="fe4c3-103">Ten temat zawiera omówienie sposobu użycia <xref:System.Windows.Media.DrawingVisual> obiekty w [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visual warstwy.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-103">This topic provides an overview of how to use <xref:System.Windows.Media.DrawingVisual> objects in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visual layer.</span></span>  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a><span data-ttu-id="fe4c3-104">Obiekt DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="fe4c3-104">DrawingVisual Object</span></span>  
 <span data-ttu-id="fe4c3-105"><xref:System.Windows.Media.DrawingVisual> To lekkie rysowania klasy, który jest używany do renderowania kształty, obrazy i tekst.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-105">The <xref:System.Windows.Media.DrawingVisual> is a lightweight drawing class that is used to render shapes, images, or text.</span></span> <span data-ttu-id="fe4c3-106">Ta klasa jest traktowane jako lekkie, ponieważ nie dostarcza obsługi układu lub zdarzeń, co zwiększa wydajność.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-106">This class is considered lightweight because it does not provide layout or event handling, which improves its performance.</span></span> <span data-ttu-id="fe4c3-107">Z tego powodu rysunki idealnie nadają się do tła i grafik przycinania.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-107">For this reason, drawings are ideal for backgrounds and clip art.</span></span>  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a><span data-ttu-id="fe4c3-108">Kontener DrawingVisual hosta</span><span class="sxs-lookup"><span data-stu-id="fe4c3-108">DrawingVisual Host Container</span></span>  
 <span data-ttu-id="fe4c3-109">Aby można było używać <xref:System.Windows.Media.DrawingVisual> obiektów, należy utworzyć kontener hosta dla obiektów.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-109">In order to use <xref:System.Windows.Media.DrawingVisual> objects, you need to create a host container for the objects.</span></span> <span data-ttu-id="fe4c3-110">Obiekt kontenera hosta musi pochodzić od <xref:System.Windows.FrameworkElement> klasy, która dostarcza układ i obsługa zdarzeń obsługi, który <xref:System.Windows.Media.DrawingVisual> klasa nie ma.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-110">The host container object must derive from the <xref:System.Windows.FrameworkElement> class, which provides the layout and event handling support that the <xref:System.Windows.Media.DrawingVisual> class lacks.</span></span> <span data-ttu-id="fe4c3-111">Obiekt kontenera hosta nie są wyświetlane wszystkie właściwości widoczne, od momentu jego głównym celem jest zawierają obiekty podrzędne.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-111">The host container object does not display any visible properties, since its main purpose is to contain child objects.</span></span> <span data-ttu-id="fe4c3-112">Jednak <xref:System.Windows.UIElement.Visibility%2A> musi mieć ustawioną właściwość kontenera hosta <xref:System.Windows.Visibility.Visible>; w przeciwnym razie żaden z jego elementów podrzędnych nie będzie widoczna.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-112">However, the <xref:System.Windows.UIElement.Visibility%2A> property of the host container must be set to <xref:System.Windows.Visibility.Visible>; otherwise, none of its child elements will be visible.</span></span>  
  
 <span data-ttu-id="fe4c3-113">Podczas tworzenia obiektu hosta kontenera obiektów visual należy przechowywać odwołania do obiektów visual w <xref:System.Windows.Media.VisualCollection>.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-113">When you create a host container object for visual objects, you need to store the visual object references in a <xref:System.Windows.Media.VisualCollection>.</span></span> <span data-ttu-id="fe4c3-114">Użyj <xref:System.Windows.Media.VisualCollection.Add%2A> metody w celu dodania do hosta kontenera obiektu visual.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-114">Use the <xref:System.Windows.Media.VisualCollection.Add%2A> method to add a visual object to the host container.</span></span> <span data-ttu-id="fe4c3-115">W poniższym przykładzie tworzony jest obiekt kontenera hosta i trzy obiekty widoczne są dodawane do jej <xref:System.Windows.Media.VisualCollection>.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-115">In the following example, a host container object is created, and three visual objects are added to its <xref:System.Windows.Media.VisualCollection>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  <span data-ttu-id="fe4c3-116">Dla przykładu kompletny kod, z którego został wyodrębniony w poprzednim przykładzie kodu, zobacz [trafień przy użyciu DrawingVisuals próbki](http://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="fe4c3-116">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).</span></span>  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a><span data-ttu-id="fe4c3-117">Tworzenie obiektów DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="fe4c3-117">Creating DrawingVisual Objects</span></span>  
 <span data-ttu-id="fe4c3-118">Po utworzeniu <xref:System.Windows.Media.DrawingVisual> obiektu, nie ma on rysowania zawartości.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-118">When you create a <xref:System.Windows.Media.DrawingVisual> object, it has no drawing content.</span></span> <span data-ttu-id="fe4c3-119">Można dodać tekstu, grafiki lub obrazu zawartości przez pobranie obiektu <xref:System.Windows.Media.DrawingContext> i rysowania do niego.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-119">You can add text, graphics, or image content by retrieving the object's <xref:System.Windows.Media.DrawingContext> and drawing into it.</span></span> <span data-ttu-id="fe4c3-120">A <xref:System.Windows.Media.DrawingContext> jest zwracany przez wywołanie metody <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> metody <xref:System.Windows.Media.DrawingVisual> obiektu.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-120">A <xref:System.Windows.Media.DrawingContext> is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span>  
  
 <span data-ttu-id="fe4c3-121">Rysowanie w prostokącie <xref:System.Windows.Media.DrawingContext>, użyj <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> metody <xref:System.Windows.Media.DrawingContext> obiektu.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-121">To draw a rectangle into the <xref:System.Windows.Media.DrawingContext>, use the <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> method of the <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="fe4c3-122">Istnieje podobnych metod rysowania innych typów zawartości.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-122">Similar methods exist for drawing other types of content.</span></span> <span data-ttu-id="fe4c3-123">Gdy skończysz rysowania zawartości do <xref:System.Windows.Media.DrawingContext>, wywołaj <xref:System.Windows.Media.DrawingContext.Close%2A> metody, aby zamknąć <xref:System.Windows.Media.DrawingContext> i utrwala zawartości.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-123">When you are finished drawing content into the <xref:System.Windows.Media.DrawingContext>, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the <xref:System.Windows.Media.DrawingContext> and persist the content.</span></span>  
  
 <span data-ttu-id="fe4c3-124">W poniższym przykładzie <xref:System.Windows.Media.DrawingVisual> obiekt jest tworzony i prostokąt jest rysowana w jego <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-124">In the following example, a <xref:System.Windows.Media.DrawingVisual> object is created, and a rectangle is drawn into its <xref:System.Windows.Media.DrawingContext>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a><span data-ttu-id="fe4c3-125">Tworzenie zastąpień dla członków FrameworkElement</span><span class="sxs-lookup"><span data-stu-id="fe4c3-125">Creating Overrides for FrameworkElement Members</span></span>  
 <span data-ttu-id="fe4c3-126">Obiekt kontenera hosta jest odpowiedzialny za zarządzanie jego kolekcja obiektów visual.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-126">The host container object is responsible for managing its collection of visual objects.</span></span> <span data-ttu-id="fe4c3-127">Wymaga to, że kontener hosta implementuje element członkowski pochodnej zastąpienia <xref:System.Windows.FrameworkElement> klasy.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-127">This requires that the host container implement member overrides for the derived <xref:System.Windows.FrameworkElement> class.</span></span>  
  
 <span data-ttu-id="fe4c3-128">Poniżej opisano dwa elementy członkowskie, należy zastąpić:</span><span class="sxs-lookup"><span data-stu-id="fe4c3-128">The following list describes the two members you must override:</span></span>  
  
-   <span data-ttu-id="fe4c3-129"><xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Zwraca element podrzędny o określonym indeksie kolekcji elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-129"><xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Returns a child at the specified index from the collection of child elements.</span></span>  
  
-   <span data-ttu-id="fe4c3-130"><xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Pobiera liczbę elementów podrzędnych visual w tym elemencie.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-130"><xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Gets the number of visual child elements within this element.</span></span>  
  
 <span data-ttu-id="fe4c3-131">W poniższym przykładzie zastąpień dla dwóch <xref:System.Windows.FrameworkElement> są implementowane elementy członkowskie.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-131">In the following example, overrides for the two <xref:System.Windows.FrameworkElement> members are implemented.</span></span>  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a><span data-ttu-id="fe4c3-132">Zapewnianie obsługi testowania trafień</span><span class="sxs-lookup"><span data-stu-id="fe4c3-132">Providing Hit Testing Support</span></span>  
 <span data-ttu-id="fe4c3-133">Obiekt kontenera hosta zapewniają obsługę zdarzeń nawet wtedy, gdy nie są wyświetlane wszystkie właściwości widoczne — jednak jego <xref:System.Windows.UIElement.Visibility%2A> musi mieć ustawioną właściwość <xref:System.Windows.Visibility.Visible>.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-133">The host container object can provide event handling even if it does not display any visible properties—however, its <xref:System.Windows.UIElement.Visibility%2A> property must be set to <xref:System.Windows.Visibility.Visible>.</span></span> <span data-ttu-id="fe4c3-134">Dzięki temu można utworzyć zdarzenia obsługi procedury dla kontenera hosta, który może być stosowane do zdarzeń myszy, takich jak wersja lewego przycisku myszy.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-134">This allows you to create an event handling routine for the host container that can trap mouse events, such as the release of the left mouse button.</span></span> <span data-ttu-id="fe4c3-135">Obsługa procedury zdarzeń można zaimplementować testowania trafień za pomocą <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-135">The event handling routine can then implement hit testing by invoking the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="fe4c3-136">Metoda <xref:System.Windows.Media.HitTestResultCallback> parametr odnosi się do zdefiniowanych przez użytkownika procedury, która służy do określenia wynikowy akcji testu trafienia.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-136">The method's <xref:System.Windows.Media.HitTestResultCallback> parameter refers to a user-defined procedure that you can use to determine the resulting action of a hit test.</span></span>  
  
 <span data-ttu-id="fe4c3-137">W poniższym przykładzie trafień testowania obsługi został zaimplementowany dla obiekt kontenera hosta i jego elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="fe4c3-137">In the following example, hit testing support is implemented for the host container object and its children.</span></span>  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="fe4c3-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fe4c3-138">See Also</span></span>  
 <xref:System.Windows.Media.DrawingVisual>  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 [<span data-ttu-id="fe4c3-139">Przegląd renderowania grafiki WPF</span><span class="sxs-lookup"><span data-stu-id="fe4c3-139">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="fe4c3-140">Testowanie w warstwie Visual trafień</span><span class="sxs-lookup"><span data-stu-id="fe4c3-140">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)