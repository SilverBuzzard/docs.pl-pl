---
title: "Wątki i wątkowość"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework]
- threading [.NET Framework], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b57cac34009e13c27c6d34a0ab402f9ecbe08305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="threads-and-threading"></a><span data-ttu-id="e825a-102">Wątki i wątkowość</span><span class="sxs-lookup"><span data-stu-id="e825a-102">Threads and Threading</span></span>
<span data-ttu-id="e825a-103">Systemy operacyjne umożliwia rozdzielenie różnych aplikacji, które działają procesów.</span><span class="sxs-lookup"><span data-stu-id="e825a-103">Operating systems use processes to separate the different applications that they are executing.</span></span> <span data-ttu-id="e825a-104">Wątki są jednostkę podstawową, system operacyjny przydziela czas procesora i więcej niż jeden wątek może wykonywania kodu wewnątrz tego procesu.</span><span class="sxs-lookup"><span data-stu-id="e825a-104">Threads are the basic unit to which an operating system allocates processor time, and more than one thread can be executing code inside that process.</span></span> <span data-ttu-id="e825a-105">Każdy wątek obsługuje programy obsługi wyjątków, priorytet i zestaw struktur, które system używa zapisać kontekstu wątku, dopóki nie zostanie określony.</span><span class="sxs-lookup"><span data-stu-id="e825a-105">Each thread maintains exception handlers, a scheduling priority, and a set of structures the system uses to save the thread context until it is scheduled.</span></span> <span data-ttu-id="e825a-106">Kontekst wątku zawiera wszystkie informacje wymagane przez wątek do bezbłędnie wznowić wykonywanie wątku zestaw rejestrów Procesora i stosu, w tym do przestrzeni adresowej procesu hosta wątku.</span><span class="sxs-lookup"><span data-stu-id="e825a-106">The thread context includes all the information the thread needs to seamlessly resume execution, including the thread's set of CPU registers and stack, in the address space of the thread's host process.</span></span>  
  
 <span data-ttu-id="e825a-107">.NET Framework dalsze dzieli procesu systemu operacyjnego do lekkie zarządzanych, podprocesów określanych jako domeny aplikacji, reprezentowany przez <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e825a-107">The .NET Framework further subdivides an operating system process into lightweight managed subprocesses, called application domains, represented by <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e825a-108">Jeden lub więcej wątków zarządzanych (reprezentowane przez <xref:System.Threading.Thread?displayProperty=nameWithType>) można uruchomić w jednej lub kilku domen aplikacji w ramach tego samego procesu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="e825a-108">One or more managed threads (represented by <xref:System.Threading.Thread?displayProperty=nameWithType>) can run in one or any number of application domains within the same managed process.</span></span> <span data-ttu-id="e825a-109">Każda domena aplikacji została uruchomiona z jednym wątkiem, kodu w tej domenie aplikacji można utworzyć dodatkowe wątki i domen aplikacji dodatkowych.</span><span class="sxs-lookup"><span data-stu-id="e825a-109">Although each application domain is started with a single thread, code in that application domain can create additional application domains and additional threads.</span></span> <span data-ttu-id="e825a-110">Wynik jest, że zarządzanego wątku mogą swobodnie przemieszczać się między domenami aplikacji wewnątrz tego samego procesu zarządzanego; może istnieć tylko jeden wątek przenoszenia między kilka domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e825a-110">The result is that a managed thread can move freely between application domains inside the same managed process; you might have only one thread moving among several application domains.</span></span>  
  
 <span data-ttu-id="e825a-111">System operacyjny, który obsługuje cenią sobie wcześniejsze wielozadaniowości tworzy efekt jednoczesne wykonywanie wielu wątków na podstawie wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="e825a-111">An operating system that supports preemptive multitasking creates the effect of simultaneous execution of multiple threads from multiple processes.</span></span> <span data-ttu-id="e825a-112">Jest to możliwe dzięki podział czasu procesora dostępne między wątków, które go potrzebują, przydzielanie przedział czasu procesora, aby każdy wątek jeden po drugim.</span><span class="sxs-lookup"><span data-stu-id="e825a-112">It does this by dividing the available processor time among the threads that need it, allocating a processor time slice to each thread one after another.</span></span> <span data-ttu-id="e825a-113">Aktualnie wykonywane wątek jest zawieszony, gdy jej czas upływający wycinka i innego wątku wznawia uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="e825a-113">The currently executing thread is suspended when its time slice elapses, and another thread resumes running.</span></span> <span data-ttu-id="e825a-114">Przełączać się z jednego wątku do innego, go zapisuje kontekst wątku preempted wątku i ponowne załadowanie kontekście wątku zapisane następnego wątku w kolejce wątku.</span><span class="sxs-lookup"><span data-stu-id="e825a-114">When the system switches from one thread to another, it saves the thread context of the preempted thread and reloads the saved thread context of the next thread in the thread queue.</span></span>  
  
 <span data-ttu-id="e825a-115">Długość przedziału czasu zależy od systemu operacyjnego i procesora.</span><span class="sxs-lookup"><span data-stu-id="e825a-115">The length of the time slice depends on the operating system and the processor.</span></span> <span data-ttu-id="e825a-116">Ponieważ każdy przedział czasu jest mały, wiele wątków ma być wykonywane jednocześnie, nawet jeśli dostępny jest tylko jeden procesor.</span><span class="sxs-lookup"><span data-stu-id="e825a-116">Because each time slice is small, multiple threads appear to be executing at the same time, even if there is only one processor.</span></span> <span data-ttu-id="e825a-117">Jest rzeczywiście w systemach wieloprocesorowych, które wykonywalnego wątki są dystrybuowane między dostępnych procesorów.</span><span class="sxs-lookup"><span data-stu-id="e825a-117">This is actually the case on multiprocessor systems, where the executable threads are distributed among the available processors.</span></span>  
  
