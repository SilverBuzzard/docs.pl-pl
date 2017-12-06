---
title: "Zgodność wersji w programie .NET Framework"
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework 4.5, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 166d61339d2b74f378b50ade4b78fd41e9692f76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="version-compatibility-in-the-net-framework"></a><span data-ttu-id="3f750-102">Zgodność wersji w programie .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3f750-102">Version Compatibility in the .NET Framework</span></span>
<span data-ttu-id="3f750-103">Zgodności z poprzednimi wersjami oznacza, że aplikacja, która została opracowana dla określonej wersji platformy będzie działać w nowszych wersjach tej platformy.</span><span class="sxs-lookup"><span data-stu-id="3f750-103">Backward compatibility means that an app that was developed for a particular version of a platform will run on later versions of that platform.</span></span> <span data-ttu-id="3f750-104">Próbuje zmaksymalizować zgodności z poprzednimi wersjami programu .NET Framework: źródła kodu napisanego dla jednej wersji programu .NET Framework należy skompilować w nowszych wersjach programu .NET Framework i zachowania tak samo w przypadku plików binarnych, działających w jednej wersji programu .NET Framework nowsze wersje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f750-104">The .NET Framework tries to maximize backward compatibility: Source code written for one version of the .NET Framework should compile on later versions of the .NET Framework, and binaries that run on one version of the .NET Framework should behave identically on later versions of the .NET Framework.</span></span>  
  
<a name="Apps"></a>   
## <a name="version-compatibility-for-apps"></a><span data-ttu-id="3f750-105">Kompatybilność wersji dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="3f750-105">Version compatibility for apps</span></span>  
 <span data-ttu-id="3f750-106">Domyślnie aplikacja jest uruchamiana w tej wersji programu .NET Framework, który został utworzony dla.</span><span class="sxs-lookup"><span data-stu-id="3f750-106">By default, an app runs on the version of the .NET Framework that it was built for.</span></span> <span data-ttu-id="3f750-107">Jeśli nie jest obecny i pliku konfiguracji aplikacji nie definiuje wersji, może wystąpić błąd inicjowania programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f750-107">If that version is not present and the app configuration file does not define supported versions, a .NET Framework initialization error may occur.</span></span> <span data-ttu-id="3f750-108">W takim przypadku do uruchomienia aplikacji nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="3f750-108">In this case, the attempt to run the app will fail.</span></span>  
  
 <span data-ttu-id="3f750-109">Aby zdefiniować określonych wersji, na których aplikacja będzie działać, należy dodać co najmniej jeden [ \<supportedRuntime >](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) elementy do pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="3f750-109">To define the specific versions on which your app runs, add one or more [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) elements to your app's configuration file.</span></span> <span data-ttu-id="3f750-110">Każdy `<supportedRuntime>` element zawiera obsługiwaną wersję środowiska uruchomieniowego przy pierwszym określanie wersji najlepszy możliwy oraz za ostatni określanie wersji najmniej preferowanych.</span><span class="sxs-lookup"><span data-stu-id="3f750-110">Each `<supportedRuntime>` element lists a supported version of the runtime, with the first specifying the most preferred version and the last specifying the least preferred version.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v2.0.50727" />  
      <supportedRuntime version="v4.0" />  
   </startup>  
