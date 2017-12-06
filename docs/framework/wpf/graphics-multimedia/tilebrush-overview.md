---
title: "TileBrush — Przegląd"
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
- TileBrush [WPF]
- brushes [WPF], TileBrush
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f759a56233e8cf2b1c1d39862706be518fefe43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="tilebrush-overview"></a><span data-ttu-id="6ad74-102">TileBrush — Przegląd</span><span class="sxs-lookup"><span data-stu-id="6ad74-102">TileBrush Overview</span></span>
<span data-ttu-id="6ad74-103"><xref:System.Windows.Media.TileBrush>obiekty umożliwiają z dużym stopniem kontrolę nad jak obszar jest rysowane przy użyciu obrazu <xref:System.Windows.Media.Drawing>, lub <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-103"><xref:System.Windows.Media.TileBrush> objects provide you with a great deal of control over how an area is painted with an image, <xref:System.Windows.Media.Drawing>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="6ad74-104">W tym temacie opisano sposób użycia <xref:System.Windows.Media.TileBrush> funkcji, aby uzyskać większą kontrolę nad jak <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, lub <xref:System.Windows.Media.VisualBrush> rysują obszaru.</span><span class="sxs-lookup"><span data-stu-id="6ad74-104">This topic describes how to use <xref:System.Windows.Media.TileBrush> features to gain more control over how an <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, or <xref:System.Windows.Media.VisualBrush> paints an area.</span></span>  
  
  
<a name="prerequisite"></a>   
## <a name="prerequisites"></a><span data-ttu-id="6ad74-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="6ad74-105">Prerequisites</span></span>  
 <span data-ttu-id="6ad74-106">Aby zrozumieć, w tym temacie, należy zrozumieć, jak używać podstawowych funkcji <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, lub <xref:System.Windows.Media.VisualBrush> klasy.</span><span class="sxs-lookup"><span data-stu-id="6ad74-106">To understand this topic, it's helpful to understand how to use the basic features of the <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, or <xref:System.Windows.Media.VisualBrush> class.</span></span> <span data-ttu-id="6ad74-107">Aby obejrzeć wprowadzenie do tych typów, zobacz [malowanie obrazów, rysunki i elementy wizualne](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="6ad74-107">For an introduction to these types, see the [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
<a name="tilebrush"></a>   
## <a name="painting-an-area-with-tiles"></a><span data-ttu-id="6ad74-108">Malowanie obszar o kafelków</span><span class="sxs-lookup"><span data-stu-id="6ad74-108">Painting an Area with Tiles</span></span>  
 <span data-ttu-id="6ad74-109"><xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, są <xref:System.Windows.Media.VisualBrush> typów <xref:System.Windows.Media.TileBrush> obiektów.</span><span class="sxs-lookup"><span data-stu-id="6ad74-109"><xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, are <xref:System.Windows.Media.VisualBrush> are types of <xref:System.Windows.Media.TileBrush> objects.</span></span> <span data-ttu-id="6ad74-110">Pędzle kafelków umożliwiają z dużym stopniem kontrolę nad jak obszar jest rysowane przy użyciu obrazu, rysunku lub visual.</span><span class="sxs-lookup"><span data-stu-id="6ad74-110">Tile brushes provide you with a great deal of control over how an area is painted with an image, drawing, or visual.</span></span> <span data-ttu-id="6ad74-111">Na przykład zamiast tylko malowanie obszar o jeden obraz rozciągnięty, można malować obszar o serię kafelków obrazu, tworzące wzorzec.</span><span class="sxs-lookup"><span data-stu-id="6ad74-111">For example, instead of just painting an area with a single stretched image, you can paint an area with a series of image tiles that create a pattern.</span></span>  
  
 <span data-ttu-id="6ad74-112">Malowanie obszar o pędzla kafelka obejmuje trzy składniki: zawartość, podstawowy Kafelek i do obszaru wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="6ad74-112">Painting an area with a tile brush involves three components: content, the base tile, and the output area.</span></span>  
  
 <span data-ttu-id="6ad74-113">![Składniki TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")</span><span class="sxs-lookup"><span data-stu-id="6ad74-113">![TileBrush components](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")</span></span>  
<span data-ttu-id="6ad74-114">Składniki TileBrush z jednego kafelka</span><span class="sxs-lookup"><span data-stu-id="6ad74-114">Components of a TileBrush with a single tile</span></span>  
  
 <span data-ttu-id="6ad74-115">![Składniki sąsiadującym TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")</span><span class="sxs-lookup"><span data-stu-id="6ad74-115">![Components of a tiled TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")</span></span>  
