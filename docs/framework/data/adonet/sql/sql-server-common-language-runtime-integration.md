---
title: "SQL Server integrację środowiska uruchomieniowego"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3705db8b9d359ce83c6c47bef58de327745bed44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="c9d02-102">SQL Server integrację środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="c9d02-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="c9d02-103">SQL Server 2005 wprowadzono integracji składnika wspólne języka wspólnego (CLR) programu .NET Framework dla programu Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="c9d02-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="c9d02-104">Oznacza to, czy możesz zapisywać procedur składowanych, wyzwalaczy, typy danych zdefiniowane przez użytkownika, funkcjach zdefiniowanych przez użytkownika, agregacje zdefiniowane przez użytkownika i przesyłania strumieniowego funkcji zwracającej tabelę przy użyciu dowolnego języka .NET Framework, w tym programu Microsoft Visual Basic .NET i firmy Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="c9d02-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="c9d02-105"><xref:Microsoft.SqlServer.Server> Przestrzeń nazw zawiera zestawu nowych interfejsów programowania aplikacji (API), dzięki czemu kod zarządzany mogą współdziałać ze środowiskiem programu Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c9d02-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="c9d02-106">W tej sekcji opisano funkcje i zachowania, które są specyficzne dla programu SQL Server integrację środowiska uruchomieniowego (języka wspólnego CLR) i programu SQL Server wewnątrzprocesowe określonego rozszerzenia do ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="c9d02-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="c9d02-107">Ta sekcja ma zapewnić tylko za mało informacji, aby rozpocząć programowanie z integrację środowiska CLR programu SQL Server i nie jest przeznaczona pełne.</span><span class="sxs-lookup"><span data-stu-id="c9d02-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="c9d02-108">Aby uzyskać szczegółowe informacje Zobacz wersji programu SQL Server — książki Online dla wersji programu SQL Server są przy użyciu.</span><span class="sxs-lookup"><span data-stu-id="c9d02-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="c9d02-109">**SQL Server — książki Online**</span><span class="sxs-lookup"><span data-stu-id="c9d02-109">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="c9d02-110">Koncepcje programowania integracji wspólnego języka środowiska uruchomieniowego (języka wspólnego CLR)</span><span class="sxs-lookup"><span data-stu-id="c9d02-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="c9d02-111">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="c9d02-111">In This Section</span></span>  
 [<span data-ttu-id="c9d02-112">Wprowadzenie do integracji środowiska CLR programu SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9d02-112">Introduction to SQL Server CLR Integration</span></span>](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="c9d02-113">Wprowadzenie do integracji środowiska CLR programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c9d02-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="c9d02-114">Zawiera łącza do dodatkowych tematów.</span><span class="sxs-lookup"><span data-stu-id="c9d02-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="c9d02-115">Funkcje zdefiniowane przez użytkownika CLR</span><span class="sxs-lookup"><span data-stu-id="c9d02-115">CLR User-Defined Functions</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 <span data-ttu-id="c9d02-116">Opisuje sposób zaimplementowania i użycia różnych typów funkcji CLR: przechowywanymi w tabeli, skalarne i zdefiniowanych przez użytkownika funkcji agregujących.</span><span class="sxs-lookup"><span data-stu-id="c9d02-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="c9d02-117">Typy danych zdefiniowane przez użytkownika CLR</span><span class="sxs-lookup"><span data-stu-id="c9d02-117">CLR User-Defined Types</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 <span data-ttu-id="c9d02-118">Opisuje sposób zaimplementowania i użycia typy CLR zdefiniowane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c9d02-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="c9d02-119">Zawiera łącza do dodatkowych tematów.</span><span class="sxs-lookup"><span data-stu-id="c9d02-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="c9d02-120">Procedury składowane CLR</span><span class="sxs-lookup"><span data-stu-id="c9d02-120">CLR Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 <span data-ttu-id="c9d02-121">Opisuje sposób zaimplementowania i użycia procedur składowanych CLR.</span><span class="sxs-lookup"><span data-stu-id="c9d02-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="c9d02-122">Zawiera łącza do dodatkowych tematów.</span><span class="sxs-lookup"><span data-stu-id="c9d02-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="c9d02-123">Wyzwalacze CLR</span><span class="sxs-lookup"><span data-stu-id="c9d02-123">CLR Triggers</span></span>](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 <span data-ttu-id="c9d02-124">Opisuje sposób zaimplementowania i użycia wyzwalacze CLR.</span><span class="sxs-lookup"><span data-stu-id="c9d02-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="c9d02-125">Zawiera łącza do dodatkowych tematów.</span><span class="sxs-lookup"><span data-stu-id="c9d02-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="c9d02-126">Połączenie kontekstu</span><span class="sxs-lookup"><span data-stu-id="c9d02-126">The Context Connection</span></span>](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 <span data-ttu-id="c9d02-127">Zawiera opis połączenia kontekstu.</span><span class="sxs-lookup"><span data-stu-id="c9d02-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="c9d02-128">Zachowanie w procesie specyficzne dla serwera SQL ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9d02-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="c9d02-129">Opisuje rozszerzenia określone w procesie programu SQL Server do ADO.NET i połączenia kontekstu.</span><span class="sxs-lookup"><span data-stu-id="c9d02-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="c9d02-130">Zawiera łącza do dodatkowych tematów.</span><span class="sxs-lookup"><span data-stu-id="c9d02-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9d02-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c9d02-131">See Also</span></span>  
 [<span data-ttu-id="c9d02-132">SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9d02-132">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="c9d02-133">Tworzenie obiekty programu SQL Server 2005 w kodzie zarządzanym</span><span class="sxs-lookup"><span data-stu-id="c9d02-133">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="c9d02-134">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="c9d02-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)