## <a name="when-to-use-multiple-threads"></a><span data-ttu-id="e825a-118">Kiedy należy używać wiele wątków</span><span class="sxs-lookup"><span data-stu-id="e825a-118">When To Use Multiple Threads</span></span>  
 <span data-ttu-id="e825a-119">Oprogramowanie, które wymaga interakcji użytkownika musi reagować na działania użytkownika tak szybko jak to możliwe, aby zapewnić użyciu zaawansowanego środowiska użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e825a-119">Software that requires user interaction must react to the user's activities as rapidly as possible to provide a rich user experience.</span></span> <span data-ttu-id="e825a-120">W tym samym czasie jednak należy ją wykonać obliczeń niezbędnych do przedstawienia danych użytkownika tak szybko, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="e825a-120">At the same time, however, it must do the calculations necessary to present data to the user as fast as possible.</span></span> <span data-ttu-id="e825a-121">Jeśli aplikacja używa tylko jeden wątek, można połączyć [programowanie asynchroniczne](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) z[.NET Framework remoting](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) lub [usług XML sieci Web](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c) utworzone za pomocą ASP .NET na potrzeby czas przetwarzania innych komputerów dodatkowo z własnych zwiększenie czasu odpowiedzi użytkownika i zmniejsza czas przetwarzania danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e825a-121">If your application uses only one thread of execution, you can combine [asynchronous programming](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) with[.NET Framework remoting](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) or [XML Web services](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c) created using ASP.NET to use the processing time of other computers in addition to that of your own to increase responsiveness to the user and decrease the data processing time of your application.</span></span> <span data-ttu-id="e825a-122">Jeśli przeprowadzasz znacznym pracy wejścia/wyjścia, można zwiększyć czas odpowiedzi aplikacji w portów We/Wy.</span><span class="sxs-lookup"><span data-stu-id="e825a-122">If you are doing intensive input/output work, you can also use I/O completion ports to increase your application's responsiveness.</span></span>  
  
