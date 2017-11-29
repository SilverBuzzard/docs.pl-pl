---
title: "Jak obrócić obiekt z wykorzystaniem ścieżki geometrycznej (animacja Matrix)"
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
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0c624b221c1e4c122728887a9d592a3275d8f8e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="a807b-102">Jak obrócić obiekt z wykorzystaniem ścieżki geometrycznej (animacja Matrix)</span><span class="sxs-lookup"><span data-stu-id="a807b-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="a807b-103">Ten przykład przedstawia sposób użycia <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> i <xref:System.Windows.Media.MatrixTransform> obracania (Tabela przestawna) ścieżce geometryczne, zdefiniowane przez obiekt <xref:System.Windows.Media.PathGeometry> obiektu.</span><span class="sxs-lookup"><span data-stu-id="a807b-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a807b-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="a807b-104">Example</span></span>  
 <span data-ttu-id="a807b-105">W poniższym przykładzie użyto <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> obiektu do animowania <xref:System.Windows.Media.MatrixTransform.Matrix%2A> właściwość <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="a807b-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="a807b-106"><xref:System.Windows.Media.MatrixTransform> Jest stosowana do przycisku i powoduje, że aby przesunąć wzdłuż ścieżki.</span><span class="sxs-lookup"><span data-stu-id="a807b-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="a807b-107">Ponieważ <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> właściwość jest ustawiona na `true`, prostokąt obraca wzdłuż tangens ścieżki.</span><span class="sxs-lookup"><span data-stu-id="a807b-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="a807b-108">Pełny przykład, zobacz [próbki animacji ścieżki](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="a807b-108">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="a807b-109">Wersja kodu powyższego przykładu używane <xref:System.Windows.Media.Animation.Storyboard> do animowania <xref:System.Windows.Media.EllipseGeometry>, mimo że tylko jeden animacja została zastosowana.</span><span class="sxs-lookup"><span data-stu-id="a807b-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="a807b-110">Prostsze dotyczą animacji jednej właściwości w kodzie jest użycie <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="a807b-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="a807b-111">Na przykład zobacz [animowania właściwości bez Using scenorysu](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="a807b-111">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a807b-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a807b-112">See Also</span></span>  
 [<span data-ttu-id="a807b-113">Animacja — omówienie</span><span class="sxs-lookup"><span data-stu-id="a807b-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="a807b-114">Ścieżka animacji — tematy porad</span><span class="sxs-lookup"><span data-stu-id="a807b-114">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [<span data-ttu-id="a807b-115">Ścieżka animacji próbki</span><span class="sxs-lookup"><span data-stu-id="a807b-115">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)