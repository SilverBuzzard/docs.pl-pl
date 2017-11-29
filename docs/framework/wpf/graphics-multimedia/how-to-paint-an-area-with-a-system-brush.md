---
title: "Jak malować obszar pędzlem systemowym"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 355df3718d90768cdfa8bc9780c44c19eb4bf9bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="864d1-102">Jak malować obszar pędzlem systemowym</span><span class="sxs-lookup"><span data-stu-id="864d1-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="864d1-103"><xref:System.Windows.SystemColors> Klasy zapewnia dostęp do systemu pędzle i kolory, takich jak <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, i <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span><span class="sxs-lookup"><span data-stu-id="864d1-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="864d1-104">Pędzel systemu <xref:System.Windows.Media.SolidColorBrush> obiekt, który umożliwia malowanie obszar kolorem określonego systemu.</span><span class="sxs-lookup"><span data-stu-id="864d1-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="864d1-105">Pędzel systemu zawsze daje wypełnieniem; Nie można użyć do Tworzenie gradientu.</span><span class="sxs-lookup"><span data-stu-id="864d1-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="864d1-106">Pędzle system służy jako statyczne lub dynamiczne zasobów.</span><span class="sxs-lookup"><span data-stu-id="864d1-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="864d1-107">Użyj zasobu dynamicznego pędzla do automatycznej aktualizacji, jeśli użytkownik zmieni pędzla systemu, ponieważ aplikacja jest uruchomiona; w przeciwnym razie użyj statycznych zasobów.</span><span class="sxs-lookup"><span data-stu-id="864d1-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="864d1-108">Klasa SystemColors zawiera szereg statycznej właściwości, które strict konwencją nazewnictwa:</span><span class="sxs-lookup"><span data-stu-id="864d1-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="864d1-109">*\<SystemColor >*pędzla</span><span class="sxs-lookup"><span data-stu-id="864d1-109">*\<SystemColor>*Brush</span></span>  
  
     <span data-ttu-id="864d1-110">Pobiera statyczny odwołanie do <xref:System.Windows.Media.SolidColorBrush> koloru określonego systemu.</span><span class="sxs-lookup"><span data-stu-id="864d1-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="864d1-111">*\<SystemColor >*BrushKey</span><span class="sxs-lookup"><span data-stu-id="864d1-111">*\<SystemColor>*BrushKey</span></span>  
  
     <span data-ttu-id="864d1-112">Pobiera dynamiczny odwołanie do <xref:System.Windows.Media.SolidColorBrush> koloru określonego systemu.</span><span class="sxs-lookup"><span data-stu-id="864d1-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="864d1-113">*\<SystemColor >*kolorów</span><span class="sxs-lookup"><span data-stu-id="864d1-113">*\<SystemColor>*Color</span></span>  
  
     <span data-ttu-id="864d1-114">Pobiera statyczny odwołanie do <xref:System.Windows.Media.Color> struktury kolorów określonego systemu.</span><span class="sxs-lookup"><span data-stu-id="864d1-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="864d1-115">*\<SystemColor >*ColorKey</span><span class="sxs-lookup"><span data-stu-id="864d1-115">*\<SystemColor>*ColorKey</span></span>  
  
     <span data-ttu-id="864d1-116">Pobiera dynamiczny odwołanie do <xref:System.Windows.Media.Color> struktury kolorów określonego systemu.</span><span class="sxs-lookup"><span data-stu-id="864d1-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="864d1-117">Jest kolorem systemowym <xref:System.Windows.Media.Color> struktury, który może służyć do konfigurowania pędzla.</span><span class="sxs-lookup"><span data-stu-id="864d1-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="864d1-118">Na przykład można utworzyć przy użyciu kolorów systemu przez ustawienie gradientu <xref:System.Windows.Media.GradientStop.Color%2A> właściwości <xref:System.Windows.Media.LinearGradientBrush> obiektu gradientu kolorów systemu.</span><span class="sxs-lookup"><span data-stu-id="864d1-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="864d1-119">Na przykład zobacz [kolorów systemu używany w gradiencie](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="864d1-119">For an example, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="864d1-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="864d1-120">Example</span></span>  
 <span data-ttu-id="864d1-121">W poniższym przykładzie użyto odwołania pędzla dynamicznego systemu można ustawić tło przycisku.</span><span class="sxs-lookup"><span data-stu-id="864d1-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="864d1-122">W następnym przykładzie użyto odwołania pędzla systemu statycznego można ustawić tło przycisku.</span><span class="sxs-lookup"><span data-stu-id="864d1-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="864d1-123">Na przykład przedstawiający sposób użycia kolorem systemowym w gradiencie zobacz [Użyj kolorów systemu w gradiencie](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="864d1-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="864d1-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="864d1-124">See Also</span></span>  
 [<span data-ttu-id="864d1-125">Kolory System używany w gradiencie</span><span class="sxs-lookup"><span data-stu-id="864d1-125">Use System Colors in a Gradient</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [<span data-ttu-id="864d1-126">Malowanie pełnych kolorów i gradientów — omówienie</span><span class="sxs-lookup"><span data-stu-id="864d1-126">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)