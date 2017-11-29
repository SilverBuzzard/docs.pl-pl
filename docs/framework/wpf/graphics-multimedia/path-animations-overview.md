---
title: "Przegląd Animacja ścieżki"
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
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 237dbe83fa52bb967d2f2429fb2beb021c084f23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="path-animations-overview"></a><span data-ttu-id="4f2af-102">Przegląd Animacja ścieżki</span><span class="sxs-lookup"><span data-stu-id="4f2af-102">Path Animations Overview</span></span>
<span data-ttu-id="4f2af-103"><a name="introduction"></a>W tym temacie przedstawiono animacje ścieżki, które umożliwiają korzystanie geometrycznych ścieżki do generowania wartości danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="4f2af-103"><a name="introduction"></a> This topic introduces path animations, which enable you to use a geometric path to generate output values.</span></span> <span data-ttu-id="4f2af-104">Ścieżka animacje są przydatne w przypadku przenoszenia i obracanie obiektów wzdłuż ścieżki złożone.</span><span class="sxs-lookup"><span data-stu-id="4f2af-104">Path animations are useful for moving and rotating objects along complex paths.</span></span>  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a><span data-ttu-id="4f2af-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4f2af-105">Prerequisites</span></span>  
 <span data-ttu-id="4f2af-106">Aby zrozumieć, w tym temacie, należy się zapoznać z [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funkcje animacji.</span><span class="sxs-lookup"><span data-stu-id="4f2af-106">To understand this topic, you should be familiar with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animations features.</span></span> <span data-ttu-id="4f2af-107">Aby obejrzeć wprowadzenie do funkcji animacji, zobacz [omówienie animacja](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4f2af-107">For an introduction to animation features, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="4f2af-108">Ponieważ używasz <xref:System.Windows.Media.PathGeometry> obiekt do definiowania animacji ścieżki, należy także zapoznać się z <xref:System.Windows.Media.PathGeometry> i różne typy <xref:System.Windows.Media.PathSegment> obiektów.</span><span class="sxs-lookup"><span data-stu-id="4f2af-108">Because you use a <xref:System.Windows.Media.PathGeometry> object to define a path animation, you should also be familiar with <xref:System.Windows.Media.PathGeometry> and the different types of <xref:System.Windows.Media.PathSegment> objects.</span></span> <span data-ttu-id="4f2af-109">Aby uzyskać więcej informacji, zobacz [omówienie geometrii](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4f2af-109">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a><span data-ttu-id="4f2af-110">Co to jest animacji ścieżki?</span><span class="sxs-lookup"><span data-stu-id="4f2af-110">What Is a Path Animation?</span></span>  
 <span data-ttu-id="4f2af-111">Animacja ścieżki jest typem <xref:System.Windows.Media.Animation.AnimationTimeline> używającą <xref:System.Windows.Media.PathGeometry> jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="4f2af-111">A path animation is a type of <xref:System.Windows.Media.Animation.AnimationTimeline> that uses a <xref:System.Windows.Media.PathGeometry> as its input.</span></span> <span data-ttu-id="4f2af-112">Zamiast do ustawiania From, lub przez właściwość (podobnie jak w przypadku From lub do/przez animacji) lub przy użyciu klucza ramki (należy użyć animacji klucza ramki), definiują ścieżkę geometryczne i użyj jej do ustawienia `PathGeometry` właściwości animacji ścieżki.</span><span class="sxs-lookup"><span data-stu-id="4f2af-112">Instead of setting a From, To, or By property (as you do for a From/To/By animation) or using key frames (as you use for a key-frame animation), you define a geometric path and use it to set the `PathGeometry` property of the path animation.</span></span> <span data-ttu-id="4f2af-113">W trakcie animacji ścieżki odczytuje x, y oraz informacje o kąt ze ścieżki i używa tych informacji do generowania danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="4f2af-113">As the path animation progresses, it reads the x, y, and angle information from the path and uses that information to generate its output.</span></span>  
  
 <span data-ttu-id="4f2af-114">Ścieżka animacje są bardzo przydatne w przypadku obiektu wzdłuż ścieżki złożonych animacji.</span><span class="sxs-lookup"><span data-stu-id="4f2af-114">Path animations are very useful for animating an object along a complex path.</span></span> <span data-ttu-id="4f2af-115">Aby przenieść obiekt na ścieżce jest użycie <xref:System.Windows.Media.MatrixTransform> i <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Aby przekształcić obiektu na ścieżce złożonych.</span><span class="sxs-lookup"><span data-stu-id="4f2af-115">One way to move an object along a path is to use a <xref:System.Windows.Media.MatrixTransform> and a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> to transform an object along a complex path.</span></span> <span data-ttu-id="4f2af-116">W poniższym przykładzie pokazano tej metody za pomocą <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> obiektu do animowania <xref:System.Windows.Media.MatrixTransform.Matrix%2A> właściwość <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="4f2af-116">The following example demonstrates this technique by using the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="4f2af-117"><xref:System.Windows.Media.MatrixTransform> Jest stosowana do przycisku i powoduje, że aby przesunąć wzdłuż ścieżki.</span><span class="sxs-lookup"><span data-stu-id="4f2af-117">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="4f2af-118">Ponieważ <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> właściwość jest ustawiona na `true`, prostokąt obraca wzdłuż tangens ścieżki.</span><span class="sxs-lookup"><span data-stu-id="4f2af-118">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="4f2af-119">Aby uzyskać więcej informacji o składni ścieżki, który jest używany w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] przykład, zobacz [składnia znacznika ścieżki](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) omówienie.</span><span class="sxs-lookup"><span data-stu-id="4f2af-119">For more information about the path syntax that is used in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) overview.</span></span> <span data-ttu-id="4f2af-120">Pełny przykład, zobacz [próbki animacji ścieżki](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="4f2af-120">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="4f2af-121">Animacja ścieżki można zastosować do właściwości, za pomocą <xref:System.Windows.Media.Animation.Storyboard> w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] i kodu lub przy użyciu <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> w kodzie.</span><span class="sxs-lookup"><span data-stu-id="4f2af-121">You can apply a path animation to a property by using a <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and code, or by using the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method in code.</span></span> <span data-ttu-id="4f2af-122">Umożliwia także animacji ścieżki do utworzenia <xref:System.Windows.Media.Animation.AnimationClock> i zastosować je do co najmniej jednej właściwości.</span><span class="sxs-lookup"><span data-stu-id="4f2af-122">You can also use a path animation to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to one or more properties.</span></span> <span data-ttu-id="4f2af-123">Aby uzyskać więcej informacji na temat różnych metod do zastosowania animacji, zobacz [— Przegląd właściwości animacji techniki](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4f2af-123">For more information about the different methods for applying animations, see [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span></span>  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a><span data-ttu-id="4f2af-124">Typy animacji ścieżki</span><span class="sxs-lookup"><span data-stu-id="4f2af-124">Path Animation Types</span></span>  
 <span data-ttu-id="4f2af-125">Ponieważ animacje Generowanie wartości właściwości, istnieją typy innej animacji dla różnych typach właściwości.</span><span class="sxs-lookup"><span data-stu-id="4f2af-125">Because animations generate property values, there are different animation types for different property types.</span></span> <span data-ttu-id="4f2af-126">Do animowania właściwości, która przyjmuje <xref:System.Double> (takich jak <xref:System.Windows.Media.TranslateTransform.X%2A> właściwość <xref:System.Windows.Media.TranslateTransform>), użyj animacji tworzącego <xref:System.Double> wartości.</span><span class="sxs-lookup"><span data-stu-id="4f2af-126">To animate a property that takes a <xref:System.Double> (such as the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform>), you use an animation that produces <xref:System.Double> values.</span></span> <span data-ttu-id="4f2af-127">Aby animować właściwości, która przyjmuje <xref:System.Windows.Point>, użyj animacji tworzącego <xref:System.Windows.Point> wartości i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="4f2af-127">To animate a property that takes a <xref:System.Windows.Point>, you use an animation that produces <xref:System.Windows.Point> values, and so on.</span></span>  
  
 <span data-ttu-id="4f2af-128">Ścieżka animacji klasy należą do <xref:System.Windows.Media.Animation> przestrzeni nazw i korzystać z następującą konwencją nazewnictwa:</span><span class="sxs-lookup"><span data-stu-id="4f2af-128">Path animation classes belong to the <xref:System.Windows.Media.Animation> namespace and use the following naming convention:</span></span>  
  
 <span data-ttu-id="4f2af-129">*\<Typ >*`AnimationUsingPath`</span><span class="sxs-lookup"><span data-stu-id="4f2af-129">*\<Type>* `AnimationUsingPath`</span></span>  
  
 <span data-ttu-id="4f2af-130">Gdzie  *\<typu >* jest typ wartości, które animuje klasy.</span><span class="sxs-lookup"><span data-stu-id="4f2af-130">Where *\<Type>* is the type of value that the class animates.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="4f2af-131">udostępnia następujące ścieżki klasy animacji.</span><span class="sxs-lookup"><span data-stu-id="4f2af-131"> provides the following path animation classes.</span></span>  
  
|<span data-ttu-id="4f2af-132">Typ właściwości</span><span class="sxs-lookup"><span data-stu-id="4f2af-132">Property type</span></span>|<span data-ttu-id="4f2af-133">Odpowiadającą klasę animacji ścieżki</span><span class="sxs-lookup"><span data-stu-id="4f2af-133">Corresponding path animation class</span></span>|<span data-ttu-id="4f2af-134">Przykład</span><span class="sxs-lookup"><span data-stu-id="4f2af-134">Example</span></span>|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[<span data-ttu-id="4f2af-135">Animowanie obiektu wzdłuż ścieżki (dwa razy Animacja)</span><span class="sxs-lookup"><span data-stu-id="4f2af-135">Animate an Object Along a Path (Double Animation)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[<span data-ttu-id="4f2af-136">Animowanie obiektu wzdłuż ścieżki (macierzy Animacja)</span><span class="sxs-lookup"><span data-stu-id="4f2af-136">Animate an Object Along a Path (Matrix Animation)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[<span data-ttu-id="4f2af-137">Animowanie obiektu wzdłuż ścieżki (punkt Animacja)</span><span class="sxs-lookup"><span data-stu-id="4f2af-137">Animate an Object Along a Path (Point Animation)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 <span data-ttu-id="4f2af-138">A <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> generuje <xref:System.Windows.Media.Matrix> wartości z jego <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f2af-138">A <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> generates <xref:System.Windows.Media.Matrix> values from its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>.</span></span> <span data-ttu-id="4f2af-139">W przypadku użycia z <xref:System.Windows.Media.MatrixTransform>, <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> można przenieść obiekt na ścieżce.</span><span class="sxs-lookup"><span data-stu-id="4f2af-139">When used with a <xref:System.Windows.Media.MatrixTransform>, a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> can move an object along a path.</span></span> <span data-ttu-id="4f2af-140">Jeśli ustawisz <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> właściwość <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> do `true`, również obraca obiekt wzdłuż krzywych ścieżki.</span><span class="sxs-lookup"><span data-stu-id="4f2af-140">If you set the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property of the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> to `true`, it also rotates the object along the curves of the path.</span></span>  
  
 <span data-ttu-id="4f2af-141">A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> generuje <xref:System.Windows.Point> wartości z x-y współrzędne i jego <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f2af-141">A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> generates <xref:System.Windows.Point> values from the x- and y-coordinates of its <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>.</span></span> <span data-ttu-id="4f2af-142">Za pomocą <xref:System.Windows.Media.Animation.PointAnimationUsingPath> do animowania właściwości, która przyjmuje <xref:System.Windows.Point> wartości, można przenieść obiekt na ścieżce.</span><span class="sxs-lookup"><span data-stu-id="4f2af-142">By using a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate a property that takes <xref:System.Windows.Point> values, you can move an object along a path.</span></span> <span data-ttu-id="4f2af-143">A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> nie można obrócić obiektów.</span><span class="sxs-lookup"><span data-stu-id="4f2af-143">A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> cannot rotate objects.</span></span>  
  
 <span data-ttu-id="4f2af-144">A <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> generuje <xref:System.Double> wartości z jego <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f2af-144">A <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> generates <xref:System.Double> values from its <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>.</span></span> <span data-ttu-id="4f2af-145">Przez ustawienie <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> właściwości, można określić czy <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> używa współrzędną x, współrzędną y lub kąta ścieżki jako dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="4f2af-145">By setting the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> property, you can specify whether the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> uses the x-coordinate, y-coordinate, or angle of the path as its output.</span></span> <span data-ttu-id="4f2af-146">Można użyć <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Obracanie obiektu lub przenieś go wzdłuż osi x i y.</span><span class="sxs-lookup"><span data-stu-id="4f2af-146">You can use a <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> to rotate an object or move it along the x-axis or y-axis.</span></span>  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a><span data-ttu-id="4f2af-147">Ścieżka animacji w danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="4f2af-147">Path Animation Input</span></span>  
 <span data-ttu-id="4f2af-148">Każda klasa animacji ścieżka zawiera <xref:System.Windows.Media.PathGeometry> właściwości do określenia jej danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="4f2af-148">Each path animation class provides a <xref:System.Windows.Media.PathGeometry> property for specifying its input.</span></span> <span data-ttu-id="4f2af-149">Używa animacji ścieżki <xref:System.Windows.Media.PathGeometry> do generowania wartości jego dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="4f2af-149">The path animation uses the <xref:System.Windows.Media.PathGeometry> to generate its output values.</span></span> <span data-ttu-id="4f2af-150"><xref:System.Windows.Media.PathGeometry> Klasa umożliwia opisują wiele złożonych dane, które składają się z łuki, krzywych i linii.</span><span class="sxs-lookup"><span data-stu-id="4f2af-150">The <xref:System.Windows.Media.PathGeometry> class lets you describe multiple complex figures that are composed of arcs, curves, and lines.</span></span>  
  
 <span data-ttu-id="4f2af-151">Istotą <xref:System.Windows.Media.PathGeometry> jest kolekcją <xref:System.Windows.Media.PathFigure> obiektów; te obiekty są więc o nazwie, ponieważ każdy rysunek opisuje dyskretne kształtu w <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="4f2af-151">At the heart of a <xref:System.Windows.Media.PathGeometry> is a collection of <xref:System.Windows.Media.PathFigure> objects; these objects are so named because each figure describes a discrete shape in the <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="4f2af-152">Każdy <xref:System.Windows.Media.PathFigure> składa się z co najmniej jednego <xref:System.Windows.Media.PathSegment> obiektów, z których każdy zawiera opis segment rysunku.</span><span class="sxs-lookup"><span data-stu-id="4f2af-152">Each <xref:System.Windows.Media.PathFigure> consists of one or more <xref:System.Windows.Media.PathSegment> objects, each of which describes a segment of the figure.</span></span>  
  
 <span data-ttu-id="4f2af-153">Istnieje wiele typów segmentów.</span><span class="sxs-lookup"><span data-stu-id="4f2af-153">There are many types of segments.</span></span>  
  
|<span data-ttu-id="4f2af-154">Typ segmentu</span><span class="sxs-lookup"><span data-stu-id="4f2af-154">Segment Type</span></span>|<span data-ttu-id="4f2af-155">Opis</span><span class="sxs-lookup"><span data-stu-id="4f2af-155">Description</span></span>|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|<span data-ttu-id="4f2af-156">Tworzy łuku między dwoma punktami.</span><span class="sxs-lookup"><span data-stu-id="4f2af-156">Creates an elliptical arc between two points.</span></span>|  
|<xref:System.Windows.Media.BezierSegment>|<span data-ttu-id="4f2af-157">Tworzy sześcienny krzywej Beziera między dwoma punktami.</span><span class="sxs-lookup"><span data-stu-id="4f2af-157">Creates a cubic Bezier curve between two points.</span></span>|  
|<xref:System.Windows.Media.LineSegment>|<span data-ttu-id="4f2af-158">Tworzy linię między dwoma punktami.</span><span class="sxs-lookup"><span data-stu-id="4f2af-158">Creates a line between two points.</span></span>|  
|<xref:System.Windows.Media.PolyBezierSegment>|<span data-ttu-id="4f2af-159">Tworzy serię sześcienny krzywych Beziera.</span><span class="sxs-lookup"><span data-stu-id="4f2af-159">Creates a series of cubic Bezier curves.</span></span>|  
|<xref:System.Windows.Media.PolyLineSegment>|<span data-ttu-id="4f2af-160">Tworzy serię wierszy.</span><span class="sxs-lookup"><span data-stu-id="4f2af-160">Creates a series of lines.</span></span>|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|<span data-ttu-id="4f2af-161">Tworzy serię kwadratową krzywych Beziera.</span><span class="sxs-lookup"><span data-stu-id="4f2af-161">Creates a series of quadratic Bezier curves.</span></span>|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|<span data-ttu-id="4f2af-162">Tworzy kwadratową krzywą Beziera.</span><span class="sxs-lookup"><span data-stu-id="4f2af-162">Creates a quadratic Bezier curve.</span></span>|  
  
 <span data-ttu-id="4f2af-163">Segmenty w <xref:System.Windows.Media.PathFigure> są łączone w pojedynczego kształtu geometryczne, która wykorzystuje punkt końcowy segmentu jako punkt początkowy następnego segmentu.</span><span class="sxs-lookup"><span data-stu-id="4f2af-163">The segments in a <xref:System.Windows.Media.PathFigure> are combined into a single geometric shape, which uses the end point of a segment as the start point of the next segment.</span></span> <span data-ttu-id="4f2af-164"><xref:System.Windows.Media.PathFigure.StartPoint%2A> Właściwość <xref:System.Windows.Media.PathFigure> określa punkt, z którego ma zostać narysowana pierwszy segment.</span><span class="sxs-lookup"><span data-stu-id="4f2af-164">The <xref:System.Windows.Media.PathFigure.StartPoint%2A> property of a <xref:System.Windows.Media.PathFigure> specifies the point from which the first segment is drawn.</span></span> <span data-ttu-id="4f2af-165">Każdy z segmentów kolejnych zostanie uruchomiony w punkcie końcowym poprzedniego segmentu.</span><span class="sxs-lookup"><span data-stu-id="4f2af-165">Each subsequent segment starts at the end point of the previous segment.</span></span> <span data-ttu-id="4f2af-166">Na przykład linią pionową z `10,50` do `10,150` można zdefiniować ustawiając <xref:System.Windows.Media.PathFigure.StartPoint%2A> właściwości `10,50` i tworzenie <xref:System.Windows.Media.LineSegment> z <xref:System.Windows.Media.LineSegment.Point%2A> ustawienie właściwości `10,150`.</span><span class="sxs-lookup"><span data-stu-id="4f2af-166">For example, a vertical line from `10,50` to `10,150` can be defined by setting the <xref:System.Windows.Media.PathFigure.StartPoint%2A> property to `10,50` and creating a <xref:System.Windows.Media.LineSegment> with a <xref:System.Windows.Media.LineSegment.Point%2A> property setting of `10,150`.</span></span>  
  
 <span data-ttu-id="4f2af-167">Aby uzyskać więcej informacji na temat <xref:System.Windows.Media.PathGeometry> obiekty, zobacz [omówienie geometrii](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4f2af-167">For more information about <xref:System.Windows.Media.PathGeometry> objects, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
 <span data-ttu-id="4f2af-168">W [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], umożliwia także specjalnej składni skróconej można ustawić <xref:System.Windows.Media.PathGeometry.Figures%2A> właściwość <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="4f2af-168">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also use a special abbreviated syntax to set the <xref:System.Windows.Media.PathGeometry.Figures%2A> property of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="4f2af-169">Aby uzyskać więcej informacji, zobacz [składnia znacznika ścieżki](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) omówienie.</span><span class="sxs-lookup"><span data-stu-id="4f2af-169">For more information, see [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) overview.</span></span>  
  
 <span data-ttu-id="4f2af-170">Aby uzyskać więcej informacji o składni ścieżki, który jest używany w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] przykład, zobacz [składnia znacznika ścieżki](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) omówienie.</span><span class="sxs-lookup"><span data-stu-id="4f2af-170">For more information about the path syntax that is used in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) overview.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2af-171">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4f2af-171">See Also</span></span>  
 [<span data-ttu-id="4f2af-172">Ścieżka animacji próbki</span><span class="sxs-lookup"><span data-stu-id="4f2af-172">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="4f2af-173">Składnia znacznika ścieżki</span><span class="sxs-lookup"><span data-stu-id="4f2af-173">Path Markup Syntax</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [<span data-ttu-id="4f2af-174">Ścieżka animacji — tematy porad</span><span class="sxs-lookup"><span data-stu-id="4f2af-174">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [<span data-ttu-id="4f2af-175">Animacja — omówienie</span><span class="sxs-lookup"><span data-stu-id="4f2af-175">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="4f2af-176">Omówienie techniki animacji właściwość</span><span class="sxs-lookup"><span data-stu-id="4f2af-176">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)