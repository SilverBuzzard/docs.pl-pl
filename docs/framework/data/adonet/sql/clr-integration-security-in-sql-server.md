---
title: "CLR Integration zabezpieczeń w programie SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: de4f4b1ae5ba252778d9463cba43a9ccb419600a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="7e3bb-102">CLR Integration zabezpieczeń w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e3bb-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="7e3bb-103">Microsoft SQL Server zapewnia integrację składnika wspólne języka wspólnego (CLR) programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="7e3bb-104">Integrację środowiska CLR umożliwia pisanie procedur składowanych, wyzwalaczy, typy danych zdefiniowane przez użytkownika, funkcjach zdefiniowanych przez użytkownika, agregacje zdefiniowane przez użytkownika i przesyłania strumieniowego funkcji zwracającej tabelę przy użyciu dowolnego języka .NET Framework, takich jak Microsoft Visual Basic .NET lub Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="7e3bb-105">Środowisko CLR obsługuje model zabezpieczeń o nazwie zabezpieczenia dostępu kodu (CAS) dla kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="7e3bb-106">W tym modelu przyznano uprawnienia do zestawów w oparciu o dowody dostarczone przez kod w metadanych.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="7e3bb-107">SQL Server model zabezpieczeń oparty na użytkownika programu SQL Server jest zintegrowany z modelu zabezpieczeń opartego na dostępie kodu środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="7e3bb-108">Zasoby zewnętrzne</span><span class="sxs-lookup"><span data-stu-id="7e3bb-108">External Resources</span></span>  
 <span data-ttu-id="7e3bb-109">Aby uzyskać więcej informacji o integracji środowiska CLR programu SQL Server zobacz następujące zasoby.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="7e3bb-110">Zasób</span><span class="sxs-lookup"><span data-stu-id="7e3bb-110">Resource</span></span>|<span data-ttu-id="7e3bb-111">Opis</span><span class="sxs-lookup"><span data-stu-id="7e3bb-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="7e3bb-112">Zabezpieczenia dostępu kodu</span><span class="sxs-lookup"><span data-stu-id="7e3bb-112">Code Access Security</span></span>](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)|<span data-ttu-id="7e3bb-113">Zawiera tematy opisujące urzędów certyfikacji w programie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="7e3bb-114">Zabezpieczenia integracji środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="7e3bb-114">CLR Integration Security</span></span>](http://go.microsoft.com/fwlink/?LinkId=59998)|<span data-ttu-id="7e3bb-115">Omówienie modelu zabezpieczeń wykonania kodu zarządzanego wewnątrz programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e3bb-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7e3bb-116">See Also</span></span>  
 [<span data-ttu-id="7e3bb-117">Zabezpieczanie aplikacji ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7e3bb-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="7e3bb-118">Scenariusze zabezpieczeń aplikacji w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e3bb-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="7e3bb-119">SQL Server integrację środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="7e3bb-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [<span data-ttu-id="7e3bb-120">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="7e3bb-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)