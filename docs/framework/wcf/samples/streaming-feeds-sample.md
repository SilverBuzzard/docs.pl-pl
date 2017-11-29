---
title: "Przykład strumieniowych kanałów informacyjnych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: becc388a03d065b5763669929806c2f85e171ffc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="streaming-feeds-sample"></a><span data-ttu-id="8992c-102">Przykład strumieniowych kanałów informacyjnych</span><span class="sxs-lookup"><span data-stu-id="8992c-102">Streaming Feeds Sample</span></span>
<span data-ttu-id="8992c-103">W tym przykładzie pokazano, jak zarządzać zespolonego źródła danych, które zawierają dużą liczbę elementów.</span><span class="sxs-lookup"><span data-stu-id="8992c-103">This sample demonstrates how to manage syndication feeds that contain large numbers of items.</span></span> <span data-ttu-id="8992c-104">Na serwerze, przykładzie pokazano, jak opóźnienie tworzenia poszczególnych <xref:System.ServiceModel.Syndication.SyndicationItem> obiektów w ramach źródła danych do bezpośrednio przed elementu są zapisywane do strumienia sieci.</span><span class="sxs-lookup"><span data-stu-id="8992c-104">On the server, the sample demonstrates how to delay the creation of individual <xref:System.ServiceModel.Syndication.SyndicationItem> objects within the feed until immediately before the item is written to the network stream.</span></span>  
  
 <span data-ttu-id="8992c-105">Na komputerze klienckim próbki pokazuje, jak niestandardowy program formatujący źródło zespolone może służyć do odczytania poszczególne elementy strumienia sieci, dzięki czemu odczytywanego pełni nigdy nie są buforowane w pamięci.</span><span class="sxs-lookup"><span data-stu-id="8992c-105">On the client, the sample shows how a custom syndication feed formatter can be used to read individual items from the network stream so that the feed being read is never fully buffered into memory.</span></span>  
  
 <span data-ttu-id="8992c-106">Aby zademonstrować najlepiej przesyłania strumieniowego możliwości zespolonego interfejsu API, w tym przykładzie użyto nieco prawdopodobne scenariusz, w którym serwer udostępnia źródło z nieograniczoną liczbę elementów.</span><span class="sxs-lookup"><span data-stu-id="8992c-106">To best demonstrate the streaming capability of the syndication API, this sample uses a somewhat unlikely scenario in which the server exposes a feed that contains an infinite number of items.</span></span> <span data-ttu-id="8992c-107">W takim przypadku serwer kontynuuje generowania nowych elementów w źródle danych, dopóki nie określa, że klient ma odczytu określoną liczbę elementów ze źródła strumieniowego (domyślnie 10).</span><span class="sxs-lookup"><span data-stu-id="8992c-107">In this case, the server continues generating new items into the feed until it determines that the client has read a specified number of items from the feed (by default, 10).</span></span> <span data-ttu-id="8992c-108">Dla uproszczenia zarówno klient, jak i serwera są zaimplementowane w tym samym procesie i używać udostępnionej `ItemCounter` obiekt, aby śledzić liczbę elementów klienta został utworzony.</span><span class="sxs-lookup"><span data-stu-id="8992c-108">For simplicity, both the client and the server are implemented in the same process and use a shared `ItemCounter` object to keep track of how many items the client has produced.</span></span> <span data-ttu-id="8992c-109">`ItemCounter` Typu istnieje tylko w celu umożliwienia przykładowy scenariusz zakończenie prawidłowo i nie jest elementem core wzorca jest uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="8992c-109">The `ItemCounter` type exists only for the purpose of allowing the sample scenario to terminate cleanly, and is not a core element of the pattern being demonstrated.</span></span>  
  
 <span data-ttu-id="8992c-110">Pokazu sprawia, że użycie [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] Iteratory (przy użyciu `yield``return` konstrukcja — słowo kluczowe).</span><span class="sxs-lookup"><span data-stu-id="8992c-110">The demonstration makes use of [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] iterators (using the `yield``return` keyword construct).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="8992c-111">Iteratory, zobacz temat "Przy użyciu Iteratory" w witrynie MSDN.</span><span class="sxs-lookup"><span data-stu-id="8992c-111"> iterators, see the "Using Iterators" topic on MSDN.</span></span>  
  
