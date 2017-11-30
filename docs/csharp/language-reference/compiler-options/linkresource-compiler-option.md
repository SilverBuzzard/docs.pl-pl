---
title: -linkresource (opcje kompilatora C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d478c42141288cc3a1478ecf43f50c961a9d2246
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-c-compiler-options"></a><span data-ttu-id="3f128-102">/linkresource (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="3f128-102">/linkresource (C# Compiler Options)</span></span>
<span data-ttu-id="3f128-103">Tworzy łącze do zasobu .NET Framework w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="3f128-103">Creates a link to a .NET Framework resource in the output file.</span></span> <span data-ttu-id="3f128-104">Plik zasobu nie została dodana do pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="3f128-104">The resource file is not added to the output file.</span></span> <span data-ttu-id="3f128-105">To różni się od [/Resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) opcję, która osadzić pliku zasobów w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="3f128-105">This differs from the [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f128-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="3f128-106">Syntax</span></span>  
  
```console  
/linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3f128-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="3f128-107">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="3f128-108">Plik zasobu .NET Framework, do którego chcesz połączyć z zestawu.</span><span class="sxs-lookup"><span data-stu-id="3f128-108">The .NET Framework resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="3f128-109">`identifier`(opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="3f128-109">`identifier` (optional)</span></span>  
 <span data-ttu-id="3f128-110">Nazwa logiczna zasobu; Nazwa, która jest używana do załadowania zasobu.</span><span class="sxs-lookup"><span data-stu-id="3f128-110">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="3f128-111">Wartość domyślna to nazwa pliku.</span><span class="sxs-lookup"><span data-stu-id="3f128-111">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="3f128-112">`accessibility-modifier`(opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="3f128-112">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="3f128-113">Dostępność zasobu: publicznych lub prywatnych.</span><span class="sxs-lookup"><span data-stu-id="3f128-113">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="3f128-114">Wartość domyślna jest publiczny.</span><span class="sxs-lookup"><span data-stu-id="3f128-114">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f128-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3f128-115">Remarks</span></span>  
 <span data-ttu-id="3f128-116">Domyślnie połączonych zasobów są publicznie udostępniane w zestawie, tworzona przez kompilator języka C#.</span><span class="sxs-lookup"><span data-stu-id="3f128-116">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="3f128-117">Zasoby prywatny, ustaw `private` jako modyfikator dostępności.</span><span class="sxs-lookup"><span data-stu-id="3f128-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="3f128-118">Nie inne modyfikator innych niż `public` lub `private` jest dozwolone.</span><span class="sxs-lookup"><span data-stu-id="3f128-118">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="3f128-119">**/ linkresource** wymaga jednego z [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) opcje inne niż **/target: module**.</span><span class="sxs-lookup"><span data-stu-id="3f128-119">**/linkresource** requires one of the [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) options other than **/target:module**.</span></span>  
  
 <span data-ttu-id="3f128-120">Jeśli `filename` to plik zasobu .NET Framework utworzone, na przykład przez [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) lub w środowisku programistycznym, jest dostępny z elementami członkowskimi w <xref:System.Resources> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="3f128-120">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="3f128-121">Aby uzyskać więcej informacji, zobacz <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3f128-121">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3f128-122">Inne zasoby, można użyć `GetManifestResource` metod w <xref:System.Reflection.Assembly> klasę, aby uzyskać dostęp do zasobu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="3f128-122">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="3f128-123">Plik określony w `filename` może być dowolnym formacie.</span><span class="sxs-lookup"><span data-stu-id="3f128-123">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="3f128-124">Na przykład można ustawić natywnej biblioteki DLL częścią zestawu, dzięki czemu mogą być zainstalowane w globalnej pamięci podręcznej zestawów i dostępne z kodu zarządzanego w zestawie.</span><span class="sxs-lookup"><span data-stu-id="3f128-124">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="3f128-125">Drugi poniższych przykładach pokazano, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="3f128-125">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="3f128-126">Można tak samo postąpić w konsolidator zestawów.</span><span class="sxs-lookup"><span data-stu-id="3f128-126">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="3f128-127">Trzeci poniższych przykładach pokazano, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="3f128-127">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="3f128-128">Aby uzyskać więcej informacji, zobacz [Al.exe (konsolidator zestawów)](../../../framework/tools/al-exe-assembly-linker.md) i [Praca z zestawami i Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="3f128-128">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="3f128-129">**/ Linkres** jest krótka forma **/linkresource**.</span><span class="sxs-lookup"><span data-stu-id="3f128-129">**/linkres** is the short form of **/linkresource**.</span></span>  
  
 <span data-ttu-id="3f128-130">Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można zmienić programowo.</span><span class="sxs-lookup"><span data-stu-id="3f128-130">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f128-131">Przykład</span><span class="sxs-lookup"><span data-stu-id="3f128-131">Example</span></span>  
 <span data-ttu-id="3f128-132">Kompiluj `in.cs` i łącza do pliku zasobów `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="3f128-132">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc /linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="3f128-133">Przykład</span><span class="sxs-lookup"><span data-stu-id="3f128-133">Example</span></span>  
 <span data-ttu-id="3f128-134">Kompiluj `A.cs` do biblioteki DLL, łącze do natywnej N.dll biblioteki DLL i umieść dane wyjściowe w globalnej pamięci podręcznej zestawów (GAC).</span><span class="sxs-lookup"><span data-stu-id="3f128-134">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="3f128-135">W tym przykładzie zarówno A.dll i N.dll będzie znajdować się w pamięci GAC.</span><span class="sxs-lookup"><span data-stu-id="3f128-135">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc /linkresource:N.dll /t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="3f128-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="3f128-136">Example</span></span>  
 <span data-ttu-id="3f128-137">W tym przykładzie jest to samo, jak poprzedni, ale przy użyciu opcji Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="3f128-137">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc /t:module A.cs  
al /out:A.dll A.netmodule /link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f128-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3f128-138">See Also</span></span>  
 [<span data-ttu-id="3f128-139">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="3f128-139">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="3f128-140">Al.exe (konsolidator zestawów)</span><span class="sxs-lookup"><span data-stu-id="3f128-140">Al.exe (Assembly Linker)</span></span>](../../../framework/tools/al-exe-assembly-linker.md)  
 [<span data-ttu-id="3f128-141">Praca z zestawami i Globalna pamięć podręczna zestawów</span><span class="sxs-lookup"><span data-stu-id="3f128-141">Working with Assemblies and the Global Assembly Cache</span></span>](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="3f128-142">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="3f128-142">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)