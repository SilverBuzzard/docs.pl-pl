---
title: "Sesje, tworzenie wystąpień i współbieżność"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50797a3b-7678-44ed-8138-49ac1602f35b
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f188bc85ae3c2601e98ad29b275c6bb8b698522f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="sessions-instancing-and-concurrency"></a><span data-ttu-id="ae541-102">Sesje, tworzenie wystąpień i współbieżność</span><span class="sxs-lookup"><span data-stu-id="ae541-102">Sessions, Instancing, and Concurrency</span></span>
<span data-ttu-id="ae541-103">A *sesji* jest korelacji wszystkich wiadomości wysłanych między dwoma punktami końcowymi.</span><span class="sxs-lookup"><span data-stu-id="ae541-103">A *session* is a correlation of all messages sent between two endpoints.</span></span> <span data-ttu-id="ae541-104">*Tworzenie wystąpienia* odwołuje się do kontrolowania okres istnienia obiektów zdefiniowanych przez użytkownika usług i ich powiązane <xref:System.ServiceModel.InstanceContext> obiektów.</span><span class="sxs-lookup"><span data-stu-id="ae541-104">*Instancing* refers to controlling the lifetime of user-defined service objects and their related <xref:System.ServiceModel.InstanceContext> objects.</span></span> <span data-ttu-id="ae541-105">*Współbieżność* jest terminu podanego do formantu liczbę wątków działających w <xref:System.ServiceModel.InstanceContext> w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="ae541-105">*Concurrency* is the term given to the control of the number of threads executing in an <xref:System.ServiceModel.InstanceContext> at the same time.</span></span>  
  
 <span data-ttu-id="ae541-106">W tym temacie opisano te ustawienia, jak używać i różnych interakcje między nimi.</span><span class="sxs-lookup"><span data-stu-id="ae541-106">This topic describes these settings, how to use them, and the various interactions between them.</span></span>  
  
## <a name="sessions"></a><span data-ttu-id="ae541-107">Kategoria Sessions</span><span class="sxs-lookup"><span data-stu-id="ae541-107">Sessions</span></span>  
 <span data-ttu-id="ae541-108">Gdy kontrakt usługi Określa <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> właściwości <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, że kontrakt jest informujący o tym, że wszystkie wywołania (to znaczy podstawowej wymiany komunikatów obsługujących wywołania) musi być częścią ta sama konwersacja.</span><span class="sxs-lookup"><span data-stu-id="ae541-108">When a service contract sets the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, that contract is saying that all calls (that is, the underlying message exchanges that support the calls) must be part of the same conversation.</span></span> <span data-ttu-id="ae541-109">Jeśli kontrakt Określa czy umożliwia sesji, ale nie wymaga jednego, mogą łączyć się klienci, a albo ustanowić sesję, czy nie.</span><span class="sxs-lookup"><span data-stu-id="ae541-109">If a contract specifies that it allows sessions but does not require one, clients can connect and either establish a session or not.</span></span> <span data-ttu-id="ae541-110">Jeśli sesja zakończy się oraz wiadomości przesyłane z tego samego opartymi na sesji jest zgłaszany wyjątek kanału.</span><span class="sxs-lookup"><span data-stu-id="ae541-110">If the session ends and a message is sent over the same session-based channel an exception is thrown.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ae541-111">sesje mają następujące funkcje koncepcyjnej główne:</span><span class="sxs-lookup"><span data-stu-id="ae541-111"> sessions have the following main conceptual features:</span></span>  
  
-   <span data-ttu-id="ae541-112">Jawnie są inicjowane i został przerwany przez wywołanie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ae541-112">They are explicitly initiated and terminated by the calling application.</span></span>  
  
-   <span data-ttu-id="ae541-113">Komunikaty dostarczone podczas sesji są przetwarzane w kolejności, w którym są odbierane.</span><span class="sxs-lookup"><span data-stu-id="ae541-113">Messages delivered during a session are processed in the order in which they are received.</span></span>  
  
