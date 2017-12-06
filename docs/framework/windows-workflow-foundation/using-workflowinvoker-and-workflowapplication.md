---
title: "Przy użyciu WorkflowInvoker i działanie obiektu WorkflowApplication"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd0e583c-a3f9-4fa2-b247-c7b3368c48a7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f1e4bb05f1b5f14554ff5183b42bbc8884cb114f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2017
---
# <a name="using-workflowinvoker-and-workflowapplication"></a><span data-ttu-id="380b0-102">Przy użyciu WorkflowInvoker i działanie obiektu WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="380b0-102">Using WorkflowInvoker and WorkflowApplication</span></span>
[!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="380b0-103">zapewnia kilka metod obsługi przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="380b0-103"> provides several methods of hosting workflows.</span></span> <span data-ttu-id="380b0-104"><xref:System.Activities.WorkflowInvoker>zapewnia prostą metodę do wywoływania przepływu pracy, tak, jakby były wywołanie metody i można używać tylko w przypadku przepływów pracy, które nie korzystają z trwałości.</span><span class="sxs-lookup"><span data-stu-id="380b0-104"><xref:System.Activities.WorkflowInvoker> provides a simple way for invoking a workflow as if it were a method call and can be used only for workflows that do not use persistence.</span></span> <span data-ttu-id="380b0-105"><xref:System.Activities.WorkflowApplication>zapewnia bardziej rozbudowane model do wykonywania przepływów pracy, które zawiera powiadomienia o zdarzenia cyklu życia, kontrola wykonywania wznowienie zakładek i trwałości.</span><span class="sxs-lookup"><span data-stu-id="380b0-105"><xref:System.Activities.WorkflowApplication> provides a richer model for executing workflows that includes notification of lifecycle events, execution control, bookmark resumption, and persistence.</span></span> <span data-ttu-id="380b0-106"><xref:System.ServiceModel.Activities.WorkflowServiceHost>zapewnia obsługę działań dotyczących komunikatów i jest używany głównie z usług przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="380b0-106"><xref:System.ServiceModel.Activities.WorkflowServiceHost> provides support for messaging activities and is primarily used with workflow services.</span></span> <span data-ttu-id="380b0-107">Ten temat stanowi wprowadzenie do przepływu pracy obsługującego z <xref:System.Activities.WorkflowInvoker> i <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="380b0-107">This topic introduces you to workflow hosting with <xref:System.Activities.WorkflowInvoker> and <xref:System.Activities.WorkflowApplication>.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="380b0-108">hosting przepływy pracy z <xref:System.ServiceModel.Activities.WorkflowServiceHost>, zobacz [usług przepływu pracy](../../../docs/framework/wcf/feature-details/workflow-services.md) i [Hosting przegląd usług przepływu pracy](../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md).</span><span class="sxs-lookup"><span data-stu-id="380b0-108"> hosting workflows with <xref:System.ServiceModel.Activities.WorkflowServiceHost>, see [Workflow Services](../../../docs/framework/wcf/feature-details/workflow-services.md) and [Hosting Workflow Services Overview](../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md).</span></span>  
  
## <a name="using-workflowinvoker"></a><span data-ttu-id="380b0-109">Przy użyciu WorkflowInvoker</span><span class="sxs-lookup"><span data-stu-id="380b0-109">Using WorkflowInvoker</span></span>  
 <span data-ttu-id="380b0-110"><xref:System.Activities.WorkflowInvoker>udostępnia model wykonania przepływu pracy, jak w przypadku wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="380b0-110"><xref:System.Activities.WorkflowInvoker> provides a model for executing a workflow as if it were a method call.</span></span> <span data-ttu-id="380b0-111">Można wywołać przepływu pracy przy użyciu <xref:System.Activities.WorkflowInvoker>, wywołaj <xref:System.Activities.WorkflowInvoker.Invoke%2A> — metoda i przekazać w definicji przepływu pracy przepływu pracy do wywołania.</span><span class="sxs-lookup"><span data-stu-id="380b0-111">To invoke a workflow using <xref:System.Activities.WorkflowInvoker>, call the <xref:System.Activities.WorkflowInvoker.Invoke%2A> method and pass in the workflow definition of the workflow to invoke.</span></span> <span data-ttu-id="380b0-112">W tym przykładzie <xref:System.Activities.Statements.WriteLine> działania jest wywoływana przy użyciu <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="380b0-112">In this example, a <xref:System.Activities.Statements.WriteLine> activity is invoked using <xref:System.Activities.WorkflowInvoker>.</span></span>  
  
 [!code-csharp[CFX_WorkflowInvokerExample#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#1)]  
  
 <span data-ttu-id="380b0-113">Jeśli przepływ pracy zostanie wywołane przy użyciu <xref:System.Activities.WorkflowInvoker>, przepływu pracy wykonuje w wątku wywołującym i <xref:System.Activities.WorkflowInvoker.Invoke%2A> metody blokuje aż przepływ pracy zostanie zakończone, w tym wszelkie czas bezczynności.</span><span class="sxs-lookup"><span data-stu-id="380b0-113">When a workflow is invoked using <xref:System.Activities.WorkflowInvoker>, the workflow executes on the calling thread and the <xref:System.Activities.WorkflowInvoker.Invoke%2A> method blocks until the workflow is complete, including any idle time.</span></span> <span data-ttu-id="380b0-114">Aby skonfigurować interwał limitu czasu, w którym należy wykonać przepływu pracy, użyj jednej z <xref:System.Activities.WorkflowInvoker.Invoke%2A> przeciążeń, które przyjmuje <xref:System.TimeSpan> parametru.</span><span class="sxs-lookup"><span data-stu-id="380b0-114">To configure a time-out interval in which the workflow must complete, use one of the <xref:System.Activities.WorkflowInvoker.Invoke%2A> overloads that takes a <xref:System.TimeSpan> parameter.</span></span> <span data-ttu-id="380b0-115">W tym przykładzie przepływu pracy została wywołana dwa razy z dwóch różnych limitu czasu odstępach czasu.</span><span class="sxs-lookup"><span data-stu-id="380b0-115">In this example, a workflow is invoked twice with two different time-out intervals.</span></span> <span data-ttu-id="380b0-116">Pierwszy complets przepływu pracy, ale druga nie.</span><span class="sxs-lookup"><span data-stu-id="380b0-116">The first workflow complets, but the second does not.</span></span>  
  
 [!code-csharp[CFX_WorkflowInvokerExample#50](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#50)]  
  
> [!NOTE]
>  <span data-ttu-id="380b0-117"><xref:System.TimeoutException> Jest tylko element zgłaszany, gdy upłynie limit czasu, a przepływ pracy przestanie być bezczynne podczas wykonywania.</span><span class="sxs-lookup"><span data-stu-id="380b0-117">The <xref:System.TimeoutException> is only thrown if the time-out interval elapses and the workflow becomes idle during execution.</span></span> <span data-ttu-id="380b0-118">Przepływ pracy, który będzie trwało dłużej niż interwał określony limit czasu, aby ukończyć zakończy się pomyślnie, jeśli przepływ pracy przejdzie w stan bezczynności.</span><span class="sxs-lookup"><span data-stu-id="380b0-118">A workflow that takes longer than the specified time-out interval to complete completes successfully if the workflow does not become idle.</span></span>  
  
 <span data-ttu-id="380b0-119"><xref:System.Activities.WorkflowInvoker>udostępnia asynchroniczne wersje metody invoke.</span><span class="sxs-lookup"><span data-stu-id="380b0-119"><xref:System.Activities.WorkflowInvoker> also provides asynchronous versions of the invoke method.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="380b0-120"><xref:System.Activities.WorkflowInvoker.InvokeAsync%2A> i <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="380b0-120"> <xref:System.Activities.WorkflowInvoker.InvokeAsync%2A> and <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A>.</span></span>  
  
### <a name="setting-input-arguments-of-a-workflow"></a><span data-ttu-id="380b0-121">Ustawienia argumentów wejściowych przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="380b0-121">Setting Input Arguments of a Workflow</span></span>  
 <span data-ttu-id="380b0-122">Dane mogą być przekazywane do przepływu pracy za pomocą słownika parametrów wejściowych, wyznaczaną przez Nazwa argumentu mapowane na argumenty wejściowe przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="380b0-122">Data can be passed into a workflow using a dictionary of input parameters, keyed by argument name, that map to the input arguments of the workflow.</span></span> <span data-ttu-id="380b0-123">W tym przykładzie <xref:System.Activities.Statements.WriteLine> jest wywoływany i wartości dla jego <xref:System.Activities.Statements.WriteLine.Text%2A> argument zostanie określony, używając słownika parametrów wejściowych.</span><span class="sxs-lookup"><span data-stu-id="380b0-123">In this example, a <xref:System.Activities.Statements.WriteLine> is invoked and the value for its <xref:System.Activities.Statements.WriteLine.Text%2A> argument is specified using the dictionary of input parameters.</span></span>  
  
 [!code-csharp[CFX_WorkflowInvokerExample#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#3)]  
  
### <a name="retrieving-output-arguments-of-a-workflow"></a><span data-ttu-id="380b0-124">Pobieranie danych wyjściowych argumenty przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="380b0-124">Retrieving Output Arguments of a Workflow</span></span>  
 <span data-ttu-id="380b0-125">Parametry wyjściowe przepływu pracy można uzyskać za pomocą słownika danych wyjściowych, która jest zwracana z wywołania <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="380b0-125">The output parameters of a workflow can be obtained using the outputs dictionary that is returned from the call to <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="380b0-126">Poniższy przykład przedstawia wywoływanie przepływu pracy składającą się z pojedynczej `Divide` działanie, czy ma dwa argumenty w danych wejściowych i wyjściowych dwóch argumentów.</span><span class="sxs-lookup"><span data-stu-id="380b0-126">The following example invokes a workflow consisting of a single `Divide` activity that has two input arguments and two output arguments.</span></span> <span data-ttu-id="380b0-127">Jeśli przepływ pracy zostanie wywołane, `arguments` słownika jest przekazywany, która zawiera wartości dla każdego wejścia argumentu, wyznaczaną przez Nazwa argumentu.</span><span class="sxs-lookup"><span data-stu-id="380b0-127">When the workflow is invoked, the `arguments` dictionary is passed which contains the values for each input argument, keyed by argument name.</span></span> <span data-ttu-id="380b0-128">Po wywołaniu `Invoke` zwraca każdy argument wyjściowy jest zwracany w `outputs` słownika, także klucze w postaci nazwy argumentu.</span><span class="sxs-lookup"><span data-stu-id="380b0-128">When the call to `Invoke` returns, each output argument is returned in the `outputs` dictionary, also keyed by argument name.</span></span>  
  
 [!code-csharp[CFX_WorkflowInvokerExample#120](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#120)]  
  
 [!code-csharp[CFX_WorkflowInvokerExample#20](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#20)]  
  
 <span data-ttu-id="380b0-129">Jeśli przepływ pracy jest pochodną <xref:System.Activities.ActivityWithResult>, takich jak `CodeActivity<TResult>` lub `Activity<TResult>`, i argumenty wyjściowe oprócz dobrze zdefiniowany <xref:System.Activities.Activity%601.Result%2A> output argumentu, przeciążenia nierodzajową `Invoke` musi być używany w celu pobrania dodatkowe argumenty.</span><span class="sxs-lookup"><span data-stu-id="380b0-129">If the workflow derives from <xref:System.Activities.ActivityWithResult>, such as `CodeActivity<TResult>` or `Activity<TResult>`, and there are output arguments in addition to the well-defined <xref:System.Activities.Activity%601.Result%2A> output argument, a non-generic overload of `Invoke` must be used in order to retrieve the additional arguments.</span></span> <span data-ttu-id="380b0-130">Aby to zrobić, definicji przepływu pracy przekazany `Invoke` musi być typu <xref:System.Activities.Activity>.</span><span class="sxs-lookup"><span data-stu-id="380b0-130">To do this, the workflow definition passed into `Invoke` must be of type <xref:System.Activities.Activity>.</span></span> <span data-ttu-id="380b0-131">W tym przykładzie `Divide` działania pochodzi z `CodeActivity<int>`, ale jest zadeklarowany jako <xref:System.Activities.Activity> tak, aby nieogólnego przeciążenia z `Invoke` jest używany, która zwraca słownika argumentów zamiast pojedynczej wartości zwracanych.</span><span class="sxs-lookup"><span data-stu-id="380b0-131">In this example the `Divide` activity derives from `CodeActivity<int>`, but is declared as <xref:System.Activities.Activity> so that a non-generic overload of `Invoke` is used which returns a dictionary of arguments instead of a single return value.</span></span>  
  
 [!code-csharp[CFX_WorkflowInvokerExample#121](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#121)]  
  
 [!code-csharp[CFX_WorkflowInvokerExample#21](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#21)]  
  
## <a name="using-workflowapplication"></a><span data-ttu-id="380b0-132">Przy użyciu obiektu WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="380b0-132">Using WorkflowApplication</span></span>  
 <span data-ttu-id="380b0-133"><xref:System.Activities.WorkflowApplication>zawiera bogaty zestaw funkcji do zarządzania wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="380b0-133"><xref:System.Activities.WorkflowApplication> provides a rich set of features for workflow instance management.</span></span> <span data-ttu-id="380b0-134"><xref:System.Activities.WorkflowApplication>działa jako serwer proxy bezpieczne wątek, do rzeczywistych <xref:System.Activities.Hosting.WorkflowInstance>, który hermetyzuje środowiska uruchomieniowego i udostępnia metody do tworzenia i ładowanie wystąpienia przepływu pracy, wstrzymywanie i wznawianie, przerywanie i powiadomienia o zdarzeniach cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="380b0-134"><xref:System.Activities.WorkflowApplication> acts as a thread safe proxy to the actual  <xref:System.Activities.Hosting.WorkflowInstance>, which encapsulates the runtime, and provides methods for creating and loading workflow instances, pausing and resuming, terminating, and notification of lifecycle events.</span></span> <span data-ttu-id="380b0-135">Do uruchamiania przepływu pracy przy użyciu <xref:System.Activities.WorkflowApplication> tworzenia <xref:System.Activities.WorkflowApplication>, subskrybowanie zdarzeń cyklu życia żądaną uruchomienia przepływu pracy i poczekaj na jego zakończenie.</span><span class="sxs-lookup"><span data-stu-id="380b0-135">To run a workflow using <xref:System.Activities.WorkflowApplication> you create the <xref:System.Activities.WorkflowApplication>, subscribe to any desired lifecycle events, start the workflow, and then wait for it to finish.</span></span> <span data-ttu-id="380b0-136">W tym przykładzie definicji przepływu pracy składający się z <xref:System.Activities.Statements.WriteLine> utworzeniu działania i <xref:System.Activities.WorkflowApplication> jest tworzony przy użyciu definicji określonego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="380b0-136">In this example, a workflow definition that consists of a <xref:System.Activities.Statements.WriteLine> activity is created and a <xref:System.Activities.WorkflowApplication> is created using the specified workflow definition.</span></span> <span data-ttu-id="380b0-137"><xref:System.Activities.WorkflowApplication.Completed%2A>jest obsługiwane, dlatego host otrzymał powiadomienie po zakończeniu przepływu pracy, przepływ pracy zostanie uruchomiony przy użyciu wywołania <xref:System.Activities.WorkflowApplication.Run%2A>, a następnie oczekiwanie hosta do ukończenia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="380b0-137"><xref:System.Activities.WorkflowApplication.Completed%2A> is handled so the host is notified when the workflow completes, the workflow is started with a call to <xref:System.Activities.WorkflowApplication.Run%2A>, and then the host waits for the workflow to complete.</span></span> <span data-ttu-id="380b0-138">Po zakończeniu przepływu pracy, <xref:System.Threading.AutoResetEvent> jest ustawiony, a host aplikacji można wznowić wykonywania, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="380b0-138">When the workflow completes, the <xref:System.Threading.AutoResetEvent> is set and the host application can resume execution, as shown in the following example.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#31](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#31)]  
  
### <a name="workflowapplication-lifecycle-events"></a><span data-ttu-id="380b0-139">Zdarzenia cyklu życia obiektu WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="380b0-139">WorkflowApplication Lifecycle Events</span></span>  
 <span data-ttu-id="380b0-140">Oprócz <xref:System.Activities.WorkflowApplication.Completed%2A>, autorzy hosta może otrzymać powiadomienie, gdy przepływ pracy zostanie zwolniony (<xref:System.Activities.WorkflowApplication.Unloaded%2A>), zostało przerwane (<xref:System.Activities.WorkflowApplication.Aborted%2A>), staje się bezczynności (<xref:System.Activities.WorkflowApplication.Idle%2A> i <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>), lub wystąpi nieobsługiwany wyjątek (<xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>).</span><span class="sxs-lookup"><span data-stu-id="380b0-140">In addition to <xref:System.Activities.WorkflowApplication.Completed%2A>, host authors can be notified when a workflow is unloaded (<xref:System.Activities.WorkflowApplication.Unloaded%2A>), aborted (<xref:System.Activities.WorkflowApplication.Aborted%2A>), becomes idle (<xref:System.Activities.WorkflowApplication.Idle%2A> and <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>), or an unhandled exception occurs (<xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>).</span></span> <span data-ttu-id="380b0-141">Deweloperzy aplikacji przepływu pracy można obsługiwać te powiadomienia i podejmij odpowiednią akcję, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="380b0-141">Workflow application developers can handle these notifications and take appropriate action, as shown in the following example.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#32](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#32)]  
  
### <a name="setting-input-arguments-of-a-workflow"></a><span data-ttu-id="380b0-142">Ustawienia argumentów wejściowych przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="380b0-142">Setting Input Arguments of a Workflow</span></span>  
 <span data-ttu-id="380b0-143">Dane mogą być przekazywane do przepływu pracy, jak została uruchomiona przy użyciu słownik parametrów, podobne do danych sposób jest przekazywany w przypadku korzystania z <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="380b0-143">Data can be passed into a workflow as it is started using a dictionary of parameters, similar to the way data is passed in when using <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="380b0-144">Argument wejściowy określonego przepływu pracy mapuje każdego elementu w słowniku.</span><span class="sxs-lookup"><span data-stu-id="380b0-144">Each item in the dictionary maps to an input argument of the specified workflow.</span></span> <span data-ttu-id="380b0-145">W tym przykładzie przepływ pracy składający się z <xref:System.Activities.Statements.WriteLine> działania jest wywoływany i jego <xref:System.Activities.Statements.WriteLine.Text%2A> argument zostanie określony, używając słownika parametrów wejściowych.</span><span class="sxs-lookup"><span data-stu-id="380b0-145">In this example, a workflow that consists of a <xref:System.Activities.Statements.WriteLine> activity is invoked and its <xref:System.Activities.Statements.WriteLine.Text%2A> argument is specified using the dictionary of input parameters.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#30](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#30)]  
  
### <a name="retrieving-output-arguments-of-a-workflow"></a><span data-ttu-id="380b0-146">Pobieranie danych wyjściowych argumenty przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="380b0-146">Retrieving Output Arguments of a Workflow</span></span>  
 <span data-ttu-id="380b0-147">Po zakończeniu przepływu pracy, można pobrać żadnych danych wyjściowych argumentów w <xref:System.Activities.WorkflowApplication.Completed%2A> obsługi uzyskując dostęp do <xref:System.Activities.WorkflowApplicationCompletedEventArgs.Outputs%2A?displayProperty=nameWithType> słownika.</span><span class="sxs-lookup"><span data-stu-id="380b0-147">When a workflow completes, any output arguments can be retrieved in the <xref:System.Activities.WorkflowApplication.Completed%2A> handler by accessing the <xref:System.Activities.WorkflowApplicationCompletedEventArgs.Outputs%2A?displayProperty=nameWithType> dictionary.</span></span> <span data-ttu-id="380b0-148">Poniższy przykład zawiera przepływu pracy przy użyciu <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="380b0-148">The following example hosts a workflow using <xref:System.Activities.WorkflowApplication>.</span></span> <span data-ttu-id="380b0-149">A <xref:System.Activities.WorkflowApplication> wystąpienia jest tworzony przy użyciu definicji przepływu pracy, składającą się z pojedynczej `DiceRoll` działania.</span><span class="sxs-lookup"><span data-stu-id="380b0-149">A <xref:System.Activities.WorkflowApplication> instance is constructed using using a workflow definition consisting of a single `DiceRoll` activity.</span></span> <span data-ttu-id="380b0-150">`DiceRoll` Działanie ma dwa argumenty danych wyjściowych reprezentujące wyniki operacji zbiorczego grupowane.</span><span class="sxs-lookup"><span data-stu-id="380b0-150">The `DiceRoll` activity has two output arguments that represent the results of the dice roll operation.</span></span> <span data-ttu-id="380b0-151">Po zakończeniu przepływu pracy, dane wyjściowe są pobierane w <xref:System.Activities.WorkflowApplication.Completed%2A> programu obsługi.</span><span class="sxs-lookup"><span data-stu-id="380b0-151">When the workflow completes, the outputs are retrieved in the <xref:System.Activities.WorkflowApplication.Completed%2A> handler.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#130](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#130)]  
  
 [!code-csharp[CFX_WorkflowApplicationExample#21](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#21)]  
  
> [!NOTE]
>  <span data-ttu-id="380b0-152"><xref:System.Activities.WorkflowApplication>i <xref:System.Activities.WorkflowInvoker> przyjmować ze słownika wejściowego argumenty i zwracać słownik `out` argumentów.</span><span class="sxs-lookup"><span data-stu-id="380b0-152"><xref:System.Activities.WorkflowApplication> and <xref:System.Activities.WorkflowInvoker> take a dictionary of input arguments and return a dictionary of `out` arguments.</span></span> <span data-ttu-id="380b0-153">Te parametry słownika, właściwości i wartości zwracane są typu `IDictionary<string, object>`.</span><span class="sxs-lookup"><span data-stu-id="380b0-153">These dictionary parameters, properties, and return values are of type `IDictionary<string, object>`.</span></span> <span data-ttu-id="380b0-154">Rzeczywiste wystąpienie klasy słownik, który jest przekazywany w może być każda klasa implementująca `IDictionary<string, object>`.</span><span class="sxs-lookup"><span data-stu-id="380b0-154">The actual instance of the dictionary class that is passed in can be any class that implements `IDictionary<string, object>`.</span></span> <span data-ttu-id="380b0-155">W tym przykładzie `Dictionary<string, object>` jest używany.</span><span class="sxs-lookup"><span data-stu-id="380b0-155">In these examples, `Dictionary<string, object>` is used.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="380b0-156">Zobacz słowników, <xref:System.Collections.Generic.IDictionary%602> i <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="380b0-156"> dictionaries, see <xref:System.Collections.Generic.IDictionary%602> and <xref:System.Collections.Generic.Dictionary%602>.</span></span>  
  
### <a name="passing-data-into-a-running-workflow-using-bookmarks"></a><span data-ttu-id="380b0-157">Przekazywanie danych do działania przepływu pracy korzystanie z zakładek</span><span class="sxs-lookup"><span data-stu-id="380b0-157">Passing Data into a Running Workflow Using Bookmarks</span></span>  
 <span data-ttu-id="380b0-158">Zakładki są mechanizm, za pomocą której działanie pasywnie poczekać wznowienie zadania było i jest mechanizm przekazywania danych do uruchomionego wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="380b0-158">Bookmarks are the mechanism by which an activity can passively wait to be resumed and are a mechanism for passing data into a running workflow instance.</span></span> <span data-ttu-id="380b0-159">Jeśli działanie oczekuje na dane, można utworzyć <xref:System.Activities.Bookmark> i zarejestruj Metoda wywołania zwrotnego wywoływana, gdy <xref:System.Activities.Bookmark> zostanie wznowione, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="380b0-159">If an activity is waiting for data, it can create a <xref:System.Activities.Bookmark> and register a callback method to be called when the <xref:System.Activities.Bookmark> is resumed, as shown in the following example.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
 <span data-ttu-id="380b0-160">Po wykonaniu `ReadLine` działanie tworzy <xref:System.Activities.Bookmark>, rejestruje wywołanie zwrotne, a następnie oczekiwanie <xref:System.Activities.Bookmark> wznowienie zadania było.</span><span class="sxs-lookup"><span data-stu-id="380b0-160">When executed, the `ReadLine` activity creates a <xref:System.Activities.Bookmark>, registers a callback, and then waits for the <xref:System.Activities.Bookmark> to be resumed.</span></span> <span data-ttu-id="380b0-161">Gdy zostanie wznowione, `ReadLine` działania przypisuje danych, który został przekazany z <xref:System.Activities.Bookmark> do jego <xref:System.Activities.Activity%601.Result%2A> argumentu.</span><span class="sxs-lookup"><span data-stu-id="380b0-161">When it is resumed, the `ReadLine` activity assigns the data that was passed with the <xref:System.Activities.Bookmark> to its <xref:System.Activities.Activity%601.Result%2A> argument.</span></span> <span data-ttu-id="380b0-162">W tym przykładzie przepływ pracy jest tworzony, który używa `ReadLine` działania zebranie nazwy użytkownika i wyświetlić je w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="380b0-162">In this example, a workflow is created that uses the `ReadLine` activity to gather the user’s name and display it to the console window.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#22](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#22)]  
  
 <span data-ttu-id="380b0-163">Gdy `ReadLine` działania jest wykonywana, tworzy <xref:System.Activities.Bookmark> o nazwie `UserName` , a następnie oczekiwanie zakładki wznowienie zadania było.</span><span class="sxs-lookup"><span data-stu-id="380b0-163">When the `ReadLine` activity is executed, it creates a <xref:System.Activities.Bookmark> named `UserName` and then waits for the bookmark to be resumed.</span></span> <span data-ttu-id="380b0-164">Zbiera dane żądanego hosta, a następnie kontynuowanie <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="380b0-164">The host collects the desired data and then resumes the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="380b0-165">Przepływ pracy wznawia, wyświetla nazwę, a następnie kończy.</span><span class="sxs-lookup"><span data-stu-id="380b0-165">The workflow resumes, displays the name, and then completes.</span></span>  
  
 <span data-ttu-id="380b0-166">Host aplikacji może sprawdzać przepływu pracy, aby określić, czy istnieją aktywne zakładek.</span><span class="sxs-lookup"><span data-stu-id="380b0-166">The host application can inspect the workflow to determine if there are any active bookmarks.</span></span> <span data-ttu-id="380b0-167">Go to zrobić przez wywołanie metody <xref:System.Activities.WorkflowApplication.GetBookmarks%2A> metody <xref:System.Activities.WorkflowApplication> wystąpienia, lub przez kontrolę <xref:System.Activities.WorkflowApplicationIdleEventArgs> w <xref:System.Activities.WorkflowApplication.Idle%2A> programu obsługi.</span><span class="sxs-lookup"><span data-stu-id="380b0-167">It can do this by calling the <xref:System.Activities.WorkflowApplication.GetBookmarks%2A> method of a <xref:System.Activities.WorkflowApplication> instance, or by inspecting the <xref:System.Activities.WorkflowApplicationIdleEventArgs> in the <xref:System.Activities.WorkflowApplication.Idle%2A> handler.</span></span>  
  
 <span data-ttu-id="380b0-168">Poniższy przykład kodu jest tak jak w poprzednim przykładzie, z tą różnicą, że wyliczane są aktywne zakładki przed wznowieniu działania zakładki.</span><span class="sxs-lookup"><span data-stu-id="380b0-168">The following code example is like the previous example except that the active bookmarks are enumerated before the bookmark is resumed.</span></span> <span data-ttu-id="380b0-169">Przepływu pracy została uruchomiona, a drugi raz <xref:System.Activities.Bookmark> jest tworzony i przepływ pracy przejdzie bezczynności, <xref:System.Activities.WorkflowApplication.GetBookmarks%2A> nosi nazwę.</span><span class="sxs-lookup"><span data-stu-id="380b0-169">The workflow is started, and once the <xref:System.Activities.Bookmark> is created and the workflow goes idle, <xref:System.Activities.WorkflowApplication.GetBookmarks%2A> is called.</span></span> <span data-ttu-id="380b0-170">Po zakończeniu przepływu pracy następujące dane wyjściowe są wyświetlane w konsoli.</span><span class="sxs-lookup"><span data-stu-id="380b0-170">When the workflow is completed, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="380b0-171">**Jak się nazywasz?**</span><span class="sxs-lookup"><span data-stu-id="380b0-171">**What is your name?**</span></span>  
<span data-ttu-id="380b0-172">**Nazwa zakładki: Nazwa_użytkownika - OwnerDisplayName: ReadLine** </span><span class="sxs-lookup"><span data-stu-id="380b0-172">**BookmarkName: UserName - OwnerDisplayName: ReadLine** </span></span>  
<span data-ttu-id="380b0-173">**Steve** </span><span class="sxs-lookup"><span data-stu-id="380b0-173">**Steve** </span></span>  
<span data-ttu-id="380b0-174">**Witaj, Steve**</span><span class="sxs-lookup"><span data-stu-id="380b0-174">**Hello, Steve**</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#14](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#14)]  
  
 <span data-ttu-id="380b0-175">Poniższy przykład kodu sprawdza <xref:System.Activities.WorkflowApplicationIdleEventArgs> przekazany <xref:System.Activities.WorkflowApplication.Idle%2A> obsługi <xref:System.Activities.WorkflowApplication> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="380b0-175">The following code example inspects the <xref:System.Activities.WorkflowApplicationIdleEventArgs> passed into the <xref:System.Activities.WorkflowApplication.Idle%2A> handler of a <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="380b0-176">W tym przykładzie przepływu pracy, przejście w stan bezczynności ma jeden <xref:System.Activities.Bookmark> o nazwie `EnterGuess`, będących własnością przez działanie o nazwie `ReadInt`.</span><span class="sxs-lookup"><span data-stu-id="380b0-176">In this example the workflow going idle has one <xref:System.Activities.Bookmark> with a name of `EnterGuess`, owned by an activity named `ReadInt`.</span></span> <span data-ttu-id="380b0-177">W tym przykładzie kodu opiera się z [porady: uruchamianie przepływu pracy](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md), który jest częścią [Wprowadzenie — samouczek](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="380b0-177">This code example is based off of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md), which is part of the [Getting Started Tutorial](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md).</span></span> <span data-ttu-id="380b0-178">Jeśli <xref:System.Activities.WorkflowApplication.Idle%2A> program obsługi, w tym kroku są modyfikowane w celu zawiera kod z tego przykładu, wyświetlane są następujące dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="380b0-178">If the <xref:System.Activities.WorkflowApplication.Idle%2A> handler in that step is modified to contain the code from this example, the following output is displayed.</span></span>  
  
 <span data-ttu-id="380b0-179">**Nazwa zakładki: EnterGuess - OwnerDisplayName: ReadInt**</span><span class="sxs-lookup"><span data-stu-id="380b0-179">**BookmarkName: EnterGuess - OwnerDisplayName: ReadInt**</span></span>
 
 [!code-csharp[CFX_WorkflowApplicationExample#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#2)]  
  
## <a name="summary"></a><span data-ttu-id="380b0-180">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="380b0-180">Summary</span></span>  
 <span data-ttu-id="380b0-181"><xref:System.Activities.WorkflowInvoker>Umożliwia uproszczonego wywoływać przepływy pracy, i chociaż zapewnia metody przekazywanie danych podczas uruchamiania przepływu pracy i wyodrębniania danych z ukończonych przepływów pracy, a nie zapewnia bardziej złożonych scenariuszach czyli gdzie <xref:System.Activities.WorkflowApplication> mogą być używane.</span><span class="sxs-lookup"><span data-stu-id="380b0-181"><xref:System.Activities.WorkflowInvoker> provides a lightweight way to invoke workflows, and although it provides methods for passing data in at the start of a workflow and extracting data from a completed workflow, it does not provide for more complex scenarios which is where <xref:System.Activities.WorkflowApplication> can be used.</span></span>