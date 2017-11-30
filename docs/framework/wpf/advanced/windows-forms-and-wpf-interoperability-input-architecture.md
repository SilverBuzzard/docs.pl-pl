---
title: "Struktura wejścia ze zdolnością do współpracy Windows Forms i WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- input architecture [WPF interoperability]
- messages [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- modeless forms [WPF]
- ElementHost keyboard and messages [WPF]
- keyboard interoperation [WPF]
- WindowsFormsHost keyboard and messages [WPF]
- modeless dialog boxes [WPF]
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b48b5d78ce3136146f7ad17f859a489b5556a000
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a><span data-ttu-id="6b9fb-102">Struktura wejścia ze zdolnością do współpracy Windows Forms i WPF</span><span class="sxs-lookup"><span data-stu-id="6b9fb-102">Windows Forms and WPF Interoperability Input Architecture</span></span>
<span data-ttu-id="6b9fb-103">Współdziałanie między [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] musi mieć obu tych technologii przetwarzania wejściowych odpowiedniej klawiatury.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-103">Interoperation between the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] requires that both technologies have the appropriate keyboard input processing.</span></span> <span data-ttu-id="6b9fb-104">W tym temacie opisano, jak te technologie zaimplementować klawiatury i przetwarzania umożliwia sprawne współdziałanie w aplikacjach hybrydowego komunikatów.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-104">This topic describes how these technologies implement keyboard and message processing to enable smooth interoperation in hybrid applications.</span></span>  
  
 <span data-ttu-id="6b9fb-105">Ten temat zawiera następujące podsekcje:</span><span class="sxs-lookup"><span data-stu-id="6b9fb-105">This topic contains the following subsections:</span></span>  
  
-   <span data-ttu-id="6b9fb-106">Niemodalne formularzach i oknach dialogowych</span><span class="sxs-lookup"><span data-stu-id="6b9fb-106">Modeless Forms and Dialog Boxes</span></span>  
  
-   <span data-ttu-id="6b9fb-107">Klawiatura WindowsFormsHost i przetwarzanie komunikatów</span><span class="sxs-lookup"><span data-stu-id="6b9fb-107">WindowsFormsHost Keyboard and Message Processing</span></span>  
  
-   <span data-ttu-id="6b9fb-108">ElementHost klawiatury i przetwarzanie komunikatów</span><span class="sxs-lookup"><span data-stu-id="6b9fb-108">ElementHost Keyboard and Message Processing</span></span>  
  
## <a name="modeless-forms-and-dialog-boxes"></a><span data-ttu-id="6b9fb-109">Niemodalne formularzach i oknach dialogowych</span><span class="sxs-lookup"><span data-stu-id="6b9fb-109">Modeless Forms and Dialog Boxes</span></span>  
 <span data-ttu-id="6b9fb-110">Wywołanie <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> metoda <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, aby otworzyć niemodalne okno formularza lub okna dialogowego z [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-110">Call the <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to open a modeless form or dialog box from a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="6b9fb-111">Wywołanie <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> metody w <xref:System.Windows.Forms.Integration.ElementHost> sterowania, aby otworzyć niemodalny [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] w obszarze [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]— aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-111">Call the <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control to open a modeless [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based application.</span></span>  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a><span data-ttu-id="6b9fb-112">Klawiatura WindowsFormsHost i przetwarzanie komunikatów</span><span class="sxs-lookup"><span data-stu-id="6b9fb-112">WindowsFormsHost Keyboard and Message Processing</span></span>  
 <span data-ttu-id="6b9fb-113">Obsługiwany przez [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplikacji opartej na [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] klawiatury i przetwarzania składa się z następujących komunikatów:</span><span class="sxs-lookup"><span data-stu-id="6b9fb-113">When hosted by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] keyboard and message processing consists of the following:</span></span>  
  
-   <span data-ttu-id="6b9fb-114"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Klas uzyskuje komunikaty z [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pętli komunikatów, który jest implementowany przez <xref:System.Windows.Interop.ComponentDispatcher> klasy.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-114">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> class acquires messages from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] message loop, which is implemented by the <xref:System.Windows.Interop.ComponentDispatcher> class.</span></span>  
  
-   <span data-ttu-id="6b9fb-115"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Klasy tworzy surogatu [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] pętli komunikatów, aby upewnić się, że zwykłych [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] przetwarzania klawiatury.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-115">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> class creates a surrogate [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] message loop to ensure that ordinary [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] keyboard processing occurs.</span></span>  
  
-   <span data-ttu-id="6b9fb-116"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Klasa implementuje <xref:System.Windows.Interop.IKeyboardInputSink> interfejs do koordynowania fokus zarządzania za pomocą [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b9fb-116">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> class implements the <xref:System.Windows.Interop.IKeyboardInputSink> interface to coordinate focus management with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
-   <span data-ttu-id="6b9fb-117"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Formanty rejestrować i uruchomić ich pętli komunikatów.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-117">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> controls register themselves and start their message loops.</span></span>  
  
 <span data-ttu-id="6b9fb-118">W poniższych sekcjach opisano te części procesu bardziej szczegółowo.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-118">The following sections describe these parts of the process in more detail.</span></span>  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a><span data-ttu-id="6b9fb-119">Pobieranie wiadomości z pętli komunikatów WPF</span><span class="sxs-lookup"><span data-stu-id="6b9fb-119">Acquiring Messages from the WPF Message Loop</span></span>  
 <span data-ttu-id="6b9fb-120"><xref:System.Windows.Interop.ComponentDispatcher> Klasa implementuje Menedżera pętli komunikatów dla [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b9fb-120">The <xref:System.Windows.Interop.ComponentDispatcher> class implements the message loop manager for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="6b9fb-121"><xref:System.Windows.Interop.ComponentDispatcher> Klasa udostępnia punkty zaczepienia, aby umożliwić klientom zewnętrznych do filtrowania wiadomości przed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] przetwarza je.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-121">The <xref:System.Windows.Interop.ComponentDispatcher> class provides hooks to enable external clients to filter messages before [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] processes them.</span></span>  
  
 <span data-ttu-id="6b9fb-122">Uchwyty współdziałanie implementacji <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> zdarzeń, dzięki czemu [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] służy do przetwarzania komunikatów przed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kontrolki.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-122">The interoperation implementation handles the <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> event, which enables [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls to process messages before [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>  
  
### <a name="surrogate-windows-forms-message-loop"></a><span data-ttu-id="6b9fb-123">Pętli komunikatów formularzy systemu Windows Surogat</span><span class="sxs-lookup"><span data-stu-id="6b9fb-123">Surrogate Windows Forms Message Loop</span></span>  
 <span data-ttu-id="6b9fb-124">Domyślnie <xref:System.Windows.Forms.Application?displayProperty=nameWithType> klasa zawiera pętli komunikatów głównej dla [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-124">By default, the <xref:System.Windows.Forms.Application?displayProperty=nameWithType> class contains the primary message loop for [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] applications.</span></span> <span data-ttu-id="6b9fb-125">Podczas współdziałanie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] komunikat pętli nie może przetwarzać komunikatów.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-125">During interoperation, the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] message loop does not process messages.</span></span> <span data-ttu-id="6b9fb-126">W związku z tym można odtworzyć ten logiki.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-126">Therefore, this logic must be reproduced.</span></span> <span data-ttu-id="6b9fb-127">Program obsługi dla <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> zdarzeń wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6b9fb-127">The handler for the <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> event performs the following steps:</span></span>  
  
1.  <span data-ttu-id="6b9fb-128">Filtry wiadomości przy użyciu <xref:System.Windows.Forms.IMessageFilter> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-128">Filters the message using the <xref:System.Windows.Forms.IMessageFilter> interface.</span></span>  
  
2.  <span data-ttu-id="6b9fb-129">Wywołania <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-129">Calls the <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> method.</span></span>  
  
3.  <span data-ttu-id="6b9fb-130">Wykonuje translację i wysyła komunikat, jeśli jest to wymagane.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-130">Translates and dispatches the message, if it is required.</span></span>  
  
4.  <span data-ttu-id="6b9fb-131">Przekazaniem do hostowania formantu, jeśli żadne inne formanty przetworzyć komunikatu.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-131">Passes the message to the hosting control, if no other controls process the message.</span></span>  
  
### <a name="ikeyboardinputsink-implementation"></a><span data-ttu-id="6b9fb-132">Implementacja IKeyboardInputSink</span><span class="sxs-lookup"><span data-stu-id="6b9fb-132">IKeyboardInputSink Implementation</span></span>  
 <span data-ttu-id="6b9fb-133">Pętli komunikatów Surogat obsługuje zarządzanie klawiatury.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-133">The surrogate message loop handles keyboard management.</span></span> <span data-ttu-id="6b9fb-134">W związku z tym <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> jest jedyną metodą <xref:System.Windows.Interop.IKeyboardInputSink> elementu członkowskiego, który wymaga implementacja <xref:System.Windows.Forms.Integration.WindowsFormsHost> klasy.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-134">Therefore, the <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> method is the only <xref:System.Windows.Interop.IKeyboardInputSink> member that requires an implementation in the <xref:System.Windows.Forms.Integration.WindowsFormsHost> class.</span></span>  
  
 <span data-ttu-id="6b9fb-135">Domyślnie <xref:System.Windows.Interop.HwndHost> klasy zwraca `false` dla jego <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> implementacji.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-135">By default, the <xref:System.Windows.Interop.HwndHost> class returns `false` for its <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> implementation.</span></span> <span data-ttu-id="6b9fb-136">Zapobiega to klawisza TAB z [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] formant [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] formantu.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-136">This prevents tabbing from a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control to a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
 <span data-ttu-id="6b9fb-137"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Implementacja <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> metoda wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6b9fb-137">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> implementation of the <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> method performs the following steps:</span></span>  
  
1.  <span data-ttu-id="6b9fb-138">Znajduje pierwsze lub ostatnie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] formant, który jest zawarty w <xref:System.Windows.Forms.Integration.WindowsFormsHost> kontroli i które można ustawić fokusu.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-138">Finds the first or last [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that is contained by the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and that can receive focus.</span></span> <span data-ttu-id="6b9fb-139">Wybór kontroli zależy od informacji przechodzenie.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-139">The control choice depends on traversal information.</span></span>  
  
2.  <span data-ttu-id="6b9fb-140">Ustawia fokus do formantu i zwraca `true`.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-140">Sets focus to the control and returns `true`.</span></span>  
  
3.  <span data-ttu-id="6b9fb-141">Jeśli formant nie może odebrać fokus, zwraca `false`.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-141">If no control can receive focus, returns `false`.</span></span>  
  
### <a name="windowsformshost-registration"></a><span data-ttu-id="6b9fb-142">WindowsFormsHost rejestracji</span><span class="sxs-lookup"><span data-stu-id="6b9fb-142">WindowsFormsHost Registration</span></span>  
 <span data-ttu-id="6b9fb-143">Gdy uchwyt okna, aby <xref:System.Windows.Forms.Integration.WindowsFormsHost> formant jest utworzony, <xref:System.Windows.Forms.Integration.WindowsFormsHost> kontroli wywołuje metody statycznej wewnętrznej rejestruje jego obecność dla pętli komunikatów.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-143">When the window handle to a <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is created, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control calls an internal static method that registers its presence for the message loop.</span></span>  
  
 <span data-ttu-id="6b9fb-144">Podczas rejestracji <xref:System.Windows.Forms.Integration.WindowsFormsHost> formant sprawdza pętli komunikatów.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-144">During registration, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control examines the message loop.</span></span> <span data-ttu-id="6b9fb-145">Jeśli nie uruchomiono pętlę komunikatów, <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> program obsługi zdarzeń jest utworzony.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-145">If the message loop has not been started, the <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> event handler is created.</span></span> <span data-ttu-id="6b9fb-146">Pętla wiadomości jest uznawany za uruchomione podczas <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> program obsługi zdarzeń jest dołączony.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-146">The message loop is considered to be running when the <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> event handler is attached.</span></span>  
  
 <span data-ttu-id="6b9fb-147">Gdy zostanie zniszczony uchwytu okna, <xref:System.Windows.Forms.Integration.WindowsFormsHost> kontroli usuwa z rejestracji.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-147">When the window handle is destroyed, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control removes itself from registration.</span></span>  
  
## <a name="elementhost-keyboard-and-message-processing"></a><span data-ttu-id="6b9fb-148">ElementHost klawiatury i przetwarzanie komunikatów</span><span class="sxs-lookup"><span data-stu-id="6b9fb-148">ElementHost Keyboard and Message Processing</span></span>  
 <span data-ttu-id="6b9fb-149">Obsługiwany przez [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] aplikacji, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] klawiatury i przetwarzania składa się z następujących komunikatów:</span><span class="sxs-lookup"><span data-stu-id="6b9fb-149">When hosted by a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] keyboard and message processing consists of the following:</span></span>  
  
-   <span data-ttu-id="6b9fb-150"><xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>, i <xref:System.Windows.Interop.IKeyboardInputSite> implementacji interfejsu.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-150"><xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>, and <xref:System.Windows.Interop.IKeyboardInputSite> interface implementations.</span></span>  
  
-   <span data-ttu-id="6b9fb-151">Klucze klawisza TAB i strzałki.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-151">Tabbing and arrow keys.</span></span>  
  
-   <span data-ttu-id="6b9fb-152">Polecenie klucze i klucze — okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-152">Command keys and dialog box keys.</span></span>  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="6b9fb-153">Przetwarzanie akceleratora.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-153"> accelerator processing.</span></span>  
  
 <span data-ttu-id="6b9fb-154">W poniższych sekcjach opisano te części bardziej szczegółowo.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-154">The following sections describe these parts in more detail.</span></span>  
  
### <a name="interface-implementations"></a><span data-ttu-id="6b9fb-155">Implementacje interfejsu</span><span class="sxs-lookup"><span data-stu-id="6b9fb-155">Interface Implementations</span></span>  
 <span data-ttu-id="6b9fb-156">W [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], komunikaty klawiatury są kierowane do uchwytu okna dla formantu, który ma fokus.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-156">In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], keyboard messages are routed to the window handle of the control that has focus.</span></span> <span data-ttu-id="6b9fb-157">W <xref:System.Windows.Forms.Integration.ElementHost> kontroli, komunikaty te są kierowane do elementu hostowanej.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-157">In the <xref:System.Windows.Forms.Integration.ElementHost> control, these messages are routed to the hosted element.</span></span> <span data-ttu-id="6b9fb-158">Aby to osiągnąć, <xref:System.Windows.Forms.Integration.ElementHost> kontrola zapewnia <xref:System.Windows.Interop.HwndSource> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-158">To accomplish this, the <xref:System.Windows.Forms.Integration.ElementHost> control provides an <xref:System.Windows.Interop.HwndSource> instance.</span></span> <span data-ttu-id="6b9fb-159">Jeśli <xref:System.Windows.Forms.Integration.ElementHost> formant ma fokus, <xref:System.Windows.Interop.HwndSource> wystąpienia kieruje większości przy użyciu klawiatury, aby mogą być przetwarzane przez [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> klasy.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-159">If the <xref:System.Windows.Forms.Integration.ElementHost> control has focus, the <xref:System.Windows.Interop.HwndSource> instance routes most keyboard input so that it can be processed by the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> class.</span></span>  
  
 <span data-ttu-id="6b9fb-160"><xref:System.Windows.Interop.HwndSource> Klasa implementuje <xref:System.Windows.Interop.IKeyboardInputSink> i <xref:System.Windows.Interop.IKeyboardInputSite> interfejsów.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-160">The <xref:System.Windows.Interop.HwndSource> class implements the <xref:System.Windows.Interop.IKeyboardInputSink> and <xref:System.Windows.Interop.IKeyboardInputSite> interfaces.</span></span>  
  
 <span data-ttu-id="6b9fb-161">Współdziałanie klawiatury zależy od implementacji <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> metodę dojścia klawisza TAB i strzałki klucza danych wejściowych, który przenosi fokus poza hostowanej elementów.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-161">Keyboard interoperation relies on implementing the <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> method to handle TAB key and arrow key input that moves focus out of hosted elements.</span></span>  
  
### <a name="tabbing-and-arrow-keys"></a><span data-ttu-id="6b9fb-162">Tabbing i klawiszy strzałek</span><span class="sxs-lookup"><span data-stu-id="6b9fb-162">Tabbing and Arrow Keys</span></span>  
 <span data-ttu-id="6b9fb-163">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Logiki zaznaczenie jest mapowany na <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> i <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> metody służące do implementacji kartę i Strzałka klucza nawigacji.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-163">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] selection logic is mapped to the <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> and <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> methods to implement TAB and arrow key navigation.</span></span> <span data-ttu-id="6b9fb-164">Zastępowanie <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> metoda wykonuje się to mapowanie.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-164">Overriding the <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> method accomplishes this mapping.</span></span>  
  
### <a name="command-keys-and-dialog-box-keys"></a><span data-ttu-id="6b9fb-165">Polecenie klucze i klucze — okno dialogowe</span><span class="sxs-lookup"><span data-stu-id="6b9fb-165">Command Keys and Dialog Box Keys</span></span>  
 <span data-ttu-id="6b9fb-166">Aby zapewnić [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pierwsza okazja do przetworzenia polecenia klucze i klucze okna dialogowego [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] polecenia wstępnego przetwarzania jest podłączony do <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> — metoda.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-166">To give [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] the first opportunity to process command keys and dialog keys, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] command preprocessing is connected to the <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> method.</span></span> <span data-ttu-id="6b9fb-167">Zastępowanie <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> metody łączy dwie technologie.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-167">Overriding the <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> method connects the two technologies.</span></span>  
  
 <span data-ttu-id="6b9fb-168">Z <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> metody hostowanej elementów może obsługiwać dowolny komunikat klucza, takich jak WM_KEYDOWN, WM_KEYUP, WM_SYSKEYDOWN lub WM_SYSKEYUP, w tym klucze polecenia, takie jak klucze kartę, wprowadź ESC i strzałki.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-168">With the <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> method, the hosted elements can handle any key message, such as WM_KEYDOWN, WM_KEYUP, WM_SYSKEYDOWN, or WM_SYSKEYUP, including command keys, such as TAB, ENTER, ESC, and arrow keys.</span></span> <span data-ttu-id="6b9fb-169">Komunikat klucza nie jest obsługiwana, jest wysyłana [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hierarchii nadrzędnej obsługi.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-169">If a key message is not handled, it is sent up the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ancestor hierarchy for handling.</span></span>  
  
### <a name="accelerator-processing"></a><span data-ttu-id="6b9fb-170">Przetwarzanie klawiszy skrótów</span><span class="sxs-lookup"><span data-stu-id="6b9fb-170">Accelerator Processing</span></span>  
 <span data-ttu-id="6b9fb-171">Poprawnie, przetworzyć akceleratorów [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] akceleratora przetwarzania musi być podłączony do [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> klasy.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-171">To process accelerators correctly, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] accelerator processing must be connected to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> class.</span></span> <span data-ttu-id="6b9fb-172">Ponadto wszystkie komunikaty WM_CHAR muszą być prawidłowo kierowane do hostowanych elementów.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-172">Additionally, all WM_CHAR messages must be correctly routed to hosted elements.</span></span>  
  
 <span data-ttu-id="6b9fb-173">Ponieważ domyślne <xref:System.Windows.Interop.HwndSource> implementacja <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> metoda zwraca `false`, WM_CHAR wiadomości są przetwarzane przy użyciu z następującą logiką:</span><span class="sxs-lookup"><span data-stu-id="6b9fb-173">Because the default <xref:System.Windows.Interop.HwndSource> implementation of the <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> method returns `false`, WM_CHAR messages are processed using the following logic:</span></span>  
  
-   <span data-ttu-id="6b9fb-174"><xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> Metoda zostanie przesłonięta, aby upewnić się, że wszystkie komunikaty WM_CHAR są przekazywane do hostowanej elementów.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-174">The <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> method is overridden to ensure that all WM_CHAR messages are forwarded to hosted elements.</span></span>  
  
-   <span data-ttu-id="6b9fb-175">Jeśli zostanie naciśnięty klawisz ALT, wiadomość jest WM_SYSCHAR.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-175">If the ALT key is pressed, the message is WM_SYSCHAR.</span></span> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="6b9fb-176">Nie przetwarzaj wstępnie tego komunikatu za pośrednictwem <xref:System.Windows.Forms.Control.IsInputChar%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-176"> does not preprocess this message through the <xref:System.Windows.Forms.Control.IsInputChar%2A> method.</span></span> <span data-ttu-id="6b9fb-177">W związku z tym <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> metoda zostanie przesłonięta w zapytaniu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> dla zarejestrowanego akceleratora.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-177">Therefore, the <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> method is overridden to query the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> for a registered accelerator.</span></span> <span data-ttu-id="6b9fb-178">Jeśli zostanie znaleziony zarejestrowanych akceleratora, <xref:System.Windows.Input.AccessKeyManager> przetwarza je.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-178">If a registered accelerator is found, <xref:System.Windows.Input.AccessKeyManager> processes it.</span></span>  
  
-   <span data-ttu-id="6b9fb-179">Jeśli nie zostanie naciśnięty klawisz ALT, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> klasy przetwarza nieobsługiwany danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-179">If the ALT key is not pressed, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> class processes the unhandled input.</span></span> <span data-ttu-id="6b9fb-180">Jeśli dane wejściowe to akcelerator <xref:System.Windows.Input.AccessKeyManager> przetwarza je.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-180">If the input is an accelerator, the <xref:System.Windows.Input.AccessKeyManager> processes it.</span></span> <span data-ttu-id="6b9fb-181"><xref:System.Windows.Input.InputManager.PostProcessInput> Zdarzenie jest obsługiwane dla komunikatów WM_CHAR, które nie zostały przetworzone.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-181">The <xref:System.Windows.Input.InputManager.PostProcessInput> event is handled for WM_CHAR messages that were not processed.</span></span>  
  
 <span data-ttu-id="6b9fb-182">Gdy użytkownik naciśnie klawisz ALT, akceleratora podpowiedzi wizualne są wyświetlane na cały formularz.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-182">When the user presses the ALT key, accelerator visual cues are shown on the whole form.</span></span> <span data-ttu-id="6b9fb-183">Do obsługi tego zachowania, wszystkie <xref:System.Windows.Forms.Integration.ElementHost> formantów w formularzu active odbierać komunikaty WM_SYSKEYDOWN, niezależnie od tego, które formant ma fokus.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-183">To support this behavior, all <xref:System.Windows.Forms.Integration.ElementHost> controls on the active form receive WM_SYSKEYDOWN messages, regardless of which control has focus.</span></span>  
  
 <span data-ttu-id="6b9fb-184">Komunikaty są wysyłane tylko z <xref:System.Windows.Forms.Integration.ElementHost> formantów w formularzu aktywne.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-184">Messages are sent only to <xref:System.Windows.Forms.Integration.ElementHost> controls in the active form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b9fb-185">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6b9fb-185">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="6b9fb-186">Wskazówki: Obsługa formantu złożonego formularzy systemu Windows na platformie WPF</span><span class="sxs-lookup"><span data-stu-id="6b9fb-186">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="6b9fb-187">Wskazówki: Hostowanie formantu złożonego WPF w formularzach systemu Windows</span><span class="sxs-lookup"><span data-stu-id="6b9fb-187">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="6b9fb-188">WPF i współdziałanie Win32</span><span class="sxs-lookup"><span data-stu-id="6b9fb-188">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)