---
title: "Obsługa częściowej awarii"
description: "Architektura Mikrousług .NET dla aplikacji .NET konteneryzowanych | Obsługa częściowej awarii"
keywords: "Docker, Mikrousług, ASP.NET, kontenera"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7d16acf3de2d395da70e8f46e59c129dec24f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="handling-partial-failure"></a><span data-ttu-id="24367-104">Obsługa częściowej awarii</span><span class="sxs-lookup"><span data-stu-id="24367-104">Handling partial failure</span></span>

<span data-ttu-id="24367-105">W systemach rozproszonych, takich jak aplikacje oparte na mikrousług istnieje ryzyko wszechobecne częściowej awarii.</span><span class="sxs-lookup"><span data-stu-id="24367-105">In distributed systems like microservices-based applications, there is an ever-present risk of partial failure.</span></span> <span data-ttu-id="24367-106">Na przykład jeden mikrousługi/kontener może zakończyć się niepowodzeniem lub mogą nie być dostępne do odpowiedzi przez krótki czas lub jednego serwera lub maszyny Wirtualnej może ulec awarii.</span><span class="sxs-lookup"><span data-stu-id="24367-106">For instance, a single microservice/container can fail or might not be available to respond for a short time, or a single VM or server can crash.</span></span> <span data-ttu-id="24367-107">Od klientów i usług są osobne procesy, usługi może nie być w stanie odpowiedzieć w odpowiednim momencie na żądanie klienta.</span><span class="sxs-lookup"><span data-stu-id="24367-107">Since clients and services are separate processes, a service might not be able to respond in a timely way to a client’s request.</span></span> <span data-ttu-id="24367-108">Usługa może być przeciążona i odpowiada bardzo wolno do żądania lub po prostu nie mogą być niedostępne przez krótki czas z powodu problemów dotyczących sieci.</span><span class="sxs-lookup"><span data-stu-id="24367-108">The service might be overloaded and responding extremely slowly to requests, or might simply not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="24367-109">Na przykład należy wziąć pod uwagę strony szczegółów w kolejności od eShopOnContainers przykładowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24367-109">For example, consider the Order details page from the eShopOnContainers sample application.</span></span> <span data-ttu-id="24367-110">Jeśli mikrousługi porządkowania nie odpowiada gdy użytkownik próbuje przesłać zamówienie, złą implementacją klasy procesu klienta (aplikacja sieci web MVC) — na przykład, jeśli kod klienta synchroniczne RPC za pomocą limitu czasu — umożliwia zablokowanie wątków nieskończoność Oczekiwanie na odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="24367-110">If the ordering microservice is unresponsive when the user tries to submit an order, a bad implementation of the client process (the MVC web application)—for example, if the client code were to use synchronous RPCs with no timeout—would block threads indefinitely waiting for a response.</span></span> <span data-ttu-id="24367-111">Oprócz tworzenia płynność pracy, co nie odpowiada oczekiwania zużywa lub blokuje wątku i wątki są bardzo przydatne w aplikacjach wysokiej skalowalności.</span><span class="sxs-lookup"><span data-stu-id="24367-111">In addition to creating a bad user experience, every unresponsive wait consumes or blocks a thread, and threads are extremely valuable in highly scalable applications.</span></span> <span data-ttu-id="24367-112">W przypadku wielu zablokowanych wątków po pewnym czasie poza wątków można uruchomić aplikacji w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="24367-112">If there are many blocked threads, eventually the application’s runtime can run out of threads.</span></span> <span data-ttu-id="24367-113">W takim przypadku aplikacja może stać się globalny nie odpowiada, a nie tylko częściowo odpowiadać jako Pokaż w rysunek 10-1.</span><span class="sxs-lookup"><span data-stu-id="24367-113">In that case, the application can become globally unresponsive instead of just partially unresponsive, as show in Figure 10-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="24367-114">**Rysunek 10-1**.</span><span class="sxs-lookup"><span data-stu-id="24367-114">**Figure 10-1**.</span></span> <span data-ttu-id="24367-115">Częściowe błędy z powodu zależności, które mają wpływ na dostępność wątku usługi</span><span class="sxs-lookup"><span data-stu-id="24367-115">Partial failures because of dependencies that impact service thread availability</span></span>

