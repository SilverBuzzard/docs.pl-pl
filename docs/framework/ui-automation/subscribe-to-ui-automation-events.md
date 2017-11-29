---
title: "Subskrybowanie zdarzeń automatyzacji interfejsu użytkownika"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
caps.latest.revision: "16"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 39275c38e4a7d28248b46f1116990c5bbe21a15f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="4329f-102">Subskrybowanie zdarzeń automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="4329f-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
>  <span data-ttu-id="4329f-103">Ta dokumentacja jest przeznaczony dla deweloperów .NET Framework, które chcą korzystać zarządzanej [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4329f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4329f-104">Aby uzyskać najnowsze informacje o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], zobacz [interfejsu API systemu Windows automatyzacji: automatyzacji interfejsu użytkownika](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4329f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4329f-105">W tym temacie przedstawiono sposób subskrybowania zdarzenia generowane przez dostawców automatyzacji interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4329f-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4329f-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="4329f-106">Example</span></span>  
 <span data-ttu-id="4329f-107">Poniższy przykład kodu rejestruje program obsługi zdarzeń dla zdarzenia, które jest wywoływane, gdy formant takie jak przycisk jest wywoływany i usuwa go podczas zamykania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="4329f-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="4329f-108">Zdarzenie jest identyfikowane przez <xref:System.Windows.Automation.AutomationEvent> przekazany jako parametr <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="4329f-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="4329f-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="4329f-109">Example</span></span>  
 <span data-ttu-id="4329f-110">Poniższy przykład przedstawia użycie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] subskrybować zdarzenie jest zgłaszane, gdy fokus się zmieni.</span><span class="sxs-lookup"><span data-stu-id="4329f-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="4329f-111">Program obsługi zdarzeń jest wyrejestrowany w metodzie, który można wywołać podczas zamykania aplikacji lub gdy powiadomienia o zdarzeniach interfejsu użytkownika nie jest już wymagane.</span><span class="sxs-lookup"><span data-stu-id="4329f-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="4329f-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4329f-112">See Also</span></span>  
 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>  
 [<span data-ttu-id="4329f-113">Przegląd zdarzeń automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="4329f-113">UI Automation Events Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-events-overview.md)