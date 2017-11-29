---
title: "Porady: rysowanie nieprzezroczystych i półprzezroczystych linii"
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
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ea65fd836a6e6fc00472f6139a0700ea859545cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a><span data-ttu-id="aba15-102">Porady: rysowanie nieprzezroczystych i półprzezroczystych linii</span><span class="sxs-lookup"><span data-stu-id="aba15-102">How to: Draw Opaque and Semitransparent Lines</span></span>
<span data-ttu-id="aba15-103">W przypadku rysowania linii, należy podać <xref:System.Drawing.Pen> do obiektu <xref:System.Drawing.Graphics.DrawLine%2A> metody <xref:System.Drawing.Graphics> klasy.</span><span class="sxs-lookup"><span data-stu-id="aba15-103">When you draw a line, you must pass a <xref:System.Drawing.Pen> object to the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="aba15-104">Jeden z parametrów <xref:System.Drawing.Pen.%23ctor%2A> Konstruktor jest <xref:System.Drawing.Color> obiektu.</span><span class="sxs-lookup"><span data-stu-id="aba15-104">One of the parameters of the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="aba15-105">Rysowanie linii nieprzezroczyste, należy ustawić składnika alfa koloru do 255.</span><span class="sxs-lookup"><span data-stu-id="aba15-105">To draw an opaque line, set the alpha component of the color to 255.</span></span> <span data-ttu-id="aba15-106">Aby narysować półprzezroczystych linii, należy ustawić składnika alfa na wartość od 1 do 254.</span><span class="sxs-lookup"><span data-stu-id="aba15-106">To draw a semitransparent line, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="aba15-107">Po narysowaniu półprzezroczystych linii w tle kolor linii mieszania kolorów tła.</span><span class="sxs-lookup"><span data-stu-id="aba15-107">When you draw a semitransparent line over a background, the color of the line is blended with the colors of the background.</span></span> <span data-ttu-id="aba15-108">Składnik alfa określa, jak mieszane kolory tła i linii; wartości alfa niemal 0 umieść ważniejsze na kolory tła i wartości alfa niemal 255 umieść ważniejsze na kolor linii.</span><span class="sxs-lookup"><span data-stu-id="aba15-108">The alpha component specifies how the line and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the line color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aba15-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="aba15-109">Example</span></span>  
 <span data-ttu-id="aba15-110">Poniższy przykład map bitowych rysuje, a następnie trzy wiersze, korzystających z mapy bitowej jako tło jest rysowane.</span><span class="sxs-lookup"><span data-stu-id="aba15-110">The following example draws a bitmap and then draws three lines that use the bitmap as a background.</span></span> <span data-ttu-id="aba15-111">Pierwszy wiersz używa składnika alfa 255, tak aby zawierała przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="aba15-111">The first line uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="aba15-112">Drugi i trzeci linii używają alfa składnika 128, dzięki czemu są one półprzezroczystych; obraz tła do wierszy jest widoczny.</span><span class="sxs-lookup"><span data-stu-id="aba15-112">The second and third lines use an alpha component of 128, so they are semitransparent; you can see the background image through the lines.</span></span> <span data-ttu-id="aba15-113">Instrukcja, która ustawia <xref:System.Drawing.Graphics.CompositingQuality%2A> właściwość powodująca usunięcie mieszania dla trzeciego wiersza w połączeniu z korekcja gamma.</span><span class="sxs-lookup"><span data-stu-id="aba15-113">The statement that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third line to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="aba15-114">Na poniższej ilustracji przedstawiono dane wyjściowe poniższy kod.</span><span class="sxs-lookup"><span data-stu-id="aba15-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="aba15-115">![Nieprzezroczystych i półprzezroczystych](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span><span class="sxs-lookup"><span data-stu-id="aba15-115">![Opaque and Semitransparent](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aba15-116">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="aba15-116">Compiling the Code</span></span>  
 <span data-ttu-id="aba15-117">Poprzedni przykład jest przeznaczony do użytku z formularzy systemu Windows i wymaga <xref:System.Windows.Forms.PaintEventArgs> `e`, który jest parametrem <xref:System.Windows.Forms.Control.Paint> obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="aba15-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba15-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aba15-118">See Also</span></span>  
 [<span data-ttu-id="aba15-119">Przenikanie alfa linii i wypełnień</span><span class="sxs-lookup"><span data-stu-id="aba15-119">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="aba15-120">Porady: zapewniają przezroczystego tła formantu</span><span class="sxs-lookup"><span data-stu-id="aba15-120">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 [<span data-ttu-id="aba15-121">Porady: Rysowanie nieprzezroczystych i półprzezroczystych pędzli</span><span class="sxs-lookup"><span data-stu-id="aba15-121">How to: Draw with Opaque and Semitransparent Brushes</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)