<span data-ttu-id="24367-116">W dużych aplikacji na podstawie mikrousług jakiekolwiek niepowodzenie częściowe mogą jest rozszerzona, zwłaszcza, jeśli większość interakcji wewnętrzny mikrousług opiera się na synchroniczne wywołania HTTP (które uważa się przed wzorzec).</span><span class="sxs-lookup"><span data-stu-id="24367-116">In a large microservices-based application, any partial failure can be amplified, especially if most of the internal microservices interaction is based on synchronous HTTP calls (which is considered an anti-pattern).</span></span> <span data-ttu-id="24367-117">Zastanów się systemu, który odbiera miliony przychodzące wywołania dziennie.</span><span class="sxs-lookup"><span data-stu-id="24367-117">Think about a system that receives millions of incoming calls per day.</span></span> <span data-ttu-id="24367-118">Jeśli system ma zły projekt, który jest oparty na długie łańcuchy synchroniczne wywołania HTTP, te połączenia przychodzące może skutkować milionów więcej połączeń wychodzących (Załóżmy, że stosunek 1:4) dziesiątki wewnętrzny mikrousług jako synchroniczne zależności.</span><span class="sxs-lookup"><span data-stu-id="24367-118">If your system has a bad design that is based on long chains of synchronous HTTP calls, these incoming calls might result in many more millions of outgoing calls (let’s suppose a ratio of 1:4) to dozens of internal microservices as synchronous dependencies.</span></span> <span data-ttu-id="24367-119">Taka sytuacja jest wyświetlany w rysunek 10-2, szczególnie zależności \#3.</span><span class="sxs-lookup"><span data-stu-id="24367-119">This situation is shown in Figure 10-2, especially dependency \#3.</span></span>

![](./media/image2.png)

<span data-ttu-id="24367-120">**Rysunek 10-2**.</span><span class="sxs-lookup"><span data-stu-id="24367-120">**Figure 10-2**.</span></span> <span data-ttu-id="24367-121">Wpływ projektu niepoprawne o długie łańcuchy żądań HTTP</span><span class="sxs-lookup"><span data-stu-id="24367-121">The impact of having an incorrect design featuring long chains of HTTP requests</span></span>

<span data-ttu-id="24367-122">Sporadyczne niepowodzenia jest praktycznie gwarantowana w rozproszonej i w chmurze oparte na systemie, nawet jeśli doskonałej dostępności ma zależności, co się.</span><span class="sxs-lookup"><span data-stu-id="24367-122">Intermittent failure is virtually guaranteed in a distributed and cloud based system, even if every dependency itself has excellent availability.</span></span> <span data-ttu-id="24367-123">Powinno to być faktów, które należy wziąć pod uwagę.</span><span class="sxs-lookup"><span data-stu-id="24367-123">This should be a fact you need to consider.</span></span>

<span data-ttu-id="24367-124">Jeśli nie projektowania i implementacji technik w celu zapewnienia odporności na uszkodzenia, można rozszerzone nawet małe awariami.</span><span class="sxs-lookup"><span data-stu-id="24367-124">If you do not design and implement techniques to ensure fault tolerance, even small downtimes can be amplified.</span></span> <span data-ttu-id="24367-125">Na przykład 50 zależności dostępności 99,99% spowoduje kilka godzin przestoju miesięcznie ze względu na to wpływ.</span><span class="sxs-lookup"><span data-stu-id="24367-125">As an example, 50 dependencies each with 99.99% of availability would result in several hours of downtime each month because of this ripple effect.</span></span> <span data-ttu-id="24367-126">Jeśli zależność mikrousługi nie powiodło się podczas obsługi dużej liczby żądań, błędu można szybko saturate — wszystkie wątki żądania dostępne w poszczególnych usług i awarii całej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24367-126">When a microservice dependency fails while handling a high volume of requests, that failure can quickly saturate all available request threads in each service and crash the whole application.</span></span>

![](./media/image3.png)

<span data-ttu-id="24367-127">**Rysunek 10-3**.</span><span class="sxs-lookup"><span data-stu-id="24367-127">**Figure 10-3**.</span></span> <span data-ttu-id="24367-128">Częściowe niepowodzenie rozszerzone o mikrousług o długie łańcuchy synchroniczne wywołania HTTP</span><span class="sxs-lookup"><span data-stu-id="24367-128">Partial failure amplified by microservices with long chains of synchronous HTTP calls</span></span>

<span data-ttu-id="24367-129">Aby zminimalizować ten problem, w sekcji "*integracji asynchroniczne mikrousługi wymusić Autonomia w mikrousługi*" (w tym rozdziale architektury), firma Microsoft zaleca użycia komunikacji asynchronicznej między wewnętrznego mikrousług.</span><span class="sxs-lookup"><span data-stu-id="24367-129">To minimize this problem, in the section "*Asynchronous microservice integration enforce microservice’s autonomy*” (in the architecture chapter), we encouraged you to use asynchronous communication across the internal microservices.</span></span> <span data-ttu-id="24367-130">Firma Microsoft krótko opisano bardziej w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="24367-130">We briefly explain more in the next section.</span></span>

<span data-ttu-id="24367-131">Ponadto ważne zaprojektowanie klienta i mikrousług aplikacji do obsługi błędów z częściowa jest — oznacza to, że tworzenie mikrousług odporne i klienta aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24367-131">In addition, it is essential that you design your microservices and client applications to handle partial failures—that is, to build resilient microservices and client applications.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="24367-132">[Poprzednie] (index.md) [dalej] (częściowe — błąd strategies.md)</span><span class="sxs-lookup"><span data-stu-id="24367-132">[Previous] (index.md) [Next] (partial-failure-strategies.md)</span></span>