---
title: "Jak animować nieprzezroczystość elementu lub pędzla"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 808d29292e176af8d3af1fc0f4a02c48ee05ea35
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a><span data-ttu-id="0311d-102">Jak animować nieprzezroczystość elementu lub pędzla</span><span class="sxs-lookup"><span data-stu-id="0311d-102">How to: Animate the Opacity of an Element or Brush</span></span>
<span data-ttu-id="0311d-103">Aby element framework zanikania i widoku, można animować jego <xref:System.Windows.UIElement.Opacity%2A> można animować właściwości lub <xref:System.Windows.Media.Brush.Opacity%2A> właściwość <xref:System.Windows.Media.Brush> (lub pędzle) używany do rysowania go.</span><span class="sxs-lookup"><span data-stu-id="0311d-103">To make a framework element fade in and out of view, you can animate its <xref:System.Windows.UIElement.Opacity%2A> property or you can animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Brush> (or brushes) used to paint it.</span></span> <span data-ttu-id="0311d-104">Animowanie nieprzezroczystość elementu ułatwia i jego elementów podrzędnych zanikania i widoku, ale animacji pędzel używany do rysowania elementu umożliwia bardziej selektywnie stopniowo część elementu.</span><span class="sxs-lookup"><span data-stu-id="0311d-104">Animating the element's opacity makes it and its children fade in and out of view, but animating the brush used to paint the element enables you to be more selective about which portion of the element fades.</span></span> <span data-ttu-id="0311d-105">Można na przykład Animuj przezroczystość pędzla stosowaną tło przycisku.</span><span class="sxs-lookup"><span data-stu-id="0311d-105">For example, you could animate the opacity of a brush used to paint a button's background.</span></span> <span data-ttu-id="0311d-106">To spowodowałoby tło przycisku do zanikania i zmniejszanie widoku, pozostawiając całkowicie nieprzezroczyste jego tekstu.</span><span class="sxs-lookup"><span data-stu-id="0311d-106">This would cause the button's background to fade in and out of view, while leaving its text fully opaque.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0311d-107">Animowanie <xref:System.Windows.Media.Brush.Opacity%2A> z <xref:System.Windows.Media.Brush> zalety wydajności za pośrednictwem animacji <xref:System.Windows.UIElement.Opacity%2A> właściwości elementu.</span><span class="sxs-lookup"><span data-stu-id="0311d-107">Animating the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.Brush> provides performance benefits over animating the <xref:System.Windows.UIElement.Opacity%2A> property of an element.</span></span>  
  
 <span data-ttu-id="0311d-108">W poniższym przykładzie dwa przyciski animowanych tak, aby ich stopniowe i widoku.</span><span class="sxs-lookup"><span data-stu-id="0311d-108">In the following example, two buttons are animated so that they fade in and out of view.</span></span> <span data-ttu-id="0311d-109">Nieprzezroczystość pierwszy <xref:System.Windows.Controls.Button> jest animowany z `1.0` do `0.0` za pośrednictwem <xref:System.Windows.Media.Animation.Timeline.Duration%2A> pięć sekund.</span><span class="sxs-lookup"><span data-stu-id="0311d-109">The Opacity of the first <xref:System.Windows.Controls.Button> is animated from `1.0` to `0.0` over a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> of five seconds.</span></span> <span data-ttu-id="0311d-110">Drugi przycisk jest również animowany, ale nieprzezroczystość SolidColorBrush używany do malowania jego <xref:System.Windows.Controls.Control.Background%2A> jest animowany zamiast nieprzezroczystości całego przycisku.</span><span class="sxs-lookup"><span data-stu-id="0311d-110">The second button is also animated, but the Opacity of the SolidColorBrush used to paint its <xref:System.Windows.Controls.Control.Background%2A> is animated rather than the opacity of the entire button.</span></span> <span data-ttu-id="0311d-111">Po uruchomieniu przykładzie przycisku pierwszej całkowicie stopniowo i widoku, gdy tło przycisku drugi stopniowo i widoku.</span><span class="sxs-lookup"><span data-stu-id="0311d-111">When the example is run, the first button completely fades in and out of view, while only the background of the second button fades in and out of view.</span></span> <span data-ttu-id="0311d-112">Tekst i obramowania pozostają całkowicie nieprzezroczyste.</span><span class="sxs-lookup"><span data-stu-id="0311d-112">Its text and border remain fully opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0311d-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="0311d-113">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 <span data-ttu-id="0311d-114">W tym przykładzie kodu zostało pominięte.</span><span class="sxs-lookup"><span data-stu-id="0311d-114">Code has been omitted from this example.</span></span> <span data-ttu-id="0311d-115">Pełny przykład przedstawiono również sposób Animuj przezroczystość <xref:System.Windows.Media.Color> w <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="0311d-115">The full sample also shows how to animate the opacity of a <xref:System.Windows.Media.Color> within a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="0311d-116">Aby uzyskać pełny przykład, zobacz [animacji nieprzezroczystość przykład elementu](http://go.microsoft.com/fwlink/?LinkID=159968).</span><span class="sxs-lookup"><span data-stu-id="0311d-116">For the full sample, see the [Animating the Opacity of an Element Sample](http://go.microsoft.com/fwlink/?LinkID=159968).</span></span>