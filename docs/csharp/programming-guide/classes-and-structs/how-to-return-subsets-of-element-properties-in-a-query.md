---
title: "Porady: zwracanie podzbiorów właściwości elementu w zapytaniu (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6654b162fbdeb59ed2a135d7d8cf58c8b3406c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="2823c-102">Porady: zwracanie podzbiorów właściwości elementu w zapytaniu (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="2823c-102">How to: Return Subsets of Element Properties in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="2823c-103">Użyj typu anonimowego w wyrażeniu zapytania, gdy oba te warunki mają zastosowanie:</span><span class="sxs-lookup"><span data-stu-id="2823c-103">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
-   <span data-ttu-id="2823c-104">Chcesz przywrócić tylko niektóre właściwości każdego elementu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="2823c-104">You want to return only some of the properties of each source element.</span></span>  
  
-   <span data-ttu-id="2823c-105">Nie masz do przechowywania wyników zapytania poza zakresem metody wykonywania zapytania.</span><span class="sxs-lookup"><span data-stu-id="2823c-105">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="2823c-106">Jeśli chcesz zwracać jedną właściwość lub pole z każdego elementu źródłowego, a następnie można użyć kropka w `select` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="2823c-106">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="2823c-107">Na przykład, aby zwrócić tylko `ID` każdego `student`, zapisać `select` klauzuli w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="2823c-107">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="2823c-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="2823c-108">Example</span></span>  
 <span data-ttu-id="2823c-109">Poniższy przykład przedstawia użycie typu anonimowego na zwracanie tylko podzestawu właściwości każdego elementu źródłowego odpowiadający określony warunek.</span><span class="sxs-lookup"><span data-stu-id="2823c-109">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 <span data-ttu-id="2823c-110">Należy pamiętać, że typu anonimowego korzysta z nazw elementu źródła jego właściwości, jeśli nie określono żadnych nazw.</span><span class="sxs-lookup"><span data-stu-id="2823c-110">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="2823c-111">Aby udostępnić nowe nazwy właściwości w typ anonimowy, należy zapisać `select` instrukcji w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="2823c-111">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="2823c-112">Jeśli spróbujesz to w poprzednim przykładzie, a następnie `Console.WriteLine` także zmienić instrukcji:</span><span class="sxs-lookup"><span data-stu-id="2823c-112">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2823c-113">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="2823c-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="2823c-114">Aby uruchomić ten kod, skopiuj i Wklej klasy w projektach Visual C# console aplikacji utworzony w [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2823c-114">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="2823c-115">Domyślnie ten projekt jest przeznaczony dla wersji 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], i ma on odwołania do System.Core.dll i `using` dyrektywy dla System.Linq.</span><span class="sxs-lookup"><span data-stu-id="2823c-115">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it will have a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="2823c-116">Jeśli co najmniej jeden z tych wymagań brakuje z projektu, należy je dodać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="2823c-116">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="2823c-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2823c-117">See Also</span></span>  
 [<span data-ttu-id="2823c-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="2823c-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2823c-119">Typy anonimowe</span><span class="sxs-lookup"><span data-stu-id="2823c-119">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="2823c-120">Wyrażenia zapytań LINQ</span><span class="sxs-lookup"><span data-stu-id="2823c-120">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)