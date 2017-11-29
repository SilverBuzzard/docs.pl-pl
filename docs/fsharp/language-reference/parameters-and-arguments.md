---
title: Parametry i argumenty (F#)
description: "Więcej informacji o obsługę języka F # do definiowania parametrów i przekazywanie argumentów do funkcji, właściwości i metod."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9b37a5c4-9263-4513-822a-fbb0d1004254
ms.openlocfilehash: 50f54bacd9ba7ec20a7151794734f93200df9f2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="c92cd-104">Parametry i argumenty</span><span class="sxs-lookup"><span data-stu-id="c92cd-104">Parameters and Arguments</span></span>

<span data-ttu-id="c92cd-105">W tym temacie opisano obsługę języka zdefiniowanie parametrów i przekazywanie argumentów do funkcji, właściwości i metod.</span><span class="sxs-lookup"><span data-stu-id="c92cd-105">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="c92cd-106">Zawiera informacje o sposobie przekazywane przez odwołanie i jak definiowanie i korzystanie z metod, które można wykonać zmienną liczbę argumentów.</span><span class="sxs-lookup"><span data-stu-id="c92cd-106">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>


## <a name="parameters-and-arguments"></a><span data-ttu-id="c92cd-107">Parametry i argumenty</span><span class="sxs-lookup"><span data-stu-id="c92cd-107">Parameters and Arguments</span></span>
<span data-ttu-id="c92cd-108">Termin *parametru* jest używany do opisu nazwy dla wartości, które mają być dostarczone.</span><span class="sxs-lookup"><span data-stu-id="c92cd-108">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="c92cd-109">Termin *argument* jest używany dla wartości podane dla każdego parametru.</span><span class="sxs-lookup"><span data-stu-id="c92cd-109">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="c92cd-110">Parametry można określić w spójnej kolekcji lub rozwinięte formularza lub kombinację obu.</span><span class="sxs-lookup"><span data-stu-id="c92cd-110">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="c92cd-111">Argument jest przekazywany za pomocą nazwy parametru jawnego.</span><span class="sxs-lookup"><span data-stu-id="c92cd-111">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="c92cd-112">Parametry metody można określony jako opcjonalne i określoną wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="c92cd-112">Parameters of methods can be specified as optional and given a default value.</span></span>


## <a name="parameter-patterns"></a><span data-ttu-id="c92cd-113">Parametr wzorce</span><span class="sxs-lookup"><span data-stu-id="c92cd-113">Parameter Patterns</span></span>
<span data-ttu-id="c92cd-114">Parametry dostarczone do funkcji i metod są ogólnie rzecz biorąc, wzorce rozdzielone spacjami.</span><span class="sxs-lookup"><span data-stu-id="c92cd-114">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="c92cd-115">Oznacza to, że w zasadzie żadnego wzorce opisem w temacie [wyrażenia dopasowania](match-expressions.md) można użyć listy parametrów dla funkcji lub elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="c92cd-115">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="c92cd-116">Metody zazwyczaj używają formy krotki przekazywanie argumentów.</span><span class="sxs-lookup"><span data-stu-id="c92cd-116">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="c92cd-117">Osiąga jaśniejszy wyników z punktu widzenia innych języków .NET, ponieważ sposób argumenty są przekazywane w metodach .NET jest zgodna z postaci spójnej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="c92cd-117">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="c92cd-118">Rozwinięte formularza jest najczęściej używana z funkcji utworzonych za pomocą `let` powiązania.</span><span class="sxs-lookup"><span data-stu-id="c92cd-118">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="c92cd-119">Następujące pseudocode przedstawiono przykłady argumenty curried i spójnej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="c92cd-119">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="c92cd-120">Gdy niektóre argumenty są w krotek, a niektóre nie są możliwe są połączone formularzy.</span><span class="sxs-lookup"><span data-stu-id="c92cd-120">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="c92cd-121">Innymi wzorami można również w listy parametrów, ale jeśli wzorzec parametru jest niezgodny z wszystkich możliwych danych wejściowych, być może niepełne dopasowania w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="c92cd-121">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="c92cd-122">Wyjątek `MatchFailureException` jest generowany, gdy wartość argumentu jest niezgodny z określonych na liście parametrów wzorców.</span><span class="sxs-lookup"><span data-stu-id="c92cd-122">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="c92cd-123">Kompilator generuje ostrzeżenie, gdy umożliwia niepełne dopasowania wzorca parametru.</span><span class="sxs-lookup"><span data-stu-id="c92cd-123">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="c92cd-124">Co najmniej jedno inne wzorzec jest często przydatne w przypadku listy parametrów, a to wzorzec wieloznaczny.</span><span class="sxs-lookup"><span data-stu-id="c92cd-124">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="c92cd-125">Na liście parametrów będą używane wzorcu symboli wieloznacznych, gdy chcesz po prostu zignoruj argumenty, które są dostarczane.</span><span class="sxs-lookup"><span data-stu-id="c92cd-125">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="c92cd-126">Poniższy kod przedstawia użycie wzorzec wieloznaczny w listy argumentów.</span><span class="sxs-lookup"><span data-stu-id="c92cd-126">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="c92cd-127">Wzorzec wieloznaczny może być przydatne, gdy nie ma potrzeby przekazanych argumentów, takich jak główny punkt wejścia do programu, gdy nie jest konieczne w argumentach wiersza polecenia, które zwykle są dostarczane w postaci tablicy ciągów, zgodnie z poniższym kodem.</span><span class="sxs-lookup"><span data-stu-id="c92cd-127">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="c92cd-128">Inne wzorce, które są czasami używane w argumentach są `as` wzorzec oraz skojarzonych z rozłączne i wzorce aktywne wzorce identyfikator.</span><span class="sxs-lookup"><span data-stu-id="c92cd-128">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="c92cd-129">Można użyć wzorcu jeden przypadek Unii rozłącznych w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="c92cd-129">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="c92cd-130">Dane wyjściowe są następujące:</span><span class="sxs-lookup"><span data-stu-id="c92cd-130">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="c92cd-131">Wzorce aktywne może służyć jako parametrów, na przykład gdy przekształcania argumentu w wybranym formacie, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="c92cd-131">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="c92cd-132">Można użyć `as` wzorzec do przechowywania wprowadzona wartość jako wartości lokalnej, jak to pokazano w następującym wierszu kodu.</span><span class="sxs-lookup"><span data-stu-id="c92cd-132">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="c92cd-133">Inny wzorzec, który jest czasami używana jest funkcja, pozostawiając ostatni argument nienazwane zapewniając jako treść funkcji, natychmiast wykonujące dopasowania wzorca na niejawnego argumentu wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="c92cd-133">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="c92cd-134">Na przykład jest następujący wiersz kodu.</span><span class="sxs-lookup"><span data-stu-id="c92cd-134">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="c92cd-135">Ten kod definiuje funkcję, która przyjmuje listę ogólnych i zwraca `true` Jeśli lista jest pusta, i `false` inaczej.</span><span class="sxs-lookup"><span data-stu-id="c92cd-135">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="c92cd-136">Korzystanie z takich technik wprowadzić kod czytelność.</span><span class="sxs-lookup"><span data-stu-id="c92cd-136">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="c92cd-137">Czasami wzorców, które obejmują niepełne dopasowania są przydatne, na przykład, jeśli wiadomo, że tylko trzy elementy list w programie, można na przykład wzorzec podobnie do następującej listy parametrów.</span><span class="sxs-lookup"><span data-stu-id="c92cd-137">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="c92cd-138">Korzystanie z wzorców, które mają niepełne dopasowania najlepiej jest zarezerwowana dla szybkie tworzenie prototypów i innych celów tymczasowego.</span><span class="sxs-lookup"><span data-stu-id="c92cd-138">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="c92cd-139">Kompilator wyświetli ostrzeżenie dla takich kodu.</span><span class="sxs-lookup"><span data-stu-id="c92cd-139">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="c92cd-140">Takie wzorce nie obejmuje również ogólne wszystkich możliwych danych wejściowych i w związku z tym nie są odpowiednie dla składnika interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="c92cd-140">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="c92cd-141">Argumenty nazwane</span><span class="sxs-lookup"><span data-stu-id="c92cd-141">Named Arguments</span></span>
<span data-ttu-id="c92cd-142">Według położenia w postaci listy rozdzielanej przecinkami argument można określić argumentów dla metody lub ich mogą zostać przekazane do metody jawnie przez podanie nazwy, a po niej znak równości i wartość, należy przesłać.</span><span class="sxs-lookup"><span data-stu-id="c92cd-142">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="c92cd-143">Jeśli zostanie określona, podając nazwę, może się pojawić w innym porządku niż w deklaracji.</span><span class="sxs-lookup"><span data-stu-id="c92cd-143">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="c92cd-144">Argumenty nazwane można wprowadzić kod bardziej przejrzysta i bardziej dostosowywalne określone typy zmian w interfejsie API, takie jak zmiany kolejności parametrów metody.</span><span class="sxs-lookup"><span data-stu-id="c92cd-144">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="c92cd-145">Nazwane argumenty nie są dozwolone tylko dla metod, nie dla `let`-powiązanych funkcji, wartości funkcji lub wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="c92cd-145">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="c92cd-146">Poniższy przykład kodu pokazuje użycie argumentów nazwanych.</span><span class="sxs-lookup"><span data-stu-id="c92cd-146">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="c92cd-147">W wywołaniu konstruktora klasy można ustawić wartości właściwości klasy przy użyciu składni podobny do nazwanych argumentów.</span><span class="sxs-lookup"><span data-stu-id="c92cd-147">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="c92cd-148">W poniższym przykładzie przedstawiono tej składni.</span><span class="sxs-lookup"><span data-stu-id="c92cd-148">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="c92cd-149">Aby uzyskać więcej informacji, zobacz [Konstruktorzy (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="c92cd-149">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="c92cd-150">Parametry opcjonalne</span><span class="sxs-lookup"><span data-stu-id="c92cd-150">Optional Parameters</span></span>
<span data-ttu-id="c92cd-151">Można określić opcjonalny parametr dla metody przy użyciu znaku zapytania przed nazwą parametru.</span><span class="sxs-lookup"><span data-stu-id="c92cd-151">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="c92cd-152">Parametry opcjonalne są interpretowane jako typ opcji języka F #, aby mogła zbadać je w zwykły sposób, że typy opcji będą pytani przy użyciu `match` wyrażenie z `Some` i `None`.</span><span class="sxs-lookup"><span data-stu-id="c92cd-152">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="c92cd-153">Parametry opcjonalne są dozwolone tylko w elementach członkowskich, nie na funkcji utworzonych za pomocą `let` powiązania.</span><span class="sxs-lookup"><span data-stu-id="c92cd-153">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="c92cd-154">Można także użyć funkcji `defaultArg`, który ustawia domyślną wartość opcjonalny argument.</span><span class="sxs-lookup"><span data-stu-id="c92cd-154">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="c92cd-155">`defaultArg` Funkcja przyjmuje opcjonalny parametr jako pierwszego argumentu oraz wartość domyślną jako drugiego.</span><span class="sxs-lookup"><span data-stu-id="c92cd-155">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="c92cd-156">Poniższy przykład przedstawia użycie parametrów opcjonalnych.</span><span class="sxs-lookup"><span data-stu-id="c92cd-156">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="c92cd-157">Dane wyjściowe są następujące:</span><span class="sxs-lookup"><span data-stu-id="c92cd-157">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a><span data-ttu-id="c92cd-158">Przekazywanie poprzez odwołanie</span><span class="sxs-lookup"><span data-stu-id="c92cd-158">Passing by Reference</span></span>
<span data-ttu-id="c92cd-159">F # obsługuje `byref` — słowo kluczowe, która określa, że parametr jest przekazywany przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="c92cd-159">F# supports the `byref` keyword, which specifies that a parameter is passed by reference.</span></span> <span data-ttu-id="c92cd-160">Oznacza to, że wszystkie zmiany na wartość są zachowywane po wykonaniu funkcji.</span><span class="sxs-lookup"><span data-stu-id="c92cd-160">This means that any changes to the value are retained after the execution of the function.</span></span> <span data-ttu-id="c92cd-161">Wartości określone na `byref` parametr musi być modyfikowalną.</span><span class="sxs-lookup"><span data-stu-id="c92cd-161">Values provided to a `byref` parameter must be mutable.</span></span> <span data-ttu-id="c92cd-162">Alternatywnie można przekazać komórki odwołań odpowiedniego typu.</span><span class="sxs-lookup"><span data-stu-id="c92cd-162">Alternatively, you can pass reference cells of the appropriate type.</span></span>

<span data-ttu-id="c92cd-163">Przekazywanie poprzez odwołanie w językach .NET ewoluował jako sposób więcej niż jedną wartość zwrócona przez funkcję.</span><span class="sxs-lookup"><span data-stu-id="c92cd-163">Passing by reference in .NET languages evolved as a way to return more than one value from a function.</span></span> <span data-ttu-id="c92cd-164">W F # można zwrócić krotka w tym celu, lub użyj komórki referencyjnych jako parametr.</span><span class="sxs-lookup"><span data-stu-id="c92cd-164">In F#, you can return a tuple for this purpose, or use a mutable reference cell as a parameter.</span></span> <span data-ttu-id="c92cd-165">`byref` Głównie podano parametru do współdziałania z bibliotekami .NET.</span><span class="sxs-lookup"><span data-stu-id="c92cd-165">The `byref` parameter is mainly provided for interoperability with .NET libraries.</span></span>

<span data-ttu-id="c92cd-166">Poniższe przykłady przedstawiają użycie `byref` — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="c92cd-166">The following examples illustrate the use of the `byref` keyword.</span></span> <span data-ttu-id="c92cd-167">Należy pamiętać, że gdy komórka odwołania można użyć jako parametru, użytkownik musi utworzyć odwołanie do komórki jako wartość nazwanego i używać go jako parametru nie wystarczy dodać `ref` operatora, jak pokazano w pierwszym wywołaniu `Increment` w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="c92cd-167">Note that when you use a reference cell as a parameter, you must create a reference cell as a named value and use that as the parameter, not just add the `ref` operator as shown in the first call to `Increment` in the following code.</span></span> <span data-ttu-id="c92cd-168">Ponieważ tworzenie komórka odwołania tworzy kopię odpowiednia wartość, pierwsze wywołanie po prostu zwiększa wartości tymczasowej.</span><span class="sxs-lookup"><span data-stu-id="c92cd-168">Because creating a reference cell creates a copy of the underlying value, the first call just increments a temporary value.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

<span data-ttu-id="c92cd-169">Krotka jako wartości zwracane służy do przechowywania wszelkich `out` parametrów w metodach biblioteki .NET.</span><span class="sxs-lookup"><span data-stu-id="c92cd-169">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="c92cd-170">Alternatywnie można traktować `out` parametr jako `byref` parametru.</span><span class="sxs-lookup"><span data-stu-id="c92cd-170">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="c92cd-171">W poniższym przykładzie kodu przedstawiono w obu kierunkach.</span><span class="sxs-lookup"><span data-stu-id="c92cd-171">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="c92cd-172">Parameter — Tablice</span><span class="sxs-lookup"><span data-stu-id="c92cd-172">Parameter Arrays</span></span>
<span data-ttu-id="c92cd-173">Czasami jest niezbędne zdefiniować funkcję, która przyjmuje dowolnej liczby parametrów typu heterogenicznych.</span><span class="sxs-lookup"><span data-stu-id="c92cd-173">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="c92cd-174">Nie jest praktyczne utworzyć wszystkie możliwe metody przeciążonej do konta dla wszystkich typów, które mogłyby zostać użyte.</span><span class="sxs-lookup"><span data-stu-id="c92cd-174">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="c92cd-175">Implementacje .NET zapewniają obsługę tych metod, za pomocą funkcji tablicy parametrów.</span><span class="sxs-lookup"><span data-stu-id="c92cd-175">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="c92cd-176">Z dowolnej liczby parametrów można podać metodę, która przyjmuje tablicy parametrów w podpisie.</span><span class="sxs-lookup"><span data-stu-id="c92cd-176">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="c92cd-177">Parametry są umieszczane w tablicy.</span><span class="sxs-lookup"><span data-stu-id="c92cd-177">The parameters are put into an array.</span></span> <span data-ttu-id="c92cd-178">Typ elementów tablicy Określa typy parametrów, które mogą zostać przekazane do funkcji.</span><span class="sxs-lookup"><span data-stu-id="c92cd-178">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="c92cd-179">W przypadku definiowania tablicy parametrów z `System.Object` jako typ elementu następnie kod klienta można przekazać wartości dowolnego typu.</span><span class="sxs-lookup"><span data-stu-id="c92cd-179">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="c92cd-180">W języku F # można zdefiniować w metodach tylko tablice parametrów.</span><span class="sxs-lookup"><span data-stu-id="c92cd-180">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="c92cd-181">Nie można ich używać w autonomicznej lub funkcji, które są definiowane w modułach.</span><span class="sxs-lookup"><span data-stu-id="c92cd-181">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="c92cd-182">Zdefiniuj tablicy parametrów przy użyciu `ParamArray` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c92cd-182">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="c92cd-183">`ParamArray` Atrybut można stosować tylko do ostatniego parametru.</span><span class="sxs-lookup"><span data-stu-id="c92cd-183">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="c92cd-184">Poniższy kod ilustruje, zarówno podczas wywoływania metody .NET, która przyjmuje tablicy parametrów, jak i definicja typu w języku F #, który ma metodę, która przyjmuje tablicy parametrów.</span><span class="sxs-lookup"><span data-stu-id="c92cd-184">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="c92cd-185">Gdy są uruchomione w projekcie, dane wyjściowe poprzedniego kodu jest następujący:</span><span class="sxs-lookup"><span data-stu-id="c92cd-185">When run in a project, the output of the previous code is as follows:</span></span>

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="c92cd-186">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c92cd-186">See Also</span></span>
[<span data-ttu-id="c92cd-187">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="c92cd-187">Members</span></span>](members/index.md)