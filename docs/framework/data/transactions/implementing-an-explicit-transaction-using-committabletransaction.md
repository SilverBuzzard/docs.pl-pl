---
title: "Implementowanie jawnych transakcji przy użyciu obiekcie CommittableTransaction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 29efe5e5-897b-46c2-a35f-e599a273acc8
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f045356fa2de6543a3b24490cb7964640a8d802c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-an-explicit-transaction-using-committabletransaction"></a><span data-ttu-id="121ad-102">Implementowanie jawnych transakcji przy użyciu obiekcie CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="121ad-102">Implementing an Explicit Transaction using CommittableTransaction</span></span>
<span data-ttu-id="121ad-103"><xref:System.Transactions.CommittableTransaction> Klasa umożliwia jawne dla aplikacji, aby używać transakcji, a nie za pomocą <xref:System.Transactions.TransactionScope> klasy niejawnie.</span><span class="sxs-lookup"><span data-stu-id="121ad-103">The <xref:System.Transactions.CommittableTransaction> class provides an explicit way for applications to use a transaction, as opposed to using the <xref:System.Transactions.TransactionScope> class implicitly.</span></span> <span data-ttu-id="121ad-104">Jest to przydatne w przypadku aplikacji, które mają być używane przez wiele wywołań funkcji lub wielu wywołań wątku tej samej transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-104">It is useful for applications that want to use the same transaction across multiple function calls or multiple thread calls.</span></span> <span data-ttu-id="121ad-105">W odróżnieniu od <xref:System.Transactions.TransactionScope> klasy, moduł zapisujący aplikacji musi w szczególności wywołać <xref:System.Transactions.CommittableTransaction.Commit%2A> i <xref:System.Transactions.Transaction.Rollback%2A> metody, aby zatwierdzić lub przerwać transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-105">Unlike the <xref:System.Transactions.TransactionScope> class, the application writer needs to specifically call the <xref:System.Transactions.CommittableTransaction.Commit%2A> and <xref:System.Transactions.Transaction.Rollback%2A> methods in order to commit or abort the transaction.</span></span>  
  
## <a name="overview-of-the-committabletransaction-class"></a><span data-ttu-id="121ad-106">Przegląd klasy CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="121ad-106">Overview of the CommittableTransaction class</span></span>  
 <span data-ttu-id="121ad-107"><xref:System.Transactions.CommittableTransaction> Klasa pochodzi z <xref:System.Transactions.Transaction> klasy, dlatego dostarczanie wszystkich funkcji drugiego.</span><span class="sxs-lookup"><span data-stu-id="121ad-107">The <xref:System.Transactions.CommittableTransaction> class derives from the <xref:System.Transactions.Transaction> class, therefore providing all the functionality of the latter.</span></span> <span data-ttu-id="121ad-108">Jest szczególnie przydatna <xref:System.Transactions.Transaction.Rollback%2A> metody w <xref:System.Transactions.Transaction> klasa, która umożliwia także wycofać <xref:System.Transactions.CommittableTransaction> obiektu.</span><span class="sxs-lookup"><span data-stu-id="121ad-108">Specifically useful is the <xref:System.Transactions.Transaction.Rollback%2A> method on the <xref:System.Transactions.Transaction> class that can also be used to rollback a <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="121ad-109"><xref:System.Transactions.Transaction> Klasa jest podobna do <xref:System.Transactions.CommittableTransaction> klasy, ale nie oferuje `Commit` metody.</span><span class="sxs-lookup"><span data-stu-id="121ad-109">The  <xref:System.Transactions.Transaction> class is similar to the <xref:System.Transactions.CommittableTransaction> class but does not offer a `Commit` method.</span></span> <span data-ttu-id="121ad-110">Umożliwia to przekazania obiektu transakcji (lub klony jego) do innych metod (potencjalnie na inny wątek) przy zachowaniu kontroli nad kiedy transakcja została zatwierdzona.</span><span class="sxs-lookup"><span data-stu-id="121ad-110">This enables you to pass the transaction object (or clones of it) to other methods (potentially on other threads) while still controlling when the transaction is committed.</span></span> <span data-ttu-id="121ad-111">Dzwonić kodu jest w stanie zarejestrować i oddawać głosy na transakcji, ale tylko twórca <xref:System.Transactions.CommittableTransaction> obiekt ma możliwość zatwierdzania transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-111">The called code is able to enlist and vote on the transaction, but only the creator of the <xref:System.Transactions.CommittableTransaction> object has the ability to commit the transaction.</span></span>  
  
 <span data-ttu-id="121ad-112">Należy zwrócić uwagę następujących typów podczas pracy z <xref:System.Transactions.CommittableTransaction> klasy,</span><span class="sxs-lookup"><span data-stu-id="121ad-112">You should note the followings when working with the <xref:System.Transactions.CommittableTransaction> class,</span></span>  
  
