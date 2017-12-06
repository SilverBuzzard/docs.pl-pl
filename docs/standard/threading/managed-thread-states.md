---
title: "Zarządzane stany wątków"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 073fb19ef34ba32ccb5d5664413718a436563770
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="managed-thread-states"></a><span data-ttu-id="bf9da-102">Zarządzane stany wątków</span><span class="sxs-lookup"><span data-stu-id="bf9da-102">Managed Thread States</span></span>
<span data-ttu-id="bf9da-103">Właściwość <xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> zapewnia maska bitowa, która wskazuje bieżący stan wątku.</span><span class="sxs-lookup"><span data-stu-id="bf9da-103">The property <xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> provides a bit mask that indicates the thread's current state.</span></span> <span data-ttu-id="bf9da-104">Wątek jest zawsze w co najmniej jedną z możliwych stanów w <xref:System.Threading.ThreadState> wyliczenia i może mieć różne stany w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="bf9da-104">A thread is always in at least one of the possible states in the <xref:System.Threading.ThreadState> enumeration, and can be in multiple states at the same time.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf9da-105">Stan wątku jest przydatne w kilku tylko dla scenariuszy debugowania.</span><span class="sxs-lookup"><span data-stu-id="bf9da-105">Thread state is only of interest in a few debugging scenarios.</span></span> <span data-ttu-id="bf9da-106">Kod nigdy nie należy używać stan wątku do synchronizowania działania wątków.</span><span class="sxs-lookup"><span data-stu-id="bf9da-106">Your code should never use thread state to synchronize the activities of threads.</span></span>  
  
 <span data-ttu-id="bf9da-107">Podczas tworzenia wątku zarządzanego znajduje się w <xref:System.Threading.ThreadState.Unstarted> stanu.</span><span class="sxs-lookup"><span data-stu-id="bf9da-107">When you create a managed thread, it is in the <xref:System.Threading.ThreadState.Unstarted> state.</span></span> <span data-ttu-id="bf9da-108">Wątek pozostaje w <xref:System.Threading.ThreadState.Unstarted> stanu, dopóki nie zostanie przeniesiona do stan uruchomienia przez system operacyjny.</span><span class="sxs-lookup"><span data-stu-id="bf9da-108">The thread remains in the <xref:System.Threading.ThreadState.Unstarted> state until it is moved into the started state by the operating system.</span></span> <span data-ttu-id="bf9da-109">Wywoływanie <xref:System.Threading.Thread.Start%2A> umożliwia systemowi operacyjnemu wiedzieć, że można uruchomić wątku; nie zmienia stan wątku.</span><span class="sxs-lookup"><span data-stu-id="bf9da-109">Calling <xref:System.Threading.Thread.Start%2A> lets the operating system know that the thread can be started; it does not change the state of the thread.</span></span>  
  
 <span data-ttu-id="bf9da-110">Niezarządzane wątków, które należy wprowadzić zarządzanego środowiska są już w stanie uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="bf9da-110">Unmanaged threads that enter the managed environment are already in the started state.</span></span> <span data-ttu-id="bf9da-111">Gdy wątek jest w stanie uruchomienia, liczbę akcji może spowodować jego zmiany stanów.</span><span class="sxs-lookup"><span data-stu-id="bf9da-111">Once a thread is in the started state, a number of actions can cause it to change states.</span></span> <span data-ttu-id="bf9da-112">W poniższej tabeli wymieniono akcje, które powodują zmianę stanu oraz odpowiadający mu stan nowego.</span><span class="sxs-lookup"><span data-stu-id="bf9da-112">The following table lists the actions that cause a change of state, along with the corresponding new state.</span></span>  
  
