---
title: "Option Compare — Instrukcja"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Compare
- vb.OptionCompare
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword [Visual Basic]
- binary comparison [Visual Basic]
- strings [Visual Basic], returning from functions
- binary comparison [Visual Basic], Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword [Visual Basic], Option Compare statement
- Binary keyword [Visual Basic], Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement [Visual Basic]
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 281b18322f5be4e7dadcb9533680b25016a44c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="option-compare-statement"></a><span data-ttu-id="a42c2-102">Option Compare — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="a42c2-102">Option Compare Statement</span></span>
<span data-ttu-id="a42c2-103">Deklaruje domyślną metodę porównywania do używania przy porównywaniu danych ciągów.</span><span class="sxs-lookup"><span data-stu-id="a42c2-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a42c2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a42c2-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="a42c2-105">Części</span><span class="sxs-lookup"><span data-stu-id="a42c2-105">Parts</span></span>  
  
|<span data-ttu-id="a42c2-106">Termin</span><span class="sxs-lookup"><span data-stu-id="a42c2-106">Term</span></span>|<span data-ttu-id="a42c2-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="a42c2-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="a42c2-108">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="a42c2-108">Optional.</span></span> <span data-ttu-id="a42c2-109">Wynikiem porównania ciągu oparte na kolejność sortowania, pochodzi z wewnętrznego reprezentacje binarne znaków.</span><span class="sxs-lookup"><span data-stu-id="a42c2-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="a42c2-110">Ten typ porównania jest szczególnie przydatny w przypadku ciągi mogą zawierać znaki, które nie mają być interpretowane jako tekst.</span><span class="sxs-lookup"><span data-stu-id="a42c2-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="a42c2-111">W takim przypadku nie chcesz odchylenia porównania z alfabetyczną ekwiwalenty, takich jak ignorowanie wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="a42c2-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="a42c2-112">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="a42c2-112">Optional.</span></span> <span data-ttu-id="a42c2-113">Wynikiem porównania ciągu oparte na porządek sortowania bez uwzględniania wielkości liter tekstu ustaleniami ustawień regionalnych systemu.</span><span class="sxs-lookup"><span data-stu-id="a42c2-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="a42c2-114">Jeśli Twoje ciągi zawiera wszystkie znaki tekstu i chcesz porównać je z uwzględnieniem konta ekwiwalenty alfabetyczne, takich jak liter i cyfr blisko związane przydaje porównania tego typu.</span><span class="sxs-lookup"><span data-stu-id="a42c2-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="a42c2-115">Na przykład, warto rozważyć `A` i `a` równe, i `Ä` i `ä` przed `B` i `b`.</span><span class="sxs-lookup"><span data-stu-id="a42c2-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a42c2-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a42c2-116">Remarks</span></span>  
 <span data-ttu-id="a42c2-117">Jeśli używana, `Option Compare` instrukcji musi występować w pliku przed wszystkimi innymi instrukcjami kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="a42c2-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="a42c2-118">`Option Compare` Instrukcji określa metodę porównywania ciągów (`Binary` lub `Text`).</span><span class="sxs-lookup"><span data-stu-id="a42c2-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="a42c2-119">Domyślną metodę porównywania tekst jest `Binary`.</span><span class="sxs-lookup"><span data-stu-id="a42c2-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="a42c2-120">A `Binary` wartość liczbową Unicode każdego znaku w ciągu każdej porównuje porównania.</span><span class="sxs-lookup"><span data-stu-id="a42c2-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="a42c2-121">A `Text` porównania porównuje każdego znaku Unicode oparte na jego leksykalne znaczenie w bieżącej kultury.</span><span class="sxs-lookup"><span data-stu-id="a42c2-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="a42c2-122">W systemie Microsoft Windows kolejność sortowania jest określany za pomocą stron kodowych.</span><span class="sxs-lookup"><span data-stu-id="a42c2-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="a42c2-123">Aby uzyskać więcej informacji, zobacz [stron kodowych](/cpp/c-runtime-library/code-pages).</span><span class="sxs-lookup"><span data-stu-id="a42c2-123">For more information, see [Code Pages](/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="a42c2-124">W poniższym przykładzie znaków w stronie kodowej angielski/Europejskiej (ANSI 1252) są sortowane przy użyciu `Option Compare Binary`, która tworzy typowe binarny porządek sortowania.</span><span class="sxs-lookup"><span data-stu-id="a42c2-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="a42c2-125">Gdy te same znaki w tej samej strony kodowej są sortowane przy użyciu `Option Compare Text`, jest generowany tekstowy porządek sortowania.</span><span class="sxs-lookup"><span data-stu-id="a42c2-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="a42c2-126">Po opcji Option Compare — instrukcja nie jest obecny</span><span class="sxs-lookup"><span data-stu-id="a42c2-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="a42c2-127">Jeśli kod źródłowy nie zawiera `Option Compare` instrukcji, **Option Compare** ustawienie [strona kompilowania, Projektant projektu (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) jest używany.</span><span class="sxs-lookup"><span data-stu-id="a42c2-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="a42c2-128">Jeśli używasz kompilatora wiersza polecenia, ustawienia określone przez [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) — opcja kompilatora jest używany.</span><span class="sxs-lookup"><span data-stu-id="a42c2-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="a42c2-129">Aby ustawić Option Compare w środowisku IDE</span><span class="sxs-lookup"><span data-stu-id="a42c2-129">To set Option Compare in the IDE</span></span>  
  
1.  <span data-ttu-id="a42c2-130">W **Eksploratora rozwiązań**, wybierz projekt.</span><span class="sxs-lookup"><span data-stu-id="a42c2-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="a42c2-131">Na **projektu** menu, kliknij przycisk **właściwości**.</span><span class="sxs-lookup"><span data-stu-id="a42c2-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="a42c2-132">Aby uzyskać więcej informacji, zobacz [NIB: Zarządzanie właściwości projektu przy użyciu projektanta projektów](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="a42c2-132">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="a42c2-133">Kliknij przycisk **skompilować** kartę.</span><span class="sxs-lookup"><span data-stu-id="a42c2-133">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="a42c2-134">Ustaw wartość **Option Compare** pole.</span><span class="sxs-lookup"><span data-stu-id="a42c2-134">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="a42c2-135">Podczas tworzenia projektu, **Option Compare** ustawienie **skompilować** ustawiono kartę **Option Compare** w **opcje** okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="a42c2-135">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="a42c2-136">Aby zmienić to ustawienie, na **narzędzia** menu, kliknij przycisk **opcje**.</span><span class="sxs-lookup"><span data-stu-id="a42c2-136">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="a42c2-137">W **opcje** okna dialogowego rozwiń **projekty i rozwiązania**, a następnie kliknij przycisk **domyślne VB**.</span><span class="sxs-lookup"><span data-stu-id="a42c2-137">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="a42c2-138">Ustawieniem domyślnym początkowej w **domyślne VB** jest **binarne**.</span><span class="sxs-lookup"><span data-stu-id="a42c2-138">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="a42c2-139">Aby ustawić Option Compare w wierszu polecenia</span><span class="sxs-lookup"><span data-stu-id="a42c2-139">To set Option Compare on the command line</span></span>  
  
-   <span data-ttu-id="a42c2-140">Obejmują [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) w — opcja kompilatora **vbc** polecenia.</span><span class="sxs-lookup"><span data-stu-id="a42c2-140">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a42c2-141">Przykład</span><span class="sxs-lookup"><span data-stu-id="a42c2-141">Example</span></span>  
 <span data-ttu-id="a42c2-142">W poniższym przykładzie użyto `Option Compare` instrukcji, aby ustawić porównanie binarne jako domyślną metodę porównywania ciągów.</span><span class="sxs-lookup"><span data-stu-id="a42c2-142">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="a42c2-143">Aby użyć tego kodu, usuń znaczniki komentarza `Option Compare Binary` instrukcji i umieszcza je w górnej części pliku źródłowego.</span><span class="sxs-lookup"><span data-stu-id="a42c2-143">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="a42c2-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="a42c2-144">Example</span></span>  
 <span data-ttu-id="a42c2-145">W poniższym przykładzie użyto `Option Compare` instrukcji, aby ustawić kolejność sortowania bez uwzględniania wielkości liter tekstu jako domyślną metodę porównywania ciągów.</span><span class="sxs-lookup"><span data-stu-id="a42c2-145">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="a42c2-146">Aby użyć tego kodu, usuń znaczniki komentarza `Option Compare Text` instrukcji i umieszcza je w górnej części pliku źródłowego.</span><span class="sxs-lookup"><span data-stu-id="a42c2-146">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a42c2-147">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a42c2-147">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>  
 <xref:Microsoft.VisualBasic.Strings.Replace%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [<span data-ttu-id="a42c2-148">/ optioncompare</span><span class="sxs-lookup"><span data-stu-id="a42c2-148">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="a42c2-149">Operatory porównania</span><span class="sxs-lookup"><span data-stu-id="a42c2-149">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="a42c2-150">Operatory porównania w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a42c2-150">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="a42c2-151">Like — Operator</span><span class="sxs-lookup"><span data-stu-id="a42c2-151">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="a42c2-152">Funkcje ciągów</span><span class="sxs-lookup"><span data-stu-id="a42c2-152">String Functions</span></span>](../../../visual-basic/language-reference/functions/string-functions.md)  
 [<span data-ttu-id="a42c2-153">Option Explicit — instrukcja</span><span class="sxs-lookup"><span data-stu-id="a42c2-153">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="a42c2-154">Option Strict — instrukcja</span><span class="sxs-lookup"><span data-stu-id="a42c2-154">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)