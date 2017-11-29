---
title: "Poziomy zaufania zabezpieczeń podczas uzyskiwania dostępu do zasobów"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb5be924-317d-4d69-b33a-3d18ecfb9d6e
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4cefe74b745eb4a1c71124176985c548f9b1244
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="security-trust-levels-in-accessing-resources"></a><span data-ttu-id="9d228-102">Poziomy zaufania zabezpieczeń podczas uzyskiwania dostępu do zasobów</span><span class="sxs-lookup"><span data-stu-id="9d228-102">Security Trust Levels in Accessing Resources</span></span>
<span data-ttu-id="9d228-103">W tym temacie opisano, jak dostęp jest ograniczony do typów zasobów, które <xref:System.Transactions> przedstawia.</span><span class="sxs-lookup"><span data-stu-id="9d228-103">This topic discusses how access is restricted on the types of resources that <xref:System.Transactions> exposes.</span></span>  
  
 <span data-ttu-id="9d228-104">Istnieją trzy główne poziomy zaufania <xref:System.Transactions>.</span><span class="sxs-lookup"><span data-stu-id="9d228-104">There are three main levels of trust for <xref:System.Transactions>.</span></span> <span data-ttu-id="9d228-105">Poziomy zaufania są definiowane w oparciu o typy zasobów który <xref:System.Transactions> ujawnia i poziom zaufania, który powinien uzyskać dostęp do tych zasobów.</span><span class="sxs-lookup"><span data-stu-id="9d228-105">The trust levels are defined based on the types of resources that <xref:System.Transactions> exposes, and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="9d228-106">Zasoby który <xref:System.Transactions> zapewnia dostęp do pamięci systemowej, zasoby całego procesu współużytkowanego i międzynarodowe zasoby systemowe.</span><span class="sxs-lookup"><span data-stu-id="9d228-106">The resources that <xref:System.Transactions> provides access to are system memory, shared process wide resources, and system wide resources.</span></span> <span data-ttu-id="9d228-107">Dostępne są następujące poziomy:</span><span class="sxs-lookup"><span data-stu-id="9d228-107">The levels are:</span></span>  
  
-   <span data-ttu-id="9d228-108">**AllowPartiallyTrustedCallers** (APTCA) dla aplikacji za pomocą transakcji w obrębie domeny pojedynczej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9d228-108">**AllowPartiallyTrustedCallers** (APTCA) for applications using transactions within a single application domain.</span></span>  
  
-   <span data-ttu-id="9d228-109">**DistributedTransactionPermission** (DTP) dla aplikacji za pomocą transakcji rozproszonych.</span><span class="sxs-lookup"><span data-stu-id="9d228-109">**DistributedTransactionPermission** (DTP) for applications using distributed transactions.</span></span>  
  
-   <span data-ttu-id="9d228-110">Pełne zaufanie trwałe zasobów, konfiguracji aplikacji do zarządzania i starsze aplikacje międzyoperacyjne.</span><span class="sxs-lookup"><span data-stu-id="9d228-110">Full trust for durable resources, configuration management applications, and legacy interop applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d228-111">Nie należy wywołać wszystkich interfejsów rejestracja przy użyciu personifikowanej kontekstów.</span><span class="sxs-lookup"><span data-stu-id="9d228-111">You should not call any of the enlistment interfaces with impersonated contexts.</span></span>  
  
## <a name="trust-levels"></a><span data-ttu-id="9d228-112">Poziomy zaufania</span><span class="sxs-lookup"><span data-stu-id="9d228-112">Trust Levels</span></span>  
  
