---
title: Serializacja dokumentu i przechowywanie
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 34b517366a5f143a86388abff5ae13022bc710c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="document-serialization-and-storage"></a><span data-ttu-id="be6ac-102">Serializacja dokumentu i przechowywanie</span><span class="sxs-lookup"><span data-stu-id="be6ac-102">Document Serialization and Storage</span></span>
[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]<span data-ttu-id="be6ac-103">udostępnia zaawansowane środowisko do tworzenia i wyświetlania dokumentów wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="be6ac-103"> provides a powerful environment for creating and displaying high quality documents.</span></span>  <span data-ttu-id="be6ac-104">Udoskonalone funkcje, które obsługują dokumenty stałej i dokumenty przepływu, zaawansowane wyświetlania formantów, połączeniu z zaawansowanych 2W i podejmij możliwości grafiki 3D [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] aplikacji do nowego poziomu jakości i środowisko użytkownika.</span><span class="sxs-lookup"><span data-stu-id="be6ac-104">Enhanced features that support both fixed-documents and flow-documents, advanced viewing controls, combined with powerful 2D and 3D graphic capabilities take [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] applications to a new level of quality and user experience.</span></span>  <span data-ttu-id="be6ac-105">Możliwość elastycznego zarządzania reprezentacji w pamięci dokumentu jest kluczowym elementem [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], i możliwość efektywnego zapisywanie i ładowanie dokumentów z magazynu danych potrzeby prawie każdej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="be6ac-105">Being able to flexibly manage an in-memory representation of a document is a key feature of [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], and being able to efficiently save and load documents from a data store is a need of almost every application.</span></span>  <span data-ttu-id="be6ac-106">Proces konwersji dokumentu z reprezentacji w pamięci wewnętrznej do magazynu danych zewnętrznych jest określane jako serializacji.</span><span class="sxs-lookup"><span data-stu-id="be6ac-106">The process of converting a document from an internal in-memory representation to an external data store is termed serialization.</span></span>  <span data-ttu-id="be6ac-107">Procesu odczytu z magazynu danych i ponowne utworzenie oryginalnego wystąpienia w pamięci jest określane jako deserializacji.</span><span class="sxs-lookup"><span data-stu-id="be6ac-107">The reverse process of reading a data store and recreating the original in-memory instance is termed deserialization.</span></span>  
  
 
  
<a name="AboutSerialization"></a>   
## <a name="about-document-serialization"></a><span data-ttu-id="be6ac-108">Informacje o serializacji dokumentu</span><span class="sxs-lookup"><span data-stu-id="be6ac-108">About Document Serialization</span></span>  
 <span data-ttu-id="be6ac-109">W idealnym przypadku proces serializacji i deserializacji dokumentu z, a następnie wstecz do pamięci jest niewidoczne dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="be6ac-109">Ideally the process of serializing and deserializing a document from and then back into memory is transparent to the application.</span></span>  <span data-ttu-id="be6ac-110">Aplikacja wywołuje element serializujący "write" metodę, aby zapisać dokument, podczas deserializacji "Przeczytaj" Metoda uzyskuje dostęp do magazynu danych i odtwarza oryginalnego wystąpienia w pamięci.</span><span class="sxs-lookup"><span data-stu-id="be6ac-110">The application calls a serializer "write" method to save the document, while a deserializer "read" method accesses the data store and recreates the original instance in memory.</span></span>  <span data-ttu-id="be6ac-111">Określony format, którego dane są przechowywane w zwykle nie jest problemem aplikacji, jak długie jako serializacja i zdeserializować procesu odtwarza dokumentu z powrotem do postaci oryginalnej.</span><span class="sxs-lookup"><span data-stu-id="be6ac-111">The specific format that the data is stored in is generally not a concern of the application as long as the serialize and deserialize process recreates the document back to its original form.</span></span>  
  
 <span data-ttu-id="be6ac-112">Aplikacje często udostępniają wiele opcji serializacji, które umożliwiają użytkownikom zapisywać dokumenty w innych nośników lub w innym formacie.</span><span class="sxs-lookup"><span data-stu-id="be6ac-112">Applications often provide multiple serialization options which allow the user to save documents to different medium or to a different format.</span></span>  <span data-ttu-id="be6ac-113">Na przykład aplikacja może oferować "Zapisz jako" Opcje przechowywania dokumentów do pliku dysku, bazy danych lub usługi sieci web.</span><span class="sxs-lookup"><span data-stu-id="be6ac-113">For example, an application might offer "Save As" options to store a document to a disk file, database, or web service.</span></span>  <span data-ttu-id="be6ac-114">Podobnie różnych serializatorów można przechowywać dokumentu w różnych formatach takich jak HTML, RTF, XML, XPS lub format innych firm.</span><span class="sxs-lookup"><span data-stu-id="be6ac-114">Similarly, different serializers could store the document in different formats such as in HTML, RTF, XML, XPS, or alternately to a third-party format.</span></span>  <span data-ttu-id="be6ac-115">Do aplikacji serializacji definiuje interfejs, który izoluje szczegółowe informacje o nośniku w implementacji każdego określonego serializatora.</span><span class="sxs-lookup"><span data-stu-id="be6ac-115">To the application, serialization defines an interface that isolates the details of the storage medium within the implementation of each specific serializer.</span></span>  <span data-ttu-id="be6ac-116">Oprócz korzyści z zastosowania zawierający szczegóły magazynu [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] <xref:System.Windows.Documents.Serialization> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] podać kilka ważnych funkcji.</span><span class="sxs-lookup"><span data-stu-id="be6ac-116">In addition to the benefits of encapsulating storage details, the [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] <xref:System.Windows.Documents.Serialization> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] provide several other important features.</span></span>  
  
