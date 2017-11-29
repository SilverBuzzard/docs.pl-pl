---
title: "Jak animować właściwości bez użycia scenorysu"
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
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cfc1de83c6c91e7a42c09b080b647aaf440e5a61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a><span data-ttu-id="9a9c9-102">Jak animować właściwości bez użycia scenorysu</span><span class="sxs-lookup"><span data-stu-id="9a9c9-102">How to: Animate a Property Without Using a Storyboard</span></span>
<span data-ttu-id="9a9c9-103">W tym przykładzie przedstawiono jeden sposób zastosowania animacji do właściwości bez użycia <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="9a9c9-103">This example shows one way to apply an animation to a property without using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a9c9-104">Ta funkcja nie jest dostępna w [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a9c9-104">This functionality is not available in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="9a9c9-105">Informacje o animowania właściwości w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], zobacz [animować właściwości przy użyciu scenorysu](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="9a9c9-105">For information about animating a property in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="9a9c9-106">Aby zastosować animacji lokalnego do właściwości, należy użyć <xref:System.Windows.UIElement.BeginAnimation%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="9a9c9-106">To apply a local animation to a property, use the <xref:System.Windows.UIElement.BeginAnimation%2A> method.</span></span> <span data-ttu-id="9a9c9-107">Ta metoda przyjmuje dwa parametry: <xref:System.Windows.DependencyProperty> , który określa właściwość animacji i animacji do zastosowania do tej właściwości.</span><span class="sxs-lookup"><span data-stu-id="9a9c9-107">This method takes two parameters: a <xref:System.Windows.DependencyProperty> that specifies the property to animate, and the animation to apply to that property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a9c9-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="9a9c9-108">Example</span></span>  
 <span data-ttu-id="9a9c9-109">Poniższy przykład przedstawia sposób animować kolor tła i szerokość <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="9a9c9-109">The following example shows how to animate the width and background color of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 <span data-ttu-id="9a9c9-110">Różne klasy animacji w <xref:System.Windows.Media.Animation> przestrzeni nazw istnieją różne typy właściwości animacji.</span><span class="sxs-lookup"><span data-stu-id="9a9c9-110">A variety of animation classes in the <xref:System.Windows.Media.Animation> namespace exist for animating different types of properties.</span></span> <span data-ttu-id="9a9c9-111">Aby uzyskać więcej informacji na temat właściwości animacji, zobacz [omówienie animacja](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a9c9-111">For more information about animating properties, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="9a9c9-112">Aby uzyskać więcej informacji na temat właściwości zależności (typ właściwości, które są wyświetlane w tym przykładzie) i ich funkcje, zobacz [Przegląd właściwości zależności](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a9c9-112">For more information about dependency properties (the type of properties that are shown in these examples) and their features, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="9a9c9-113">Istnieją inne sposoby animować bez użycia <xref:System.Windows.Media.Animation.Storyboard> obiektów; Aby uzyskać więcej informacji, zobacz [— Przegląd właściwości animacji techniki](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a9c9-113">There are other ways to animate without using <xref:System.Windows.Media.Animation.Storyboard> objects; for more information, see [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9c9-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9a9c9-114">See Also</span></span>  
 <xref:System.Windows.Media.Animation.AnimationTimeline>  
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>  
 <xref:System.Windows.Media.Animation>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="9a9c9-115">Omówienie techniki animacji właściwość</span><span class="sxs-lookup"><span data-stu-id="9a9c9-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [<span data-ttu-id="9a9c9-116">Animacja — omówienie</span><span class="sxs-lookup"><span data-stu-id="9a9c9-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)