-   <span data-ttu-id="121ad-113">Tworzenie <xref:System.Transactions.CommittableTransaction> transakcji nie ustawiono otoczenia transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-113">Creating a <xref:System.Transactions.CommittableTransaction> transaction does not set the ambient transaction.</span></span> <span data-ttu-id="121ad-114">Należy w szczególności wartości i zresetować otoczenia transakcji, aby upewnić się, że menedżerów zasobów działają w kontekście transakcji po prawej, w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="121ad-114">You need to specifically set and reset the ambient transaction, to ensure that resource managers operate under the right transaction context when appropriate.</span></span> <span data-ttu-id="121ad-115">Jest sposobem ustawienia bieżącej transakcji otoczenia przez ustawienie statycznego <xref:System.Transactions.Transaction.Current%2A> dla właściwości globalnym <xref:System.Transactions.Transaction> obiektu.</span><span class="sxs-lookup"><span data-stu-id="121ad-115">The way to set the current ambient transaction is by setting the static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object.</span></span>  
  
-   <span data-ttu-id="121ad-116">Element <xref:System.Transactions.CommittableTransaction> obiektu nie może być używany ponownie.</span><span class="sxs-lookup"><span data-stu-id="121ad-116">A <xref:System.Transactions.CommittableTransaction> object cannot be reused.</span></span> <span data-ttu-id="121ad-117">Po <xref:System.Transactions.CommittableTransaction> obiektu została przekazana lub wycofana, nie może być używana ponownie w transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-117">Once a <xref:System.Transactions.CommittableTransaction> object has been committed or rolled back, it cannot be used again in a transaction.</span></span> <span data-ttu-id="121ad-118">Oznacza to, że nie można ustawić jako bieżący kontekst transakcji otoczenia.</span><span class="sxs-lookup"><span data-stu-id="121ad-118">That is, it cannot be set as the current ambient transaction context.</span></span>  
  