-   <span data-ttu-id="ae541-114">Sesje skorelowania grupy wiadomości w konwersacji.</span><span class="sxs-lookup"><span data-stu-id="ae541-114">Sessions correlate a group of messages into a conversation.</span></span> <span data-ttu-id="ae541-115">Znaczenie tej korelacji jest klasą abstrakcyjną.</span><span class="sxs-lookup"><span data-stu-id="ae541-115">The meaning of that correlation is an abstraction.</span></span> <span data-ttu-id="ae541-116">Na przykład jeden kanał opartymi na sesji mogą mieć związek wiadomości opartych na połączenie sieciowe udostępnionych podczas innego opartymi na sesji kanału może skorelować wiadomości opartych na udostępnionych tagu w treści wiadomości.</span><span class="sxs-lookup"><span data-stu-id="ae541-116">For instance, one session-based channel may correlate messages based on a shared network connection while another session-based channel may correlate messages based on a shared tag in the message body.</span></span> <span data-ttu-id="ae541-117">Funkcje, które mogą być uzyskane z sesji są zależne od charakteru korelacji.</span><span class="sxs-lookup"><span data-stu-id="ae541-117">The features that can be derived from the session depend on the nature of the correlation.</span></span>  
  
-   <span data-ttu-id="ae541-118">Brak ma skojarzone z magazynu danych ogólnych [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sesji.</span><span class="sxs-lookup"><span data-stu-id="ae541-118">There is no general data store associated with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] session.</span></span>  
  
 <span data-ttu-id="ae541-119">Jeśli znasz <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> klasy w [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplikacji i funkcji umożliwia, można zauważyć następujące różnice między tego rodzaju sesji i [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sesji:</span><span class="sxs-lookup"><span data-stu-id="ae541-119">If you are familiar with the <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> class in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] applications and the functionality it provides, you might notice the following differences between that kind of session and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sessions:</span></span>  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="ae541-120">sesje są zawsze inicjowanych przez serwer.</span><span class="sxs-lookup"><span data-stu-id="ae541-120"> sessions are always server-initiated.</span></span>  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="ae541-121">sesje są niejawnie nieuporządkowaną.</span><span class="sxs-lookup"><span data-stu-id="ae541-121"> sessions are implicitly unordered.</span></span>  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="ae541-122">sesje udostępniają mechanizm magazynu danych ogólnych żądań.</span><span class="sxs-lookup"><span data-stu-id="ae541-122"> sessions provide a general data storage mechanism across requests.</span></span>  
  
 <span data-ttu-id="ae541-123">Aplikacje klienckie i aplikacje usług interakcji z sesji na różne sposoby.</span><span class="sxs-lookup"><span data-stu-id="ae541-123">Client applications and service applications interact with sessions in different ways.</span></span> <span data-ttu-id="ae541-124">Aplikacje klienckie zainicjować sesji i następnie odbierania i przetwarzania wiadomości wysyłane w ramach sesji.</span><span class="sxs-lookup"><span data-stu-id="ae541-124">Client applications initiate sessions and then receive and process the messages sent within the session.</span></span> <span data-ttu-id="ae541-125">Aplikacje usługi mogą używać sesji jako punkt rozszerzeń można dodać dodatkowe zachowanie.</span><span class="sxs-lookup"><span data-stu-id="ae541-125">Service applications can use sessions as an extensibility point to add additional behavior.</span></span> <span data-ttu-id="ae541-126">W tym celu praca bezpośrednio z <xref:System.ServiceModel.InstanceContext> lub implementowanie dostawcy kontekstu niestandardowego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="ae541-126">This is done by working directly with the <xref:System.ServiceModel.InstanceContext> or implementing a custom instance context provider.</span></span>  
  
## <a name="instancing"></a><span data-ttu-id="ae541-127">Tworzenie wystąpienia</span><span class="sxs-lookup"><span data-stu-id="ae541-127">Instancing</span></span>  
 <span data-ttu-id="ae541-128">Zachowanie wystąpień (skonfigurowane za pomocą <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> właściwości) kontrolki jak <xref:System.ServiceModel.InstanceContext> jest tworzony w odpowiedzi na wiadomości przychodzących.</span><span class="sxs-lookup"><span data-stu-id="ae541-128">The instancing behavior (set by using the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> property) controls how the <xref:System.ServiceModel.InstanceContext> is created in response to incoming messages.</span></span> <span data-ttu-id="ae541-129">Domyślnie każdy <xref:System.ServiceModel.InstanceContext> jest skojarzony z jednego obiektu usługi zdefiniowane przez użytkownika, tak (w przypadku domyślnego) ustawienie <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> właściwość również określa wystąpień obiektów zdefiniowanych przez użytkownika usługi.</span><span class="sxs-lookup"><span data-stu-id="ae541-129">By default, each <xref:System.ServiceModel.InstanceContext> is associated with one user-defined service object, so (in the default case) setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property also controls the instancing of user-defined service objects.</span></span> <span data-ttu-id="ae541-130"><xref:System.ServiceModel.InstanceContextMode> Wyliczenie definiuje tryb wystąpień.</span><span class="sxs-lookup"><span data-stu-id="ae541-130">The <xref:System.ServiceModel.InstanceContextMode> enumeration defines the instancing modes.</span></span>  
  
 <span data-ttu-id="ae541-131">Dostępne są następujące tryby wystąpień:</span><span class="sxs-lookup"><span data-stu-id="ae541-131">The following instancing modes are available:</span></span>  
  
-   <span data-ttu-id="ae541-132"><xref:System.ServiceModel.InstanceContextMode.PerCall>: Nowy <xref:System.ServiceModel.InstanceContext> (i w związku z tym usługa obiektu) jest tworzony dla każdego żądania klienta.</span><span class="sxs-lookup"><span data-stu-id="ae541-132"><xref:System.ServiceModel.InstanceContextMode.PerCall>: A new <xref:System.ServiceModel.InstanceContext> (and therefore service object) is created for each client request.</span></span>  
  
-   <span data-ttu-id="ae541-133"><xref:System.ServiceModel.InstanceContextMode.PerSession>: Nowy <xref:System.ServiceModel.InstanceContext> (i w związku z tym usługa obiektu) jest tworzone dla każdej nowej sesji klienta i przechowywane przez czas ich istnienia sesji (wymaga powiązania, które obsługuje sesji).</span><span class="sxs-lookup"><span data-stu-id="ae541-133"><xref:System.ServiceModel.InstanceContextMode.PerSession>: A new <xref:System.ServiceModel.InstanceContext> (and therefore service object) is created for each new client session and maintained for the lifetime of that session (this requires a binding that supports sessions).</span></span>  
  
-   <span data-ttu-id="ae541-134"><xref:System.ServiceModel.InstanceContextMode.Single>: Jeden <xref:System.ServiceModel.InstanceContext> (i w związku z tym usługa obiektu) obsługuje wszystkie żądania klienta przez czas ich istnienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ae541-134"><xref:System.ServiceModel.InstanceContextMode.Single>: A single <xref:System.ServiceModel.InstanceContext> (and therefore service object) handles all client requests for the lifetime of the application.</span></span>  
  
 <span data-ttu-id="ae541-135">Poniższy przykład kodu pokazuje domyślne <xref:System.ServiceModel.InstanceContextMode> wartość <xref:System.ServiceModel.InstanceContextMode.PerSession> jawnie ustawiania klasy usługi.</span><span class="sxs-lookup"><span data-stu-id="ae541-135">The following code example shows the default <xref:System.ServiceModel.InstanceContextMode> value, <xref:System.ServiceModel.InstanceContextMode.PerSession> being explicitly set on a service class.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]   