</configuration>  
```  
  
 <span data-ttu-id="3f750-111">Aby uzyskać więcej informacji, zobacz [porady: Konfigurowanie aplikacji do obsługi platformy .NET Framework 4 lub 4.x](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md).</span><span class="sxs-lookup"><span data-stu-id="3f750-111">For more information, see [How to: Configure an App to Support .NET Framework 4 or 4.x](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md).</span></span>  
  
## <a name="version-compatibility-for-components"></a><span data-ttu-id="3f750-112">Kompatybilność wersji dla składników</span><span class="sxs-lookup"><span data-stu-id="3f750-112">Version compatibility for components</span></span>  
 <span data-ttu-id="3f750-113">Aplikację można kontrolować wersji programu .NET Framework, na którym działa, ale nie składnika.</span><span class="sxs-lookup"><span data-stu-id="3f750-113">An app can control the version of the .NET Framework on which it runs, but a component cannot.</span></span> <span data-ttu-id="3f750-114">Składniki i biblioteki klas są ładowane w ramach danej aplikacji, a w związku z tym automatycznego uruchamiania na wersji programu .NET Framework, która aplikacja jest uruchamiana na.</span><span class="sxs-lookup"><span data-stu-id="3f750-114">Components and class libraries are loaded in the context of a particular app, and therefore automatically run on the version of the .NET Framework that the app runs on.</span></span>  
  
 <span data-ttu-id="3f750-115">Z powodu tego ograniczenia gwarancje zgodności są szczególnie istotne dla składników.</span><span class="sxs-lookup"><span data-stu-id="3f750-115">Because of this restriction, compatibility guarantees are especially important for components.</span></span> <span data-ttu-id="3f750-116">Począwszy od programu .NET Framework 4, można określić stopień, do którego składnik oczekuje się w celu zachowania zgodności w różnych wersjach, stosując <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType> atrybutu dla tego składnika.</span><span class="sxs-lookup"><span data-stu-id="3f750-116">Starting with the .NET Framework 4, you can specify the degree to which a component is expected to remain compatible across multiple versions by applying the <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType> attribute to that component.</span></span> <span data-ttu-id="3f750-117">Narzędzia można użyć tego atrybutu, aby wykryć potencjalnych naruszeń zgodności gwarantuje w przyszłych wersjach składnika.</span><span class="sxs-lookup"><span data-stu-id="3f750-117">Tools can use this attribute to detect potential violations of the compatibility guarantee in future versions of a component.</span></span>  
  
## <a name="backward-compatibility-and-the-net-framework-45"></a><span data-ttu-id="3f750-118">Zgodność z poprzednimi wersjami i .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3f750-118">Backward compatibility and the .NET Framework 4.5</span></span>  
 <span data-ttu-id="3f750-119">.NET Framework 4.5 lub nowszy jest zgodny z aplikacjami, które zostały utworzone we wcześniejszych wersjach programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f750-119">The .NET Framework 4.5 and later versions are backward-compatible with apps that were built with earlier versions of the .NET Framework.</span></span> <span data-ttu-id="3f750-120">Innymi słowy aplikacje i składniki utworzone w poprzednich wersjach będzie działać bez żadnych modyfikacji w programie .NET Framework 4.5 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="3f750-120">In other words, apps and components built with previous versions will work without modification on the .NET Framework 4.5 and later versions.</span></span> <span data-ttu-id="3f750-121">Domyślnie aplikacje uruchamiać na wersji środowiska CLR, dla którego zostały opracowane, więc musisz podać plik konfiguracji do włączenia aplikacji do uruchamiania na .NET Framework 4.5 lub nowszy.</span><span class="sxs-lookup"><span data-stu-id="3f750-121">However, by default, apps run on the version of the common language runtime for which they were developed, so you may have to provide a configuration file to enable your app to run on the .NET Framework 4.5 or later versions.</span></span> <span data-ttu-id="3f750-122">Aby uzyskać więcej informacji, zobacz [kompatybilność wersji dla aplikacji](#Apps) wcześniej w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="3f750-122">For more information, see the [Version compatibility for apps](#Apps) section earlier in this article.</span></span>  
  
 <span data-ttu-id="3f750-123">W praktyce to zgodności można uszkodzony pozornie wpływu zmiany w .NET Framework i zmian w technik programowania.</span><span class="sxs-lookup"><span data-stu-id="3f750-123">In practice, this compatibility can be broken by seemingly inconsequential changes in the .NET Framework and changes in programming techniques.</span></span> <span data-ttu-id="3f750-124">Lepsza wydajność programu .NET Framework 4.5 mogą na przykład ujawnić sytuacji wyścigu, które nie były wykonywane we wcześniejszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="3f750-124">For example, performance improvements in the .NET Framework 4.5 can expose a race condition that did not occur on earlier versions.</span></span> <span data-ttu-id="3f750-125">Podobnie, przy użyciu ścieżki ustalony do zestawów platformy .NET Framework, wykonywanie porównanie równości z określoną wersją programu .NET Framework i pobierania wartości pola prywatnej przy użyciu odbicia nie są zapewniającej rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="3f750-125">Similarly, using a hard-coded path to .NET Framework assemblies, performing an equality comparison with a particular version of the .NET Framework, and getting the value of a private field by using reflection are not backward-compatible practices.</span></span> <span data-ttu-id="3f750-126">Ponadto każda wersja programu .NET Framework obejmuje poprawki błędów i zmiany dotyczące zabezpieczeń, które mogą wpłynąć na zgodność niektóre aplikacje i składniki.</span><span class="sxs-lookup"><span data-stu-id="3f750-126">In addition, each version of the .NET Framework includes bug fixes and security-related changes that can affect the compatibility of some apps and components.</span></span>  
  
 <span data-ttu-id="3f750-127">Jeśli aplikację lub składnik nie działa zgodnie z oczekiwaniami w .NET Framework 4.5 (łącznie z jego wersje punktu [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 lub 4.7.1, użyj poniższej listy kontrolne:</span><span class="sxs-lookup"><span data-stu-id="3f750-127">If your app or component does not work as expected on the .NET Framework 4.5 (including its point releases, the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, or 4.7.1, use the following checklists:</span></span>  
  
-  <span data-ttu-id="3f750-128">Jeśli aplikacja został opracowany, aby uruchomić w dowolnej wersji systemu .NET Framework, począwszy od programu .NET Framework 4.0, zobacz [zgodność aplikacji w programie .NET Framework](application-compatibility.md) do wygenerowania listy zmian między sieci docelowej wersji .NET Framework i wersji, na którym jest uruchomiona aplikacja.</span><span class="sxs-lookup"><span data-stu-id="3f750-128">If your app was developed to run on any version of the .NET Framework starting with the .NET Framework 4.0, see [Application Compatibility in the .NET Framework](application-compatibility.md) to generate lists of changes between your targeted .NET Framework version and the version on which your app is running.</span></span>  

- <span data-ttu-id="3f750-129">Jeśli masz aplikację .NET Framework 3.5, zobacz też [zagadnienia migracji programu .NET Framework 4](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3f750-129">If you have a .NET Framework 3.5 app, also see [.NET Framework 4 Migration Issues](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md).</span></span>

- <span data-ttu-id="3f750-130">Jeśli masz aplikację .NET Framework 2.0, zobacz też [zmiany w programie .NET Framework 3.5 z dodatkiem SP1](http://go.microsoft.com/fwlink/?LinkId=186989).</span><span class="sxs-lookup"><span data-stu-id="3f750-130">If you have a .NET Framework 2.0 app, also see [Changes in .NET Framework 3.5 SP1](http://go.microsoft.com/fwlink/?LinkId=186989).</span></span>

- <span data-ttu-id="3f750-131">Jeśli masz aplikację .NET Framework 1.1, zobacz też [zmiany w programie .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkID=125263).</span><span class="sxs-lookup"><span data-stu-id="3f750-131">If you have a .NET Framework 1.1 app, also see [Changes in .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkID=125263).</span></span>  
  
-   <span data-ttu-id="3f750-132">Jeśli są ponowną kompilację istniejącego kodu źródłowego do uruchamiania na .NET Framework 4.5 lub jego punktu wersjach lub jeśli tworzysz nową wersję aplikacji lub składnika, którego celem jest [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] lub jego punktu zwalnia z istniejących wyboru podstawowej, kod źródłowy [ Co to jest przestarzałe w bibliotece klas](../../../docs/framework/whats-new/whats-obsolete.md) przestarzałe typy i składniki oraz zastosowanie obejścia problemu opisanego.</span><span class="sxs-lookup"><span data-stu-id="3f750-132">If you are recompiling existing source code to run on the .NET Framework 4.5 or its point releases, or if you are developing a new version of an app or component that targets the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or its point releases from an existing source code base, check [What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md) for obsolete types and members, and apply the workaround described.</span></span> <span data-ttu-id="3f750-133">(Wcześniej skompilowany kod będzie nadal działać względem typów i elementów członkowskich, które zostały oznaczone jako przestarzałe.)</span><span class="sxs-lookup"><span data-stu-id="3f750-133">(Previously compiled code will continue to run against types and members that have been marked as obsolete.)</span></span>  
  
-   <span data-ttu-id="3f750-134">Jeśli okaże się, że zmiany w [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] uległ aplikację wyboru [schemat ustawień środowiska uruchomieniowego](../../../docs/framework/configure-apps/file-schema/runtime/index.md) ustalenie, czy umożliwia ustawienie środowiska uruchomieniowego w pliku konfiguracyjnym aplikacji Przywróć poprzednie.</span><span class="sxs-lookup"><span data-stu-id="3f750-134">If you determine that a change in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] has broken your app, check the [Runtime Settings Schema](../../../docs/framework/configure-apps/file-schema/runtime/index.md) to determine whether you can use a runtime setting in your app's configuration file to restore the previous behavior.</span></span>  
  
-   <span data-ttu-id="3f750-135">Jeśli napotkasz problem, który nie jest udokumentowany pliku [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=154815) usterek i skontaktuj się z [ netfxcf@microsoft.com ](mailto:netfxcf@microsoft.com) numer błędu.</span><span class="sxs-lookup"><span data-stu-id="3f750-135">If you encounter an issue that is not documented, file a [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=154815) bug and contact [netfxcf@microsoft.com](mailto:netfxcf@microsoft.com) with the bug number.</span></span>  
  
## <a name="compatibility-and-side-by-side-execution"></a><span data-ttu-id="3f750-136">Zgodność i side-by-side wykonywania</span><span class="sxs-lookup"><span data-stu-id="3f750-136">Compatibility and side-by-side execution</span></span>  
 <span data-ttu-id="3f750-137">Jeśli nie można znaleźć odpowiedniego rozwiązania, opis problemu, należy pamiętać, że program .NET Framework 4.5 (lub jeden z jego wersje punktu) działa równolegle z wersji 1.1, 2.0 i 3.5 i jest dostępna aktualizacja w miejscu, które zastępuje w wersji 4.</span><span class="sxs-lookup"><span data-stu-id="3f750-137">If you cannot find a suitable workaround for your issue, remember that the .NET Framework 4.5 (or one of its point releases) runs side by side with versions 1.1, 2.0, and 3.5, and is an in-place update that replaces version 4.</span></span> <span data-ttu-id="3f750-138">Dla aplikacji, które odnoszą się do wersji 1.1, 2.0 i 3.5 można zainstalować odpowiednią wersję programu .NET Framework na komputerze docelowym, aby uruchomić aplikację w jego najlepsze środowisko.</span><span class="sxs-lookup"><span data-stu-id="3f750-138">For apps that target versions 1.1, 2.0, and 3.5, you can install the appropriate version of the .NET Framework on the target machine to run the app in its best environment.</span></span> <span data-ttu-id="3f750-139">Aby uzyskać więcej informacji na temat wykonywania side-by-side, zobacz [wykonywania Side-by-Side](../../../docs/framework/deployment/side-by-side-execution.md).</span><span class="sxs-lookup"><span data-stu-id="3f750-139">For more information about side-by-side execution, see [Side-by-Side Execution](../../../docs/framework/deployment/side-by-side-execution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f750-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3f750-140">See Also</span></span>  
 [<span data-ttu-id="3f750-141">Nowości</span><span class="sxs-lookup"><span data-stu-id="3f750-141">What's New</span></span>](../../../docs/framework/whats-new/index.md)  
 [<span data-ttu-id="3f750-142">Co to jest przestarzałe w bibliotece klas</span><span class="sxs-lookup"><span data-stu-id="3f750-142">What's Obsolete in the Class Library</span></span>](../../../docs/framework/whats-new/whats-obsolete.md)  
 [<span data-ttu-id="3f750-143">Zgodność aplikacji</span><span class="sxs-lookup"><span data-stu-id="3f750-143">Application Compatibility</span></span>](../../../docs/framework/migration-guide/application-compatibility.md)  
 [<span data-ttu-id="3f750-144">Wsparcia technicznego produktów firmy Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3f750-144">Microsoft .NET Framework Support Lifecycle Policy</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=248212)  
 [<span data-ttu-id="3f750-145">Problemy dotyczące programu .NET framework 4 migracji</span><span class="sxs-lookup"><span data-stu-id="3f750-145">.NET Framework 4 Migration Issues</span></span>](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)