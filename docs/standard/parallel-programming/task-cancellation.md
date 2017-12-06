---
title: Anulowanie zadania
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, cancellation
- asynchronous task cancellation
ms.assetid: 3ecf1ea9-e399-4a6a-a0d6-8475f48dcb28
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 106c89ca9fcfb8bbab23b982cdc524ff78d21d15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="task-cancellation"></a><span data-ttu-id="b8822-102">Anulowanie zadania</span><span class="sxs-lookup"><span data-stu-id="b8822-102">Task Cancellation</span></span>
<span data-ttu-id="b8822-103"><xref:System.Threading.Tasks.Task?displayProperty=nameWithType> i <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> klasy obsługuje anulowania przy użyciu anulowanie tokenów w programie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8822-103">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> classes support cancellation through the use of cancellation tokens in the .NET Framework.</span></span> <span data-ttu-id="b8822-104">Aby uzyskać więcej informacji, zobacz [anulowanie w zarządzanych wątkach](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="b8822-104">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="b8822-105">W klasach Task anulowanie pociąga za sobą współpracę pełnomocnika użytkownika, który reprezentuje możliwości anulowania operacji i kodu, który zażądał anulowania.</span><span class="sxs-lookup"><span data-stu-id="b8822-105">In the Task classes, cancellation involves cooperation between the user delegate, which represents a cancelable operation and the code that requested the cancellation.</span></span>  <span data-ttu-id="b8822-106">Pomyślne anulowania obejmuje żądania wywołania kodu <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> — metoda i delegowanie użytkownika zakończenie operacji w odpowiednim czasie.</span><span class="sxs-lookup"><span data-stu-id="b8822-106">A successful cancellation involves the requesting code calling the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method, and the user delegate terminating the operation in a timely manner.</span></span> <span data-ttu-id="b8822-107">Można zakończyć operację przy użyciu jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="b8822-107">You can terminate the operation by using one of these options:</span></span>  
  
-   <span data-ttu-id="b8822-108">Powracając po prostu od pełnomocnika.</span><span class="sxs-lookup"><span data-stu-id="b8822-108">By simply returning from the delegate.</span></span> <span data-ttu-id="b8822-109">W wielu scenariuszach jest wystarczające; Jednak wystąpienie zadania, które zostało anulowane w ten sposób przejścia do <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType> stanu, aby nie <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> stanu.</span><span class="sxs-lookup"><span data-stu-id="b8822-109">In many scenarios this is sufficient; however, a task instance that is canceled in this way transitions to the <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType> state, not to the <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> state.</span></span>  
  
