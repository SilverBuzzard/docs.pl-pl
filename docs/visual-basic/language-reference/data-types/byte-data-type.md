---
title: "Byte — Typ danych (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6475ff3ed905abb022a9ef60204c04b45130ae22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="c2aca-102">Byte — typ danych (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2aca-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="c2aca-103">Przechowuje 8-bitową (1-bajtowy) liczb całkowitych bez znaku z zakresu wartości od 0 do 255.</span><span class="sxs-lookup"><span data-stu-id="c2aca-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2aca-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c2aca-104">Remarks</span></span>

<span data-ttu-id="c2aca-105">Użyj `Byte` — typ danych zawierający dane binarne.</span><span class="sxs-lookup"><span data-stu-id="c2aca-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="c2aca-106">Wartość domyślna `Byte` ma wartość 0.</span><span class="sxs-lookup"><span data-stu-id="c2aca-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="c2aca-107">Przydziały literału</span><span class="sxs-lookup"><span data-stu-id="c2aca-107">Literal assignments</span></span>

<span data-ttu-id="c2aca-108">Można zadeklarować i zainicjuj `Byte` zmiennej przez przypisanie dziesiętną literału, literałem szesnastkowe ósemkowe literał lub (począwszy od 2017 Visual Basic) literał binarny.</span><span class="sxs-lookup"><span data-stu-id="c2aca-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="c2aca-109">Jeśli całkowity literału jest poza zakresem `Byte` (to znaczy, jeśli jest mniejszy niż <xref:System.Byte.MinValue?displayProperty=nameWithType> lub większa niż <xref:System.Byte.MaxValue?displayProperty=nameWithType>), występuje błąd kompilacji.</span><span class="sxs-lookup"><span data-stu-id="c2aca-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="c2aca-110">W poniższym przykładzie liczb całkowitych równa 201, które są reprezentowane jako dziesiętne szesnastkowych, i literały binarne są niejawnie konwertowane z [całkowitą](integer-data-type.md) do `byte` wartości.</span><span class="sxs-lookup"><span data-stu-id="c2aca-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="c2aca-111">Użyj prefiksu `&h` lub `&H` do oznaczania literałem szesnastkowe prefiks `&b` lub `&B` do oznaczania literał binarny i prefiks `&o` lub `&O` do oznaczania ósemkowe literału.</span><span class="sxs-lookup"><span data-stu-id="c2aca-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="c2aca-112">Literałów dziesiętnych mają nie ma prefiksu.</span><span class="sxs-lookup"><span data-stu-id="c2aca-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="c2aca-113">Począwszy od 2017 Visual Basic, umożliwia także znaku podkreślenia `_`, jako separator cyfr w celu zwiększenia czytelności, jak w poniższym przykładzie pokazano.</span><span class="sxs-lookup"><span data-stu-id="c2aca-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

## <a name="programming-tips"></a><span data-ttu-id="c2aca-114">Porady dotyczące programowania</span><span class="sxs-lookup"><span data-stu-id="c2aca-114">Programming tips</span></span>

-   <span data-ttu-id="c2aca-115">**Wartości ujemne.**</span><span class="sxs-lookup"><span data-stu-id="c2aca-115">**Negative Numbers.**</span></span> <span data-ttu-id="c2aca-116">Ponieważ `Byte` jest typu unsigned, nie może reprezentować wartość ujemną.</span><span class="sxs-lookup"><span data-stu-id="c2aca-116">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="c2aca-117">Jeśli używasz jednoargumentowy minus (`-`) operator na wyrażenie obliczane do typu `Byte`, Visual Basic konwertuje wyrażenie `Short` pierwszy.</span><span class="sxs-lookup"><span data-stu-id="c2aca-117">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="c2aca-118">**Konwersje formatu.**</span><span class="sxs-lookup"><span data-stu-id="c2aca-118">**Format Conversions.**</span></span> <span data-ttu-id="c2aca-119">Gdy Visual Basic odczytuje i zapisuje pliki lub gdy wywołuje bibliotek DLL, metod i właściwości, może automatycznie przekonwertować między formatami danych.</span><span class="sxs-lookup"><span data-stu-id="c2aca-119">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="c2aca-120">Dane binarne przechowywane w `Byte` zmiennych i tablic są zachowywane w trakcie konwersji taki format.</span><span class="sxs-lookup"><span data-stu-id="c2aca-120">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="c2aca-121">Nie należy używać `String` zmiennej dla danych binarnych, ponieważ jego zawartość może być uszkodzony podczas konwersji między formatami ANSI i Unicode.</span><span class="sxs-lookup"><span data-stu-id="c2aca-121">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="c2aca-122">**Rozszerzanie.**</span><span class="sxs-lookup"><span data-stu-id="c2aca-122">**Widening.**</span></span> <span data-ttu-id="c2aca-123">`Byte` Rozszerzenie typu danych do `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, lub `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2aca-123">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="c2aca-124">Oznacza to, że można przekonwertować `Byte` do żadnego z tych typów bez napotkania <xref:System.OverflowException?displayProperty=nameWithType> błędu.</span><span class="sxs-lookup"><span data-stu-id="c2aca-124">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="c2aca-125">**Znaki typu.**</span><span class="sxs-lookup"><span data-stu-id="c2aca-125">**Type Characters.**</span></span> <span data-ttu-id="c2aca-126">`Byte`nie ma znak literalny typu ani znak typu identyfikator.</span><span class="sxs-lookup"><span data-stu-id="c2aca-126">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="c2aca-127">**Typ struktury.**</span><span class="sxs-lookup"><span data-stu-id="c2aca-127">**Framework Type.**</span></span> <span data-ttu-id="c2aca-128">Danego typu w programie .NET Framework jest <xref:System.Byte?displayProperty=nameWithType> struktury.</span><span class="sxs-lookup"><span data-stu-id="c2aca-128">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="c2aca-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="c2aca-129">Example</span></span>

 <span data-ttu-id="c2aca-130">W poniższym przykładzie `b` jest `Byte` zmiennej.</span><span class="sxs-lookup"><span data-stu-id="c2aca-130">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="c2aca-131">Instrukcje pokazują zakresu zmiennej i stosowania operatory przesunięcia bitowego do niego.</span><span class="sxs-lookup"><span data-stu-id="c2aca-131">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="c2aca-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c2aca-132">See Also</span></span>

 <xref:System.Byte?displayProperty=nameWithType>  
 [<span data-ttu-id="c2aca-133">Typy danych</span><span class="sxs-lookup"><span data-stu-id="c2aca-133">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="c2aca-134">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="c2aca-134">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="c2aca-135">Konwersja — podsumowanie</span><span class="sxs-lookup"><span data-stu-id="c2aca-135">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="c2aca-136">Skuteczne stosowanie typów danych</span><span class="sxs-lookup"><span data-stu-id="c2aca-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)