---
title: 'Co to jest F #'
description: 'Dowiedz się więcej o jakie F # języka programowania i nowości programowanie F #. Więcej informacji na temat rozbudowane typy danych, funkcje i jak one współdziałają ze sobą.'
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2018
ms.locfileid: "40240628"
---
# <a name="what-is-f"></a><span data-ttu-id="3fa0a-104">Co to jest F #</span><span class="sxs-lookup"><span data-stu-id="3fa0a-104">What is F#</span></span> #

<span data-ttu-id="3fa0a-105">F # to funkcjonalny język programowania, która ułatwia pisanie kodu poprawne i łatwego w utrzymaniu.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="3fa0a-106">Programowanie w języku F # obejmuje głównie Definiowanie typy i funkcje, które wywnioskować typu i automatycznie uogólniony.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="3fa0a-107">Dzięki temu zespół nadal korzystać z domeny problemu i manipulowanie nimi swoje dane, a nie szczegóły programowania.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="3fa0a-108">F # zawiera wiele funkcji, takich jak:</span><span class="sxs-lookup"><span data-stu-id="3fa0a-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="3fa0a-109">Lightweight — Składnia</span><span class="sxs-lookup"><span data-stu-id="3fa0a-109">Lightweight syntax</span></span>
* <span data-ttu-id="3fa0a-110">Klasa Immutable domyślnie</span><span class="sxs-lookup"><span data-stu-id="3fa0a-110">Immutable by default</span></span>
* <span data-ttu-id="3fa0a-111">Wnioskowanie o typie i automatyczna Generalizacja</span><span class="sxs-lookup"><span data-stu-id="3fa0a-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="3fa0a-112">Funkcje pierwszej klasy</span><span class="sxs-lookup"><span data-stu-id="3fa0a-112">First-class functions</span></span>
* <span data-ttu-id="3fa0a-113">Typy danych zaawansowane</span><span class="sxs-lookup"><span data-stu-id="3fa0a-113">Powerful data types</span></span>
* <span data-ttu-id="3fa0a-114">Dopasowanie wzorca</span><span class="sxs-lookup"><span data-stu-id="3fa0a-114">Pattern matching</span></span>
* <span data-ttu-id="3fa0a-115">Programowanie asynchroniczne</span><span class="sxs-lookup"><span data-stu-id="3fa0a-115">Async programming</span></span>

<span data-ttu-id="3fa0a-116">Pełny zestaw funkcji są udokumentowane w artykule [dokumentacja języka F #](language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="3fa0a-116">A full set of features are documented in the [F# language reference](language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="3fa0a-117">Rozbudowane typy danych</span><span class="sxs-lookup"><span data-stu-id="3fa0a-117">Rich data types</span></span>

<span data-ttu-id="3fa0a-118">Typy danych, takich jak [rekordów](language-reference/records.md) i [sumy rozłączne](language-reference/discriminated-unions.md) pozwalają reprezentują złożonych danych i domeny.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-118">Data types such as [Records](language-reference/records.md) and [Discriminated Unions](language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

<span data-ttu-id="3fa0a-119">Rekordów F # i sumy rozłączne są inną niż null, niezmienne i porównywalnych domyślnie, dzięki czemu jest bardzo łatwa w użyciu.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="3fa0a-120">Wymuszone poprawność przy użyciu funkcji dopasowywania do wzorca</span><span class="sxs-lookup"><span data-stu-id="3fa0a-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="3fa0a-121">Funkcje F # są łatwe do deklarowania i Zaawansowane w praktyce.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="3fa0a-122">W połączeniu z [dopasowywania do wzorca](language-reference/pattern-matching.md), umożliwiają definiowanie zachowania, którego poprawność jest wymuszana przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-122">When combined with [pattern matching](language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

<span data-ttu-id="3fa0a-123">Funkcje F # są także najwyższej jakości, co oznacza, mogą być przekazywane jako parametry i zwracane przez inne funkcje.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="3fa0a-124">Funkcje, aby zdefiniować operacje na obiektach</span><span class="sxs-lookup"><span data-stu-id="3fa0a-124">Functions to define operations on objects</span></span>

<span data-ttu-id="3fa0a-125">F # zawiera pełne wsparcie dla obiektów, które są typy danych przydatne, gdy potrzebujesz mieszania danych i funkcji.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="3fa0a-126">Funkcje F # są używane do manipulowania obiektami.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="3fa0a-127">Zamiast pisania kodu, który jest zorientowana obiektowo, w języku F #, często napiszesz kod, traktuje obiekty jako inny typ danych dla funkcji do manipulowania.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="3fa0a-128">Funkcje, takie jak [interfejsów ogólnych](language-reference/interfaces.md), [wyrażenia obiektów](language-reference/object-expressions.md)oraz korzystać z [członków](language-reference/members/index.md) są powszechne w większych programów F #.</span><span class="sxs-lookup"><span data-stu-id="3fa0a-128">Features such as [generic interfaces](language-reference/interfaces.md), [object expressions](language-reference/object-expressions.md), and judicious use of [members](language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3fa0a-129">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="3fa0a-129">Next steps</span></span>

<span data-ttu-id="3fa0a-130">Aby dowiedzieć się więcej na temat większy zbiór funkcji F #, zapoznaj się z [Przewodnik po F #](tour.md).</span><span class="sxs-lookup"><span data-stu-id="3fa0a-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>