### <a name="aptca-partial-trust"></a><span data-ttu-id="9d228-113">APTCA (częściowej relacji zaufania)</span><span class="sxs-lookup"><span data-stu-id="9d228-113">APTCA (Partial Trust)</span></span>  
 <span data-ttu-id="9d228-114"><xref:System.Transactions> Zestawu może być wywoływany przez kod częściowo zaufany, ponieważ została ona oznaczona z **AllowPartiallyTrustedCallers** atrybutu (APTCA).</span><span class="sxs-lookup"><span data-stu-id="9d228-114">The <xref:System.Transactions> assembly can be called by partially trusted code because it has been marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="9d228-115">Ten atrybut zasadniczo usuwa niejawne <xref:System.Security.Permissions.SecurityAction.LinkDemand> dla **FullTrust** oznacza to zestaw uprawnień w przeciwnym razie automatycznie umieszczane w każdej metody publicznie dostępne w poszczególnych typów.</span><span class="sxs-lookup"><span data-stu-id="9d228-115">This attribute essentially removes the implicit <xref:System.Security.Permissions.SecurityAction.LinkDemand> for the **FullTrust** permission set that is otherwise automatically placed on each publicly accessible method in each type.</span></span> <span data-ttu-id="9d228-116">Niektóre typy i elementy członkowskie nadal wymaga jednak lepsze gwarancje uprawnień.</span><span class="sxs-lookup"><span data-stu-id="9d228-116">However, some types and members still require stronger permissions.</span></span>  
  
 <span data-ttu-id="9d228-117">Atrybut APTCA umożliwia aplikacjom używanie transakcji w częściowej relacji zaufania w domenie pojedynczej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9d228-117">The APTCA attribute enables applications to use transactions in partial trust within a single application domain.</span></span> <span data-ttu-id="9d228-118">Umożliwia to-eskalowany transakcji i nietrwałe, które mogą być używane do obsługi błędów.</span><span class="sxs-lookup"><span data-stu-id="9d228-118">This enables non-escalated transactions and volatile enlistments that can be used for error handling.</span></span> <span data-ttu-id="9d228-119">Przykładem tego jest tablicy skrótów transakcyjne i aplikacja, która korzysta z niego.</span><span class="sxs-lookup"><span data-stu-id="9d228-119">One example of this is a transacted hash table and an application that uses it.</span></span> <span data-ttu-id="9d228-120">Dane mogą być dodawane do lub usunięte z tabeli skrótu w pojedynczą transakcję.</span><span class="sxs-lookup"><span data-stu-id="9d228-120">Data can be added to and removed from the hash table under a single transaction.</span></span> <span data-ttu-id="9d228-121">Jeśli transakcja jest później wycofana, wszystkie zmiany wprowadzone w tabeli wyznaczania wartości skrótu, w tym transakcji można cofnąć.</span><span class="sxs-lookup"><span data-stu-id="9d228-121">If the transaction is later rolled back, all of the changes made to the hash table under that transaction can be undone.</span></span>  
  
### <a name="distributedtransactionpermission-dtp"></a><span data-ttu-id="9d228-122">DistributedTransactionPermission (DTP)</span><span class="sxs-lookup"><span data-stu-id="9d228-122">DistributedTransactionPermission (DTP)</span></span>  
 <span data-ttu-id="9d228-123">Gdy <xref:System.Transactions> eskalacji transakcji, aby były zarządzane przez MSDTC, <xref:System.Transactions> wymagań <xref:System.Transactions.DistributedTransactionPermission> (DTP), aby utworzyć transakcji rozproszonych.</span><span class="sxs-lookup"><span data-stu-id="9d228-123">When a <xref:System.Transactions> transaction is escalated to be managed by MSDTC, <xref:System.Transactions> demands the <xref:System.Transactions.DistributedTransactionPermission> (DTP) to create the distributed transaction.</span></span> <span data-ttu-id="9d228-124">Oznacza to, że transakcje mogą być przekazany kod (takie jak za pomocą serializacji lub dodatkowe trwałych rejestracji) musi otrzymać DTP.</span><span class="sxs-lookup"><span data-stu-id="9d228-124">This means that the code that causes the transaction to be escalated (such as through serialization or additional durable enlistments) would need to be granted DTP.</span></span> <span data-ttu-id="9d228-125">Kod, który pierwotnie został utworzony <xref:System.Transactions> transakcji nie trzeba mieć to uprawnienie.</span><span class="sxs-lookup"><span data-stu-id="9d228-125">The code that originally created the <xref:System.Transactions> transaction does not necessarily need to possess this permission.</span></span>  
  
