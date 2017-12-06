---
title: "Porady: modyfikowanie zawartości ciągu (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b0810d5722c2c32f7884187bb2e3fc5a039825c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-string-contents-c-programming-guide"></a><span data-ttu-id="e3ee8-102">Porady: modyfikowanie zawartości ciągu (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="e3ee8-102">How to: Modify String Contents (C# Programming Guide)</span></span>
<span data-ttu-id="e3ee8-103">Ponieważ ciągi są *niezmienialnych*, nie jest możliwe (bez użycia niebezpiecznego kodu) Aby zmodyfikować wartość ciągu obiektu po jego utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-103">Because strings are *immutable*, it is not possible (without using unsafe code) to modify the value of a string object after it has been created.</span></span> <span data-ttu-id="e3ee8-104">Jednak istnieje wiele sposobów, aby zmodyfikować wartość ciągu i zapisać wynik w nowym obiekcie string.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-104">However, there are many ways to modify the value of a string and store the result in a new string object.</span></span> <span data-ttu-id="e3ee8-105"><xref:System.String?displayProperty=nameWithType> Klasa udostępnia metody, które pracują na dane wejściowe ciągu i zwraca nowy obiekt ciągu.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-105">The <xref:System.String?displayProperty=nameWithType> class provides methods that operate on an input string and return a new string object.</span></span> <span data-ttu-id="e3ee8-106">W wielu przypadkach nowego obiektu można przypisać do zmiennej, która przechowywać oryginalnego ciągu.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-106">In many cases, you can assign the new object to the variable that held the original string.</span></span> <span data-ttu-id="e3ee8-107"><xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> Klasa udostępnia dodatkowe metody, które działają w podobny sposób.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-107">The <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class provides additional methods that work in a similar manner.</span></span> <span data-ttu-id="e3ee8-108"><xref:System.Text.StringBuilder?displayProperty=nameWithType> Klasa udostępnia buforu znak, który można modyfikować "w miejscu."</span><span class="sxs-lookup"><span data-stu-id="e3ee8-108">The <xref:System.Text.StringBuilder?displayProperty=nameWithType> class provides a character buffer that you can modify "in-place."</span></span> <span data-ttu-id="e3ee8-109">Należy wywołać <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> metodę, aby utworzyć nowy obiekt ciągu zawierający bieżącą zawartość buforu.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-109">You call the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> method to create a new string object that contains the current contents of the buffer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3ee8-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="e3ee8-110">Example</span></span>  
 <span data-ttu-id="e3ee8-111">Poniższy przykład przedstawia różne sposoby Zamień lub usuń podciągów w określonym ciągu.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-111">The following example shows various ways to replace or remove substrings in a specified string.</span></span>  
  
 [!code-csharp[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="e3ee8-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="e3ee8-112">Example</span></span>  
 <span data-ttu-id="e3ee8-113">Aby uzyskać dostęp do poszczególnych znaków w ciągu przy użyciu notacji tablicy, można użyć <xref:System.Text.StringBuilder> obiektu, który overloads `[]` operatora, aby zapewnić dostęp do buforu wewnętrznego znaków.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-113">To access the individual characters in a string by using array notation, you can use the <xref:System.Text.StringBuilder> object, which overloads the `[]` operator to provide access to its internal character buffer.</span></span> <span data-ttu-id="e3ee8-114">Możesz również przekonwertować ciągu do tablicy znaków, za pomocą <xref:System.String.ToCharArray%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-114">You can also convert the string to an array of chars by using the <xref:System.String.ToCharArray%2A> method.</span></span> <span data-ttu-id="e3ee8-115">W poniższym przykładzie użyto `ToCharArray` do utworzenia tablicy.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-115">The following example uses `ToCharArray` to create the array.</span></span> <span data-ttu-id="e3ee8-116">Niektóre elementy tej tablicy następnie są modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-116">Some elements of this array are then modified.</span></span> <span data-ttu-id="e3ee8-117">Ciąg konstruktora, który przyjmuje wartość typu char tablicy jako parametr wejściowy jest następnie wywoływana w celu utworzenia nowych parametrów.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-117">A string constructor that takes a char array as an input parameter is then called to create a new string.</span></span>  
  
 [!code-csharp[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="e3ee8-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="e3ee8-118">Example</span></span>  
 <span data-ttu-id="e3ee8-119">Poniższy przykład jest dostępna dla tych bardzo rzadko sytuacje, w których można zmodyfikować ciąg w miejscu przy użyciu niebezpiecznego kodu w sposób podobny do tablic char w stylu języka C.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-119">The following example is provided for those very rare situations in which you may want to modify a string in-place by using unsafe code in a manner similar to C-style char arrays.</span></span> <span data-ttu-id="e3ee8-120">W przykładzie przedstawiono sposób dostępu do poszczególnych znaków "w miejscu" za pomocą fixed — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-120">The example shows how to access the individual characters "in-place" by using the fixed keyword.</span></span> <span data-ttu-id="e3ee8-121">Ilustruje też jedną możliwe ubocznym niebezpieczne operacje na ciągach będącą wynikiem sposób kompilatora C# wewnętrznie przechowuje ciągi (stażystów).</span><span class="sxs-lookup"><span data-stu-id="e3ee8-121">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="e3ee8-122">Ogólnie rzecz biorąc możesz nie powinni używać tej metody, chyba że jest bezwzględnie konieczne.</span><span class="sxs-lookup"><span data-stu-id="e3ee8-122">In general, you should not use this technique unless it is absolutely necessary.</span></span>  
  
 [!code-csharp[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e3ee8-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e3ee8-123">See Also</span></span>  
 [<span data-ttu-id="e3ee8-124">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="e3ee8-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e3ee8-125">Ciągi</span><span class="sxs-lookup"><span data-stu-id="e3ee8-125">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)