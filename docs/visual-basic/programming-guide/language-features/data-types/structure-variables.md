---
title: Zmienne struktur (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef42c44de84caffde909eb2b3e9361016a6abb97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="2cc1f-102">Zmienne struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cc1f-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="2cc1f-103">Po utworzeniu struktury procedury poziomie modułu i zmienne można zadeklarować jako tego typu.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="2cc1f-104">Na przykład można utworzyć struktury rejestrującą informacje o systemie komputera.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="2cc1f-105">W poniższym przykładzie pokazano to.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="2cc1f-106">Teraz można zadeklarować zmienne tego typu.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-106">You can now declare variables of that type.</span></span> <span data-ttu-id="2cc1f-107">Następujące oświadczenie przedstawiono to.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="2cc1f-108">Klasy i modułów, struktur zadeklarowane za pomocą [instrukcji Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) domyślną dostępu publicznego.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="2cc1f-109">Jeśli planujesz struktury ma charakter prywatny, upewnij się, Zadeklaruj ją przy użyciu [prywatnej](../../../../visual-basic/language-reference/modifiers/private.md) — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="2cc1f-110">Dostęp do wartości — struktura</span><span class="sxs-lookup"><span data-stu-id="2cc1f-110">Access to Structure Values</span></span>  
 <span data-ttu-id="2cc1f-111">Aby przypisać i pobrać wartości z elementów zmiennej struktury, należy użyć takiej samej składni używanej do ustawiania i pobierania właściwości w obiekcie.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="2cc1f-112">Umieść operatora dostępu do elementu członkowskiego (`.`) między nazwą zmiennej struktury i nazwy elementu.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="2cc1f-113">Poniższy przykład uzyskuje dostęp do elementów zmiennych wcześniej zadeklarowany jako typ `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="2cc1f-114">Przypisywanie zmienne struktur</span><span class="sxs-lookup"><span data-stu-id="2cc1f-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="2cc1f-115">Można także przypisać jedną zmienną do innego, jeśli oba warunki są tego samego typu struktury.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="2cc1f-116">Wszystkie elementy struktury jeden zostanie skopiowana do odpowiednich elementów w innym.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="2cc1f-117">Następujące oświadczenie przedstawiono to.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="2cc1f-118">Jeśli element struktury jest typem referencyjnym, takich jak `String`, `Object`, lub jest kopiowany tablicy wskaźników do danych.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="2cc1f-119">W poprzednim przykładzie Jeśli `systemInfo` zawiera zmienną obiektu, a następnie w poprzednim przykładzie będzie kopiowany wskaźnika z `mySystem` do `yourSystem`, a zmiany obiektu danych za pośrednictwem struktury co będzie obowiązywać podczas uzyskiwania dostępu do za pomocą innych struktury.</span><span class="sxs-lookup"><span data-stu-id="2cc1f-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc1f-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2cc1f-120">See Also</span></span>  
 [<span data-ttu-id="2cc1f-121">Typy danych</span><span class="sxs-lookup"><span data-stu-id="2cc1f-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="2cc1f-122">Podstawowe typy danych</span><span class="sxs-lookup"><span data-stu-id="2cc1f-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="2cc1f-123">Złożone typy danych</span><span class="sxs-lookup"><span data-stu-id="2cc1f-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="2cc1f-124">Typy wartości i typy referencyjne</span><span class="sxs-lookup"><span data-stu-id="2cc1f-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="2cc1f-125">Struktury</span><span class="sxs-lookup"><span data-stu-id="2cc1f-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="2cc1f-126">Rozwiązywanie problemów z typów danych</span><span class="sxs-lookup"><span data-stu-id="2cc1f-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="2cc1f-127">Porady: deklarowanie struktury</span><span class="sxs-lookup"><span data-stu-id="2cc1f-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="2cc1f-128">Struktury oraz inne elementy programowania</span><span class="sxs-lookup"><span data-stu-id="2cc1f-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="2cc1f-129">Struktury i klasy</span><span class="sxs-lookup"><span data-stu-id="2cc1f-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="2cc1f-130">Structure — instrukcja</span><span class="sxs-lookup"><span data-stu-id="2cc1f-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)