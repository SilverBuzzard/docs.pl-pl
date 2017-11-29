---
title: "Typy systemów współrzędnych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be89584ee8e7a82c405bf8664bfad18ced6d989a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="fea7a-102">Typy systemów współrzędnych</span><span class="sxs-lookup"><span data-stu-id="fea7a-102">Types of Coordinate Systems</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="fea7a-103">używa trzech przestrzeni współrzędnych: world, strony i urządzenia.</span><span class="sxs-lookup"><span data-stu-id="fea7a-103"> uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="fea7a-104">Współrzędnych świata są współrzędne użyta do modelowania określonego world grafiki i współrzędne, które są przekazywane do metody w programie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fea7a-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="fea7a-105">Układ współrzędnych używany przez powierzchni rysowania, takich jak formularz lub formant można znaleźć współrzędnych strony.</span><span class="sxs-lookup"><span data-stu-id="fea7a-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="fea7a-106">Współrzędne urządzenia są współrzędne używany przez urządzenie fizyczne sformułowane, takich jak ekranu lub arkusza.</span><span class="sxs-lookup"><span data-stu-id="fea7a-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="fea7a-107">Podczas wywoływania `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, punkty, które są przekazywane do <xref:System.Drawing.Graphics.DrawLine%2A> metoda —`(0, 0)` i `(160, 80)`— znajdują się w przestrzeni współrzędnych świata.</span><span class="sxs-lookup"><span data-stu-id="fea7a-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="fea7a-108">Przed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] można narysować linię na ekranie, współrzędne przekazuj sekwencję transformacji.</span><span class="sxs-lookup"><span data-stu-id="fea7a-108">Before [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="fea7a-109">Jeden przekształcania, nazywany transformacji świata konwertuje współrzędnych świata współrzędnych strony i innym przekształcania, nazywany transformacja strony konwertuje współrzędne strony współrzędnych urządzenia.</span><span class="sxs-lookup"><span data-stu-id="fea7a-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="fea7a-110">Transformacje i system współrzędnych</span><span class="sxs-lookup"><span data-stu-id="fea7a-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="fea7a-111">Załóżmy, że chcesz używać współrzędnych, który ma swoją witryną źródłową w treści obszaru klienckiego, a nie w lewym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="fea7a-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="fea7a-112">Powiedz, na przykład, że chcesz punkt początkowy za 100 pikseli od lewej krawędzi obszaru klienckiego i 50 pikseli od góry obszaru klienckiego.</span><span class="sxs-lookup"><span data-stu-id="fea7a-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="fea7a-113">Na poniższej ilustracji przedstawiono układ współrzędnych.</span><span class="sxs-lookup"><span data-stu-id="fea7a-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="fea7a-114">![System współrzędnych](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="fea7a-114">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="fea7a-115">Podczas wywoływania `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, pobrać wiersza pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="fea7a-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="fea7a-116">![System współrzędnych](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="fea7a-116">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="fea7a-117">Współrzędne punktów końcowych linii w trzech przestrzeni współrzędnych są następujące:</span><span class="sxs-lookup"><span data-stu-id="fea7a-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fea7a-118">World</span><span class="sxs-lookup"><span data-stu-id="fea7a-118">World</span></span>|<span data-ttu-id="fea7a-119">(0, 0) do (160, 80)</span><span class="sxs-lookup"><span data-stu-id="fea7a-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="fea7a-120">Strona</span><span class="sxs-lookup"><span data-stu-id="fea7a-120">Page</span></span>|<span data-ttu-id="fea7a-121">(100, 50) do (260, 130)</span><span class="sxs-lookup"><span data-stu-id="fea7a-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="fea7a-122">Urządzenie</span><span class="sxs-lookup"><span data-stu-id="fea7a-122">Device</span></span>|<span data-ttu-id="fea7a-123">(100, 50) do (260, 130)</span><span class="sxs-lookup"><span data-stu-id="fea7a-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="fea7a-124">Pamiętaj, że przestrzeni współrzędnych strony ma swoją witryną źródłową w lewym górnym rogu obszaru klienckiego; zawsze będzie wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="fea7a-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="fea7a-125">Należy również zauważyć, że jednostka miary jest piksela, współrzędnych urządzenia są takie same jak współrzędnych strony.</span><span class="sxs-lookup"><span data-stu-id="fea7a-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="fea7a-126">Jeśli ustawisz jednostka miary inną niż pikseli (na przykład cala) współrzędnych urządzenia może się różnić od współrzędnych strony.</span><span class="sxs-lookup"><span data-stu-id="fea7a-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="fea7a-127">Transformacja świata, który mapuje współrzędnych świata na współrzędnych strony, jest przechowywany w <xref:System.Drawing.Graphics.Transform%2A> właściwość <xref:System.Drawing.Graphics> klasy.</span><span class="sxs-lookup"><span data-stu-id="fea7a-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="fea7a-128">W powyższym przykładzie transformacja świata jest 100 jednostek tłumaczenia, w kierunku x i 50 jednostek w kierunku y.</span><span class="sxs-lookup"><span data-stu-id="fea7a-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="fea7a-129">Poniższy przykład przedstawia transformacji świata z <xref:System.Drawing.Graphics> obiekt, a następnie użyty <xref:System.Drawing.Graphics> obiektu do rysowania linii na powyższej ilustracji:</span><span class="sxs-lookup"><span data-stu-id="fea7a-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="fea7a-130">Transformacja strony mapuje współrzędnych strony współrzędnych urządzenia.</span><span class="sxs-lookup"><span data-stu-id="fea7a-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="fea7a-131"><xref:System.Drawing.Graphics> Klasa udostępnia <xref:System.Drawing.Graphics.PageUnit%2A> i <xref:System.Drawing.Graphics.PageScale%2A> właściwości do manipulowania transformacja strony.</span><span class="sxs-lookup"><span data-stu-id="fea7a-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="fea7a-132"><xref:System.Drawing.Graphics> Klasa udostępnia również dwie właściwości tylko do odczytu, <xref:System.Drawing.Graphics.DpiX%2A> i <xref:System.Drawing.Graphics.DpiY%2A>, badania poziome i pionowe punktów na cal urządzenia.</span><span class="sxs-lookup"><span data-stu-id="fea7a-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="fea7a-133">Można użyć <xref:System.Drawing.Graphics.PageUnit%2A> właściwość <xref:System.Drawing.Graphics> klasy, aby określić jednostkę miary niż piksela.</span><span class="sxs-lookup"><span data-stu-id="fea7a-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fea7a-134">Nie można ustawić <xref:System.Drawing.Graphics.PageUnit%2A> właściwości <xref:System.Drawing.GraphicsUnit.World>, ponieważ to nie jest jednostką fizycznych i spowodują wyjątek.</span><span class="sxs-lookup"><span data-stu-id="fea7a-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="fea7a-135">Poniższy przykład rysuje z (0, 0) do (2, 1), gdzie punktu (2 i 1) to 2 cala w prawo i 1 cala w dół od punktu (0, 0):</span><span class="sxs-lookup"><span data-stu-id="fea7a-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  <span data-ttu-id="fea7a-136">Jeśli nie określisz szerokość pióra podczas konstruowania pióra, poprzedni przykład narysuje wiersza, który jest jeden cal szerokości.</span><span class="sxs-lookup"><span data-stu-id="fea7a-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="fea7a-137">Można określić szerokość pióra w drugim argumentem <xref:System.Drawing.Pen> konstruktora:</span><span class="sxs-lookup"><span data-stu-id="fea7a-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="fea7a-138">Jeśli przyjęto założenie, że urządzenia wyświetlającego ma 96 punktów na cal w kierunku poziomym oraz 96 punktów na cal w kierunku pionowym, punkty końcowe wiersza w powyższym przykładzie są następujące współrzędne w trzech przestrzeni współrzędnych:</span><span class="sxs-lookup"><span data-stu-id="fea7a-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fea7a-139">World</span><span class="sxs-lookup"><span data-stu-id="fea7a-139">World</span></span>|<span data-ttu-id="fea7a-140">(0, 0) do (2, 1)</span><span class="sxs-lookup"><span data-stu-id="fea7a-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="fea7a-141">Strona</span><span class="sxs-lookup"><span data-stu-id="fea7a-141">Page</span></span>|<span data-ttu-id="fea7a-142">(0, 0) do (2, 1)</span><span class="sxs-lookup"><span data-stu-id="fea7a-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="fea7a-143">Urządzenie</span><span class="sxs-lookup"><span data-stu-id="fea7a-143">Device</span></span>|<span data-ttu-id="fea7a-144">(0, 0, aby (192, 96)</span><span class="sxs-lookup"><span data-stu-id="fea7a-144">(0, 0, to (192, 96)</span></span>|  
  
 <span data-ttu-id="fea7a-145">Należy pamiętać, że pochodzenia przestrzeni współrzędnych świata jest w lewym górnym rogu obszaru klienckiego, dlatego współrzędnych strony są takie same jak współrzędnych świata.</span><span class="sxs-lookup"><span data-stu-id="fea7a-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="fea7a-146">Przekształcenia world i strony, aby uzyskać różne efekty można łączyć.</span><span class="sxs-lookup"><span data-stu-id="fea7a-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="fea7a-147">Załóżmy na przykład, ma być używany jako jednostka miary cali i chcesz pochodzenia systemu współrzędnych być 2 cala od lewej krawędzi obszaru klienckiego i 1/2 cala od góry obszaru klienckiego.</span><span class="sxs-lookup"><span data-stu-id="fea7a-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="fea7a-148">Poniższy przykład przedstawia transformacji świata i strony z <xref:System.Drawing.Graphics> obiekt, a następnie rysuje z (0, 0) do (2, 1):</span><span class="sxs-lookup"><span data-stu-id="fea7a-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="fea7a-149">Na poniższej ilustracji przedstawiono wiersza i układ współrzędnych.</span><span class="sxs-lookup"><span data-stu-id="fea7a-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="fea7a-150">![System współrzędnych](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="fea7a-150">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="fea7a-151">Jeśli przyjęto założenie, że urządzenia wyświetlającego ma 96 punktów na cal w kierunku poziomym oraz 96 punktów na cal w kierunku pionowym, punkty końcowe wiersza w powyższym przykładzie są następujące współrzędne w trzech przestrzeni współrzędnych:</span><span class="sxs-lookup"><span data-stu-id="fea7a-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fea7a-152">World</span><span class="sxs-lookup"><span data-stu-id="fea7a-152">World</span></span>|<span data-ttu-id="fea7a-153">(0, 0) do (2, 1)</span><span class="sxs-lookup"><span data-stu-id="fea7a-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="fea7a-154">Strona</span><span class="sxs-lookup"><span data-stu-id="fea7a-154">Page</span></span>|<span data-ttu-id="fea7a-155">(2, 0,5) do (4, 1.5)</span><span class="sxs-lookup"><span data-stu-id="fea7a-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="fea7a-156">Urządzenie</span><span class="sxs-lookup"><span data-stu-id="fea7a-156">Device</span></span>|<span data-ttu-id="fea7a-157">(192, 48) do (384, 144)</span><span class="sxs-lookup"><span data-stu-id="fea7a-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fea7a-158">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fea7a-158">See Also</span></span>  
 [<span data-ttu-id="fea7a-159">Systemy i transformacje współrzędnych</span><span class="sxs-lookup"><span data-stu-id="fea7a-159">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="fea7a-160">Macierzowe przedstawienie przekształcenia</span><span class="sxs-lookup"><span data-stu-id="fea7a-160">Matrix Representation of Transformations</span></span>](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)