|<span data-ttu-id="bf9da-113">Akcja</span><span class="sxs-lookup"><span data-stu-id="bf9da-113">Action</span></span>|<span data-ttu-id="bf9da-114">Wynikowa nowy stan</span><span class="sxs-lookup"><span data-stu-id="bf9da-114">Resulting new state</span></span>|  
|------------|-------------------------|  
|<span data-ttu-id="bf9da-115">Konstruktor <xref:System.Threading.Thread> nosi nazwę klasy.</span><span class="sxs-lookup"><span data-stu-id="bf9da-115">The constructor for the <xref:System.Threading.Thread> class is called.</span></span>|<xref:System.Threading.ThreadState.Unstarted>|  
|<span data-ttu-id="bf9da-116">Inny wątek wywołania <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf9da-116">Another thread calls <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.Unstarted>|  
|<span data-ttu-id="bf9da-117">Wątek odpowiada <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> i uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="bf9da-117">The thread responds to <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> and starts running.</span></span>|<xref:System.Threading.ThreadState.Running>|  
|<span data-ttu-id="bf9da-118">Wywołania wątku <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf9da-118">The thread calls <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|<span data-ttu-id="bf9da-119">Wywołania wątku <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> na inny obiekt.</span><span class="sxs-lookup"><span data-stu-id="bf9da-119">The thread calls <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> on another object.</span></span>|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|<span data-ttu-id="bf9da-120">Wywołania wątku <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> w innym wątku.</span><span class="sxs-lookup"><span data-stu-id="bf9da-120">The thread calls <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> on another thread.</span></span>|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|<span data-ttu-id="bf9da-121">Inny wątek wywołania <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf9da-121">Another thread calls <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.SuspendRequested>|  
|<span data-ttu-id="bf9da-122">Wątek odpowiada <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> żądania.</span><span class="sxs-lookup"><span data-stu-id="bf9da-122">The thread responds to a <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> request.</span></span>|<xref:System.Threading.ThreadState.Suspended>|  
|<span data-ttu-id="bf9da-123">Inny wątek wywołania <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf9da-123">Another thread calls <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.Running>|  
|<span data-ttu-id="bf9da-124">Inny wątek wywołania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf9da-124">Another thread calls <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.AbortRequested>|  
|<span data-ttu-id="bf9da-125">Wątek odpowiada <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf9da-125">The thread responds to an <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>|<span data-ttu-id="bf9da-126"><xref:System.Threading.ThreadState.Aborted>, następnie<xref:System.Threading.ThreadState.Stopped></span><span class="sxs-lookup"><span data-stu-id="bf9da-126"><xref:System.Threading.ThreadState.Aborted>, then <xref:System.Threading.ThreadState.Stopped></span></span>|  
  
 <span data-ttu-id="bf9da-127">Ponieważ <xref:System.Threading.ThreadState.Running> stan ma wartość 0, nie można wykonać bitowych testów, aby odnaleźć ten stan.</span><span class="sxs-lookup"><span data-stu-id="bf9da-127">Because the <xref:System.Threading.ThreadState.Running> state has a value of 0, it is not possible to perform a bit test to discover this state.</span></span> <span data-ttu-id="bf9da-128">Zamiast tego można użyć następującego testu (w pseudo-kodzie):</span><span class="sxs-lookup"><span data-stu-id="bf9da-128">Instead, the following test (in pseudo-code) can be used:</span></span>  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 <span data-ttu-id="bf9da-129">Wątki są często więcej niż jednego stanu w danym momencie.</span><span class="sxs-lookup"><span data-stu-id="bf9da-129">Threads are often in more than one state at any given time.</span></span> <span data-ttu-id="bf9da-130">Na przykład, jeśli wątek jest zablokowany na <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> połączeń i innego wątku wywołania <xref:System.Threading.Thread.Abort%2A> w tym samym wątku, wątek będą zarówno <xref:System.Threading.ThreadState.WaitSleepJoin> i <xref:System.Threading.ThreadState.AbortRequested> Państwa, w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="bf9da-130">For example, if a thread is blocked on a <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> call and another thread calls <xref:System.Threading.Thread.Abort%2A> on that same thread, the thread will be in both the <xref:System.Threading.ThreadState.WaitSleepJoin> and the <xref:System.Threading.ThreadState.AbortRequested> states at the same time.</span></span> <span data-ttu-id="bf9da-131">W takim przypadku natychmiast zwraca wątku z wywołania <xref:System.Threading.Monitor.Wait%2A> lub przerwane, zostanie wyświetlony <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="bf9da-131">In that case, as soon as the thread returns from the call to <xref:System.Threading.Monitor.Wait%2A> or is interrupted, it will receive the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 <span data-ttu-id="bf9da-132">Gdy wątek pozostawia <xref:System.Threading.ThreadState.Unstarted> stanu w wyniku wywołania <xref:System.Threading.Thread.Start%2A>, nigdy nie powraca do <xref:System.Threading.ThreadState.Unstarted> stanu.</span><span class="sxs-lookup"><span data-stu-id="bf9da-132">Once a thread leaves the <xref:System.Threading.ThreadState.Unstarted> state as the result of a call to <xref:System.Threading.Thread.Start%2A>, it can never return to the <xref:System.Threading.ThreadState.Unstarted> state.</span></span> <span data-ttu-id="bf9da-133">Wątek nigdy nie może pozostać <xref:System.Threading.ThreadState.Stopped> stanu.</span><span class="sxs-lookup"><span data-stu-id="bf9da-133">A thread can never leave the <xref:System.Threading.ThreadState.Stopped> state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9da-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bf9da-134">See Also</span></span>  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadState>  
 [<span data-ttu-id="bf9da-135">Wątkowość</span><span class="sxs-lookup"><span data-stu-id="bf9da-135">Threading</span></span>](../../../docs/standard/threading/index.md)