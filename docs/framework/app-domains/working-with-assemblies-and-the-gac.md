---
title: "Praca z zestawami i globalną pamięcią podręczną zestawów"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0c656cbad746e044a6dbf187ce86fd4738d6ef98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a><span data-ttu-id="6ac02-102">Praca z zestawami i globalną pamięcią podręczną zestawów</span><span class="sxs-lookup"><span data-stu-id="6ac02-102">Working with Assemblies and the Global Assembly Cache</span></span>
<span data-ttu-id="6ac02-103">Jeśli zestaw ma być współużytkowany przez kilka aplikacji, można go zainstalować w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6ac02-103">If you intend to share an assembly among several applications, you can install it into the global assembly cache.</span></span> <span data-ttu-id="6ac02-104">Każdy komputer z zainstalowanym środowiskiem uruchomieniowym języka wspólnego posiada tę pamięć podręczną kodu dla całego komputera.</span><span class="sxs-lookup"><span data-stu-id="6ac02-104">Each computer where the common language runtime is installed has this machine-wide code cache.</span></span> <span data-ttu-id="6ac02-105">Globalna pamięć podręczna zestawów przechowuje zestawy wyznaczonych być współużytkowane przez kilka aplikacji na komputerze.</span><span class="sxs-lookup"><span data-stu-id="6ac02-105">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span> <span data-ttu-id="6ac02-106">Aby zestaw można było zainstalować w globalnej pamięci podręcznej zestawów, musi mieć silną nazwę.</span><span class="sxs-lookup"><span data-stu-id="6ac02-106">An assembly must have a strong name to be installed in the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ac02-107">Zestawy umieszczone w globalnej pamięci podręcznej zestawów muszą mieć taką samą nazwę zestawu i pliku (bez rozszerzenia pliku).</span><span class="sxs-lookup"><span data-stu-id="6ac02-107">Assemblies placed in the global assembly cache must have the same assembly name and file name (not including the file name extension).</span></span> <span data-ttu-id="6ac02-108">Na przykład zestaw o nazwie myAssembly musi mieć nazwę pliku myAssembly.exe lub myAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="6ac02-108">For example, an assembly with the assembly name of myAssembly must have a file name of either myAssembly.exe or myAssembly.dll.</span></span>  
  
 <span data-ttu-id="6ac02-109">Udostępnianie zestawów poprzez instalowanie ich w globalnej pamięci podręcznej zestawów należy stosować tylko w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="6ac02-109">You should share assemblies by installing them into the global assembly cache only when necessary.</span></span> <span data-ttu-id="6ac02-110">Ogólna wytyczna stanowi, iż zależności zestawów powinny pozostawać poufne, a zestawy należy umieszczać w katalogu aplikacji, chyba że współużytkowanie zestawu jest wyraźnie wymagane.</span><span class="sxs-lookup"><span data-stu-id="6ac02-110">As a general guideline, keep assembly dependencies private and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="6ac02-111">Ponadto nie trzeba instalować zestawów w globalnej pamięci podręcznej zestawów, aby je udostępnić usłudze międzyoperacyjnej modelu COM lub kodowi niezarządzanemu.</span><span class="sxs-lookup"><span data-stu-id="6ac02-111">In addition, you do not have to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
 <span data-ttu-id="6ac02-112">Istnieje kilka powodów, dla których instalowanie zestawu w globalnej pamięci podręcznej zestawów może się okazać konieczne:</span><span class="sxs-lookup"><span data-stu-id="6ac02-112">There are several reasons why you might want to install an assembly into the global assembly cache:</span></span>  
  
-   <span data-ttu-id="6ac02-113">Udostępniona lokalizacja.</span><span class="sxs-lookup"><span data-stu-id="6ac02-113">Shared location.</span></span>  
  
     <span data-ttu-id="6ac02-114">Zestawy, które powinny być używane przez aplikacje, można umieścić w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6ac02-114">Assemblies that should be used by applications can be put in the global assembly cache.</span></span> <span data-ttu-id="6ac02-115">Jeśli na przykład wszystkie aplikacje powinny używać zestawu znajdującego się w globalnej pamięci podręcznej zestawów, do pliku Machine.config można dodać instrukcje zasad dotyczących wersji, które przekierowują odwołania do zestawu.</span><span class="sxs-lookup"><span data-stu-id="6ac02-115">For example, if all applications should use an assembly located in the global assembly cache, a version policy statement can be added to the Machine.config file that redirects references to the assembly.</span></span>  
  
-   <span data-ttu-id="6ac02-116">Bezpieczeństwo plików.</span><span class="sxs-lookup"><span data-stu-id="6ac02-116">File security.</span></span>  
  
     <span data-ttu-id="6ac02-117">Administratorzy często chronią główny katalog systemowy przy użyciu listy kontroli dostępu (ACL), która decyduje o uprawnieniach zapisu i wykonywania.</span><span class="sxs-lookup"><span data-stu-id="6ac02-117">Administrators often protect the systemroot directory using an Access Control List (ACL) to control write and execute access.</span></span> <span data-ttu-id="6ac02-118">Ponieważ globalna pamięć podręczna zestawów jest instalowana w głównym katalogu systemowym, dziedziczy listę kontroli dostępu tego katalogu.</span><span class="sxs-lookup"><span data-stu-id="6ac02-118">Because the global assembly cache is installed in the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="6ac02-119">Zaleca się, że tylko użytkownicy z uprawnieniami administratora można usunąć pliki z pamięci podręcznej GAC.</span><span class="sxs-lookup"><span data-stu-id="6ac02-119">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
