---
title: "Tablice wielowymiarowe (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab3a93c21ddb9541a6149967605b851ea5a50a3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="742d7-102">Tablice wielowymiarowe (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="742d7-102">Multidimensional Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="742d7-103">Tablice mogą mieć więcej niż jednym wymiarze.</span><span class="sxs-lookup"><span data-stu-id="742d7-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="742d7-104">Na przykład następujące oświadczenie tworzy jest tablicą dwuwymiarową cztery wierszy z dwóch kolumn.</span><span class="sxs-lookup"><span data-stu-id="742d7-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 <span data-ttu-id="742d7-105">Następujące oświadczenie tworzy tablicę trzy wymiary, 4, 2 i 3.</span><span class="sxs-lookup"><span data-stu-id="742d7-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a><span data-ttu-id="742d7-106">Inicjowanie tablicy</span><span class="sxs-lookup"><span data-stu-id="742d7-106">Array Initialization</span></span>  
 <span data-ttu-id="742d7-107">Można zainicjować tablicy po deklaracji, jak to pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="742d7-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 <span data-ttu-id="742d7-108">Można również zainicjować tablicy bez określania rangę.</span><span class="sxs-lookup"><span data-stu-id="742d7-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 <span data-ttu-id="742d7-109">Jeśli wybierzesz opcję zadeklarować zmienną tablicową bez inicjowania, należy użyć `new` operatora, aby przypisać tablicę zmiennej.</span><span class="sxs-lookup"><span data-stu-id="742d7-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="742d7-110">Korzystanie z `new` przedstawiono w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="742d7-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 <span data-ttu-id="742d7-111">Poniższy przykład przypisuje wartość do elementu określonej tablicy.</span><span class="sxs-lookup"><span data-stu-id="742d7-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 <span data-ttu-id="742d7-112">Podobnie poniższy przykład pobiera wartość elementu określonego tablicy i przypisuje go do zmiennej `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="742d7-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 <span data-ttu-id="742d7-113">Poniższy przykład kodu inicjuje elementów tablicy wartości domyślne (z wyjątkiem Tablice nieregularne).</span><span class="sxs-lookup"><span data-stu-id="742d7-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="742d7-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="742d7-114">See Also</span></span>  
 [<span data-ttu-id="742d7-115">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="742d7-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="742d7-116">Tablice</span><span class="sxs-lookup"><span data-stu-id="742d7-116">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="742d7-117">Tablice jednowymiarowe</span><span class="sxs-lookup"><span data-stu-id="742d7-117">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="742d7-118">Tablice nieregularne</span><span class="sxs-lookup"><span data-stu-id="742d7-118">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)