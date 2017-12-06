---
title: "Mid — Instrukcja"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61d812ef91acc65728b04efc9aa99e3975e71d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="mid-statement"></a><span data-ttu-id="d4023-102">Mid — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="d4023-102">Mid Statement</span></span>
<span data-ttu-id="d4023-103">Zamienia określoną liczbę znaków w `String` zmiennej znakami z innego ciągu.</span><span class="sxs-lookup"><span data-stu-id="d4023-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4023-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d4023-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="d4023-105">Części</span><span class="sxs-lookup"><span data-stu-id="d4023-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="d4023-106">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="d4023-106">Required.</span></span> <span data-ttu-id="d4023-107">Nazwa `String` zmienną do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="d4023-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="d4023-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="d4023-108">Required.</span></span> <span data-ttu-id="d4023-109">`Integer`wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="d4023-109">`Integer` expression.</span></span> <span data-ttu-id="d4023-110">Znak na pozycji w `Target` której rozpoczyna się zastępowanie tekstu.</span><span class="sxs-lookup"><span data-stu-id="d4023-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="d4023-111">`Start`używa jednego indeksu.</span><span class="sxs-lookup"><span data-stu-id="d4023-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="d4023-112">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="d4023-112">Optional.</span></span> <span data-ttu-id="d4023-113">`Integer`wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="d4023-113">`Integer` expression.</span></span> <span data-ttu-id="d4023-114">Liczba znaków do zastąpienia.</span><span class="sxs-lookup"><span data-stu-id="d4023-114">Number of characters to replace.</span></span> <span data-ttu-id="d4023-115">Pominięcie wszystkich `String` jest używany.</span><span class="sxs-lookup"><span data-stu-id="d4023-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="d4023-116">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="d4023-116">Required.</span></span> <span data-ttu-id="d4023-117">`String`wyrażenie, które zastępuje część `Target`.</span><span class="sxs-lookup"><span data-stu-id="d4023-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="d4023-118">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="d4023-118">Exceptions</span></span>  
  
|<span data-ttu-id="d4023-119">Typ wyjątku</span><span class="sxs-lookup"><span data-stu-id="d4023-119">Exception type</span></span>|<span data-ttu-id="d4023-120">Warunek</span><span class="sxs-lookup"><span data-stu-id="d4023-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="d4023-121">`Start`< = 0 lub `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="d4023-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4023-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d4023-122">Remarks</span></span>  
 <span data-ttu-id="d4023-123">Liczba znaków zawsze jest mniejsza niż liczba znaków w `Target`.</span><span class="sxs-lookup"><span data-stu-id="d4023-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="d4023-124">Visual Basic ma <xref:Microsoft.VisualBasic.Strings.Mid%2A> funkcji i `Mid` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="d4023-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="d4023-125">Te elementy jednocześnie działać na określoną liczbę znaków w ciągu, ale `Mid` funkcja zwraca znaków podczas `Mid` instrukcji zastępuje znaki.</span><span class="sxs-lookup"><span data-stu-id="d4023-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="d4023-126">Aby uzyskać więcej informacji, zobacz <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4023-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4023-127">`MidB` Instrukcji wcześniejszych wersji programu Visual Basic zastępuje podciąg w bajtach, zamiast znaków.</span><span class="sxs-lookup"><span data-stu-id="d4023-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="d4023-128">Służy przede wszystkim do konwersji ciągów w aplikacjach z zestawami dwubajtowych znaków (znaków DBCS).</span><span class="sxs-lookup"><span data-stu-id="d4023-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="d4023-129">Wszystkie ciągi Visual Basic są w formacie Unicode, i `MidB` nie jest już obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="d4023-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4023-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="d4023-130">Example</span></span>  
 <span data-ttu-id="d4023-131">W tym przykładzie użyto `Mid` instrukcji, aby zastąpić określoną liczbę znaków w zmiennej ciągu znakami z innego ciągu.</span><span class="sxs-lookup"><span data-stu-id="d4023-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="d4023-132">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d4023-132">Requirements</span></span>  
 <span data-ttu-id="d4023-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="d4023-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="d4023-134">**Moduł:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="d4023-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="d4023-135">**Zestaw:**[!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4023-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4023-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d4023-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="d4023-137">Ciągi</span><span class="sxs-lookup"><span data-stu-id="d4023-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="d4023-138">Wprowadzenie do ciągów w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4023-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)