<span data-ttu-id="6ad74-116">Składniki TileBrush z TileMode kafelków</span><span class="sxs-lookup"><span data-stu-id="6ad74-116">Components of a TileBrush with a TileMode of Tile</span></span>  
  
 <span data-ttu-id="6ad74-117">Obszar wyjściowy jest obszaru są rysowane, takich jak <xref:System.Windows.Shapes.Shape.Fill%2A> z <xref:System.Windows.Shapes.Ellipse> lub <xref:System.Windows.Controls.Control.Background%2A> z <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-117">The output area is the area being painted, such as the <xref:System.Windows.Shapes.Shape.Fill%2A> of an <xref:System.Windows.Shapes.Ellipse> or the <xref:System.Windows.Controls.Control.Background%2A> of a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="6ad74-118">Kolejne sekcje opisują dwa składniki programu <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-118">The next sections describe the other two components of a <xref:System.Windows.Media.TileBrush>.</span></span>  
  
<a name="brushcontent"></a>   
## <a name="brush-content"></a><span data-ttu-id="6ad74-119">Pędzel zawartości</span><span class="sxs-lookup"><span data-stu-id="6ad74-119">Brush Content</span></span>  
 <span data-ttu-id="6ad74-120">Istnieją trzy różne typy <xref:System.Windows.Media.TileBrush> i maluje każdego z innym typem zawartości.</span><span class="sxs-lookup"><span data-stu-id="6ad74-120">There are three different types of <xref:System.Windows.Media.TileBrush> and each paints with a different type of content.</span></span>  
  
-   <span data-ttu-id="6ad74-121">Jeśli jest pędzla <xref:System.Windows.Media.ImageBrush>, ta zawartość jest obrazem <xref:System.Windows.Media.ImageBrush.ImageSource%2A> właściwość określa zawartość <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-121">If the brush is an <xref:System.Windows.Media.ImageBrush>, this content is an image The <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property specifies the contents of the <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
-   <span data-ttu-id="6ad74-122">Jeśli jest pędzla <xref:System.Windows.Media.DrawingBrush>, ta zawartość jest rysunku.</span><span class="sxs-lookup"><span data-stu-id="6ad74-122">If the brush is a <xref:System.Windows.Media.DrawingBrush>, this content is a drawing.</span></span> <span data-ttu-id="6ad74-123"><xref:System.Windows.Media.DrawingBrush.Drawing%2A> Właściwość określa zawartość <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-123">The <xref:System.Windows.Media.DrawingBrush.Drawing%2A> property specifies the contents of the <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
-   <span data-ttu-id="6ad74-124">Jeśli jest pędzla <xref:System.Windows.Media.VisualBrush>, ta zawartość jest element wizualny.</span><span class="sxs-lookup"><span data-stu-id="6ad74-124">If the brush is a <xref:System.Windows.Media.VisualBrush>, this content is a visual.</span></span> <span data-ttu-id="6ad74-125"><xref:System.Windows.Media.VisualBrush.Visual%2A> Właściwość określa zawartość <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-125">The <xref:System.Windows.Media.VisualBrush.Visual%2A> property specifies the content of the <xref:System.Windows.Media.VisualBrush>.</span></span>  
  
 <span data-ttu-id="6ad74-126">Można określić pozycji i wymiary <xref:System.Windows.Media.TileBrush> zawartości przy użyciu <xref:System.Windows.Media.TileBrush.Viewbox%2A> właściwości, chociaż często pozostaw <xref:System.Windows.Media.TileBrush.Viewbox%2A> ustawioną wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="6ad74-126">You can specify the position and dimensions of <xref:System.Windows.Media.TileBrush> content by using the <xref:System.Windows.Media.TileBrush.Viewbox%2A> property, although it is common to leave the <xref:System.Windows.Media.TileBrush.Viewbox%2A> set to its default value.</span></span> <span data-ttu-id="6ad74-127">Domyślnie <xref:System.Windows.Media.TileBrush.Viewbox%2A> jest skonfigurowany do przechowywania całkowicie zawartość pędzla.</span><span class="sxs-lookup"><span data-stu-id="6ad74-127">By default, the <xref:System.Windows.Media.TileBrush.Viewbox%2A> is configured to completely contain the brush's contents.</span></span> <span data-ttu-id="6ad74-128">Aby uzyskać więcej informacji o konfigurowaniu <xref:System.Windows.Controls.Viewbox>, zobacz <xref:System.Windows.Controls.Viewbox> strony właściwości.</span><span class="sxs-lookup"><span data-stu-id="6ad74-128">For more information about configuring the <xref:System.Windows.Controls.Viewbox>, see the <xref:System.Windows.Controls.Viewbox> property page.</span></span>  
  