### <a name="features-of-net-framework-30-document-serializers"></a><span data-ttu-id="be6ac-117">Funkcje programu .NET Framework 3.0 dokumentu serializatorów</span><span class="sxs-lookup"><span data-stu-id="be6ac-117">Features of .NET Framework 3.0 Document Serializers</span></span>  
  
-   <span data-ttu-id="be6ac-118">Bezpośredni dostęp do obiektów wysokiego poziomu dokumentu (drzewa logicznego i elementy wizualne) Włącz wydajnego magazynu podzielonym na strony zawartość, elementy 2D i 3D, obrazy, nośnik, hiperłącza, adnotacje i innej zawartości pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="be6ac-118">Direct access to the high-level document objects (logical tree and visuals) enable efficient storage of paginated content, 2D/3D elements, images, media, hyperlinks, annotations, and other support content.</span></span>  
  
-   <span data-ttu-id="be6ac-119">Operacji synchronicznych i asynchronicznych.</span><span class="sxs-lookup"><span data-stu-id="be6ac-119">Synchronous and asynchronous operation.</span></span>  
  
-   <span data-ttu-id="be6ac-120">Obsługa wtyczek serializatorów z rozszerzonymi funkcjami:</span><span class="sxs-lookup"><span data-stu-id="be6ac-120">Support for plug-in serializers with enhanced capabilities:</span></span>  
  
    -   <span data-ttu-id="be6ac-121">Dostęp do całego systemu do użytku przez wszystkie [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="be6ac-121">System-wide access for use by all [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] applications.</span></span>  
  
    -   <span data-ttu-id="be6ac-122">Odnajdowanie wtyczki prostą aplikację.</span><span class="sxs-lookup"><span data-stu-id="be6ac-122">Simple application plug-in discoverability.</span></span>  
  
    -   <span data-ttu-id="be6ac-123">Proste wdrożenie, instalacji i aktualizacji niestandardowych wtyczek innych firm.</span><span class="sxs-lookup"><span data-stu-id="be6ac-123">Simple deployment, installation, and update for custom third-party plug-ins.</span></span>  
  
    -   <span data-ttu-id="be6ac-124">Obsługa interfejsu użytkownika dla ustawień niestandardowych środowiska wykonawczego i opcje.</span><span class="sxs-lookup"><span data-stu-id="be6ac-124">User interface support for custom run-time settings and options.</span></span>  
  
### <a name="xps-print-path"></a><span data-ttu-id="be6ac-125">Ścieżki wydruku XPS</span><span class="sxs-lookup"><span data-stu-id="be6ac-125">XPS Print Path</span></span>  
 <span data-ttu-id="be6ac-126">[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] Ścieżki wydruku również zapewnia mechanizm extensible zapisywanie dokumentów za pomocą drukowania.</span><span class="sxs-lookup"><span data-stu-id="be6ac-126">The [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] print path also provides an extensible mechanism for writing documents through print output.</span></span>  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]<span data-ttu-id="be6ac-127">pełni rolę zarówno format pliku dokumentu i format macierzysty buforu wydruku dla [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be6ac-127"> serves as both a document file format and is the native print spool format for [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].</span></span>  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]<span data-ttu-id="be6ac-128">dokumenty mogą być wysyłane bezpośrednio do [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-zgodnych drukarek bez konieczności konwersji do formatu pośrednich.</span><span class="sxs-lookup"><span data-stu-id="be6ac-128"> documents can be sent directly to [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-compatible printers without the need for conversion to an intermediate format.</span></span>  <span data-ttu-id="be6ac-129">Zobacz [Omówienie drukowania](../../../../docs/framework/wpf/advanced/printing-overview.md) dodatkowe informacje na temat opcji wyjściowych ścieżki wydruku i możliwości.</span><span class="sxs-lookup"><span data-stu-id="be6ac-129">See the [Printing Overview](../../../../docs/framework/wpf/advanced/printing-overview.md) for additional information on print path output options and capabilities.</span></span>  
  
<a name="PluginSerializers"></a>   
## <a name="plug-in-serializers"></a><span data-ttu-id="be6ac-130">Wtyczka serializatorów</span><span class="sxs-lookup"><span data-stu-id="be6ac-130">Plug-in Serializers</span></span>  
 <span data-ttu-id="be6ac-131"><xref:System.Windows.Documents.Serialization> Interfejsów API zapewniają obsługę dla wtyczki serializatorów i serializatorów połączone, które są instalowane osobno z aplikacji, wiązania w czasie wykonywania i są dostępne za pomocą <xref:System.Windows.Documents.Serialization.SerializerProvider> mechanizmu odnajdowania.</span><span class="sxs-lookup"><span data-stu-id="be6ac-131">The <xref:System.Windows.Documents.Serialization> APIs provide support for both plug-in serializers and linked serializers that are installed separately from the application, bind at run time, and are accessed by using the <xref:System.Windows.Documents.Serialization.SerializerProvider> discovery mechanism.</span></span>  <span data-ttu-id="be6ac-132">Wtyczka serializatorów oferują rozszerzoną korzyści w celu ułatwienia wdrażania i używania całego systemu.</span><span class="sxs-lookup"><span data-stu-id="be6ac-132">Plug-in serializers offer enhanced benefits for ease of deployment and system-wide use.</span></span>  <span data-ttu-id="be6ac-133">Połączone serializatorów również można zaimplementować w środowiskach częściowej relacji zaufania takich jak [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] gdzie serializatorów wtyczka nie są dostępne.</span><span class="sxs-lookup"><span data-stu-id="be6ac-133">Linked serializers can also be implemented for partial trust environments such as [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] where plug-in serializers are not accessible.</span></span>  <span data-ttu-id="be6ac-134">Połączone serializatorów, oparte na pochodnej implementacja <xref:System.Windows.Documents.Serialization.SerializerWriter> klasy, kompilowania i połączone bezpośrednio do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="be6ac-134">Linked serializers, which are based on a derived implementation of the <xref:System.Windows.Documents.Serialization.SerializerWriter> class, are compiled and linked directly into the application.</span></span>  <span data-ttu-id="be6ac-135">Zarówno serializatorów wtyczki, jak i połączonych serializatorów działać przez identycznych metod publicznych i zdarzenia, które ułatwiają Użyj jednego lub obu tych rodzajów serializatorów w tej samej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="be6ac-135">Both plug-in serializers and linked serializers operate through identical public methods and events which make it easy to use either or both types of serializers in the same application.</span></span>  
  
 <span data-ttu-id="be6ac-136">Wtyczki serializatorów pomocy deweloperzy aplikacji, zapewniając rozszerzeń formaty plików i nowe projekty magazynu bez konieczności kodu bezpośrednio dla każdego potencjalnych format w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="be6ac-136">Plug-in serializers aid application developers by providing extensibility to new storage designs and file formats without having to code directly for every potential format at build time.</span></span>  <span data-ttu-id="be6ac-137">Wtyczka serializatorów również korzystać inne firmy przez zapewnienie standardowej metody wdrażania, instalacji i aktualizacji systemu dostępne dodatki plug-in formatów plików niestandardowych lub zastrzeżonych.</span><span class="sxs-lookup"><span data-stu-id="be6ac-137">Plug-in serializers also benefit third-party developers by providing a standardized means to deploy, install, and update system accessible plug-ins for custom or proprietary file formats.</span></span>  
  
### <a name="using-a-plug-in-serializer"></a><span data-ttu-id="be6ac-138">Przy użyciu serializatora wtyczki</span><span class="sxs-lookup"><span data-stu-id="be6ac-138">Using a Plug-in Serializer</span></span>  
 <span data-ttu-id="be6ac-139">Wtyczka serializatorów są proste w użyciu.</span><span class="sxs-lookup"><span data-stu-id="be6ac-139">Plug-in serializers are simple to use.</span></span>  <span data-ttu-id="be6ac-140"><xref:System.Windows.Documents.Serialization.SerializerProvider> Wylicza klasy <xref:System.Windows.Documents.Serialization.SerializerDescriptor> obiekt dla każdego wtyczki zainstalowane w systemie.</span><span class="sxs-lookup"><span data-stu-id="be6ac-140">The <xref:System.Windows.Documents.Serialization.SerializerProvider> class enumerates a <xref:System.Windows.Documents.Serialization.SerializerDescriptor> object for each plug-in installed on the system.</span></span>  <span data-ttu-id="be6ac-141"><xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> Właściwość filtruje zainstalowanych wtyczek na podstawie bieżącej konfiguracji i sprawdza, czy serializator może załadować i używane przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="be6ac-141">The <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> property filters the installed plug-ins based on the current configuration and verifies that the serializer can be loaded and used by the application.</span></span>  <span data-ttu-id="be6ac-142"><xref:System.Windows.Documents.Serialization.SerializerDescriptor> Dostępne są także inne właściwości, takie jak <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> i <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, które aplikacji można używać w celu monitowania użytkownika o wyborze serializator dla formatu dostępnych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="be6ac-142">The <xref:System.Windows.Documents.Serialization.SerializerDescriptor> also provides other properties, such as <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> and <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, which the application can use to prompt the user in selecting a serializer for an available output format.</span></span>  <span data-ttu-id="be6ac-143">Domyślna wtyczka serializatora dla [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] jest dostarczana z [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] i jest zawsze wyliczyć.</span><span class="sxs-lookup"><span data-stu-id="be6ac-143">A default plug-in serializer for [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] is provided with [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] and is always enumerated.</span></span>  <span data-ttu-id="be6ac-144">Po wybraniu przez użytkownika format danych wyjściowych <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> metoda służy do tworzenia <xref:System.Windows.Documents.Serialization.SerializerWriter> dla określonego formatu.</span><span class="sxs-lookup"><span data-stu-id="be6ac-144">After the user selects an output format, the <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> method is used to create a <xref:System.Windows.Documents.Serialization.SerializerWriter> for the specific format.</span></span>  <span data-ttu-id="be6ac-145"><xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> Następnie można wywołać metody do wyjściowego strumienia dokumentów w magazynie danych.</span><span class="sxs-lookup"><span data-stu-id="be6ac-145">The <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> method can then be called to output the document stream to the data store.</span></span>  
  
 <span data-ttu-id="be6ac-146">Poniżej przedstawiono przykładową aplikację, która używa <xref:System.Windows.Documents.Serialization.SerializerProvider> metody we właściwości "PlugInFileFilter".</span><span class="sxs-lookup"><span data-stu-id="be6ac-146">The following example illustrates an application that uses the <xref:System.Windows.Documents.Serialization.SerializerProvider> method in a "PlugInFileFilter" property.</span></span>  <span data-ttu-id="be6ac-147">PlugInFileFilter wylicza zainstalowane dodatki plug-in i tworzy ciąg filtru z opcjami dostępności pliku <xref:Microsoft.Win32.SaveFileDialog>.</span><span class="sxs-lookup"><span data-stu-id="be6ac-147">PlugInFileFilter enumerates the installed plug-ins and builds a filter string with the available file options for a <xref:Microsoft.Win32.SaveFileDialog>.</span></span>  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 <span data-ttu-id="be6ac-148">Po wybraniu przez użytkownika nazwa pliku wyjściowego poniższy przykład przedstawia użycie <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> metody do przechowywania danego dokumentu w określonym formacie.</span><span class="sxs-lookup"><span data-stu-id="be6ac-148">After an output file name has been selected by the user, the following example illustrates use of the <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> method to store a given document in a specified format.</span></span>  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### <a name="installing-plug-in-serializers"></a><span data-ttu-id="be6ac-149">Instalowanie wtyczki serializatorów</span><span class="sxs-lookup"><span data-stu-id="be6ac-149">Installing Plug-in Serializers</span></span>  
 <span data-ttu-id="be6ac-150"><xref:System.Windows.Documents.Serialization.SerializerProvider> Klasa zapewnia interfejs wyższego poziomu dla odnajdywania szeregującego wtyczki i dostępu.</span><span class="sxs-lookup"><span data-stu-id="be6ac-150">The <xref:System.Windows.Documents.Serialization.SerializerProvider> class supplies the upper-level application interface for plug-in serializer discovery and access.</span></span>  <span data-ttu-id="be6ac-151"><xref:System.Windows.Documents.Serialization.SerializerProvider>Lokalizuje i lista aplikacji serializatorów, które są zainstalowane i jest dostępny w systemie.</span><span class="sxs-lookup"><span data-stu-id="be6ac-151"><xref:System.Windows.Documents.Serialization.SerializerProvider> locates and provides the application a list of the serializers that are installed and accessible on the system.</span></span>  <span data-ttu-id="be6ac-152">Szczegółowe informacje na temat zainstalowanych serializatorów są definiowane za pomocą ustawień rejestru.</span><span class="sxs-lookup"><span data-stu-id="be6ac-152">The specifics of the installed serializers are defined through registry settings.</span></span>  <span data-ttu-id="be6ac-153">Wtyczka serializatorów można dodać do rejestru za pomocą <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> metody; lub, jeśli [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] nie jest jeszcze zainstalowany, może skryptu instalacja dodatku bezpośrednio zestaw rejestru wartości samej siebie.</span><span class="sxs-lookup"><span data-stu-id="be6ac-153">Plug-in serializers can be added to the registry by using the <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> method; or if [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] is not yet installed, the plug-in installation script can directly set the registry values itself.</span></span>  <span data-ttu-id="be6ac-154"><xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> Metody można użyć do usunięcia wcześniej zainstalowane wtyczki lub ustawienia rejestru można zresetować podobnie przez skrypt dezinstalacji skryptu.</span><span class="sxs-lookup"><span data-stu-id="be6ac-154">The <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> method can be used to remove a previously installed plug-in, or the registry settings can be reset similarly by an uninstall script.</span></span>  
  
### <a name="creating-a-plug-in-serializer"></a><span data-ttu-id="be6ac-155">Tworzenie szeregującego wtyczki</span><span class="sxs-lookup"><span data-stu-id="be6ac-155">Creating a Plug-in Serializer</span></span>  
 <span data-ttu-id="be6ac-156">Zarówno wtyczki serializatorów połączonego serializatorów korzystanie z tych samych metod publicznych narażonych i zdarzeń i podobnie można zaprojektować działanie synchronicznie lub asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="be6ac-156">Both plug-in serializers and linked serializers use the same exposed public methods and events, and similarly can be designed to operate either synchronously or asynchronously.</span></span>  <span data-ttu-id="be6ac-157">Istnieją trzy podstawowe kroki, które zwykle zachowana w celu utworzenia szeregującego wtyczki:</span><span class="sxs-lookup"><span data-stu-id="be6ac-157">There are three basic steps normally followed to create a plug-in serializer:</span></span>  
  
1.  <span data-ttu-id="be6ac-158">Wdrożenie i debugowania serializator najpierw jako połączony serializatora.</span><span class="sxs-lookup"><span data-stu-id="be6ac-158">Implement and debug the serializer first as a linked serializer.</span></span>  <span data-ttu-id="be6ac-159">Początkowo tworzenie serializator skompilowany i połączone bezpośrednio w aplikacji test zapewnia pełny dostęp do punktów przerwania i innych usług debugowania przydatne do testowania.</span><span class="sxs-lookup"><span data-stu-id="be6ac-159">Initially creating the serializer compiled and linked directly in a test application provides full access to breakpoints and other debug services helpful for testing.</span></span>  
  
2.  <span data-ttu-id="be6ac-160">Po serializator został w pełni przetestowany, <xref:System.Windows.Documents.Serialization.ISerializerFactory> interfejs jest dodawany do tworzenia dodatku plug-in.</span><span class="sxs-lookup"><span data-stu-id="be6ac-160">After the serializer is fully tested, an <xref:System.Windows.Documents.Serialization.ISerializerFactory> interface is added to create a plug-in.</span></span>  <span data-ttu-id="be6ac-161"><xref:System.Windows.Documents.Serialization.ISerializerFactory> Interfejsu zezwala na dostęp do wszystkich [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] obiektów, takich jak drzewa logicznego <xref:System.Windows.UIElement> obiektów, <xref:System.Windows.Documents.IDocumentPaginatorSource>, i <xref:System.Windows.Media.Visual> elementy.</span><span class="sxs-lookup"><span data-stu-id="be6ac-161">The <xref:System.Windows.Documents.Serialization.ISerializerFactory> interface permits full access to all [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] objects which includes the logical tree, <xref:System.Windows.UIElement> objects, <xref:System.Windows.Documents.IDocumentPaginatorSource>, and <xref:System.Windows.Media.Visual> elements.</span></span>  <span data-ttu-id="be6ac-162">Ponadto <xref:System.Windows.Documents.Serialization.ISerializerFactory> zapewnia te same metody synchroniczne i asynchroniczne i zdarzenia używane przez połączone serializatorów.</span><span class="sxs-lookup"><span data-stu-id="be6ac-162">Additionally <xref:System.Windows.Documents.Serialization.ISerializerFactory> provides the same synchronous and asynchronous methods and events used by linked serializers.</span></span>  <span data-ttu-id="be6ac-163">Ponieważ dużych dokumentów może trwać do wyjściowego, operacje asynchroniczne zaleca się obsługa interakcji z użytkownikiem reakcji i oferuje opcji "Anuluj", jeśli występuje problem związany z magazynem danych.</span><span class="sxs-lookup"><span data-stu-id="be6ac-163">Since large documents can take time to output, asynchronous operations are recommended to maintain responsive user interaction and offer a "Cancel" option if some problem occurs with the data store.</span></span>  
  
3.  <span data-ttu-id="be6ac-164">Po utworzeniu szeregującego wtyczki skrypt instalacji jest zaimplementowany dla dystrybucji i instalowanie (i odinstalowywanie) wtyczki (zobacz powyżej, "[Instalowanie dodatku typu Plug-in serializatorów](#InstallingPluginSerializers)").</span><span class="sxs-lookup"><span data-stu-id="be6ac-164">After the plug-in serializer is created, an installation script is implemented for distributing and installing (and uninstalling) the plug-in (see above, "[Installing Plug-in Serializers](#InstallingPluginSerializers)").</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6ac-165">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="be6ac-165">See Also</span></span>  
 <xref:System.Windows.Documents.Serialization>  
 <xref:System.Windows.Xps.XpsDocumentWriter>  
 <xref:System.Windows.Xps.Packaging.XpsDocument>  
 [<span data-ttu-id="be6ac-166">Dokumentów na platformie WPF</span><span class="sxs-lookup"><span data-stu-id="be6ac-166">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="be6ac-167">Omówienie drukowania</span><span class="sxs-lookup"><span data-stu-id="be6ac-167">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="be6ac-168">Formatu XML Paper Specification: omówienie</span><span class="sxs-lookup"><span data-stu-id="be6ac-168">XML Paper Specification: Overview</span></span>](http://go.microsoft.com/fwlink?LinkID=106246)