## <a name="service"></a><span data-ttu-id="8992c-112">Usługa</span><span class="sxs-lookup"><span data-stu-id="8992c-112">Service</span></span>  
 <span data-ttu-id="8992c-113">Usługa implementuje podstawowego <xref:System.ServiceModel.Web.WebGetAttribute> kontraktu, który składa się z jednej operacji, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="8992c-113">The service implements a basic <xref:System.ServiceModel.Web.WebGetAttribute> contract that consists of one operation, as shown in the following code.</span></span>  
  
```  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
```  
  
 <span data-ttu-id="8992c-114">Usługa implementuje tego kontraktu przy użyciu `ItemGenerator` klasy w celu utworzenia potencjalnie nieskończone strumienia <xref:System.ServiceModel.Syndication.SyndicationItem> wystąpienia przy użyciu iteratora, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="8992c-114">The service implements this contract by using an `ItemGenerator` class to create a potentially infinite stream of <xref:System.ServiceModel.Syndication.SyndicationItem> instances using an iterator, as shown in the following code.</span></span>  
  
```  
class ItemGenerator  
{  
    public IEnumerable<SyndicationItem> GenerateItems()  
    {  
        while (counter.GetCount() < maxItemsRead)  
        {  
            itemsReturned++;  
            yield return CreateNextItem();  
        }  
  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="8992c-115">Podczas wdrażania usługi tworzy dane wyjściowe w źródle danych `ItemGenerator.GenerateItems()` jest używany zamiast buforowanego kolekcję elementów.</span><span class="sxs-lookup"><span data-stu-id="8992c-115">When the service implementation creates the feed, the output of `ItemGenerator.GenerateItems()` is used instead of a buffered collection of items.</span></span>  
  
```  
public Atom10FeedFormatter StreamedFeed()  
{  
    SyndicationFeed feed = new SyndicationFeed("Streamed feed", "Feed to test streaming", null);  
    //Generate an infinite stream of items. Both the client and the service share  
    //a reference to the ItemCounter, which allows the sample to terminate  
    //execution after the client has read 10 items from the stream  
    ItemGenerator itemGenerator = new ItemGenerator(this.counter, 10);  
  
    feed.Items = itemGenerator.GenerateItems();  
    return feed.GetAtom10Formatter();  
}  
```  
  
 <span data-ttu-id="8992c-116">W związku z tym strumienia elementu pełni nigdy nie są buforowane w pamięci.</span><span class="sxs-lookup"><span data-stu-id="8992c-116">As a result, the item stream is never fully buffered into memory.</span></span> <span data-ttu-id="8992c-117">To zachowanie można zaobserwować, ustawiając punkt przerwania dla `yield``return` instrukcji wewnątrz `ItemGenerator.GenerateItems()` — metoda i zauważyć, że ten punkt przerwania napotkano po raz pierwszy po usługi zwrócił wynik `StreamedFeed()` metody.</span><span class="sxs-lookup"><span data-stu-id="8992c-117">You can observe this behavior by setting a breakpoint on the `yield``return` statement inside of the `ItemGenerator.GenerateItems()` method and noting that this breakpoint is encountered for the first time after the service has returned the result of the `StreamedFeed()` method.</span></span>  
  
## <a name="client"></a><span data-ttu-id="8992c-118">Klient</span><span class="sxs-lookup"><span data-stu-id="8992c-118">Client</span></span>  
 <span data-ttu-id="8992c-119">W tym przykładzie klient używa niestandardowego <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> implementacji, który wybrano opcję opóźnienia materialization poszczególnych elementów w źródle danych, zamiast buforowania ich do pamięci.</span><span class="sxs-lookup"><span data-stu-id="8992c-119">The client in this sample uses a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> implementation that delays the materialization of individual items in the feed instead of buffering them into memory.</span></span> <span data-ttu-id="8992c-120">Niestandardowa `StreamedAtom10FeedFormatter` wystąpienia jest używane w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="8992c-120">The custom `StreamedAtom10FeedFormatter` instance is used as follows.</span></span>  
  
```  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
```  
  
 <span data-ttu-id="8992c-121">Zazwyczaj wywołanie <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> nie może zwracać dopóki całą zawartość źródła danych zostały odczytu z sieci i buforowane w pamięci.</span><span class="sxs-lookup"><span data-stu-id="8992c-121">Normally, a call to <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> does not return until the entire contents of the feed have been read from the network and buffered into memory.</span></span> <span data-ttu-id="8992c-122">Jednak `StreamedAtom10FeedFormatter` obiekt zastąpienia <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> do zwrócenia iteratora zamiast buforowanego kolekcji, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="8992c-122">However, the `StreamedAtom10FeedFormatter` object overrides <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> to return an iterator instead of a buffered collection, as shown in the following code.</span></span>  
  
```  
protected override IEnumerable<SyndicationItem> ReadItems(XmlReader reader, SyndicationFeed feed, out bool areAllItemsRead)  
{  
    areAllItemsRead = false;  
    return DelayReadItems(reader, feed);  
}  
  
