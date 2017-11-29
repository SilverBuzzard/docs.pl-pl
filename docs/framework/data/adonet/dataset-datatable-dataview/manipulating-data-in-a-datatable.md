---
title: Manipulowanie danymi w DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 341723d44960d4eaf9d8338e3c266720816c0899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="8cefc-102">Manipulowanie danymi w DataTable</span><span class="sxs-lookup"><span data-stu-id="8cefc-102">Manipulating Data in a DataTable</span></span>
<span data-ttu-id="8cefc-103">Po utworzeniu <xref:System.Data.DataTable> w <xref:System.Data.DataSet>, można wykonywać działania sam, jak przy użyciu tabelę w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="8cefc-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="8cefc-104">Można dodać, wyświetlać, edytować i usuwać dane w tabeli; można monitorować błędów i zdarzeń; i można wyszukiwać dane w tabeli.</span><span class="sxs-lookup"><span data-stu-id="8cefc-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="8cefc-105">Podczas modyfikowania danych w **DataTable**, można też sprawdzić czy zmiany są poprawne i określ, czy do programowego zaakceptować lub odrzucić zmiany.</span><span class="sxs-lookup"><span data-stu-id="8cefc-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8cefc-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="8cefc-106">In This Section</span></span>  
 [<span data-ttu-id="8cefc-107">Dodawanie danych do elementu DataTable</span><span class="sxs-lookup"><span data-stu-id="8cefc-107">Adding Data to a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-data-to-a-datatable.md)  
 <span data-ttu-id="8cefc-108">Wyjaśniono, jak utworzyć nowe wiersze i dodać je do tabeli.</span><span class="sxs-lookup"><span data-stu-id="8cefc-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="8cefc-109">Wyświetlanie danych w DataTable</span><span class="sxs-lookup"><span data-stu-id="8cefc-109">Viewing Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/viewing-data-in-a-datatable.md)  
 <span data-ttu-id="8cefc-110">Opisuje sposób uzyskać dostęp do danych w wierszu, łącznie z oryginalnego i bieżącej wersji danych.</span><span class="sxs-lookup"><span data-stu-id="8cefc-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="8cefc-111">Metoda Load</span><span class="sxs-lookup"><span data-stu-id="8cefc-111">The Load Method</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/the-load-method.md)  
 <span data-ttu-id="8cefc-112">Opisuje **obciążenia** metody, aby wypełnić **DataTable** z wierszami.</span><span class="sxs-lookup"><span data-stu-id="8cefc-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="8cefc-113">Zmiany elementu DataTable</span><span class="sxs-lookup"><span data-stu-id="8cefc-113">DataTable Edits</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-edits.md)  
 <span data-ttu-id="8cefc-114">Wyjaśniono, jak modyfikować danych w wierszu, w tym wstrzymywania zmiany do wiersza, dopóki proponowanych zmian są zweryfikowane i zaakceptowane.</span><span class="sxs-lookup"><span data-stu-id="8cefc-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="8cefc-115">Stany wiersza i wersje wiersza</span><span class="sxs-lookup"><span data-stu-id="8cefc-115">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 <span data-ttu-id="8cefc-116">Zawiera informacje o stanach innego wiersza.</span><span class="sxs-lookup"><span data-stu-id="8cefc-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="8cefc-117">Usunięcie elementu DataRow</span><span class="sxs-lookup"><span data-stu-id="8cefc-117">DataRow Deletion</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarow-deletion.md)  
 <span data-ttu-id="8cefc-118">Opisuje sposób usuwania wiersza z tabeli.</span><span class="sxs-lookup"><span data-stu-id="8cefc-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="8cefc-119">Informacje o błędzie wiersza</span><span class="sxs-lookup"><span data-stu-id="8cefc-119">Row Error Information</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 <span data-ttu-id="8cefc-120">Wyjaśniono, jak można wstawić informacje o błędzie na wiersz, aby ułatwić rozwiązywanie problemów z danymi w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8cefc-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="8cefc-121">Metoda AcceptChanges i RejectChanges</span><span class="sxs-lookup"><span data-stu-id="8cefc-121">AcceptChanges and RejectChanges</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="8cefc-122">Wyjaśniono, jak zaakceptować lub odrzucić zmiany wprowadzone do wiersza.</span><span class="sxs-lookup"><span data-stu-id="8cefc-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cefc-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8cefc-123">See Also</span></span>  
 [<span data-ttu-id="8cefc-124">DataTables</span><span class="sxs-lookup"><span data-stu-id="8cefc-124">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="8cefc-125">Obsługa zdarzeń DataTable</span><span class="sxs-lookup"><span data-stu-id="8cefc-125">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="8cefc-126">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="8cefc-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)