public class CalculatorService : ICalculatorInstance   
{   
    ...  
}  
```  
  
 <span data-ttu-id="ae541-136">I podczas <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> właściwość określa, jak często <xref:System.ServiceModel.InstanceContext> wydaniu <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> i <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> właściwości formantu, kiedy zwolniony jest obiekt usługi.</span><span class="sxs-lookup"><span data-stu-id="ae541-136">And while the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> property controls how often the <xref:System.ServiceModel.InstanceContext> is released, the <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> properties control when the service object is released.</span></span>  
  
### <a name="well-known-singleton-services"></a><span data-ttu-id="ae541-137">Dobrze znanego pojedynczego wystąpienia usług</span><span class="sxs-lookup"><span data-stu-id="ae541-137">Well-Known Singleton Services</span></span>  
 <span data-ttu-id="ae541-138">Czasami jest przydatne jedną odmianę obiektów usługi SIS: można utworzyć obiektu usługi samodzielnie i Utwórz hosta usługi przy użyciu tego obiektu.</span><span class="sxs-lookup"><span data-stu-id="ae541-138">One variation on single instance service objects is sometimes useful: you can create a service object yourself and create the service host using that object.</span></span> <span data-ttu-id="ae541-139">Aby to zrobić, należy także ustawić <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> właściwości <xref:System.ServiceModel.InstanceContextMode.Single> lub jest zgłaszany wyjątek, po otwarciu hosta usługi.</span><span class="sxs-lookup"><span data-stu-id="ae541-139">To do so, you must also set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.InstanceContextMode.Single> or an exception is thrown when the service host is opened.</span></span>  
  
 <span data-ttu-id="ae541-140">Użyj <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=nameWithType> konstruktora w celu utworzenia takiej usługi.</span><span class="sxs-lookup"><span data-stu-id="ae541-140">Use the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=nameWithType> constructor to create such a service.</span></span> <span data-ttu-id="ae541-141">Zapewnia alternatywę do wdrażania niestandardowego <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> po możesz podać wystąpienie określonego obiektu do użytku przez usługi singleton.</span><span class="sxs-lookup"><span data-stu-id="ae541-141">It provides an alternative to implementing a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> when you wish to provide a specific object instance for use by a singleton service.</span></span> <span data-ttu-id="ae541-142">Można użyć tego przeciążenia, gdy Twoje typ implementacji usługi jest trudne do skonstruowania (na przykład, jeśli nie implementuje domyślnego publicznego konstruktora bez parametrów).</span><span class="sxs-lookup"><span data-stu-id="ae541-142">You can use this overload when your service implementation type is difficult to construct (for example, if it does not implement a default parameterless public constructor).</span></span>  
  
 <span data-ttu-id="ae541-143">Należy pamiętać, że jeśli obiekt został dostarczony do tego konstruktora, niektóre funkcje jest powiązany z [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] inaczej wystąpień pracy zachowanie.</span><span class="sxs-lookup"><span data-stu-id="ae541-143">Note that when an object is provided to this constructor, some features related to the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] instancing behavior work differently.</span></span> <span data-ttu-id="ae541-144">Na przykład wywołanie elementu <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> nie obowiązuje, gdy została podana pojedyncze wystąpienie obiektu.</span><span class="sxs-lookup"><span data-stu-id="ae541-144">For example, calling <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> has no effect when a singleton object instance is provided.</span></span> <span data-ttu-id="ae541-145">Podobnie inny mechanizm wersji wystąpienia jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="ae541-145">Similarly, any other instance-release mechanism is ignored.</span></span> <span data-ttu-id="ae541-146"><xref:System.ServiceModel.ServiceHost> Zawsze zachowuje się tak, jakby <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> ma ustawioną wartość właściwości <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> dla wszystkich operacji.</span><span class="sxs-lookup"><span data-stu-id="ae541-146">The <xref:System.ServiceModel.ServiceHost> always behaves as if the <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> property is set to <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> for all operations.</span></span>  
  
### <a name="sharing-instancecontext-objects"></a><span data-ttu-id="ae541-147">Udostępnianie obiektów InstanceContext</span><span class="sxs-lookup"><span data-stu-id="ae541-147">Sharing InstanceContext Objects</span></span>  
 <span data-ttu-id="ae541-148">Można również sterować które podczas zamykania kanału sesji lub połączenia jest skojarzony z którym <xref:System.ServiceModel.InstanceContext> obiektu przez siebie wykonanie tego skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="ae541-148">You can also control which sessionful channel or call is associated with which <xref:System.ServiceModel.InstanceContext> object by performing that association yourself.</span></span>  
  
## <a name="concurrency"></a><span data-ttu-id="ae541-149">Współbieżność</span><span class="sxs-lookup"><span data-stu-id="ae541-149">Concurrency</span></span>  
 <span data-ttu-id="ae541-150">Współbieżność jest formant liczbę wątków, które są aktywne w <xref:System.ServiceModel.InstanceContext> w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="ae541-150">Concurrency is the control of the number of threads active in an <xref:System.ServiceModel.InstanceContext> at any one time.</span></span> <span data-ttu-id="ae541-151">To jest kontrolowany za pomocą <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> z <xref:System.ServiceModel.ConcurrencyMode> wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="ae541-151">This is controlled by using the <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> with the <xref:System.ServiceModel.ConcurrencyMode> enumeration.</span></span>  
  
 <span data-ttu-id="ae541-152">Dostępne są następujące trzy tryby współbieżności:</span><span class="sxs-lookup"><span data-stu-id="ae541-152">The following three concurrency modes are available:</span></span>  
  
-   <span data-ttu-id="ae541-153"><xref:System.ServiceModel.ConcurrencyMode.Single>: Każdy kontekst wystąpienia może zawierać maksymalnie jeden wątek przetwarzania komunikatów w kontekście wystąpienia naraz.</span><span class="sxs-lookup"><span data-stu-id="ae541-153"><xref:System.ServiceModel.ConcurrencyMode.Single>: Each instance context is allowed to have a maximum of one thread processing messages in the instance context at a time.</span></span> <span data-ttu-id="ae541-154">Inne wątki chcą używać tego samego wystąpienia kontekstu zablokować aż do oryginalnego wątku opuszcza kontekstu wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="ae541-154">Other threads wishing to use the same instance context must block until the original thread exits the instance context.</span></span>  
  
-   <span data-ttu-id="ae541-155"><xref:System.ServiceModel.ConcurrencyMode.Multiple>: Każde wystąpienie usługi może mieć wiele wątków jednocześnie przetwarzanie komunikatów.</span><span class="sxs-lookup"><span data-stu-id="ae541-155"><xref:System.ServiceModel.ConcurrencyMode.Multiple>: Each service instance can have multiple threads processing messages concurrently.</span></span> <span data-ttu-id="ae541-156">Implementacja usługi musi być wielowątkowość ten tryb współbieżności.</span><span class="sxs-lookup"><span data-stu-id="ae541-156">The service implementation must be thread-safe to use this concurrency mode.</span></span>  
  
-   <span data-ttu-id="ae541-157"><xref:System.ServiceModel.ConcurrencyMode.Reentrant>: Każde wystąpienie usługi przetwarza jeden komunikat w czasie, ale akceptuje wywołań wielobieżnej operacji.</span><span class="sxs-lookup"><span data-stu-id="ae541-157"><xref:System.ServiceModel.ConcurrencyMode.Reentrant>: Each service instance processes one message at a time, but accepts re-entrant operation calls.</span></span> <span data-ttu-id="ae541-158">Usługa akceptuje tylko te wywołania, gdy wywołuje za pośrednictwem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] obiektu klienta.</span><span class="sxs-lookup"><span data-stu-id="ae541-158">The service only accepts these calls when it is calling out through a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae541-159">Opis i tworzenia kodu korzystającego z bezpiecznie więcej niż jeden wątek może być trudne do zapisania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="ae541-159">Understanding and developing code that safely uses more than one thread can be difficult to write successfully.</span></span> <span data-ttu-id="ae541-160">Przed użyciem <xref:System.ServiceModel.ConcurrencyMode.Multiple> lub <xref:System.ServiceModel.ConcurrencyMode.Reentrant> wartości, upewnij się, że usługa prawidłowo jest przeznaczony dla tych trybów.</span><span class="sxs-lookup"><span data-stu-id="ae541-160">Before using <xref:System.ServiceModel.ConcurrencyMode.Multiple> or <xref:System.ServiceModel.ConcurrencyMode.Reentrant> values, ensure that your service is properly designed for these modes.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="ae541-161"> <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae541-161"> <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>.</span></span>  
  
 <span data-ttu-id="ae541-162">Użycie współbieżności jest powiązany z trybu tworzenia.</span><span class="sxs-lookup"><span data-stu-id="ae541-162">The use of concurrency is related to the instancing mode.</span></span> <span data-ttu-id="ae541-163">W <xref:System.ServiceModel.InstanceContextMode.PerCall> wystąpień, współbieżności nie jest ważna, ponieważ każdy komunikat jest przetwarzany przez nowy <xref:System.ServiceModel.InstanceContext> i w związku z tym jest aktywny w nie więcej niż jeden wątek <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="ae541-163">In <xref:System.ServiceModel.InstanceContextMode.PerCall> instancing, concurrency is not relevant, because each message is processed by a new <xref:System.ServiceModel.InstanceContext> and, therefore, never more than one thread is active in the <xref:System.ServiceModel.InstanceContext>.</span></span>  
  
 <span data-ttu-id="ae541-164">Poniższy przykład kodu pokazuje ustawienie <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> właściwości <xref:System.ServiceModel.ConcurrencyMode.Multiple>.</span><span class="sxs-lookup"><span data-stu-id="ae541-164">The following code example demonstrates setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> property to <xref:System.ServiceModel.ConcurrencyMode.Multiple>.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]   
public class CalculatorService : ICalculatorConcurrency   
{   
    ...  
}  
```  
  
