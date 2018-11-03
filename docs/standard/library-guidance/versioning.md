---
title: Biblioteki i przechowywania wersji platformy .NET
description: Zalecenia dotyczące najlepszych rozwiązań dla wersji bibliotek platformy .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: f95c8ade1f91af5c13184b839b327c9397c6fe5a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187861"
---
# <a name="versioning"></a><span data-ttu-id="a1fc1-103">Przechowywanie wersji</span><span class="sxs-lookup"><span data-stu-id="a1fc1-103">Versioning</span></span>

<span data-ttu-id="a1fc1-104">Biblioteka oprogramowania rzadko zakończeniu w wersji 1.0.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-104">A software library is rarely complete in version 1.0.</span></span> <span data-ttu-id="a1fc1-105">Dobre bibliotek z czasem ewoluować, dodawanie funkcji, naprawianie błędów i poprawę wydajności.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-105">Good libraries evolve over time, adding features, fixing bugs and improving performance.</span></span> <span data-ttu-id="a1fc1-106">Należy pamiętać, że można zwolnić nowe wersje biblioteki .NET, zapewniając dodatkową wartość z każdą wersją, bez przerywania istniejących użytkowników.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-106">It is important that you can release new versions of a .NET library, providing additional value with each version, without breaking existing users.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="a1fc1-107">Fundamentalne zmiany</span><span class="sxs-lookup"><span data-stu-id="a1fc1-107">Breaking changes</span></span>

<span data-ttu-id="a1fc1-108">Aby uzyskać informacje na temat przełomowych zmian między wersjami obsługi, zobacz [istotne zmiany w](./breaking-changes.md).</span><span class="sxs-lookup"><span data-stu-id="a1fc1-108">For information about handling breaking changes between versions, see [Breaking changes](./breaking-changes.md).</span></span>

## <a name="version-numbers"></a><span data-ttu-id="a1fc1-109">Numery wersji</span><span class="sxs-lookup"><span data-stu-id="a1fc1-109">Version numbers</span></span>

<span data-ttu-id="a1fc1-110">Biblioteka .NET zawiera wiele sposobów, aby określić wersję.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-110">A .NET library has many ways to specify a version.</span></span> <span data-ttu-id="a1fc1-111">Te wersje są dla Ciebie najważniejsze:</span><span class="sxs-lookup"><span data-stu-id="a1fc1-111">These versions are the most important:</span></span>

### <a name="nuget-package-version"></a><span data-ttu-id="a1fc1-112">Wersja pakietu NuGet</span><span class="sxs-lookup"><span data-stu-id="a1fc1-112">NuGet package version</span></span>

<span data-ttu-id="a1fc1-113">[Pakietu NuGet w wersji](/nuget/reference/package-versioning) jest wyświetlana w witrynie NuGet.org, Menedżer pakietów NuGet usługi Visual Studio i jest dodawany do kodu źródłowego, gdy jest używany pakiet.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-113">The [NuGet package version](/nuget/reference/package-versioning) is displayed on NuGet.org, the Visual Studio NuGet package manager, and is added to source code when the package is used.</span></span> <span data-ttu-id="a1fc1-114">Wersja pakietu NuGet jest często będzie widoczna dla użytkowników numeru wersji i będzie odnoszą się do niego podczas rozmawiamy o wersji biblioteki, używane.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-114">The NuGet package version is the version number users will commonly see, and they'll refer to it when they talk about the version of a library they're using.</span></span> <span data-ttu-id="a1fc1-115">Wersja pakietu NuGet jest używany przez NuGet i nie ma wpływu na zachowanie środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-115">The NuGet package version is used by NuGet and has no effect on runtime behavior.</span></span>

```xml
<PackageVersion>1.0.0-alpha1</PackageVersion>
```

<span data-ttu-id="a1fc1-116">Identyfikator pakietu NuGet, które są połączone z wersji pakietu NuGet służy do identyfikowania pakiet nuget.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-116">The NuGet package identifier combined with the NuGet package version is used to identify a package in NuGet.</span></span> <span data-ttu-id="a1fc1-117">Na przykład `Newtonsoft.Json`  +  `11.0.2`.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-117">For example, `Newtonsoft.Json` + `11.0.2`.</span></span> <span data-ttu-id="a1fc1-118">Pakiet z sufiksem to pakiet wersji wstępnej i ma specjalne zachowanie, który sprawia, że niezwykle przydatna przy testowaniu.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-118">A package with a suffix is a pre-release package and has special behavior that makes it ideal for testing.</span></span> <span data-ttu-id="a1fc1-119">Aby uzyskać więcej informacji, zobacz [pakiety w wersji wstępnej](./nuget.md#pre-release-packages).</span><span class="sxs-lookup"><span data-stu-id="a1fc1-119">For more information, see [Pre-release packages](./nuget.md#pre-release-packages).</span></span>

