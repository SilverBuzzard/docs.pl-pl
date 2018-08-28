---
title: Historia wersji platformy .NET core
description: Zobacz oś czasu dla wersji środowiska uruchomieniowego .NET Core, .NET Core SDK, kompilator języka C# i VB.NET kompilatora.
ms.date: 07/26/2018
ms.openlocfilehash: 90fd4ba57620a3a005f2148c0335a76a6fa54a30
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936644"
---
# <a name="net-core-version-history"></a><span data-ttu-id="59c45-103">Historia wersji .NET Core</span><span class="sxs-lookup"><span data-stu-id="59c45-103">NET Core version history</span></span>

<span data-ttu-id="59c45-104">Numery wersji dla platformy .NET Core to wyzwanie, ponieważ zestaw .NET Core SDK i środowisko uruchomieniowe programu .NET Core w wersji na inną odstępach czasu.</span><span class="sxs-lookup"><span data-stu-id="59c45-104">Version numbers for .NET Core are challenging because .NET Core SDK and .NET Core Runtime release on different cadences.</span></span> <span data-ttu-id="59c45-105">Różne odstępach czasu oznaczają, że zespół wymuszono wykonaj tylko dwa spośród następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="59c45-105">The different cadences mean the team was forced to do only two of the following three things:</span></span>

1. <span data-ttu-id="59c45-106">Wersja niezależnie, w szczególności, dzięki czemu narzędzia, C# i VB, aby awansować szybciej niż środowisko uruchomieniowe programu .NET Core.</span><span class="sxs-lookup"><span data-stu-id="59c45-106">Release independently, specifically allowing tools, C# and VB to advance faster than the .NET Core Runtime.</span></span>
2. <span data-ttu-id="59c45-107">Obsługa wyrównanie, numery wersji między .NET Core SDK i środowisko uruchomieniowe programu .NET Core.</span><span class="sxs-lookup"><span data-stu-id="59c45-107">Maintain alignment in version numbers between .NET Core SDK and .NET Core Runtime.</span></span>
3. <span data-ttu-id="59c45-108">Użyj semantyki przechowywania wersji dla platformy .NET Core SDK i środowisko uruchomieniowe programu .NET Core.</span><span class="sxs-lookup"><span data-stu-id="59c45-108">Use semantic versioning for both the .NET Core SDK and .NET Core Runtime.</span></span>

<span data-ttu-id="59c45-109">2.0.0 wymusić wyrównanie wersji i sprawnie zanalizować w jednej wersji.</span><span class="sxs-lookup"><span data-stu-id="59c45-109">2.0.0 forced version alignment and proceeded smoothly for one release.</span></span> <span data-ttu-id="59c45-110">W grudniu 2017 r zestawu .NET Core SDK miał wersji funkcji, nie odpowiedniej wersji w środowisku uruchomieniowym .NET Core.</span><span class="sxs-lookup"><span data-stu-id="59c45-110">In December 2017 .NET Core SDK had a feature release, with no corresponding release in the .NET Core Runtime.</span></span> <span data-ttu-id="59c45-111">Zespól cele 1 i 3, utraty wyrównanie między środowisko uruchomieniowe programu .NET Core i zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="59c45-111">The team chose goals 1 and 3, losing alignment between the .NET Core Runtime and SDK.</span></span> <span data-ttu-id="59c45-112">Różne wersje programu .NET Core SDK 2.1.x zostały wydane przed platformy .NET Core środowiska uruchomieniowego 2.1.</span><span class="sxs-lookup"><span data-stu-id="59c45-112">Several .NET Core SDK 2.1.x versions were released before .NET Core Runtime 2.1.</span></span> <span data-ttu-id="59c45-113">Ponieważ zestaw SDK nie jest zgodny będzie przekazywać, te wersje zestawu SDK 2.1.x nie jest przeznaczona platformy .NET Core środowiska uruchomieniowego 2.1.</span><span class="sxs-lookup"><span data-stu-id="59c45-113">Since the SDK is not forwards compatible, these 2.1.x SDK versions could not target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="59c45-114">Zespół odpowiedział na znaczną pomyłek, przełączając się cele 1 i 2, porzucenie semantycznego przechowywania wersji, zgodnie z opisem w [wersji platformy .NET Core](index.md#versioning-details).</span><span class="sxs-lookup"><span data-stu-id="59c45-114">The team responded to the considerable confusion by switching to goals 1 and 2, abandoning semantic versioning as described in [.NET Core versioning](index.md#versioning-details).</span></span>

<span data-ttu-id="59c45-115">Ze względu na czas decyzji, Porzuć wersji semantycznej wystąpiły przejściowe wydań w 2.1.10x i 2.1.20x wersji numer zakresy, które również nie można kierować platformy .NET Core środowiska uruchomieniowego 2.1.</span><span class="sxs-lookup"><span data-stu-id="59c45-115">Because of the timing of the decision to abandon semantic versioning, there were transitional releases in the 2.1.10x and 2.1.20x version number ranges that also can't target .NET Core Runtime 2.1.</span></span>

<span data-ttu-id="59c45-116">Pierwsze dwie cyfry numery wersji dopasowania z 2.1.0 wersję środowiska uruchomieniowego programu .NET Core i 2.1.300 wersji programu .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="59c45-116">The first two digits of the version numbers realign with the 2.1.0 version of the .NET Core Runtime and the 2.1.300 version of the .NET Core SDK.</span></span>

<span data-ttu-id="59c45-117">Szczegółowe informacje o wersjach poszczególnych składników, w tym platformy i języka w wersji kompilatora, można znaleźć na [strony pobierania dla platformy .NET Core](https://www.microsoft.com/net/download/dotnet-core/current).</span><span class="sxs-lookup"><span data-stu-id="59c45-117">Detailed information about the versions of individual components, including framework and language compiler versions, can be found on the [.NET Core downloads page](https://www.microsoft.com/net/download/dotnet-core/current).</span></span> <span data-ttu-id="59c45-118">Aby uzyskać szczegółowe informacje na temat poprzednich wersji, wybierz żądaną wersję z [pobierania .NET Core archiwa strony](https://www.microsoft.com/net/download/archives).</span><span class="sxs-lookup"><span data-stu-id="59c45-118">For detailed information about previous versions, select the requested version from the [.NET Core download archives page](https://www.microsoft.com/net/download/archives).</span></span> <span data-ttu-id="59c45-119">Obsługa szczegółowych informacji można znaleźć w artykułów opisujących official będzie przydatna dla [.NET obsługuje zasady](https://www.microsoft.com/net/Support/Policy).</span><span class="sxs-lookup"><span data-stu-id="59c45-119">Detailed support information can be found in the article describing the official [.NET Support Policy](https://www.microsoft.com/net/Support/Policy).</span></span>