### <a name="advantages-of-multiple-threads"></a><span data-ttu-id="e825a-123">Zalety wiele wątków</span><span class="sxs-lookup"><span data-stu-id="e825a-123">Advantages of Multiple Threads</span></span>  
 <span data-ttu-id="e825a-124">Jednak przy użyciu więcej niż jeden wątek, jest najbardziej zaawansowanych technik, można zwiększyć czas odpowiedzi dla użytkownika i przetwarzania danych, które są niezbędne, aby uzyskać zadanie wykonywane w niemal tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="e825a-124">Using more than one thread, however, is the most powerful technique available to increase responsiveness to the user and process the data necessary to get the job done at almost the same time.</span></span> <span data-ttu-id="e825a-125">Na komputerze z jednym procesorem wiele wątków można utworzyć ten efekt, wykorzystaniu małych okresów Between zdarzeń użytkownika do przetwarzania danych w tle.</span><span class="sxs-lookup"><span data-stu-id="e825a-125">On a computer with one processor, multiple threads can create this effect, taking advantage of the small periods of time in between user events to process the data in the background.</span></span> <span data-ttu-id="e825a-126">Na przykład użytkownik może edytować arkusza kalkulacyjnego, podczas gdy inny wątek jest ponowne obliczanie inne części arkusza kalkulacyjnego w tej samej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e825a-126">For example, a user can edit a spreadsheet while another thread is recalculating other parts of the spreadsheet within the same application.</span></span>  
  
 <span data-ttu-id="e825a-127">Bez żadnych modyfikacji ta sama aplikacja będzie znacznie zwiększyć komfort użytkowników uruchamianych na komputerze z więcej niż jeden procesor.</span><span class="sxs-lookup"><span data-stu-id="e825a-127">Without modification, the same application would dramatically increase user satisfaction when run on a computer with more than one processor.</span></span> <span data-ttu-id="e825a-128">Domeny pojedynczej aplikacji można użyć wielu wątków można wykonywać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="e825a-128">Your single application domain could use multiple threads to accomplish the following tasks:</span></span>  
  
-   <span data-ttu-id="e825a-129">Komunikacji za pośrednictwem sieci do serwera sieci Web i bazę danych.</span><span class="sxs-lookup"><span data-stu-id="e825a-129">Communicate over a network, to a Web server, and to a database.</span></span>  
  
-   <span data-ttu-id="e825a-130">Wykonywanie operacji, które zająć dużo czasu.</span><span class="sxs-lookup"><span data-stu-id="e825a-130">Perform operations that take a large amount of time.</span></span>  
  
-   <span data-ttu-id="e825a-131">Odróżnić zadania różnych priorytetów.</span><span class="sxs-lookup"><span data-stu-id="e825a-131">Distinguish tasks of varying priority.</span></span> <span data-ttu-id="e825a-132">Na przykład wątku o wysokim priorytecie zarządza wrażliwego na czas zadania i niskiego priorytetu wątku wykonuje inne zadania.</span><span class="sxs-lookup"><span data-stu-id="e825a-132">For example, a high-priority thread manages time-critical tasks, and a low-priority thread performs other tasks.</span></span>  
  
-   <span data-ttu-id="e825a-133">Zezwalaj na interfejsie użytkownika będzie odpowiadać, podczas przydzielania czasu na zadania w tle.</span><span class="sxs-lookup"><span data-stu-id="e825a-133">Allow the user interface to remain responsive, while allocating time to background tasks.</span></span>  
  
### <a name="disadvantages-of-multiple-threads"></a><span data-ttu-id="e825a-134">Wady wiele wątków</span><span class="sxs-lookup"><span data-stu-id="e825a-134">Disadvantages of Multiple Threads</span></span>  
 <span data-ttu-id="e825a-135">Zaleca się używać jak najmniejszej liczby wątków jak to możliwe, a tym samym minimalizując użycie zasobów systemu operacyjnego i poprawia wydajność.</span><span class="sxs-lookup"><span data-stu-id="e825a-135">It is recommended that you use as few threads as possible, thereby minimizing the use of operating-system resources and improving performance.</span></span> <span data-ttu-id="e825a-136">Wątkowość ma również wymagania dotyczące zasobów i potencjalnych konfliktów wziąć pod uwagę podczas projektowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e825a-136">Threading also has resource requirements and potential conflicts to be considered when designing your application.</span></span> <span data-ttu-id="e825a-137">Wymagania dotyczące zasobów są następujące:</span><span class="sxs-lookup"><span data-stu-id="e825a-137">The resource requirements are as follows:</span></span>  
  