-   <span data-ttu-id="6ac02-120">Przechowywanie wersji Side-by-side.</span><span class="sxs-lookup"><span data-stu-id="6ac02-120">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="6ac02-121">W globalnej pamięci podręcznej zestawów można przechowywać wiele kopii zestawów o takiej samej nazwie, ale różnych informacjach o wersji.</span><span class="sxs-lookup"><span data-stu-id="6ac02-121">Multiple copies of assemblies with the same name but different version information can be maintained in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="6ac02-122">Dodatkowa lokalizacja wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="6ac02-122">Additional search location.</span></span>  
  
     <span data-ttu-id="6ac02-123">Środowisko uruchomieniowe języka wspólnego najpierw sprawdza globalną pamięć podręczną zestawów w poszukiwaniu zestawu, który pasuje do żądania o zestaw, a dopiero potem wykonuje sondowanie lub używa informacji o bazie kodu w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="6ac02-123">The common language runtime checks the global assembly cache for an assembly that matches the assembly request before probing or using the codebase information in a configuration file.</span></span>  
  
 <span data-ttu-id="6ac02-124">Istnieją też scenariusze, w których nie należy jawnie instalować zestawów w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6ac02-124">Note that there are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="6ac02-125">Umieszczenie w tej pamięci jednego z zestawów tworzących aplikację sprawi, że nie będzie już można zreplikować ani zainstalować aplikacji przy użyciu polecenia XCOPY kopiującego katalog aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ac02-125">If you place one of the assemblies that make up an application into the global assembly cache, you can no longer replicate or install the application by using XCOPY to copy the application directory.</span></span> <span data-ttu-id="6ac02-126">W takim przypadku należy również przenieść zestaw do globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6ac02-126">In this case, you must also move the assembly into the global assembly cache.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ac02-127">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="6ac02-127">In This Section</span></span>  
 [<span data-ttu-id="6ac02-128">Porady: Instalowanie zestawu w globalnej pamięci podręcznej zestawów</span><span class="sxs-lookup"><span data-stu-id="6ac02-128">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 <span data-ttu-id="6ac02-129">Opis sposobów instalowania zestawu w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6ac02-129">Describes the ways to install an assembly into the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6ac02-130">Porady: wyświetlanie zawartości globalnej pamięci podręcznej zestawów</span><span class="sxs-lookup"><span data-stu-id="6ac02-130">How to: View the Contents of the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)  
 <span data-ttu-id="6ac02-131">Wyjaśniono, jak używać [Gacutil.exe (narzędzie globalnej pamięci podręcznej zestawów)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) do wyświetlania zawartości pamięci podręcznej GAC.</span><span class="sxs-lookup"><span data-stu-id="6ac02-131">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6ac02-132">Porady: usuwanie zestawu z globalnej pamięci podręcznej zestawów</span><span class="sxs-lookup"><span data-stu-id="6ac02-132">How to: Remove an Assembly from the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 <span data-ttu-id="6ac02-133">Wyjaśniono, jak używać [Gacutil.exe (narzędzie globalnej pamięci podręcznej zestawów)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) usunięcie zestawu z globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6ac02-133">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to remove an assembly from the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6ac02-134">Używanie obsługiwanych składników z globalnej pamięci podręcznej zestawów</span><span class="sxs-lookup"><span data-stu-id="6ac02-134">Using Serviced Components with the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/use-serviced-components-with-the-gac.md)  
 <span data-ttu-id="6ac02-135">Wyjaśnienie, dlaczego obsługiwane składniki (zarządzanie składniki modelu COM+) należy umieszczać w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6ac02-135">Explains why serviced components (managed COM+ components) should be placed in the global assembly cache.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6ac02-136">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="6ac02-136">Related Sections</span></span>  
 [<span data-ttu-id="6ac02-137">Tworzenie zestawów</span><span class="sxs-lookup"><span data-stu-id="6ac02-137">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="6ac02-138">Omówienie procesu tworzenia zestawów.</span><span class="sxs-lookup"><span data-stu-id="6ac02-138">Provides an overview of creating assemblies.</span></span>  
  
 [<span data-ttu-id="6ac02-139">Globalna pamięć podręczna zestawów</span><span class="sxs-lookup"><span data-stu-id="6ac02-139">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 <span data-ttu-id="6ac02-140">Opis globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6ac02-140">Describes the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6ac02-141">Porady: wyświetlanie zawartości zestawu</span><span class="sxs-lookup"><span data-stu-id="6ac02-141">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="6ac02-142">Wyjaśniono, jak używać [Ildasm.exe (dezasembler IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) Aby wyświetlić informacje o języku pośrednim (MSIL) firmy Microsoft w zestawie.</span><span class="sxs-lookup"><span data-stu-id="6ac02-142">Explains how to use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in an assembly.</span></span>  
  
 [<span data-ttu-id="6ac02-143">Jak lokalizuje zestawów przez środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="6ac02-143">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="6ac02-144">Wyjaśnienie, jak środowisko uruchomieniowe języka wspólnego lokalizuje i ładuje zestawy składające się na aplikację.</span><span class="sxs-lookup"><span data-stu-id="6ac02-144">Describes how the common language runtime locates and loads the assemblies that make up your application.</span></span>  
  
 [<span data-ttu-id="6ac02-145">Programowanie za pomocą zestawów</span><span class="sxs-lookup"><span data-stu-id="6ac02-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="6ac02-146">Opis koncepcji zestawów jako bloków konstrukcyjnych zarządzanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6ac02-146">Describes assemblies, the building blocks of managed applications.</span></span>