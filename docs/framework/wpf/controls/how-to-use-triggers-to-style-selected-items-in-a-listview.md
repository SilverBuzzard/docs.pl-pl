---
title: "Jak użyć wyzwalaczy, aby nadać styl zaznaczonym elementom w ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e86c7f875376a4ab28eec7cd032a165745445441
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="4c327-102">Jak użyć wyzwalaczy, aby nadać styl zaznaczonym elementom w ListView</span><span class="sxs-lookup"><span data-stu-id="4c327-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="4c327-103">W tym przykładzie pokazano sposób definiowania <xref:System.Windows.Style.Triggers%2A> dla <xref:System.Windows.Controls.ListViewItem> sterowania, aby gdy wartość właściwości <xref:System.Windows.Controls.ListViewItem> zmiany, <xref:System.Windows.Style> z <xref:System.Windows.Controls.ListViewItem> zmianach w odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="4c327-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c327-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="4c327-104">Example</span></span>  
 <span data-ttu-id="4c327-105">Jeśli chcesz <xref:System.Windows.Style> z <xref:System.Windows.Controls.ListViewItem> zmiany w odpowiedzi na zmiany właściwości, należy zdefiniować <xref:System.Windows.Style.Triggers%2A> dla <xref:System.Windows.Style> zmienić.</span><span class="sxs-lookup"><span data-stu-id="4c327-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="4c327-106">W poniższym przykładzie zdefiniowano <xref:System.Windows.Trigger> stanowiąca <xref:System.Windows.Controls.Control.Foreground%2A> właściwości <xref:System.Windows.Media.Brushes.Blue%2A> i zmienia <xref:System.Windows.FrameworkElement.Cursor%2A> do wyświetlenia <xref:System.Windows.Input.CursorType.Hand> podczas <xref:System.Windows.UIElement.IsMouseOver%2A> zmiany właściwości `true`.</span><span class="sxs-lookup"><span data-stu-id="4c327-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="4c327-107">W poniższym przykładzie zdefiniowano <xref:System.Windows.MultiTrigger> stanowiąca <xref:System.Windows.Controls.Control.Foreground%2A> właściwość <xref:System.Windows.Controls.ListViewItem> do <xref:System.Windows.Media.Brushes.Yellow%2A> podczas <xref:System.Windows.Controls.ListViewItem> wybrany element i ma fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="4c327-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="4c327-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4c327-108">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="4c327-109">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="4c327-109">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="4c327-110">ListView — omówienie</span><span class="sxs-lookup"><span data-stu-id="4c327-110">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="4c327-111">Omówienie widoku GridView</span><span class="sxs-lookup"><span data-stu-id="4c327-111">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)