<a name="thebasetile"></a>   
## <a name="the-base-tile"></a><span data-ttu-id="6ad74-129">Podstawowy Kafelek</span><span class="sxs-lookup"><span data-stu-id="6ad74-129">The Base Tile</span></span>  
 <span data-ttu-id="6ad74-130">A <xref:System.Windows.Media.TileBrush> projekty na podstawowy Kafelek jego zawartości.</span><span class="sxs-lookup"><span data-stu-id="6ad74-130">A <xref:System.Windows.Media.TileBrush> projects its content onto a base tile.</span></span> <span data-ttu-id="6ad74-131"><xref:System.Windows.Media.TileBrush.Stretch%2A> Formantów właściwości jak <xref:System.Windows.Media.TileBrush> zawartości jest rozciągany tak, aby wypełnić podstawowy Kafelek.</span><span class="sxs-lookup"><span data-stu-id="6ad74-131">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property controls how <xref:System.Windows.Media.TileBrush> content is stretched to fill the base tile.</span></span> <span data-ttu-id="6ad74-132"><xref:System.Windows.Media.TileBrush.Stretch%2A> Właściwość przyjmuje następujące wartości zdefiniowane przez <xref:System.Windows.Media.Stretch> wyliczenie:</span><span class="sxs-lookup"><span data-stu-id="6ad74-132">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property accepts the following values, defined by the <xref:System.Windows.Media.Stretch> enumeration:</span></span>  
  
-   <span data-ttu-id="6ad74-133"><xref:System.Windows.Media.Stretch.None>Pędzla zawartości nie jest rozciągany tak, aby wypełnić kafelka.</span><span class="sxs-lookup"><span data-stu-id="6ad74-133"><xref:System.Windows.Media.Stretch.None>: The brush's content is not stretched to fill the tile.</span></span>  
  
-   <span data-ttu-id="6ad74-134"><xref:System.Windows.Media.Stretch.Fill>Zawartość pędzla jest skalowane w celu dopasowania kafelka.</span><span class="sxs-lookup"><span data-stu-id="6ad74-134"><xref:System.Windows.Media.Stretch.Fill>: The brush's content is scaled to fit the tile.</span></span> <span data-ttu-id="6ad74-135">Ponieważ zawartość wysokość i szerokość są skalowane niezależnie, jego oryginalny współczynnik proporcji zawartości mogą nie zostać zachowane.</span><span class="sxs-lookup"><span data-stu-id="6ad74-135">Because the content's height and width are scaled independently, the original aspect ratio of the content might not be preserved.</span></span> <span data-ttu-id="6ad74-136">Oznacza to, że zawartość pędzla może wypaczenia aby wypełnić fragment danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="6ad74-136">That is, the brush's content might be warped in order to completely fill the output tile.</span></span>  
  
-   <span data-ttu-id="6ad74-137"><xref:System.Windows.Media.Stretch.Uniform>Tak, aby zmieścił się całkowicie w kafelku skalowania zawartości pędzla.</span><span class="sxs-lookup"><span data-stu-id="6ad74-137"><xref:System.Windows.Media.Stretch.Uniform>: The brush's content is scaled so that it fits completely within the tile.</span></span> <span data-ttu-id="6ad74-138">Zawartość współczynnik proporcji jest zachowywany.</span><span class="sxs-lookup"><span data-stu-id="6ad74-138">The content's aspect ratio is preserved.</span></span>  
  