## <a name="sessions-interact-with-instancecontext-settings"></a><span data-ttu-id="ae541-165">Sesje interakcję z ustawieniami InstanceContext</span><span class="sxs-lookup"><span data-stu-id="ae541-165">Sessions Interact with InstanceContext Settings</span></span>  
 <span data-ttu-id="ae541-166">Sesje i <xref:System.ServiceModel.InstanceContext> interakcji kombinacja wartości w zależności od <xref:System.ServiceModel.SessionMode> wyliczenia w umowie i <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> właściwość implementacji usługi, która kontroluje skojarzenie między kanałów i określonych obiekty usługi.</span><span class="sxs-lookup"><span data-stu-id="ae541-166">Sessions and <xref:System.ServiceModel.InstanceContext> interact depending upon the combination of the value of the <xref:System.ServiceModel.SessionMode> enumeration in a contract and the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> property on the service implementation, which controls the association between channels and specific service objects.</span></span>  
  
 <span data-ttu-id="ae541-167">W poniższej tabeli przedstawiono wynik kanał przychodzący Obsługa sesji albo nie obsługuje sesji podana usługa kombinacja wartości <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> właściwości i <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="ae541-167">The following table shows the result of an incoming channel either supporting sessions or not supporting sessions given a service's combination of the values of the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property and the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> property.</span></span>  
  
