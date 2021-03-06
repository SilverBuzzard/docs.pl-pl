---
title: Jak określić niestandardowe położenie okna podręcznego
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: e6e81a6e0819ba3eb39a1c568e6872414e671544
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261306"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Jak określić niestandardowe położenie okna podręcznego
W tym przykładzie pokazano, jak określić niestandardowe położenie <xref:System.Windows.Controls.Primitives.Popup> decyduje o <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> właściwość jest ustawiona na <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.  
  
## <a name="example"></a>Przykład  
 Gdy <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> właściwość jest ustawiona na <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> wywołuje zdefiniowane wystąpienie <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegować. Ten delegat zwraca zestaw możliwych punktów, które są względne wobec lewym górnym rogu w obszarze docelowym i górnym lewym rogu <xref:System.Windows.Controls.Primitives.Popup>. <xref:System.Windows.Controls.Primitives.Popup> Umieszczania występuje w momencie, który zapewnia widoczność najlepsze.  
  
 Poniższy przykład pokazuje jak zdefiniować położenie <xref:System.Windows.Controls.Primitives.Popup> , ustawiając <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> właściwość <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Pokazano również, jak utworzyć i przypisać <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegata w celu umieść <xref:System.Windows.Controls.Primitives.Popup>.  Delegat wywołania zwrotnego zwraca dwa <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> obiektów.  Jeśli <xref:System.Windows.Controls.Primitives.Popup> jest ukryta przez krawędzi ekranu, na pierwszym miejscu <xref:System.Windows.Controls.Primitives.Popup> jest umieszczany na drugim miejscu.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Aby uzyskać pełny przykład, zobacz [przykładowe położenia okna podręcznego](https://go.microsoft.com/fwlink/?LinkID=160032).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Okno podręczne — omówienie](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [Tematy z instrukcjami](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