-   <span data-ttu-id="6ad74-139"><xref:System.Windows.Media.Stretch.UniformToFill>Zawartość pędzla skalowania, aby całkowicie wypełnia obszaru wyjściowego przy zachowaniu zawartości oryginalnego współczynnika proporcji.</span><span class="sxs-lookup"><span data-stu-id="6ad74-139"><xref:System.Windows.Media.Stretch.UniformToFill>: The brush's content is scaled so that it completely fills the output area while preserving the content's original aspect ratio.</span></span>  
  
 <span data-ttu-id="6ad74-140">Na poniższym obrazie przedstawiono różne <xref:System.Windows.Media.TileBrush.Stretch%2A> ustawienia.</span><span class="sxs-lookup"><span data-stu-id="6ad74-140">The following image illustrates the different <xref:System.Windows.Media.TileBrush.Stretch%2A> settings.</span></span>  
  
 <span data-ttu-id="6ad74-141">![Różne ustawienia TileBrush Stretch](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")</span><span class="sxs-lookup"><span data-stu-id="6ad74-141">![Different TileBrush Stretch settings](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")</span></span>  
  
 <span data-ttu-id="6ad74-142">W poniższym przykładzie zawartość <xref:System.Windows.Media.ImageBrush> ustawiono tak, aby nie stretch aby wypełnił obszar danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="6ad74-142">In the following example, the content of an <xref:System.Windows.Media.ImageBrush> is set so that it does not stretch to fill the output area.</span></span>  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 <span data-ttu-id="6ad74-143">Domyślnie <xref:System.Windows.Media.TileBrush> generuje pojedynczy fragment (podstawowy Kafelek) i rozciąga się tego kafelka, aby wypełnić obszaru wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="6ad74-143">By default, a <xref:System.Windows.Media.TileBrush> generates a single tile (the base tile) and stretches that tile to completely fill the output area.</span></span> <span data-ttu-id="6ad74-144">Przez ustawienie można zmienić rozmiar i położenie podstawowy Kafelek <xref:System.Windows.Media.TileBrush.Viewport%2A> i <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="6ad74-144">You can change the size and position of the base tile by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>  
  
<a name="basetilesize"></a>   
### <a name="base-tile-size"></a><span data-ttu-id="6ad74-145">Rozmiar kafelka podstawowej</span><span class="sxs-lookup"><span data-stu-id="6ad74-145">Base Tile Size</span></span>  
 <span data-ttu-id="6ad74-146"><xref:System.Windows.Media.TileBrush.Viewport%2A> Właściwość określa rozmiar i położenie podstawowy Kafelek i <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> właściwość określa, czy <xref:System.Windows.Media.TileBrush.Viewport%2A> jest określona za pomocą współrzędnych bezwzględny lub względny.</span><span class="sxs-lookup"><span data-stu-id="6ad74-146">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property determines the size and position of the base tile, and the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property determines whether the <xref:System.Windows.Media.TileBrush.Viewport%2A> is specified using absolute or relative coordinates.</span></span> <span data-ttu-id="6ad74-147">Jeśli współrzędnych względnych, są one względem rozmiar obszaru danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="6ad74-147">If the coordinates are relative, they are relative to the size of the output area.</span></span> <span data-ttu-id="6ad74-148">Reprezentuje punkt (0,0) lewym górnym rogu obszaru wyjściowego i (1,1) reprezentuje dolnej prawym narożniku obszaru wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="6ad74-148">The point (0,0) represents the top left corner of the output area, and (1,1) represents the bottom right corner of the output area.</span></span> <span data-ttu-id="6ad74-149">Aby określić, że <xref:System.Windows.Media.TileBrush.Viewport%2A> właściwość używa współrzędne bezwzględne, ustaw <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> właściwości <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-149">To specify that the <xref:System.Windows.Media.TileBrush.Viewport%2A> property uses absolute coordinates, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>  
  
 <span data-ttu-id="6ad74-150">Na poniższej ilustracji przedstawiono różnice w danych wyjściowych między <xref:System.Windows.Media.TileBrush> z względna lub bezwzględna <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-150">The following illustration shows the difference in output between a <xref:System.Windows.Media.TileBrush> with relative versus absolute <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>.</span></span> <span data-ttu-id="6ad74-151">Zwróć uwagę, że na ilustracjach każdego przedstawiono sąsiadującym wzorzec; w następnej sekcji opisano sposób określania wzorca kafelka.</span><span class="sxs-lookup"><span data-stu-id="6ad74-151">Notice that the illustrations each show a tiled pattern; the next section describes how to specify tile pattern.</span></span>  
  
 <span data-ttu-id="6ad74-152">![Bezwzględny i jednostkach względnych okienka ekranu](../../../../docs/framework/wpf/graphics-multimedia/media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")</span><span class="sxs-lookup"><span data-stu-id="6ad74-152">![Absolute and Relative Viewport Units](../../../../docs/framework/wpf/graphics-multimedia/media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")</span></span>  
  
 <span data-ttu-id="6ad74-153">W poniższym przykładzie obraz służy do tworzenia kafelka, który ma szerokości i wysokości 50%.</span><span class="sxs-lookup"><span data-stu-id="6ad74-153">In the following example, an image is used to create a tile that has a width and height of 50%.</span></span> <span data-ttu-id="6ad74-154">Podstawowy Kafelek znajduje się pod adresem (0,0) obszaru wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="6ad74-154">The base tile is located at (0,0) of the output area.</span></span>  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 <span data-ttu-id="6ad74-155">W następnym przykładzie fragmentów <xref:System.Windows.Media.ImageBrush> do 25 o 25 pikselach niezależnych od urządzenia.</span><span class="sxs-lookup"><span data-stu-id="6ad74-155">The next example sets the tiles of an <xref:System.Windows.Media.ImageBrush> to 25 by 25 device independent pixels.</span></span> <span data-ttu-id="6ad74-156">Ponieważ <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> są bezwzględne, <xref:System.Windows.Media.ImageBrush> Kafelki są zawsze 25 o 25 pikseli, niezależnie od rozmiaru obszaru są rysowane.</span><span class="sxs-lookup"><span data-stu-id="6ad74-156">Because the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> are absolute, the <xref:System.Windows.Media.ImageBrush> tiles are always 25 by 25 pixels, regardless of the size of the area being painted.</span></span>  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>   