-   <span data-ttu-id="e825a-138">System zajmują pamięć dla wymaganych przez procesy, informacje o kontekście **elementu AppDomain** obiektów i wątków.</span><span class="sxs-lookup"><span data-stu-id="e825a-138">The system consumes memory for the context information required by processes, **AppDomain** objects, and threads.</span></span> <span data-ttu-id="e825a-139">W związku z tym liczba procesów, **elementu AppDomain** obiektów i wątków, które mogą być tworzone jest ograniczone przez ilość dostępnej pamięci.</span><span class="sxs-lookup"><span data-stu-id="e825a-139">Therefore, the number of processes, **AppDomain** objects, and threads that can be created is limited by available memory.</span></span>  
  
-   <span data-ttu-id="e825a-140">Rejestrowanie informacji o dużej liczby wątków zużywa czas procesora znaczące.</span><span class="sxs-lookup"><span data-stu-id="e825a-140">Keeping track of a large number of threads consumes significant processor time.</span></span> <span data-ttu-id="e825a-141">Jeśli ma zbyt wiele wątków, większość z nich nie dokona znaczącego postępu.</span><span class="sxs-lookup"><span data-stu-id="e825a-141">If there are too many threads, most of them will not make significant progress.</span></span> <span data-ttu-id="e825a-142">W przypadku większości aktualna liczba wątków w jeden proces, rzadziej zaplanowane wątków w innych procesów.</span><span class="sxs-lookup"><span data-stu-id="e825a-142">If most of the current threads are in one process, threads in other processes are scheduled less frequently.</span></span>  
  
-   <span data-ttu-id="e825a-143">Kontrolowanie wykonanie kodu z wielu wątków jest złożony i może być źródłem wiele błędów.</span><span class="sxs-lookup"><span data-stu-id="e825a-143">Controlling code execution with many threads is complex, and can be a source of many bugs.</span></span>  
  
-   <span data-ttu-id="e825a-144">Niszczenie wątków wymaga uprzedniego uzyskania informacji o to, co może się zdarzyć i obsługi tych problemów.</span><span class="sxs-lookup"><span data-stu-id="e825a-144">Destroying threads requires knowing what could happen and handling those issues.</span></span>  
  
 <span data-ttu-id="e825a-145">Zapewnianie współdzielonym dostępem do zasobów mogą powodować konflikty.</span><span class="sxs-lookup"><span data-stu-id="e825a-145">Providing shared access to resources can create conflicts.</span></span> <span data-ttu-id="e825a-146">Aby uniknąć konfliktów, możesz zsynchronizować lub kontrolować dostęp do zasobów udostępnionych.</span><span class="sxs-lookup"><span data-stu-id="e825a-146">To avoid conflicts, you must synchronize, or control the access to, shared resources.</span></span> <span data-ttu-id="e825a-147">Synchronizujący dostęp prawidłowo (w domenach aplikacji tego samego lub innego) może doprowadzić do problemów, takich jak zakleszczenie (w których dwoma wątkami przestaje odpowiadać podczas każdego oczekiwania przez drugą do ukończenia) i zastępować warunkami (jeśli jest to wynik nietypowych występuje z powodu Nieoczekiwany krytyczne zależności od chronometrażu dwóch zdarzeń).</span><span class="sxs-lookup"><span data-stu-id="e825a-147">Failure to synchronize access properly (in the same or different application domains) can lead to problems such as deadlocks (in which two threads stop responding while each waits for the other to complete) and race conditions (when an anomalous result occurs due to an unexpected critical dependence on the timing of two events).</span></span> <span data-ttu-id="e825a-148">System udostępnia obiekty synchronizacji, które mogą służyć do zapewnienia koordynacji zasobów, udostępnianie między wiele wątków.</span><span class="sxs-lookup"><span data-stu-id="e825a-148">The system provides synchronization objects that can be used to coordinate resource sharing among multiple threads.</span></span> <span data-ttu-id="e825a-149">Zmniejszenie liczby wątków ułatwia synchronizacji zasobów.</span><span class="sxs-lookup"><span data-stu-id="e825a-149">Reducing the number of threads makes it easier to synchronize resources.</span></span>  
  
 <span data-ttu-id="e825a-150">Zasoby, które wymagają synchronizacji obejmują:</span><span class="sxs-lookup"><span data-stu-id="e825a-150">Resources that require synchronization include:</span></span>  
  
