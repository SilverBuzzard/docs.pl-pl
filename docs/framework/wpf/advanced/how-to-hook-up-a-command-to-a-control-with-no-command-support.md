---
title: Jak podpiąć polecenie do formantu bez użycia obsługi poleceń
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
ms.openlocfilehash: e6ef78cd7e1578745f0bde5c0e9e799bb5e641a9
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805610"
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>Jak podpiąć polecenie do formantu bez użycia obsługi poleceń
Poniższy przykład przedstawia sposób Podłączanie <xref:System.Windows.Input.RoutedCommand> do <xref:System.Windows.Controls.Control> którego nie ma wbudowaną obsługą dla polecenia.  Dla kompletnego przykładu, który przechwytuje się poleceń do wielu źródeł, zobacz [utworzyć niestandardowe próbę RoutedCommand](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand) próbki.  
  
## <a name="example"></a>Przykład  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] udostępnia bibliotekę używanych poleceń, które programistom wystąpić regularnie.  Klasy, które obejmują biblioteki polecenia są: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, i <xref:System.Windows.Documents.EditingCommands>.  
  
 Statycznych <xref:System.Windows.Input.RoutedCommand> obiektów, które składają się następujące klasy nie zostanie podana logiki polecenia.  Logika dla polecenia jest skojarzony z polecenie z <xref:System.Windows.Input.CommandBinding>.  Wiele formantów w [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utworzone w obsłudze niektórych poleceń w bibliotece polecenia.  <xref:System.Windows.Controls.TextBox>, na przykład obsługuje wiele poleceń edycji aplikacji, takich jak <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, i <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Deweloper aplikacji nie trzeba wykonywać żadnych czynności specjalne do pobrania tych poleceń, aby pracować z tych kontrolek.  Jeśli <xref:System.Windows.Controls.TextBox> jest element docelowy polecenia po wykonaniu polecenia obsłuży przy użyciu polecenia <xref:System.Windows.Input.CommandBinding> wbudowane w formancie.  
  
 Poniżej pokazano, jak używać <xref:System.Windows.Controls.Button> jako źródło polecenia <xref:System.Windows.Input.ApplicationCommands.Open%2A> polecenia.  A <xref:System.Windows.Input.CommandBinding> utworzeniu tego określonego stowarzyszonych <xref:System.Windows.Input.CanExecuteRoutedEventHandler> i <xref:System.Windows.Input.CanExecuteRoutedEventHandler> z <xref:System.Windows.Input.RoutedCommand>.  
  
 Po pierwsze utworzono źródło polecenia.  A <xref:System.Windows.Controls.Button> jest używany jako źródło polecenia.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Następnie <xref:System.Windows.Input.ExecutedRoutedEventHandler> i <xref:System.Windows.Input.CanExecuteRoutedEventHandler> są tworzone.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> Po prostu otwiera <xref:System.Windows.MessageBox> oznaczającego wykonania polecenia.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> Ustawia <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> właściwości `true`.  Zwykle, może wykonać obsługi przeprowadza się sprawdza bardziej niezawodne, jeśli wykonanie polecenia na aktualnym elemencie docelowym polecenia.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Na koniec <xref:System.Windows.Input.CommandBinding> jest tworzony w katalogu głównym <xref:System.Windows.Window> aplikacji, które kojarzy obsługi kierowane zdarzenia do <xref:System.Windows.Input.ApplicationCommands.Open%2A> polecenia.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>Zobacz też  
 [Przegląd poleceń](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Podpinanie polecenia do kontrolki za pomocą obsługi poleceń](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
