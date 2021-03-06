---
title: Jak dodać obsługę zdarzeń z użyciem kodu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 782f668557c3cb081d30e7835006af63c9ca4df5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542626"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Jak dodać obsługę zdarzeń z użyciem kodu
W tym przykładzie przedstawiono sposób dodawania obsługi zdarzeń do elementu przy użyciu kodu.  
  
 Jeśli chcesz dodać program obsługi zdarzeń do [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementu i stronie znaczników, który zawiera element został już załadowany, należy dodać program obsługi przy użyciu kodu. Alternatywnie Jeśli tworzysz górę drzewa element aplikacji całkowicie przy użyciu kodu i typ deklarujący nie elementów przy użyciu [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], należy wywołać określonej metody dodawania obsługi zdarzeń do skonstruowanego element drzewa.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład umożliwia dodanie nowego <xref:System.Windows.Controls.Button> do istniejącej strony wstępnie zdefiniowanego w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Plik CodeBehind implementuje metoda obsługi zdarzeń, a następnie dodaje tej metody jako nowy program obsługi zdarzeń, na <xref:System.Windows.Controls.Button>.  
  
 W języku C# przykładzie użyto `+=` operatora, aby przypisać program obsługi zdarzeń. To jest tym samym operator, który jest używany do przypisywania obsługi w [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] model obsługi zdarzeń. Microsoft Visual Basic nie obsługuje tego operatora jako środek Dodawanie programów obsługi zdarzeń. Zamiast tego wymaga jednego z dwóch metod:  
  
-   Użyj <xref:System.Windows.UIElement.AddHandler%2A> metody, wraz z `AddressOf` operatora, aby odwołać implementację programu obsługi zdarzeń.  
  
-   Użyj `Handles` słowa kluczowego jako część definicji programu obsługi zdarzeń. Ta metoda nie jest wyświetlany w tym miejscu; zobacz [Visual Basic i obsługi zdarzeń WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Dodawanie obsługi zdarzeń w początkowo przeanalizowany [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] strony jest znacznie prostsze. W elemencie obiektu, której chcesz dodać procedury obsługi zdarzeń Dodaj atrybut, który odpowiada nazwie zdarzenia, które mają być obsługiwane. Następnie określ wartość atrybutu z nazwą metody obsługi zdarzeń, zdefiniowanego w pliku CodeBehind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] strony. Aby uzyskać więcej informacji, zobacz [omówienie XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) lub [kierowane Przegląd zdarzeń](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Przegląd zdarzeń trasowanych](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Tematy z instrukcjami](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