-   <span data-ttu-id="e825a-151">Zasoby systemowe (na przykład portów komunikacji).</span><span class="sxs-lookup"><span data-stu-id="e825a-151">System resources (such as communications ports).</span></span>  
  
-   <span data-ttu-id="e825a-152">Zasoby współużytkowane przez wiele procesów (np. dojścia do plików).</span><span class="sxs-lookup"><span data-stu-id="e825a-152">Resources shared by multiple processes (such as file handles).</span></span>  
  
-   <span data-ttu-id="e825a-153">Zasoby aplikacji jednej domeny (np. static globalnych, wystąpienie pola) dostęp wiele wątków.</span><span class="sxs-lookup"><span data-stu-id="e825a-153">The resources of a single application domain (such as global, static, and instance fields) accessed by multiple threads.</span></span>  
  
### <a name="threading-and-application-design"></a><span data-ttu-id="e825a-154">Projekt wątków i aplikacji</span><span class="sxs-lookup"><span data-stu-id="e825a-154">Threading and Application Design</span></span>  
 <span data-ttu-id="e825a-155">Ogólnie rzecz biorąc, przy użyciu <xref:System.Threading.ThreadPool> klasy jest najprostszym sposobem obsługi wielu wątków stosunkowo krótkich zadań nieblokowanych innych wątków i gdy nie oczekuje żadnych określonego harmonogramu zadań.</span><span class="sxs-lookup"><span data-stu-id="e825a-155">In general, using the <xref:System.Threading.ThreadPool> class is the easiest way to handle multiple threads for relatively short tasks that will not block other threads and when you do not expect any particular scheduling of the tasks.</span></span> <span data-ttu-id="e825a-156">Jednak istnieje wiele powodów do tworzenia własnych wątków:</span><span class="sxs-lookup"><span data-stu-id="e825a-156">However, there are a number of reasons to create your own threads:</span></span>  
  
-   <span data-ttu-id="e825a-157">Jeśli potrzebujesz zadania określonego priorytetem.</span><span class="sxs-lookup"><span data-stu-id="e825a-157">If you need a task to have a particular priority.</span></span>  
  
-   <span data-ttu-id="e825a-158">Jeśli zadanie, które może być długi czas wykonywania (i w związku z tym zablokować inne zadania).</span><span class="sxs-lookup"><span data-stu-id="e825a-158">If you have a task that might run a long time (and therefore block other tasks).</span></span>  
  
-   <span data-ttu-id="e825a-159">Jeśli musisz umieścić wątków w jednowątkowym trybie apartment (wszystkie **puli wątków** wątki są wielowątkowe apartamentu).</span><span class="sxs-lookup"><span data-stu-id="e825a-159">If you need to place threads into a single-threaded apartment (all **ThreadPool** threads are in the multithreaded apartment).</span></span>  
  
-   <span data-ttu-id="e825a-160">Jeśli potrzebujesz stabilna tożsamości, skojarzony z wątkiem.</span><span class="sxs-lookup"><span data-stu-id="e825a-160">If you need a stable identity associated with the thread.</span></span> <span data-ttu-id="e825a-161">Na przykład należy użyć dedykowanego wątku przerwać wątek, wstrzymanie go lub go odnaleźć według nazwy.</span><span class="sxs-lookup"><span data-stu-id="e825a-161">For example, you should use a dedicated thread to abort that thread, suspend it, or discover it by name.</span></span>  
  
