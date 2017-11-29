---
title: "Co można zrobić za pomocą LINQ do SQL"
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
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 26d20a220f1d88cee0b577d112048c8bb0e84285
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="what-you-can-do-with-linq-to-sql"></a><span data-ttu-id="4f104-102">Co można zrobić za pomocą LINQ do SQL</span><span class="sxs-lookup"><span data-stu-id="4f104-102">What You Can Do With LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4f104-103">obsługuje wszystkie funkcje klucza, który można oczekiwać Deweloper SQL.</span><span class="sxs-lookup"><span data-stu-id="4f104-103"> supports all the key capabilities you would expect as a SQL developer.</span></span> <span data-ttu-id="4f104-104">Można wyszukiwać informacje i wstawiania, aktualizacji i usuwania informacji z tabel.</span><span class="sxs-lookup"><span data-stu-id="4f104-104">You can query for information, and insert, update, and delete information from tables.</span></span>  
  
## <a name="selecting"></a><span data-ttu-id="4f104-105">Wybieranie</span><span class="sxs-lookup"><span data-stu-id="4f104-105">Selecting</span></span>  
 <span data-ttu-id="4f104-106">Wybieranie (*projekcji*) jest to osiągane przez właśnie zapisywania [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] kwerendy w języku programowania, a następnie wykonywanie tej kwerendy można pobrać wyników.</span><span class="sxs-lookup"><span data-stu-id="4f104-106">Selecting (*projection*) is achieved by just writing a [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] query in your own programming language, and then executing that query to retrieve the results.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4f104-107">przekłada się wszelkie niezbędne działania na potrzeby operacji SQL, które znasz.</span><span class="sxs-lookup"><span data-stu-id="4f104-107"> itself translates all the necessary operations into the necessary SQL operations that you are familiar with.</span></span> <span data-ttu-id="4f104-108">Aby uzyskać więcej informacji, zobacz [LINQ do SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="4f104-108">For more information, see [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="4f104-109">W poniższym przykładzie nazwy firm klientów z Londynu są pobierane i wyświetlane w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="4f104-109">In the following example, the company names of customers from London are retrieved and displayed in the console window.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a><span data-ttu-id="4f104-110">Wstawianie</span><span class="sxs-lookup"><span data-stu-id="4f104-110">Inserting</span></span>  
 <span data-ttu-id="4f104-111">Aby wykonać SQL `Insert`, wystarczy dodać obiekty do modelu obiektów, które zostały utworzone i wywołanie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> na <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="4f104-111">To execute a SQL `Insert`, just add objects to the object model you have created, and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="4f104-112">W poniższym przykładzie nowego klienta i informacje na temat klienta jest dodawany do `Customers` tabeli za pomocą <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f104-112">In the following example, a new customer and information about the customer is added to the `Customers` table by using <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a><span data-ttu-id="4f104-113">Aktualizowanie</span><span class="sxs-lookup"><span data-stu-id="4f104-113">Updating</span></span>  
 <span data-ttu-id="4f104-114">Aby `Update` zapisu bazy danych, najpierw pobrać element i edytować bezpośrednio w modelu obiektu.</span><span class="sxs-lookup"><span data-stu-id="4f104-114">To `Update` a database entry, first retrieve the item and edit it directly in the object model.</span></span> <span data-ttu-id="4f104-115">Po zmodyfikowaniu obiektu wywołać <xref:System.Data.Linq.DataContext.SubmitChanges%2A> na <xref:System.Data.Linq.DataContext> aktualizacji bazy danych.</span><span class="sxs-lookup"><span data-stu-id="4f104-115">After you have modified the object, call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to update the database.</span></span>  
  
 <span data-ttu-id="4f104-116">W poniższym przykładzie są pobierane wszystkich klientów, którzy są w Londynie.</span><span class="sxs-lookup"><span data-stu-id="4f104-116">In the following example, all customers who are from London are retrieved.</span></span> <span data-ttu-id="4f104-117">Następnie nazwę miasta jest zmieniony z "Londynie" na "Metro — Londynie".</span><span class="sxs-lookup"><span data-stu-id="4f104-117">Then the name of the city is changed from "London" to "London - Metro".</span></span> <span data-ttu-id="4f104-118">Na koniec <xref:System.Data.Linq.DataContext.SubmitChanges%2A> jest wywoływana, aby wysłać zmiany do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="4f104-118">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to send the changes to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a><span data-ttu-id="4f104-119">Usuwanie</span><span class="sxs-lookup"><span data-stu-id="4f104-119">Deleting</span></span>  
 <span data-ttu-id="4f104-120">Aby `Delete` elementu, Usuń element z kolekcji, do której należy, a następnie wywołania <xref:System.Data.Linq.DataContext.SubmitChanges%2A> na <xref:System.Data.Linq.DataContext> można zatwierdzić zmiany.</span><span class="sxs-lookup"><span data-stu-id="4f104-120">To `Delete` an item, remove the item from the collection to which it belongs, and then call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to commit the change.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4f104-121">nie rozpoznaje operacjami usuwania kaskadowego.</span><span class="sxs-lookup"><span data-stu-id="4f104-121"> does not recognize cascade-delete operations.</span></span> <span data-ttu-id="4f104-122">Jeśli chcesz usunąć wiersz w tabeli, która ma ograniczenia na nim, zobacz [porady: usuwanie wierszy z bazy danych](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="4f104-122">If you want to delete a row in a table that has constraints against it, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="4f104-123">W poniższym przykładzie klienta, który ma `CustomerID` z `98128` są pobierane z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="4f104-123">In the following example, the customer who has `CustomerID` of `98128` is retrieved from the database.</span></span> <span data-ttu-id="4f104-124">Po potwierdzeniu, że pobrano wiersza klienta, a następnie <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> jest wywoływana, aby usunąć ten obiekt z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="4f104-124">Then, after confirming that the customer row was retrieved, <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> is called to remove that object from the collection.</span></span> <span data-ttu-id="4f104-125">Na koniec <xref:System.Data.Linq.DataContext.SubmitChanges%2A> jest wywoływana w celu przekazywania do usunięcia bazy danych.</span><span class="sxs-lookup"><span data-stu-id="4f104-125">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to forward the deletion to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4f104-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4f104-126">See Also</span></span>  
 [<span data-ttu-id="4f104-127">Przewodnik programowania w języku</span><span class="sxs-lookup"><span data-stu-id="4f104-127">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [<span data-ttu-id="4f104-128">LINQ do SQL modelu obiektów</span><span class="sxs-lookup"><span data-stu-id="4f104-128">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="4f104-129">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="4f104-129">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)