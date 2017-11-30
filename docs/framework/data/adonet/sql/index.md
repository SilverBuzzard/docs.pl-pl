---
title: SQL Server i ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ab519f7881dd20c3fd9e2e08fef14591477d94a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="323fb-102">SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="323fb-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="323fb-103">W tej sekcji opisano funkcje i zachowania, które są specyficzne dla dostawcy danych programu .NET Framework dla programu SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="323fb-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="323fb-104"><xref:System.Data.SqlClient>zapewnia dostęp do wersji programu SQL Server, który hermetyzuje protokołów specyficzny dla bazy danych.</span><span class="sxs-lookup"><span data-stu-id="323fb-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="323fb-105">Funkcje dostawcy danych zaprojektowano w sposób podobny do dostawcy danych .NET Framework dla OLE DB i ODBC, Oracle.</span><span class="sxs-lookup"><span data-stu-id="323fb-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="323fb-106"><xref:System.Data.SqlClient>zawiera dane tabelaryczne analizator strumienia (TDS) do bezpośredniego komunikowania się z serwerem SQL.</span><span class="sxs-lookup"><span data-stu-id="323fb-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="323fb-107">Aby użyć dostawcy danych programu .NET Framework dla programu SQL Server, musi odwoływać się aplikacji <xref:System.Data.SqlClient> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="323fb-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="323fb-108">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="323fb-108">In This Section</span></span>  
 [<span data-ttu-id="323fb-109">Zabezpieczenia serwera SQL</span><span class="sxs-lookup"><span data-stu-id="323fb-109">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="323fb-110">Zawiera omówienie funkcji zabezpieczeń programu SQL Server i scenariusze aplikacji do tworzenia bezpiecznego aplikacji ADO.NET obiektu docelowego programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="323fb-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="323fb-111">Danych programu SQL Server typy i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="323fb-111">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 <span data-ttu-id="323fb-112">Opisuje sposób pracy z typami danych programu SQL Server oraz sposób ich interakcji z typami danych .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="323fb-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="323fb-113">Dane binarne i duża wartość serwera SQL</span><span class="sxs-lookup"><span data-stu-id="323fb-113">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="323fb-114">Opisuje sposób pracy z danymi duża wartość w programie SQL Server.</span><span class="sxs-lookup"><span data-stu-id="323fb-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="323fb-115">Operacje danych serwera SQL w ADO.NET</span><span class="sxs-lookup"><span data-stu-id="323fb-115">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 <span data-ttu-id="323fb-116">Opisuje sposób pracy z danymi w programie SQL Server.</span><span class="sxs-lookup"><span data-stu-id="323fb-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="323fb-117">Zawiera sekcje dotyczące operacje kopiowania masowego, MARS operacji asynchronicznych i parametry przechowywanymi w tabeli.</span><span class="sxs-lookup"><span data-stu-id="323fb-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="323fb-118">Funkcje serwera SQL i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="323fb-118">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 <span data-ttu-id="323fb-119">Zawiera opis funkcji programu SQL Server, które są przydatne dla deweloperów aplikacji ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="323fb-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="323fb-120">LINQ do SQL</span><span class="sxs-lookup"><span data-stu-id="323fb-120">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="323fb-121">Opisuje podstawowe bloki konstrukcyjne, procesów i technik wymagane do utworzenia LINQ do SQL aplikacji.</span><span class="sxs-lookup"><span data-stu-id="323fb-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="323fb-122">Pełną dokumentację aparatu bazy danych programu SQL Server dla programu SQL Server — książki Online dla używanej wersji programu SQL Server są używane.</span><span class="sxs-lookup"><span data-stu-id="323fb-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="323fb-123">SQL Server — książki Online</span><span class="sxs-lookup"><span data-stu-id="323fb-123">SQL Server Books Online</span></span>](http://msdn.microsoft.com/library/ms130214.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="323fb-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="323fb-124">See Also</span></span>  
 [<span data-ttu-id="323fb-125">Zabezpieczanie aplikacji ADO.NET</span><span class="sxs-lookup"><span data-stu-id="323fb-125">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="323fb-126">Mapowanie typu danych w ADO.NET</span><span class="sxs-lookup"><span data-stu-id="323fb-126">Data Type Mappings in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="323fb-127">Zbiory danych, DataTables i DataViews</span><span class="sxs-lookup"><span data-stu-id="323fb-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="323fb-128">Trwa pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="323fb-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="323fb-129">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="323fb-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)