-   <span data-ttu-id="e825a-162">Jeśli musisz uruchomić wątki w tle, które współdziałają z interfejsem użytkownika, .NET Framework w wersji 2.0 zapewnia <xref:System.ComponentModel.BackgroundWorker> składnika, który komunikuje się za pomocą zdarzeń, z między wątkami przekazywanie do wątku interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e825a-162">If you need to run background threads that interact with the user interface, the .NET Framework version 2.0 provides a <xref:System.ComponentModel.BackgroundWorker> component that communicates using events, with cross-thread marshaling to the user-interface thread.</span></span>  
  
### <a name="threading-and-exceptions"></a><span data-ttu-id="e825a-163">Wątki i wyjątków</span><span class="sxs-lookup"><span data-stu-id="e825a-163">Threading and Exceptions</span></span>  
 <span data-ttu-id="e825a-164">Obsługa wyjątków w wątkach.</span><span class="sxs-lookup"><span data-stu-id="e825a-164">Do handle exceptions in threads.</span></span> <span data-ttu-id="e825a-165">Nieobsługiwane wyjątki w wątkach, wątki w tle nawet, zazwyczaj zakończenie procesu.</span><span class="sxs-lookup"><span data-stu-id="e825a-165">Unhandled exceptions in threads, even background threads, generally terminate the process.</span></span> <span data-ttu-id="e825a-166">Istnieją trzy wyjątki od tej reguły:</span><span class="sxs-lookup"><span data-stu-id="e825a-166">There are three exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="e825a-167">A <xref:System.Threading.ThreadAbortException> wyjątek w wątku, ponieważ <xref:System.Threading.Thread.Abort%2A> została wywołana.</span><span class="sxs-lookup"><span data-stu-id="e825a-167">A <xref:System.Threading.ThreadAbortException> is thrown in a thread because <xref:System.Threading.Thread.Abort%2A> was called.</span></span>  
  
-   <span data-ttu-id="e825a-168"><xref:System.AppDomainUnloadedException> Jest zgłaszany w wątku, ponieważ Trwa zwalnianie domen aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e825a-168">An <xref:System.AppDomainUnloadedException> is thrown in a thread because the application domain is being unloaded.</span></span>  
  
-   <span data-ttu-id="e825a-169">Środowisko uruchomieniowe języka wspólnego lub procesu hosta kończy wątku.</span><span class="sxs-lookup"><span data-stu-id="e825a-169">The common language runtime or a host process terminates the thread.</span></span>  
  
 <span data-ttu-id="e825a-170">Aby uzyskać więcej informacji, zobacz [wyjątki w zarządzanych wątkach](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="e825a-170">For more information, see [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e825a-171">W wersji systemu .NET Framework 1.0 i 1.1 środowisko uruchomieniowe języka wspólnego dyskretnie traps niektóre wyjątki, na przykład w wątku puli wątków.</span><span class="sxs-lookup"><span data-stu-id="e825a-171">In the .NET Framework versions 1.0 and 1.1, the common language runtime silently traps some exceptions, for example in thread pool threads.</span></span> <span data-ttu-id="e825a-172">Może to doprowadzić do uszkodzenia aplikacji i może spowodować zawieszenie, aplikacje, które mogą być bardzo trudne do debugowania.</span><span class="sxs-lookup"><span data-stu-id="e825a-172">This may corrupt application state and eventually cause applications to hang, which might be very difficult to debug.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e825a-173">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e825a-173">See Also</span></span>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [<span data-ttu-id="e825a-174">Synchronizowanie danych na potrzeby wielowątkowości</span><span class="sxs-lookup"><span data-stu-id="e825a-174">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [<span data-ttu-id="e825a-175">Zarządzana Pula wątków</span><span class="sxs-lookup"><span data-stu-id="e825a-175">The Managed Thread Pool</span></span>](../../../docs/standard/threading/the-managed-thread-pool.md)