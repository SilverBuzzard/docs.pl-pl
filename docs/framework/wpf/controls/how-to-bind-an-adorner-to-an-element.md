---
title: "Jak powiązać moduł definiowania układu z elementem"
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
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2b1da3216ce6d3507c304ff957728d33ba1b9bd9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="1aa6f-102">Jak powiązać moduł definiowania układu z elementem</span><span class="sxs-lookup"><span data-stu-id="1aa6f-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="1aa6f-103">W tym przykładzie pokazano, jak programowo powiązać modułu definiowania układu kodu z określonej <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="1aa6f-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1aa6f-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="1aa6f-104">Example</span></span>  
 <span data-ttu-id="1aa6f-105">Aby powiązać modułu definiowania układu kodu do określonego <xref:System.Windows.UIElement>, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="1aa6f-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1aa6f-106">Wywołanie `static` — metoda <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> uzyskanie <xref:System.Windows.Documents.AdornerLayer> obiekt do <xref:System.Windows.UIElement> do można adorned.</span><span class="sxs-lookup"><span data-stu-id="1aa6f-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="1aa6f-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>przedstawiono w górę drzewa wizualnego, rozpoczynając od określonego **UIElement**i zwraca znajdzie pierwszą warstwę modułu definiowania układu kodu.</span><span class="sxs-lookup"><span data-stu-id="1aa6f-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="1aa6f-108">(Jeśli nie zostaną znalezione nie warstwy modułu definiowania układu kodu, metoda zwraca wartość null.)</span><span class="sxs-lookup"><span data-stu-id="1aa6f-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="1aa6f-109">Wywołanie <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodę, aby powiązać modułu definiowania układu kodu w miejscu docelowym **UIElement**.</span><span class="sxs-lookup"><span data-stu-id="1aa6f-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="1aa6f-110">Poniższy przykład wiąże SimpleCircleAdorner (pokazanym powyżej), aby <xref:System.Windows.Controls.TextBox> o nazwie *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="1aa6f-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="1aa6f-111">Przy użyciu [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] powiązać modułu definiowania układu kodu do innego elementu nie jest obecnie obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="1aa6f-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa6f-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1aa6f-112">See Also</span></span>  
 [<span data-ttu-id="1aa6f-113">Omówienie modułu definiowania układu kodu</span><span class="sxs-lookup"><span data-stu-id="1aa6f-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)