<span data-ttu-id="a1fc1-120">Ponieważ wersja pakietu NuGet jest najbardziej widoczne wersji dla deweloperów, to dobry pomysł, aby zaktualizować go za pomocą [Semantic Versioning (SemVer)](https://semver.org/).</span><span class="sxs-lookup"><span data-stu-id="a1fc1-120">Because the NuGet package version is the most visible version to developers, it's a good idea to update it using [Semantic Versioning (SemVer)](https://semver.org/).</span></span> <span data-ttu-id="a1fc1-121">SemVer oznacza znaczenie zmiany między wersji, a także pomaga deweloperom podjąć świadomą decyzję, wybierając jakie wersję do użycia.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-121">SemVer indicates the significance of changes between release and helps developers make an informed decision when choosing what version to use.</span></span> <span data-ttu-id="a1fc1-122">Na przykład, przechodząc od `1.0` do `2.0` oznacza, że są potencjalnie przełomowe zmiany.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-122">For example, going from `1.0` to `2.0` indicates that there are potentially breaking changes.</span></span>

<span data-ttu-id="a1fc1-123">**ROZWAŻ ✔️** przy użyciu [SemVer 2.0.0](https://semver.org/) do wersji pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-123">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="a1fc1-124">**CZY ✔️** używać wersji pakietu NuGet w publiczną dokumentację, ponieważ numer wersji, którą użytkownicy zobaczą często.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-124">**✔️ DO** use the NuGet package version in public documentation as it's the version number that users will commonly see.</span></span>

<span data-ttu-id="a1fc1-125">**CZY ✔️** zawierać sufiks wersji wstępnej, podczas przekazywania pakietu niż wersja stabilna.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-125">**✔️ DO** include a pre-release suffix when releasing a non-stable package.</span></span>

> <span data-ttu-id="a1fc1-126">Użytkownicy muszą zgadzaj się na wprowadzenie pakiety w wersji wstępnej, dzięki czemu będzie zrozumiałe, że pakiet nie została zakończona.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-126">Users must opt in to getting pre-release packages, so they will understand that the package is not complete.</span></span>

### <a name="assembly-version"></a><span data-ttu-id="a1fc1-127">Wersja zestawu</span><span class="sxs-lookup"><span data-stu-id="a1fc1-127">Assembly version</span></span>

<span data-ttu-id="a1fc1-128">Wersja zestawu jest środowisko CLR używa w czasie wykonywania, aby wybrać wersję zestawu do załadowania.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-128">The assembly version is what the CLR uses at runtime to select which version of an assembly to load.</span></span> <span data-ttu-id="a1fc1-129">Wybieranie zestawu przy użyciu tylko wersji mają zastosowanie do zestawów o silnej nazwie.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-129">Selecting an assembly using versioning only applies to assemblies with a strong name.</span></span>

```xml
<AssemblyVersion>1.0.0.0</AssemblyVersion>
```

<span data-ttu-id="a1fc1-130">Windows .NET Framework w CLR wymaga dokładnie dopasowany do obciążenia silne silną.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-130">The Windows .NET Framework CLR demands an exact match to load a strong named assembly.</span></span> <span data-ttu-id="a1fc1-131">Na przykład `Libary1, Version=1.0.0.0` został skompilowany z odwołaniem do `Newtonsoft.Json, Version=11.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-131">For example, `Libary1, Version=1.0.0.0` was compiled with a reference to `Newtonsoft.Json, Version=11.0.0.0`.</span></span> <span data-ttu-id="a1fc1-132">.NET Framework załaduje tylko tej wersji dokładnie `11.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-132">The .NET Framework will only load that exact version `11.0.0.0`.</span></span> <span data-ttu-id="a1fc1-133">Aby załadować innej wersji w czasie wykonywania, należy dodać przekierowanie powiązania do pliku konfiguracji aplikacji .NET.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-133">To load a different version at runtime, a binding redirect must be added to the .NET application's config file.</span></span>

<span data-ttu-id="a1fc1-134">Silne nazwy w połączeniu z wersji zestawu umożliwia [ładowania wersji zestawu strict](../../framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="a1fc1-134">Strong naming combined with assembly version enables [strict assembly version loading](../../framework/app-domains/assembly-versioning.md).</span></span> <span data-ttu-id="a1fc1-135">Chociaż silnych nazw biblioteki ma wiele korzyści, często powoduje wyjątki środowiska uruchomieniowego, których nie można znaleźć zestawu i [wymaga przekierowania powiązań](../../framework/configure-apps/redirect-assembly-versions.md) w `app.config` / `web.config` naprawy.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-135">While strong naming a library has a number of benefits, it often results in runtime exceptions that an assembly can't be found and [requires binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) in `app.config`/`web.config` to be fixed.</span></span> <span data-ttu-id="a1fc1-136">Ładowanie zestawu .NET core została swobodna i .NET Core CLR zostanie automatycznie załadowany zestawów w czasie wykonywania za pomocą nowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-136">.NET Core assembly loading has been relaxed, and the .NET Core CLR will automatically load assemblies at runtime with a higher version.</span></span>

<span data-ttu-id="a1fc1-137">**ROZWAŻ ✔️** tylko tym wersja główna w AssemblyVersion.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-137">**✔️ CONSIDER** only including a major version in the AssemblyVersion.</span></span>

> <span data-ttu-id="a1fc1-138">np. 1.0 biblioteki i biblioteki 1.0.1 zarówno mają AssemblyVersion z `1.0.0.0`, podczas gdy biblioteki w wersji 2.0 ma AssemblyVersion z `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-138">e.g. Library 1.0 and Library 1.0.1 both have an AssemblyVersion of `1.0.0.0`, while Library 2.0 has AssemblyVersion of `2.0.0.0`.</span></span> <span data-ttu-id="a1fc1-139">Jeśli wersja zestawu zmienia się rzadziej, zmniejsza przekierowań powiązań.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-139">When the assembly version changes less often, it reduces binding redirects.</span></span>

<span data-ttu-id="a1fc1-140">**ROZWAŻ ✔️** synchronizacja główny numer wersji AssemblyVersion i wersję pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-140">**✔️ CONSIDER** keeping the major version number of the AssemblyVersion and the NuGet package version in sync.</span></span>

> <span data-ttu-id="a1fc1-141">AssemblyVersion znajduje się w niektórych komunikaty informacyjne, wyświetlana użytkownikowi, np. Nazwa zestawu i zestawu kwalifikowane nazwy typów w komunikaty o wyjątkach.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-141">The AssemblyVersion is included in some informational messages displayed to the user, e.g. the assembly name and assembly qualified type names in exception messages.</span></span> <span data-ttu-id="a1fc1-142">Utrzymywanie relacji między wersjami zawiera więcej informacji dla deweloperów, która wersja używają.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-142">Maintaining a relationship between the versions provides more information to developers about which version they are using.</span></span>

<span data-ttu-id="a1fc1-143">**❌ NIE** mają stały AssemblyVersion.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-143">**❌ DO NOT** have a fixed AssemblyVersion.</span></span>

> <span data-ttu-id="a1fc1-144">Podczas niezmiennych AssemblyVersion eliminuje potrzebę przekierowania powiązań, oznacza to, że tylko jedną wersję zestawu można zainstalować w globalnej pamięci podręcznej zestawów (GAC).</span><span class="sxs-lookup"><span data-stu-id="a1fc1-144">While an unchanging AssemblyVersion avoids the need for binding redirects, it means that only a single version of the assembly can be installed in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="a1fc1-145">Ponadto aplikacje, które odwołują się do zestawu w GAC spowoduje awarię, jeśli inna aplikacja zostaje zaktualizowana o przełomowe zmiany zestawu w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-145">Also, the applications that reference the assembly in the GAC will break if another application updates the GAC assembly with breaking changes.</span></span>

### <a name="assembly-file-version"></a><span data-ttu-id="a1fc1-146">Wersja pliku zestawu</span><span class="sxs-lookup"><span data-stu-id="a1fc1-146">Assembly file version</span></span>

<span data-ttu-id="a1fc1-147">Wersja pliku zestawu jest używana do wyświetlania wersji pliku w Windows i nie ma wpływu na zachowanie środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-147">The assembly file version is used to display a file version in Windows and has no effect on runtime behavior.</span></span> <span data-ttu-id="a1fc1-148">Ustawienie tej wersji jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-148">Setting this version is optional.</span></span> <span data-ttu-id="a1fc1-149">Jest ona widoczna w oknie dialogowym właściwości pliku w Eksploratorze Windows:</span><span class="sxs-lookup"><span data-stu-id="a1fc1-149">It's visible in the File Properties dialog in Windows Explorer:</span></span>

```xml
<FileVersion>11.0.2.21924</FileVersion>
```

<span data-ttu-id="a1fc1-150">![Eksplorator Windows](./media/versioning/win-properties.png "Eksplorator Windows")</span><span class="sxs-lookup"><span data-stu-id="a1fc1-150">![Windows Explorer](./media/versioning/win-properties.png "Windows Explorer")</span></span>

> [!NOTE]
> <span data-ttu-id="a1fc1-151">Ostrzeżenie dotyczące kompilacji nieszkodliwe jest wywoływane, jeśli ta wersja nie jest zgodna z formatem `Major.Minor.Build.Revision`.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-151">An innocuous build warning is raised if this version does not follow the format `Major.Minor.Build.Revision`.</span></span> <span data-ttu-id="a1fc1-152">Można bezpiecznie zignorować to ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-152">The warning can be safely ignored.</span></span>

<span data-ttu-id="a1fc1-153">**ROZWAŻ ✔️** tym ciągłej integracji kompilacji numer poprawki AssemblyFileVersion.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-153">**✔️ CONSIDER** including a continuous integration build number as the AssemblyFileVersion revision.</span></span>

> <span data-ttu-id="a1fc1-154">Na przykład tworzysz projekt w wersji 1.0.0 i numer kompilacji ciągłej integracji jest 99, więc Twoja AssemblyFileVersion jest 1.0.0.99.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-154">For example, you are building version 1.0.0 of your project, and the continuous integration build number is 99 so your AssemblyFileVersion is 1.0.0.99.</span></span>

### <a name="assembly-informational-version"></a><span data-ttu-id="a1fc1-155">Informacje o wersji zestawu</span><span class="sxs-lookup"><span data-stu-id="a1fc1-155">Assembly informational version</span></span>

<span data-ttu-id="a1fc1-156">Informacje o wersji zestawu jest używana do rejestrowania dodatkowe informacje o wersji i nie ma wpływu na zachowanie środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-156">The assembly informational version is used to record additional version information and has no effect on runtime behavior.</span></span> <span data-ttu-id="a1fc1-157">Ustawienie tej wersji jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-157">Setting this version is optional.</span></span> <span data-ttu-id="a1fc1-158">Jeśli używasz SourceLink tej wersji zostanie ustawiona na kompilacji z wersji pakietu NuGet oraz wersja kontroli źródła.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-158">If you're using SourceLink, this version will be set on build with the NuGet package version plus a source control version.</span></span> <span data-ttu-id="a1fc1-159">Na przykład `1.0.0-beta1+204ff0a` zawiera skrót zatwierdzenia zestawu został skompilowany z kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-159">For example, `1.0.0-beta1+204ff0a` includes the commit hash of the source code the assembly was built from.</span></span> <span data-ttu-id="a1fc1-160">Aby uzyskać więcej informacji, zobacz [SourceLink](./sourcelink.md).</span><span class="sxs-lookup"><span data-stu-id="a1fc1-160">For more information, see [SourceLink](./sourcelink.md).</span></span>

```xml
<AssemblyInformationalVersion>The quick brown fox jumped over the lazy dog.</AssemblyInformationalVersion>
```

<span data-ttu-id="a1fc1-161">**Należy UNIKAĆ ❌** samodzielnie ustawienie informacje o wersji zestawu.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-161">**❌ AVOID** setting the assembly informational version yourself.</span></span>

> <span data-ttu-id="a1fc1-162">Zezwalaj na SourceLink do automatycznego generowania wersji zawierający metadane kontroli źródła i NuGet.</span><span class="sxs-lookup"><span data-stu-id="a1fc1-162">Allow SourceLink to automatically generate the version containing NuGet and source control metadata.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="a1fc1-163">[Poprzednie](./publish-nuget-package.md)
[dalej](./breaking-changes.md)</span><span class="sxs-lookup"><span data-stu-id="a1fc1-163">[Previous](./publish-nuget-package.md)
[Next](./breaking-changes.md)</span></span>