|<span data-ttu-id="ae541-168">Wartość InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="ae541-168">InstanceContextMode value</span></span>|<xref:System.ServiceModel.SessionMode.Required>|<xref:System.ServiceModel.SessionMode.Allowed>|<xref:System.ServiceModel.SessionMode.NotAllowed>|  
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="ae541-169">PerCall</span><span class="sxs-lookup"><span data-stu-id="ae541-169">PerCall</span></span>|<span data-ttu-id="ae541-170">-Zachowanie podczas zamykania kanału: sesji i <xref:System.ServiceModel.InstanceContext> dla każdego wywołania.</span><span class="sxs-lookup"><span data-stu-id="ae541-170">-   Behavior with sessionful channel: A session and <xref:System.ServiceModel.InstanceContext> for each call.</span></span><br /><span data-ttu-id="ae541-171">— Zachowanie z kanałem Bezsesyjne: wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ae541-171">-   Behavior with sessionless channel: An exception is thrown.</span></span>|<span data-ttu-id="ae541-172">-Zachowanie podczas zamykania kanału: sesji i <xref:System.ServiceModel.InstanceContext> dla każdego wywołania.</span><span class="sxs-lookup"><span data-stu-id="ae541-172">-   Behavior with sessionful channel: A session and <xref:System.ServiceModel.InstanceContext> for each call.</span></span><br /><span data-ttu-id="ae541-173">— Zachowanie z kanałem Bezsesyjne: <xref:System.ServiceModel.InstanceContext> dla każdego wywołania.</span><span class="sxs-lookup"><span data-stu-id="ae541-173">-   Behavior with sessionless channel: An <xref:System.ServiceModel.InstanceContext> for each call.</span></span>|<span data-ttu-id="ae541-174">-Zachowanie podczas zamykania kanału: wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ae541-174">-   Behavior with sessionful channel: An exception is thrown.</span></span><br /><span data-ttu-id="ae541-175">— Zachowanie z kanałem Bezsesyjne: <xref:System.ServiceModel.InstanceContext> dla każdego wywołania.</span><span class="sxs-lookup"><span data-stu-id="ae541-175">-   Behavior with sessionless channel: An <xref:System.ServiceModel.InstanceContext> for each call.</span></span>|  
|<span data-ttu-id="ae541-176">PerSession</span><span class="sxs-lookup"><span data-stu-id="ae541-176">PerSession</span></span>|<span data-ttu-id="ae541-177">-Zachowanie podczas zamykania kanału: sesji i <xref:System.ServiceModel.InstanceContext> dla poszczególnych kanałów.</span><span class="sxs-lookup"><span data-stu-id="ae541-177">-   Behavior with sessionful channel: A session and <xref:System.ServiceModel.InstanceContext> for each channel.</span></span><br /><span data-ttu-id="ae541-178">— Zachowanie z kanałem Bezsesyjne: wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ae541-178">-   Behavior with sessionless channel: An exception is thrown.</span></span>|<span data-ttu-id="ae541-179">-Zachowanie podczas zamykania kanału: sesji i <xref:System.ServiceModel.InstanceContext> dla poszczególnych kanałów.</span><span class="sxs-lookup"><span data-stu-id="ae541-179">-   Behavior with sessionful channel: A session and <xref:System.ServiceModel.InstanceContext> for each channel.</span></span><br /><span data-ttu-id="ae541-180">— Zachowanie z kanałem Bezsesyjne: <xref:System.ServiceModel.InstanceContext> dla każdego wywołania.</span><span class="sxs-lookup"><span data-stu-id="ae541-180">-   Behavior with sessionless channel: An <xref:System.ServiceModel.InstanceContext> for each call.</span></span>|<span data-ttu-id="ae541-181">-Zachowanie podczas zamykania kanału: wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ae541-181">-   Behavior with sessionful channel: An exception is thrown.</span></span><br /><span data-ttu-id="ae541-182">— Zachowanie z kanałem Bezsesyjne: <xref:System.ServiceModel.InstanceContext> dla każdego wywołania.</span><span class="sxs-lookup"><span data-stu-id="ae541-182">-   Behavior with sessionless channel: An <xref:System.ServiceModel.InstanceContext> for each call.</span></span>|  
|<span data-ttu-id="ae541-183">Single</span><span class="sxs-lookup"><span data-stu-id="ae541-183">Single</span></span>|<span data-ttu-id="ae541-184">-Zachowanie podczas zamykania kanału: sesji i jeden <xref:System.ServiceModel.InstanceContext> dla wszystkich wywołań.</span><span class="sxs-lookup"><span data-stu-id="ae541-184">-   Behavior with sessionful channel: A session and one <xref:System.ServiceModel.InstanceContext> for all calls.</span></span><br /><span data-ttu-id="ae541-185">— Zachowanie z kanałem Bezsesyjne: wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ae541-185">-   Behavior with sessionless channel: An exception is thrown.</span></span>|<span data-ttu-id="ae541-186">-Zachowanie podczas zamykania kanału: sesji i <xref:System.ServiceModel.InstanceContext> dla pojedynczego wystąpienia utworzone lub określonych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ae541-186">-   Behavior with sessionful channel: A session and <xref:System.ServiceModel.InstanceContext> for the created or user-specified singleton.</span></span><br /><span data-ttu-id="ae541-187">— Zachowanie z kanałem Bezsesyjne: <xref:System.ServiceModel.InstanceContext> dla pojedynczego wystąpienia utworzone lub określonych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ae541-187">-   Behavior with sessionless channel: An <xref:System.ServiceModel.InstanceContext> for the created or user-specified singleton.</span></span>|<span data-ttu-id="ae541-188">-Zachowanie podczas zamykania kanału: wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ae541-188">-   Behavior with sessionful channel: An exception is thrown.</span></span><br /><span data-ttu-id="ae541-189">— Zachowanie z kanałem Bezsesyjne: <xref:System.ServiceModel.InstanceContext> dla każdej utworzonej pojedyncze lub pojedyncze określone przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ae541-189">-   Behavior with sessionless channel: An <xref:System.ServiceModel.InstanceContext> for each created singleton or for the user-specified singleton.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae541-190">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ae541-190">See Also</span></span>  
 [<span data-ttu-id="ae541-191">Korzystanie z sesji</span><span class="sxs-lookup"><span data-stu-id="ae541-191">Using Sessions</span></span>](../../../../docs/framework/wcf/using-sessions.md)  
 [<span data-ttu-id="ae541-192">Porady: Tworzenie usługi wymagającej użycia sesji</span><span class="sxs-lookup"><span data-stu-id="ae541-192">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)  
 [<span data-ttu-id="ae541-193">Porady: Tworzenie wystąpienia usługi sterowania</span><span class="sxs-lookup"><span data-stu-id="ae541-193">How to: Control Service Instancing</span></span>](../../../../docs/framework/wcf/feature-details/how-to-control-service-instancing.md)  
 [<span data-ttu-id="ae541-194">Współbieżność</span><span class="sxs-lookup"><span data-stu-id="ae541-194">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)  
 [<span data-ttu-id="ae541-195">Tworzenie wystąpienia</span><span class="sxs-lookup"><span data-stu-id="ae541-195">Instancing</span></span>](../../../../docs/framework/wcf/samples/instancing.md)  
 [<span data-ttu-id="ae541-196">Sesji</span><span class="sxs-lookup"><span data-stu-id="ae541-196">Session</span></span>](../../../../docs/framework/wcf/samples/session.md)