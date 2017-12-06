---
title: "Dodawanie logiki biznesowej przy użyciu metody częściowe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f9cbaa156fd794a6f9faf44d8d980159f8ae520e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="f0d93-102">Dodawanie logiki biznesowej przy użyciu metody częściowe</span><span class="sxs-lookup"><span data-stu-id="f0d93-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="f0d93-103">Można dostosować [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] i C# wygenerowany kod w Twojej [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projektów przy użyciu *metody częściowe*.</span><span class="sxs-lookup"><span data-stu-id="f0d93-103">You can customize [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="f0d93-104">Kod który [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generuje definiuje podpisów w ramach jednej metody częściowej.</span><span class="sxs-lookup"><span data-stu-id="f0d93-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="f0d93-105">Jeśli chcesz zaimplementować metodę, można dodać własne metody częściowej.</span><span class="sxs-lookup"><span data-stu-id="f0d93-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="f0d93-106">Jeśli nie należy dodawać własną implementację, kompilator odrzuca podpis metody częściowe i wywołuje metody domyślnej [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0d93-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0d93-107">Jeśli używasz [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], można użyć [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] dodać weryfikacji i inne dostosowania do klas jednostek.</span><span class="sxs-lookup"><span data-stu-id="f0d93-107">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="f0d93-108">Na przykład domyślnego mapowania dla `Customer` klasa w bazie danych Northwind zawiera następujące metody częściowej:</span><span class="sxs-lookup"><span data-stu-id="f0d93-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="f0d93-109">Można zaimplementować własnej metody przez dodanie następującego kodu do własnych częściowego `Customer` klasy:</span><span class="sxs-lookup"><span data-stu-id="f0d93-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="f0d93-110">Ta metoda jest zwykle używana w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] do przesłonięcia metody domyślnej `Insert`, `Update`, `Delete`oraz zweryfikowanie właściwości podczas zdarzenia cyklu życia obiektów.</span><span class="sxs-lookup"><span data-stu-id="f0d93-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="f0d93-111">Aby uzyskać więcej informacji, zobacz [metody częściowe](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) lub [partial — metoda () (odwołanie w C#)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="f0d93-111">For more information, see [Partial Methods](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) or [partial (Method) (C# Reference)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0d93-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="f0d93-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f0d93-113">Opis</span><span class="sxs-lookup"><span data-stu-id="f0d93-113">Description</span></span>  
 <span data-ttu-id="f0d93-114">W poniższym przykładzie przedstawiono `ExampleClass` najpierw może być zdefiniowana przez narzędzie generowania kodu, takie jak SQLMetal, a następnie jak może zastosować tylko jeden z dwóch metod.</span><span class="sxs-lookup"><span data-stu-id="f0d93-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f0d93-115">Kod</span><span class="sxs-lookup"><span data-stu-id="f0d93-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="f0d93-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="f0d93-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f0d93-117">Opis</span><span class="sxs-lookup"><span data-stu-id="f0d93-117">Description</span></span>  
 <span data-ttu-id="f0d93-118">W poniższym przykładzie użyto relacji między `Shipper` i `Order` jednostek.</span><span class="sxs-lookup"><span data-stu-id="f0d93-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="f0d93-119">Należy zwrócić uwagę wśród metod metody częściowe `InsertShipper` i `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="f0d93-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="f0d93-120">Te metody zastąpienie domyślnych metod częściowych dostarczonych przez [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapowania.</span><span class="sxs-lookup"><span data-stu-id="f0d93-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f0d93-121">Kod</span><span class="sxs-lookup"><span data-stu-id="f0d93-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f0d93-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f0d93-122">See Also</span></span>  
 [<span data-ttu-id="f0d93-123">Tworzenie i przesyłanie zmian danych</span><span class="sxs-lookup"><span data-stu-id="f0d93-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="f0d93-124">Dostosowywanie wstawiania, aktualizowania i usuwania operacji</span><span class="sxs-lookup"><span data-stu-id="f0d93-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)