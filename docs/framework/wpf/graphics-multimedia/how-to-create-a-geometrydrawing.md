---
title: 'Porady: tworzenie GeometryDrawing'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f0fa86a9786e5440db9fec0cee76c5ed28363b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="74c68-102">Porady: tworzenie GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="74c68-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="74c68-103">W tym przykładzie pokazano, jak utworzyć i wyświetlić <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="74c68-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="74c68-104">A <xref:System.Windows.Media.GeometryDrawing> umożliwia utworzenie kształt z wypełnieniem lecz konspektu przez skojarzenie <xref:System.Windows.Media.Pen> i <xref:System.Windows.Media.Brush> z <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="74c68-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="74c68-105"><xref:System.Windows.Media.GeometryDrawing.Geometry%2A> Opisuje strukturę kształtu <xref:System.Windows.Media.GeometryDrawing.Brush%2A> opisuje wypełnienia kształtu i <xref:System.Windows.Media.GeometryDrawing.Pen%2A> opisuje konturu kształtu.</span><span class="sxs-lookup"><span data-stu-id="74c68-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74c68-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="74c68-106">Example</span></span>  
 <span data-ttu-id="74c68-107">W poniższym przykładzie użyto <xref:System.Windows.Media.GeometryDrawing> do renderowania kształtu.</span><span class="sxs-lookup"><span data-stu-id="74c68-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="74c68-108">Kształt jest opisane przez <xref:System.Windows.Media.GeometryGroup> i dwa <xref:System.Windows.Media.EllipseGeometry> obiektów.</span><span class="sxs-lookup"><span data-stu-id="74c68-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="74c68-109">Wewnątrz kształtu jest malowany <xref:System.Windows.Media.LinearGradientBrush> i konturu jej jest rysowany z <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span><span class="sxs-lookup"><span data-stu-id="74c68-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="74c68-110"><xref:System.Windows.Media.GeometryDrawing> Jest wyświetlany za pomocą <xref:System.Windows.Media.ImageDrawing> i <xref:System.Windows.Controls.Image> elementu.</span><span class="sxs-lookup"><span data-stu-id="74c68-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="74c68-111">Na poniższej ilustracji przedstawiono powstałe w ten sposób <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="74c68-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="74c68-112">![GeometryDrawing zawierający dwie elipsy](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="74c68-112">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="74c68-113">Do tworzenia bardziej złożonych rysunków, można połączyć wiele obiektów rysowania w jednej złożonym Rysowanie za pomocą <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="74c68-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c68-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="74c68-114">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup>  
 [<span data-ttu-id="74c68-115">Rysowanie obiekty — omówienie</span><span class="sxs-lookup"><span data-stu-id="74c68-115">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="74c68-116">Omówienie geometrii</span><span class="sxs-lookup"><span data-stu-id="74c68-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="74c68-117">Tworzenie złożonego rysunku</span><span class="sxs-lookup"><span data-stu-id="74c68-117">Create a Composite Drawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)