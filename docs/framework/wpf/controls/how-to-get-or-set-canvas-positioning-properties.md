---
title: "Jak pobrać lub ustawić właściwości ustawienia kanwy"
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
helpviewer_keywords: Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2b2f20754c8425149f73f10af773604539125adb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="c8c0c-102">Jak pobrać lub ustawić właściwości ustawienia kanwy</span><span class="sxs-lookup"><span data-stu-id="c8c0c-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="c8c0c-103">Ten przykład przedstawia sposób użycia metody pozycjonowania <xref:System.Windows.Controls.Canvas> element, aby umieścić zawartość elementu podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="c8c0c-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="c8c0c-104">W tym przykładzie użyto zawartość <xref:System.Windows.Controls.ListBoxItem> do reprezentowania pozycjonowanie wartości i konwertuje wartości do wystąpienia <xref:System.Double>, który jest wymagany argument dla rozmieszczania.</span><span class="sxs-lookup"><span data-stu-id="c8c0c-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="c8c0c-105">Wartości są następnie konwertowana do ciągów i wyświetlana jako tekst w <xref:System.Windows.Controls.TextBlock> elementu przy użyciu <xref:System.Windows.Controls.Canvas.GetLeft%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="c8c0c-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8c0c-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="c8c0c-106">Example</span></span>  
 <span data-ttu-id="c8c0c-107">Poniższy przykład tworzy <xref:System.Windows.Controls.ListBox> mającego jedenaście wybieralny element <xref:System.Windows.Controls.ListBoxItem> elementów.</span><span class="sxs-lookup"><span data-stu-id="c8c0c-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="c8c0c-108"><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Wyzwalacze zdarzeń `ChangeLeft` niestandardowej metody, która definiuje blok kodu kolejne.</span><span class="sxs-lookup"><span data-stu-id="c8c0c-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="c8c0c-109">Każdy <xref:System.Windows.Controls.ListBoxItem> reprezentuje <xref:System.Double> wartość, która jest jeden z argumentów który <xref:System.Windows.Controls.Canvas.SetLeft%2A> metody <xref:System.Windows.Controls.Canvas> akceptuje.</span><span class="sxs-lookup"><span data-stu-id="c8c0c-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="c8c0c-110">Aby można było używać <xref:System.Windows.Controls.ListBoxItem> do reprezentowania wystąpienia <xref:System.Double>, należy najpierw przekonwertować <xref:System.Windows.Controls.ListBoxItem> poprawny typ danych.</span><span class="sxs-lookup"><span data-stu-id="c8c0c-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="c8c0c-111">Gdy użytkownik zmienia <xref:System.Windows.Controls.ListBox> zaznaczenia, wywołuje `ChangeLeft` niestandardowej metody.</span><span class="sxs-lookup"><span data-stu-id="c8c0c-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="c8c0c-112">Ta metoda przekazuje <xref:System.Windows.Controls.ListBoxItem> do <xref:System.Windows.LengthConverter> obiektu, który konwertuje <xref:System.Windows.Controls.ContentControl.Content%2A> z <xref:System.Windows.Controls.ListBoxItem> na wystąpienie <xref:System.Double> (Zwróć uwagę, że ta wartość została przekonwertowana na <xref:System.String> przy użyciu <xref:System.Windows.Controls.Control.ToString%2A> Metoda).</span><span class="sxs-lookup"><span data-stu-id="c8c0c-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="c8c0c-113">Ta wartość jest następnie przekazywane z powrotem do <xref:System.Windows.Controls.Canvas.SetLeft%2A> i <xref:System.Windows.Controls.Canvas.GetLeft%2A> metody <xref:System.Windows.Controls.Canvas> aby można było zmienić jego położenie `text1` obiektu.</span><span class="sxs-lookup"><span data-stu-id="c8c0c-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c8c0c-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c8c0c-114">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.ListBoxItem>  
 <xref:System.Windows.LengthConverter>  
 [<span data-ttu-id="c8c0c-115">Omówienie paneli</span><span class="sxs-lookup"><span data-stu-id="c8c0c-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)