private IEnumerable<SyndicationItem> DelayReadItems(XmlReader reader, SyndicationFeed feed)  
{  
    while (reader.IsStartElement("entry", "http://www.w3.org/2005/Atom"))  
    {  
        yield return this.ReadItem(reader, feed);  
    }  
  
    reader.ReadEndElement();  
}  
```  
  
 <span data-ttu-id="8992c-123">W związku z tym każdy element nie został odczytany z sieci do aplikacji klienckiej, przechodzenie przez wyniki `ReadItems()` jest gotowe do użycia go.</span><span class="sxs-lookup"><span data-stu-id="8992c-123">As a result, each item is not read from the network until the client application traversing the results of `ReadItems()` is ready to use it.</span></span> <span data-ttu-id="8992c-124">To zachowanie można zaobserwować, ustawiając punkt przerwania dla `yield``return` instrukcji wewnątrz `StreamedAtom10FeedFormatter.DelayReadItems()` i że napotkano po raz pierwszy po wywołaniu tego punktu przerwania po raz pierwszy `ReadFrom()` zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="8992c-124">You can observe this behavior by setting a breakpoint on the `yield``return` statement inside of `StreamedAtom10FeedFormatter.DelayReadItems()` and noticing that this breakpoint is encountered for the first time after the call to `ReadFrom()` completes.</span></span>  
  
 <span data-ttu-id="8992c-125">Poniższe instrukcje przedstawiają sposób skompilować i uruchomić próbki.</span><span class="sxs-lookup"><span data-stu-id="8992c-125">The following instructions show how to build and run the sample.</span></span> <span data-ttu-id="8992c-126">Należy pamiętać, że chociaż serwer przestaje generowania elementów, gdy klient może odczytywać 10 elementów, dane wyjściowe zawierają czy klient otrzymuje znacznie więcej niż 10 elementów.</span><span class="sxs-lookup"><span data-stu-id="8992c-126">Note that although the server stops generating items after the client has read 10 items, the output shows that the client reads significantly more than 10 items.</span></span> <span data-ttu-id="8992c-127">Jest to spowodowane powiązanie sieciowe używane przez próbki przesyła dane w czterech kilobajtów (KB) segmentów.</span><span class="sxs-lookup"><span data-stu-id="8992c-127">This is because the networking binding used by the sample transmits data in four-kilobyte (KB) segments.</span></span> <span data-ttu-id="8992c-128">Tak klient odbierze 4KB danych elementu przed ma możliwość odczytu nawet jednego elementu.</span><span class="sxs-lookup"><span data-stu-id="8992c-128">As such, the client receives 4KB of item data before it has the opportunity to read even one item.</span></span> <span data-ttu-id="8992c-129">Jest to normalne zachowanie (wysyłania strumienia danych HTTP w rozsądnych rozmiarach segmentów zwiększa wydajność).</span><span class="sxs-lookup"><span data-stu-id="8992c-129">This is normal behavior (sending streamed HTTP data in reasonably-sized segments increases performance).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8992c-130">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="8992c-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8992c-131">Upewnij się, że wykonano procedurę [jednorazowego procedurę instalacji dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8992c-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8992c-132">Tworzenie wersji języka C# lub Visual Basic .NET rozwiązania, postępuj zgodnie z instrukcjami [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8992c-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8992c-133">Aby uruchomić przykładowy w konfiguracji pojedynczej lub między komputerami, postępuj zgodnie z instrukcjami w [uruchamiania przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8992c-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8992c-134">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="8992c-134">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8992c-135">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="8992c-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8992c-136">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="8992c-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8992c-137">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="8992c-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a><span data-ttu-id="8992c-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8992c-138">See Also</span></span>  
 [<span data-ttu-id="8992c-139">Autonomiczny kanał diagnostyczny</span><span class="sxs-lookup"><span data-stu-id="8992c-139">Stand-Alone Diagnostics Feed</span></span>](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)