### <a name="tiling-behavior"></a><span data-ttu-id="6ad74-157">Zachowanie kafelków</span><span class="sxs-lookup"><span data-stu-id="6ad74-157">Tiling Behavior</span></span>  
 <span data-ttu-id="6ad74-158">A <xref:System.Windows.Media.TileBrush> tworzy sąsiadującym wzorzec podczas jego podstawowy Kafelek nie wypełnia całkowicie obszaru wyjściowego i tryb kafelków innych następnie <xref:System.Windows.Media.TileMode.None> jest określona.</span><span class="sxs-lookup"><span data-stu-id="6ad74-158">A <xref:System.Windows.Media.TileBrush> produces a tiled pattern when its base tile does not completely fill the output area and a tiling mode other then <xref:System.Windows.Media.TileMode.None> is specified.</span></span> <span data-ttu-id="6ad74-159">Gdy kafelka pędzla kafelka nie wypełnia całkowicie obszar wyjściowy jego <xref:System.Windows.Media.TileBrush.TileMode%2A> właściwość określa, czy powinny zostać zduplikowane podstawowy Kafelek, aby wypełnił obszar danych wyjściowych, a jeśli tak, jak Kafelek podstawowym powinny zostać zduplikowane.</span><span class="sxs-lookup"><span data-stu-id="6ad74-159">When a tile brush's tile does not completely fill the output area, its <xref:System.Windows.Media.TileBrush.TileMode%2A> property specifies whether the base tile should be duplicated to fill the output area and, if so, how the base tile should be duplicated.</span></span> <span data-ttu-id="6ad74-160"><xref:System.Windows.Media.TileBrush.TileMode%2A> Właściwość przyjmuje następujące wartości zdefiniowane przez <xref:System.Windows.Media.TileMode> wyliczenie:</span><span class="sxs-lookup"><span data-stu-id="6ad74-160">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property accepts the following values, defined by the <xref:System.Windows.Media.TileMode> enumeration:</span></span>  
  
-   <span data-ttu-id="6ad74-161"><xref:System.Windows.Media.TileMode.None>: Tylko podstawowy Kafelek jest rysowane.</span><span class="sxs-lookup"><span data-stu-id="6ad74-161"><xref:System.Windows.Media.TileMode.None>: Only the base tile is drawn.</span></span>  
  
-   <span data-ttu-id="6ad74-162"><xref:System.Windows.Media.TileMode.Tile>: Podstawowy Kafelek ma zostać narysowana i pozostałe obszar jest wypełniony, powtarzając podstawowy Kafelek tak, aby był przylegające do lewej krawędzi następnej i prawej krawędzi jednego kafelka podobnie do dołu i z góry.</span><span class="sxs-lookup"><span data-stu-id="6ad74-162"><xref:System.Windows.Media.TileMode.Tile>: The base tile is drawn and the remaining area is filled by repeating the base tile such that the right edge of one tile is adjacent to the left edge of the next, and similarly for bottom and top.</span></span>  
  