### <a name="fulltrust-link-demands"></a><span data-ttu-id="9d228-126">Wymaga FullTrust łącza</span><span class="sxs-lookup"><span data-stu-id="9d228-126">FullTrust Link Demands</span></span>  
 <span data-ttu-id="9d228-127">Ten poziom uprawnień jest przeznaczony do ograniczenia aplikacji, które zapisują trwałe zasobów.</span><span class="sxs-lookup"><span data-stu-id="9d228-127">This permission level is intended to restrict applications that are writing to durable resources.</span></span> <span data-ttu-id="9d228-128">W przypadku awarii aplikacji musi istnieć możliwość odzyskania z menedżerem transakcji, aby określić ostateczny wynik transakcji, tak aby można było uaktualnić trwałych danych.</span><span class="sxs-lookup"><span data-stu-id="9d228-128">Upon failure, the application needs to be able to recover with the transaction manager to determine the final outcome of the transaction, so that it can update permanent data.</span></span> <span data-ttu-id="9d228-129">Ten typ aplikacji nosi nazwę menedżera trwałe źródła.</span><span class="sxs-lookup"><span data-stu-id="9d228-129">This type of application is known as a durable source manager.</span></span> <span data-ttu-id="9d228-130">Klasycznym przykładem tego typu aplikacji jest SQL.</span><span class="sxs-lookup"><span data-stu-id="9d228-130">A classic example of this type of application is SQL.</span></span>  
  
 <span data-ttu-id="9d228-131">Aby włączyć odzyskiwanie, ten typ aplikacji może stale zużywanie zasobów systemowych.</span><span class="sxs-lookup"><span data-stu-id="9d228-131">To enable recovery, this type of application has the ability to permanently consume system resources.</span></span> <span data-ttu-id="9d228-132">Jest to spowodowane Menedżer transakcji do odzyskania musi zapamiętać transakcje, które mają wykonywane, dopóki nie można potwierdzić, że otrzymane wyniki wszystkich menedżerów trwałe zasobów, które uczestniczą w transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d228-132">This is because the recoverable transaction manager must remember transactions that have committed until it can confirm that all durable resource managers that are participating in the transaction have received the outcome.</span></span> <span data-ttu-id="9d228-133">Dlatego ten typ aplikacji wymaga pełnego zaufania i nie powinna być uruchamiana, chyba że któremu przyznano poziom zaufania.</span><span class="sxs-lookup"><span data-stu-id="9d228-133">Therefore, this type of application requires full trust and should not be run unless that level of trust has been granted.</span></span>  
  
 <span data-ttu-id="9d228-134">Aby uzyskać więcej informacji o trwałych rejestracji i odzyskiwania, zobacz [rejestrowanie zasobów jako uczestnicy transakcji](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) i [wykonywania odzyskiwania](../../../../docs/framework/data/transactions/performing-recovery.md) tematów.</span><span class="sxs-lookup"><span data-stu-id="9d228-134">For more information on durable enlistments and recovery, see the [Enlisting Resources as Participants in a Transaction](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) and [Performing Recovery](../../../../docs/framework/data/transactions/performing-recovery.md) topics.</span></span>  
  
 <span data-ttu-id="9d228-135">Aplikacje wykonujące starszych międzyoperacyjnego korzystają z modelu COM + również muszą mieć pełne zaufanie.</span><span class="sxs-lookup"><span data-stu-id="9d228-135">Applications that perform legacy interop work with COM+ are also required to have full trust.</span></span>  
  
 <span data-ttu-id="9d228-136">Poniżej przedstawiono listę typów i członków, których nie można wywołać przez częściowo zaufanego kodu, ponieważ są one oznaczone **FullTrust** zabezpieczenia deklaratywne atrybutu:</span><span class="sxs-lookup"><span data-stu-id="9d228-136">The following is a list of types and members that are not callable by partially trusted code because they are decorated with the **FullTrust** declarative security attribute:</span></span>  
  
 `PermissionSetAttribute(SecurityAction.LinkDemand, Name := "FullTrust")`  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>  
  
-   <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>  
  
-   <xref:System.Transactions.TransactionInterop>  
  
-   <xref:System.Transactions.TransactionManager.DistributedTransactionStarted>  
  
-   <xref:System.Transactions.HostCurrentTransactionCallback>  
  
-   <xref:System.Transactions.TransactionManager.Reenlist%2A>  
  
-   <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>  
  
-   <xref:System.Transactions.TransactionScope.%23ctor%28System.Transactions.TransactionScopeOption%2CSystem.Transactions.TransactionOptions%2CSystem.Transactions.EnterpriseServicesInteropOption%29>  
  
 <span data-ttu-id="9d228-137">Tylko do bezpośredniego obiektu wywołującego jest wymagany do posiadał **FullTrust** zestawu uprawnień do użycia powyżej typach lub metodach.</span><span class="sxs-lookup"><span data-stu-id="9d228-137">Only the immediate caller is required to possess the **FullTrust** permission set to use the above types or methods.</span></span>