-   <span data-ttu-id="b8822-110">Przez zgłaszanie <xref:System.OperationCanceledException> i przekazanie jej przez token, na których zażądano anulowania.</span><span class="sxs-lookup"><span data-stu-id="b8822-110">By throwing a <xref:System.OperationCanceledException> and passing it the token on which cancellation was requested.</span></span> <span data-ttu-id="b8822-111">Preferowaną metodą w tym celu jest użycie <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="b8822-111">The preferred way to do this is to use the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method.</span></span> <span data-ttu-id="b8822-112">Zadanie, które zostało anulowane w ten sposób, przechodzi do stanu Canceled, którego kod wywołujący może użyć do sprawdzenia, czy zadanie odpowiedziało na żądanie anulowania.</span><span class="sxs-lookup"><span data-stu-id="b8822-112">A task that is canceled in this way transitions to the Canceled state, which the calling code can use to verify that the task responded to its cancellation request.</span></span>  
  
 <span data-ttu-id="b8822-113">Poniższy przykład przedstawia podstawowy wzorzec anulowania zadania ze zgłoszeniem wyjątku.</span><span class="sxs-lookup"><span data-stu-id="b8822-113">The following example shows the basic pattern for task cancellation that throws the exception.</span></span> <span data-ttu-id="b8822-114">Należy zauważyć, że token jest przekazywany do pełnomocnika użytkownika i do samego wystąpienia zadania.</span><span class="sxs-lookup"><span data-stu-id="b8822-114">Note that the token is passed to the user delegate and to the task instance itself.</span></span>  
  
 [!code-csharp[TPL_Cancellation#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/snippet02.cs#02)]
 [!code-vb[TPL_Cancellation#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/module1.vb#02)]  
  
 <span data-ttu-id="b8822-115">Aby uzyskać bardziej szczegółowy przykład, zobacz [porady: anulowanie zadania i jego elementy podrzędne](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).</span><span class="sxs-lookup"><span data-stu-id="b8822-115">For a more complete example, see [How to: Cancel a Task and Its Children](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).</span></span>  
  
 <span data-ttu-id="b8822-116">Gdy wystąpienie zadania przestrzega <xref:System.OperationCanceledException> zgłoszone przez kod użytkownika, porównuje token wyjątek do jego skojarzony tokenu (jeden, który został przekazany do interfejsu API, który utworzył zadanie).</span><span class="sxs-lookup"><span data-stu-id="b8822-116">When a task instance observes an <xref:System.OperationCanceledException> thrown by user code, it compares the exception's token to its associated token (the one that was passed to the API that created the Task).</span></span> <span data-ttu-id="b8822-117">Jeśli są one takie same i tokenu <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> właściwość zwraca wartość true, interpretuje jako potwierdzeniem anulowania i przechodzi w stan Anulowane zadania.</span><span class="sxs-lookup"><span data-stu-id="b8822-117">If they are the same and the token's <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property returns true, the task interprets this as acknowledging cancellation and transitions to the Canceled state.</span></span> <span data-ttu-id="b8822-118">Jeśli nie używasz <xref:System.Threading.Tasks.Task.Wait%2A> lub <xref:System.Threading.Tasks.Task.WaitAll%2A> metody oczekiwania zadania, a następnie zadanie tylko ustawia jego stan na <xref:System.Threading.Tasks.TaskStatus.Canceled>.</span><span class="sxs-lookup"><span data-stu-id="b8822-118">If you do not use a <xref:System.Threading.Tasks.Task.Wait%2A> or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the task, then the task just sets its status to <xref:System.Threading.Tasks.TaskStatus.Canceled>.</span></span>  
  
 <span data-ttu-id="b8822-119">Jeśli są oczekiwanie na zadanie, które przechodzi w stan Anulowane <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> wyjątek (ujęte w <xref:System.AggregateException> wyjątek) zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="b8822-119">If you are waiting on a Task that transitions to the Canceled state, a <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> exception (wrapped in an <xref:System.AggregateException> exception) is thrown.</span></span> <span data-ttu-id="b8822-120">Należy zauważyć, że ten wyjątek wskazuje pomyślne anulowanie, a nie błędną sytuację.</span><span class="sxs-lookup"><span data-stu-id="b8822-120">Note that this exception indicates successful cancellation instead of a faulty situation.</span></span> <span data-ttu-id="b8822-121">W związku z tym zadania <xref:System.Threading.Tasks.Task.Exception%2A> zwraca właściwość `null`.</span><span class="sxs-lookup"><span data-stu-id="b8822-121">Therefore, the task's <xref:System.Threading.Tasks.Task.Exception%2A> property returns `null`.</span></span>  
  
 <span data-ttu-id="b8822-122">Jeśli token <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> właściwość zwraca wartość false lub token wyjątek niezgodny zadania obiektu tokenu, <xref:System.OperationCanceledException> jest traktowany jak normalne wyjątek, powodując zadań, aby przejść w stan końcowy: Faulted.</span><span class="sxs-lookup"><span data-stu-id="b8822-122">If the token's <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property returns false or if the exception's token does not match the Task's token, the <xref:System.OperationCanceledException> is treated like a normal exception, causing the Task to transition to the Faulted state.</span></span> <span data-ttu-id="b8822-123">Należy także zauważyć, że obecność innych wyjątków także spowoduje przejście zadania do stanu Faulted.</span><span class="sxs-lookup"><span data-stu-id="b8822-123">Also note that the presence of other exceptions will also cause the Task to transition to the Faulted state.</span></span> <span data-ttu-id="b8822-124">Można pobrać stanu ukończonego zadania w <xref:System.Threading.Tasks.Task.Status%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="b8822-124">You can get the status of the completed task in the <xref:System.Threading.Tasks.Task.Status%2A> property.</span></span>  
  
 <span data-ttu-id="b8822-125">Możliwe jest, że zadanie będzie kontynuować przetwarzanie niektórych elementy po żądania anulowania.</span><span class="sxs-lookup"><span data-stu-id="b8822-125">It is possible that a task may continue to process some items after cancellation is requested.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8822-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b8822-126">See Also</span></span>  
 [<span data-ttu-id="b8822-127">Anulowanie w zarządzanych wątkach</span><span class="sxs-lookup"><span data-stu-id="b8822-127">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 [<span data-ttu-id="b8822-128">Porady: anulowanie zadania i jego elementów podrzędnych</span><span class="sxs-lookup"><span data-stu-id="b8822-128">How to: Cancel a Task and Its Children</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)