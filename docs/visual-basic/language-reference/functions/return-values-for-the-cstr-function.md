---
title: "Zwracane wartości dla funkcji CStr (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b498c9b1b7916467c96ed2c645c7131192a5e8b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="896b5-102">Zwracane wartości dla funkcji CStr (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="896b5-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="896b5-103">W poniższej tabeli opisano wartości zwracanych przez `CStr` dla różnych typów danych z `expression`.</span><span class="sxs-lookup"><span data-stu-id="896b5-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="896b5-104">Jeśli `expression` jest typu</span><span class="sxs-lookup"><span data-stu-id="896b5-104">If `expression` type is</span></span>|<span data-ttu-id="896b5-105">`CStr`Zwraca</span><span class="sxs-lookup"><span data-stu-id="896b5-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="896b5-106">Boolean — typ danych</span><span class="sxs-lookup"><span data-stu-id="896b5-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="896b5-107">Ciąg zawierający "wartość True" lub "False".</span><span class="sxs-lookup"><span data-stu-id="896b5-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="896b5-108">Date — typ danych</span><span class="sxs-lookup"><span data-stu-id="896b5-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="896b5-109">Ciąg zawierający `Date` wartość (Data i godzina) w formacie daty krótkiej systemu.</span><span class="sxs-lookup"><span data-stu-id="896b5-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="896b5-110">Numeryczne typy danych</span><span class="sxs-lookup"><span data-stu-id="896b5-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="896b5-111">Ciąg reprezentujący liczbę.</span><span class="sxs-lookup"><span data-stu-id="896b5-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="896b5-112">Data i CStr</span><span class="sxs-lookup"><span data-stu-id="896b5-112">CStr and Date</span></span>  
 <span data-ttu-id="896b5-113">`Date` Typu zawsze zawiera informacje zarówno datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="896b5-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="896b5-114">W celu konwersji typu, Visual Basic uważa 1/1/0001 (1 stycznia 1 roku) *neutralne wartość* daty i 00:00:00 (północ) jako neutralny wartość po raz.</span><span class="sxs-lookup"><span data-stu-id="896b5-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="896b5-115">`CStr`nie ma wartości neutralne w ciągu wynikowym.</span><span class="sxs-lookup"><span data-stu-id="896b5-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="896b5-116">Na przykład, jeśli przekonwertujesz `#January 1, 0001 9:30:00#` na ciąg, wynikiem jest "9:30:00 AM"; informacje o dacie jest pomijane.</span><span class="sxs-lookup"><span data-stu-id="896b5-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="896b5-117">Jednak informacje o dacie jest nadal znajdują się w oryginalnym `Date` wartości i może zostać przywrócona z funkcji takich jak <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span><span class="sxs-lookup"><span data-stu-id="896b5-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="896b5-118">`CStr` Funkcja wykonuje jego konwersja na podstawie ustawień bieżącej kultury aplikacji.</span><span class="sxs-lookup"><span data-stu-id="896b5-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="896b5-119">Aby uzyskać reprezentację liczby w określonej kultury, użyj numeru `ToString(IFormatProvider)` metody.</span><span class="sxs-lookup"><span data-stu-id="896b5-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="896b5-120">Na przykład użyć <xref:System.Double.ToString%2A?displayProperty=nameWithType> podczas konwertowania wartości typu `Double` do `String`.</span><span class="sxs-lookup"><span data-stu-id="896b5-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="896b5-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="896b5-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>  
 [<span data-ttu-id="896b5-122">Funkcje konwersji typu</span><span class="sxs-lookup"><span data-stu-id="896b5-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="896b5-123">Boolean — typ danych</span><span class="sxs-lookup"><span data-stu-id="896b5-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="896b5-124">Date — typ danych</span><span class="sxs-lookup"><span data-stu-id="896b5-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)