## <a name="creating-a-committabletransaction"></a><span data-ttu-id="121ad-119">Tworzenie CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="121ad-119">Creating a CommittableTransaction</span></span>  
 <span data-ttu-id="121ad-120">Poniższy przykład tworzy nową <xref:System.Transactions.CommittableTransaction> i zatwierdza go.</span><span class="sxs-lookup"><span data-stu-id="121ad-120">The following sample creates a new <xref:System.Transactions.CommittableTransaction> and commits it.</span></span>  
  
 [!code-csharp[Tx_CommittableTx#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_committabletx/cs/committabletxwithsql.cs#1)]
 [!code-vb[Tx_CommittableTx#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_committabletx/vb/committabletxwithsql.vb#1)]  
  
 <span data-ttu-id="121ad-121">Utworzenie wystąpienia <xref:System.Transactions.CommittableTransaction> automatycznie nie ustawiono kontekstu otoczenia transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-121">Creating an instance of <xref:System.Transactions.CommittableTransaction> does not automatically set the ambient transaction context.</span></span> <span data-ttu-id="121ad-122">Dlatego żadnych operacji na Menedżera zasobów nie jest częścią tej transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-122">Therefore, any operation on a resource manager is not part of that transaction.</span></span> <span data-ttu-id="121ad-123">Statycznych <xref:System.Transactions.Transaction.Current%2A> właściwość globalnej <xref:System.Transactions.Transaction> obiekt jest używany do ustawić lub pobrać transakcja otoczenia i aplikacja musi ustawić ręcznie, aby upewnić się, że Menedżer zasobów mogą uczestniczyć w transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-123">The static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object is used to set or retrieve the ambient transaction and the application must manually set it to ensure that resource managers can participate in the transaction.</span></span> <span data-ttu-id="121ad-124">Istnieje również dobrze jest zapisać stary transakcji otoczenia i go przywrócić po zakończeniu za pomocą <xref:System.Transactions.CommittableTransaction> obiektu.</span><span class="sxs-lookup"><span data-stu-id="121ad-124">It is also a good practice to save the old ambient transaction and restore it when you finish using the <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="121ad-125">Aby zatwierdzić transakcji, musisz jawnie wywołać <xref:System.Transactions.CommittableTransaction.Commit%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="121ad-125">To commit the transaction, you need to explicitly call the <xref:System.Transactions.CommittableTransaction.Commit%2A> method.</span></span> <span data-ttu-id="121ad-126">Dla wycofywania transakcji, należy wywołać <xref:System.Transactions.Transaction.Rollback%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="121ad-126">For rolling back a transaction, you should call the <xref:System.Transactions.Transaction.Rollback%2A> method.</span></span> <span data-ttu-id="121ad-127">Należy zauważyć, że do <xref:System.Transactions.CommittableTransaction> została przekazana lub wycofana, wszystkie zasoby zaangażowane w tej transakcji nadal jest zablokowany.</span><span class="sxs-lookup"><span data-stu-id="121ad-127">It is important to note that until a <xref:System.Transactions.CommittableTransaction> has been committed or rolled back, all the resources involved in that transaction are still locked.</span></span>  
  
 <span data-ttu-id="121ad-128">Element <xref:System.Transactions.CommittableTransaction> obiektu można stosować w przypadku wywołania funkcji i wątków.</span><span class="sxs-lookup"><span data-stu-id="121ad-128">A <xref:System.Transactions.CommittableTransaction> object can be used across function calls and threads.</span></span> <span data-ttu-id="121ad-129">Jednak jest maksymalnie Deweloper aplikacji do obsługi wyjątków, a w szczególności wywołać <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> metody w przypadku awarii.</span><span class="sxs-lookup"><span data-stu-id="121ad-129">However, it is up to the application developer to handle exceptions and specifically call the <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> method in case of failures.</span></span>  
  
## <a name="asynchronous-commit"></a><span data-ttu-id="121ad-130">Zatwierdzanie asynchroniczne</span><span class="sxs-lookup"><span data-stu-id="121ad-130">Asynchronous Commit</span></span>  
 <span data-ttu-id="121ad-131"><xref:System.Transactions.CommittableTransaction> Klasa zawiera także mechanizm asynchronicznie Zatwierdzanie transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-131">The <xref:System.Transactions.CommittableTransaction> class also provides a mechanism for committing a transaction asynchronously.</span></span> <span data-ttu-id="121ad-132">Zatwierdzanie transakcji może zająć sporo czasu, ponieważ mogą dotyczyć, wiele dostęp do bazy danych i opóźnienia sieci.</span><span class="sxs-lookup"><span data-stu-id="121ad-132">A transaction commit can take substantial time, as it might involve multiple database access and possible network latency.</span></span> <span data-ttu-id="121ad-133">Chce się uniknąć zakleszczenie w aplikacjach wysokiej przepływności, można użyć zatwierdzania asynchronicznego na zakończenie pracy transakcyjnej tak szybko, jak to możliwe i uruchom operację zatwierdzania jako zadania w tle.</span><span class="sxs-lookup"><span data-stu-id="121ad-133">When you want to avoid deadlocks in high throughput applications, you can use asynchronous commit to finish the transactional work as soon as possible, and run the commit operation as a background task.</span></span> <span data-ttu-id="121ad-134"><xref:System.Transactions.CommittableTransaction.BeginCommit%2A> i <xref:System.Transactions.CommittableTransaction.EndCommit%2A> metody <xref:System.Transactions.CommittableTransaction> klasy pozwalają w tym celu.</span><span class="sxs-lookup"><span data-stu-id="121ad-134">The <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> and <xref:System.Transactions.CommittableTransaction.EndCommit%2A> methods of the <xref:System.Transactions.CommittableTransaction> class allow you to do so.</span></span>  
  
 <span data-ttu-id="121ad-135">Można wywołać metodę <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> wysłania Napad zatwierdzania do wątków z puli wątków.</span><span class="sxs-lookup"><span data-stu-id="121ad-135">You can call <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> to dispatch the commit holdup to a thread from the thread pool.</span></span> <span data-ttu-id="121ad-136">Można również wywołać <xref:System.Transactions.CommittableTransaction.EndCommit%2A> do określenia, czy transakcja faktycznie została zatwierdzona.</span><span class="sxs-lookup"><span data-stu-id="121ad-136">You can also call <xref:System.Transactions.CommittableTransaction.EndCommit%2A> to determine if the transaction has actually been committed.</span></span> <span data-ttu-id="121ad-137">Jeśli nie można przekazać z jakiegokolwiek powodu, transakcji <xref:System.Transactions.CommittableTransaction.EndCommit%2A> zgłasza wyjątek transakcji.</span><span class="sxs-lookup"><span data-stu-id="121ad-137">If the transaction failed to commit for whatever reason, <xref:System.Transactions.CommittableTransaction.EndCommit%2A> raises a transaction exception.</span></span> <span data-ttu-id="121ad-138">Jeśli transakcja nie jest jeszcze przekazano do czasu <xref:System.Transactions.CommittableTransaction.EndCommit%2A> jest wywoływana, obiekt wywołujący zostało zablokowane do chwili transakcji nie zostanie przekazana lub zostało przerwane.</span><span class="sxs-lookup"><span data-stu-id="121ad-138">If the transaction is not yet committed by the time <xref:System.Transactions.CommittableTransaction.EndCommit%2A> is called, the caller is blocked until the transaction is committed or aborted.</span></span>  
  
 <span data-ttu-id="121ad-139">Najprostszym sposobem czy asynchroniczne zatwierdzania jest dostarczając metodę wywołania zwrotnego wywoływana, gdy zatwierdzania zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="121ad-139">The easiest way to do an asynchronous commit is by providing a callback method, to be called when committing is finished.</span></span> <span data-ttu-id="121ad-140">Jednakże, należy wywołać <xref:System.Transactions.CommittableTransaction.EndCommit%2A> metody w oryginalnym <xref:System.Transactions.CommittableTransaction> obiekt używany do wywoływania połączenie.</span><span class="sxs-lookup"><span data-stu-id="121ad-140">However, you must call the <xref:System.Transactions.CommittableTransaction.EndCommit%2A> method on the original <xref:System.Transactions.CommittableTransaction> object used to invoke the call.</span></span> <span data-ttu-id="121ad-141">Uzyskanie ten obiekt umożliwia przypisanie elementu podrzędnego *IAsyncResult* parametru metody wywołania zwrotnego, ponieważ <xref:System.Transactions.CommittableTransaction> klasa implementuje <xref:System.IAsyncResult> klasy.</span><span class="sxs-lookup"><span data-stu-id="121ad-141">To obtain that object, you can downcast the *IAsyncResult* parameter of the callback method, since the <xref:System.Transactions.CommittableTransaction> class implements <xref:System.IAsyncResult> class.</span></span>  
  
 <span data-ttu-id="121ad-142">W poniższym przykładzie pokazano, jak można zrobić zatwierdzania asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="121ad-142">The following example shows how an asynchronous commit can be done.</span></span>  
  
```csharp  
public void DoTransactionalWork()  
{  
     Transaction oldAmbient = Transaction.Current;  
     CommittableTransaction committableTransaction = new CommittableTransaction();  
     Transaction.Current = committableTransaction;  
  
     try  
     {  
          /* Perform transactional work here */  
          // No errors - commit transaction asynchronously  
          committableTransaction.BeginCommit(OnCommitted,null);  
     }  
     finally  
     {  
          //Restore the ambient transaction   
          Transaction.Current = oldAmbient;  
     }  
}  
void OnCommitted(IAsyncResult asyncResult)  
{  
     CommittableTransaction committableTransaction;  
     committableTransaction = asyncResult as CommittableTransaction;     
     Debug.Assert(committableTransaction != null);  
     try  
     {  
          using(committableTransaction)  
          {  
               committableTransaction.EndCommit(asyncResult);  
          }  
     }  
     catch(TransactionException e)  
     {  
          //Handle the failure to commit  
     }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="121ad-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="121ad-143">See Also</span></span>  
 [<span data-ttu-id="121ad-144">Implementowanie transakcji niejawnej przy użyciu zakresu transakcji</span><span class="sxs-lookup"><span data-stu-id="121ad-144">Implementing an Implicit Transaction using Transaction Scope</span></span>](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
 [<span data-ttu-id="121ad-145">Przetwarzanie transakcji</span><span class="sxs-lookup"><span data-stu-id="121ad-145">Transaction Processing</span></span>](../../../../docs/framework/data/transactions/index.md)