-   <span data-ttu-id="6ad74-163"><xref:System.Windows.Media.TileMode.FlipX>: Taki sam jak <xref:System.Windows.Media.TileMode.Tile>, ale alternatywny kolumn fragmentów są przerzucane poziomo.</span><span class="sxs-lookup"><span data-stu-id="6ad74-163"><xref:System.Windows.Media.TileMode.FlipX>: The same as <xref:System.Windows.Media.TileMode.Tile>, but alternate columns of tiles are flipped horizontally.</span></span>  
  
-   <span data-ttu-id="6ad74-164"><xref:System.Windows.Media.TileMode.FlipY>: Taki sam jak <xref:System.Windows.Media.TileMode.Tile>, ale Kafelki wiersze są przerzucane pionowo.</span><span class="sxs-lookup"><span data-stu-id="6ad74-164"><xref:System.Windows.Media.TileMode.FlipY>: The same as <xref:System.Windows.Media.TileMode.Tile>, but alternate rows of tiles are flipped vertically.</span></span>  
  
-   <span data-ttu-id="6ad74-165"><xref:System.Windows.Media.TileMode.FlipXY>: Kombinację <xref:System.Windows.Media.TileMode.FlipX> i <xref:System.Windows.Media.TileMode.FlipY>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-165"><xref:System.Windows.Media.TileMode.FlipXY>: A combination of <xref:System.Windows.Media.TileMode.FlipX> and <xref:System.Windows.Media.TileMode.FlipY>.</span></span>  
  
 <span data-ttu-id="6ad74-166">Na poniższym obrazie przedstawiono kafelków różne tryby.</span><span class="sxs-lookup"><span data-stu-id="6ad74-166">The following image illustrates the different tiling modes.</span></span>  
  
 <span data-ttu-id="6ad74-167">![Różne ustawienia TileBrush TileMode](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")</span><span class="sxs-lookup"><span data-stu-id="6ad74-167">![Different TileBrush TileMode settings](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")</span></span>  
  
 <span data-ttu-id="6ad74-168">W poniższym przykładzie jest używany obraz do malowania prostokąt 100 pikseli szerokości i wysokości 100 pikseli.</span><span class="sxs-lookup"><span data-stu-id="6ad74-168">In the following example, an image is used to paint a rectangle that is 100 pixels wide and 100 pixels tall.</span></span> <span data-ttu-id="6ad74-169">Przez ustawienie pędzla <xref:System.Windows.Media.TileBrush.Viewport%2A> została ustawiona na 0,0,0.25,0.25, pędzla podstawowy Kafelek ma zostać za 1/4 obszaru wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="6ad74-169">By setting the brush's <xref:System.Windows.Media.TileBrush.Viewport%2A> has been set to 0,0,0.25,0.25, the brush's base tile is made to be 1/4 of the output area.</span></span> <span data-ttu-id="6ad74-170">Pędzel <xref:System.Windows.Media.TileBrush.TileMode%2A> ma ustawioną wartość <xref:System.Windows.Media.TileMode.FlipXY>.</span><span class="sxs-lookup"><span data-stu-id="6ad74-170">The brush's <xref:System.Windows.Media.TileBrush.TileMode%2A> is set to <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="6ad74-171">tak, aby wypełnił prostokąt z wierszami kafelków.</span><span class="sxs-lookup"><span data-stu-id="6ad74-171">so that it fills the rectangle with rows of tiles.</span></span>  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a><span data-ttu-id="6ad74-172">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6ad74-172">See Also</span></span>  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 <xref:System.Windows.Media.TileBrush>  
 [<span data-ttu-id="6ad74-173">Malowanie obrazów, rysunki i elementy wizualne</span><span class="sxs-lookup"><span data-stu-id="6ad74-173">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="6ad74-174">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="6ad74-174">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)  
 [<span data-ttu-id="6ad74-175">Obiekty obiektu freezable — omówienie</span><span class="sxs-lookup"><span data-stu-id="6ad74-175">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="6ad74-176">Przykładowe ImageBrush</span><span class="sxs-lookup"><span data-stu-id="6ad74-176">ImageBrush Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [<span data-ttu-id="6ad74-177">Przykładowe VisualBrush</span><span class="sxs-lookup"><span data-stu-id="6ad74-177">VisualBrush Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160049)