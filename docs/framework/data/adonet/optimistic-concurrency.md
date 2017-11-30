---
title: "Optymistycznej współbieżności"
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
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 45939dcec8b8db8e1b06ebfc67d89bfead67575a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="optimistic-concurrency"></a><span data-ttu-id="d570f-102">Optymistycznej współbieżności</span><span class="sxs-lookup"><span data-stu-id="d570f-102">Optimistic Concurrency</span></span>
<span data-ttu-id="d570f-103">W środowisku wielodostępnym są dwa modele aktualizacji danych w bazie danych: optymistycznej współbieżności i pesymistyczne współbieżności.</span><span class="sxs-lookup"><span data-stu-id="d570f-103">In a multiuser environment, there are two models for updating data in a database: optimistic concurrency and pessimistic concurrency.</span></span> <span data-ttu-id="d570f-104"><xref:System.Data.DataSet> Obiektu zaprojektowano w celu wspierać stosowanie optymistycznej współbieżności długotrwałe działań, np. danych zdalnych i interakcji z danymi.</span><span class="sxs-lookup"><span data-stu-id="d570f-104">The <xref:System.Data.DataSet> object is designed to encourage the use of optimistic concurrency for long-running activities, such as remoting data and interacting with data.</span></span>  
  
 <span data-ttu-id="d570f-105">Pesymistyczne współbieżności obejmuje blokowania wierszy w źródle danych, aby uniemożliwić innym użytkownikom modyfikowanie danych w taki sposób, który ma wpływ na bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d570f-105">Pessimistic concurrency involves locking rows at the data source to prevent other users from modifying data in a way that affects the current user.</span></span> <span data-ttu-id="d570f-106">Pesymistyczne modelu gdy użytkownik wykona akcję wywołującą blokady do zastosowania, inni użytkownicy nie można wykonać akcje, które spowodowałoby to konflikt z blokadą do momentu zwolnieniem właściciel blokady.</span><span class="sxs-lookup"><span data-stu-id="d570f-106">In a pessimistic model, when a user performs an action that causes a lock to be applied, other users cannot perform actions that would conflict with the lock until the lock owner releases it.</span></span> <span data-ttu-id="d570f-107">Ten model jest używane głównie w środowiskach, w której jest mocno rywalizacji o danych, dzięki czemu koszty ochrony danych przy użyciu blokady jest mniejsza niż koszt wycofywanie transakcji, jeśli występują konflikty współbieżności.</span><span class="sxs-lookup"><span data-stu-id="d570f-107">This model is primarily used in environments where there is heavy contention for data, so that the cost of protecting data with locks is less than the cost of rolling back transactions if concurrency conflicts occur.</span></span>  
  
 <span data-ttu-id="d570f-108">W związku z tym modelem współbieżności pesymistyczne użytkownika, który aktualizuje wiersz ustanawia blokady.</span><span class="sxs-lookup"><span data-stu-id="d570f-108">Therefore, in a pessimistic concurrency model, a user who updates a row establishes a lock.</span></span> <span data-ttu-id="d570f-109">Dopóki użytkownik nie ma Zakończono aktualizację i zwolnione blokady, nikt można zmienić tego wiersza.</span><span class="sxs-lookup"><span data-stu-id="d570f-109">Until the user has finished the update and released the lock, no one else can change that row.</span></span> <span data-ttu-id="d570f-110">Pesymistyczne współbieżności z tego powodu najlepiej jest implementowane, gdy blokady razy będzie krótkie, jak programowe przetwarzania rekordów.</span><span class="sxs-lookup"><span data-stu-id="d570f-110">For this reason, pessimistic concurrency is best implemented when lock times will be short, as in programmatic processing of records.</span></span> <span data-ttu-id="d570f-111">Pesymistyczne współbieżności nie jest opcją skalowalne, gdy użytkownicy są interakcji z danymi i powoduje rekordów do zablokowania dla stosunkowo dużej okresów.</span><span class="sxs-lookup"><span data-stu-id="d570f-111">Pessimistic concurrency is not a scalable option when users are interacting with data and causing records to be locked for relatively large periods of time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d570f-112">Jeśli trzeba zaktualizować wiele wierszy w tej samej operacji, następnie utworzenie transakcji to opcja większą skalowalność niż przy użyciu pesymistyczne blokowanie.</span><span class="sxs-lookup"><span data-stu-id="d570f-112">If you need to update multiple rows in the same operation, then creating a transaction is a more scalable option than using pessimistic locking.</span></span>  
  
 <span data-ttu-id="d570f-113">Z kolei użytkowników, którzy korzystają optymistycznej współbieżności nie Blokuj wiersz podczas jej odczytywania.</span><span class="sxs-lookup"><span data-stu-id="d570f-113">By contrast, users who use optimistic concurrency do not lock a row when reading it.</span></span> <span data-ttu-id="d570f-114">Gdy użytkownik chce, aby zaktualizować wiersza, aplikacja musi ustalić, czy inny użytkownik zmienił wiersza od czasu odczytu.</span><span class="sxs-lookup"><span data-stu-id="d570f-114">When a user wants to update a row, the application must determine whether another user has changed the row since it was read.</span></span> <span data-ttu-id="d570f-115">Optymistycznej współbieżności jest zwykle używany w środowiskach o niskim rywalizacji danych.</span><span class="sxs-lookup"><span data-stu-id="d570f-115">Optimistic concurrency is generally used in environments with a low contention for data.</span></span> <span data-ttu-id="d570f-116">Optymistycznej współbieżności zwiększa wydajność, ponieważ nie blokowanie rekordów jest wymagane, i blokowanie rekordów wymaga dodatkowych zasobów serwera.</span><span class="sxs-lookup"><span data-stu-id="d570f-116">Optimistic concurrency improves performance because no locking of records is required, and locking of records requires additional server resources.</span></span> <span data-ttu-id="d570f-117">Ponadto w celu utrzymania blokady rekordu, trwałe połączenie z serwerem bazy danych jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="d570f-117">Also, in order to maintain record locks, a persistent connection to the database server is required.</span></span> <span data-ttu-id="d570f-118">Ponieważ nie jest to w przypadku modelu optymistycznej współbieżności, połączenia z serwerem mogą obsługiwać większą liczbę klientów w krótszym czasie.</span><span class="sxs-lookup"><span data-stu-id="d570f-118">Because this is not the case in an optimistic concurrency model, connections to the server are free to serve a larger number of clients in less time.</span></span>  
  
 <span data-ttu-id="d570f-119">W modelu optymistycznej współbieżności naruszenie jest uważana za miały miejsce w przypadku, gdy użytkownik otrzyma wartość z bazy danych, inny użytkownik modyfikuje wartość przed pierwszy użytkownik próbował go zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="d570f-119">In an optimistic concurrency model, a violation is considered to have occurred if, after a user receives a value from the database, another user modifies the value before the first user has attempted to modify it.</span></span> <span data-ttu-id="d570f-120">Jak serwer rozpoznaje Naruszenie współbieżności najlepiej jest wyświetlany przez pierwszego opisującym w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="d570f-120">How the server resolves a concurrency violation is best shown by first describing the following example.</span></span>  
  
 <span data-ttu-id="d570f-121">Poniższe tabele postępuj zgodnie z przykładem optymistycznej współbieżności.</span><span class="sxs-lookup"><span data-stu-id="d570f-121">The following tables follow an example of optimistic concurrency.</span></span>  
  
 <span data-ttu-id="d570f-122">O godzinie 13:00 Użytkownik1 odczytuje wiersz z bazy danych z następującymi wartościami:</span><span class="sxs-lookup"><span data-stu-id="d570f-122">At 1:00 p.m., User1 reads a row from the database with the following values:</span></span>  
  
 <span data-ttu-id="d570f-123">**IDKlienta nazwisko imię**</span><span class="sxs-lookup"><span data-stu-id="d570f-123">**CustID     LastName     FirstName**</span></span>  
  
 <span data-ttu-id="d570f-124">Robert Smith 101</span><span class="sxs-lookup"><span data-stu-id="d570f-124">101          Smith             Bob</span></span>  
  
|<span data-ttu-id="d570f-125">Nazwa kolumny</span><span class="sxs-lookup"><span data-stu-id="d570f-125">Column name</span></span>|<span data-ttu-id="d570f-126">Oryginalna wartość</span><span class="sxs-lookup"><span data-stu-id="d570f-126">Original value</span></span>|<span data-ttu-id="d570f-127">Bieżąca wartość</span><span class="sxs-lookup"><span data-stu-id="d570f-127">Current value</span></span>|<span data-ttu-id="d570f-128">Wartość w bazie danych</span><span class="sxs-lookup"><span data-stu-id="d570f-128">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="d570f-129">IDKlienta</span><span class="sxs-lookup"><span data-stu-id="d570f-129">CustID</span></span>|<span data-ttu-id="d570f-130">101</span><span class="sxs-lookup"><span data-stu-id="d570f-130">101</span></span>|<span data-ttu-id="d570f-131">101</span><span class="sxs-lookup"><span data-stu-id="d570f-131">101</span></span>|<span data-ttu-id="d570f-132">101</span><span class="sxs-lookup"><span data-stu-id="d570f-132">101</span></span>|  
|<span data-ttu-id="d570f-133">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="d570f-133">LastName</span></span>|<span data-ttu-id="d570f-134">Smith</span><span class="sxs-lookup"><span data-stu-id="d570f-134">Smith</span></span>|<span data-ttu-id="d570f-135">Smith</span><span class="sxs-lookup"><span data-stu-id="d570f-135">Smith</span></span>|<span data-ttu-id="d570f-136">Smith</span><span class="sxs-lookup"><span data-stu-id="d570f-136">Smith</span></span>|  
|<span data-ttu-id="d570f-137">Imię</span><span class="sxs-lookup"><span data-stu-id="d570f-137">FirstName</span></span>|<span data-ttu-id="d570f-138">Robert</span><span class="sxs-lookup"><span data-stu-id="d570f-138">Bob</span></span>|<span data-ttu-id="d570f-139">Robert</span><span class="sxs-lookup"><span data-stu-id="d570f-139">Bob</span></span>|<span data-ttu-id="d570f-140">Robert</span><span class="sxs-lookup"><span data-stu-id="d570f-140">Bob</span></span>|  
  
 <span data-ttu-id="d570f-141">O godzinie 13:01 Użytkownik2 odczytuje tego samego wiersza.</span><span class="sxs-lookup"><span data-stu-id="d570f-141">At 1:01 p.m., User2 reads the same row.</span></span>  
  
 <span data-ttu-id="d570f-142">O godzinie 13:03, zmiany Użytkownik2 **imię** z "Bob" do "Robert" i aktualizuje bazę danych.</span><span class="sxs-lookup"><span data-stu-id="d570f-142">At 1:03 p.m., User2 changes **FirstName** from "Bob" to "Robert" and updates the database.</span></span>  
  
|<span data-ttu-id="d570f-143">Nazwa kolumny</span><span class="sxs-lookup"><span data-stu-id="d570f-143">Column name</span></span>|<span data-ttu-id="d570f-144">Oryginalna wartość</span><span class="sxs-lookup"><span data-stu-id="d570f-144">Original value</span></span>|<span data-ttu-id="d570f-145">Bieżąca wartość</span><span class="sxs-lookup"><span data-stu-id="d570f-145">Current value</span></span>|<span data-ttu-id="d570f-146">Wartość w bazie danych</span><span class="sxs-lookup"><span data-stu-id="d570f-146">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="d570f-147">IDKlienta</span><span class="sxs-lookup"><span data-stu-id="d570f-147">CustID</span></span>|<span data-ttu-id="d570f-148">101</span><span class="sxs-lookup"><span data-stu-id="d570f-148">101</span></span>|<span data-ttu-id="d570f-149">101</span><span class="sxs-lookup"><span data-stu-id="d570f-149">101</span></span>|<span data-ttu-id="d570f-150">101</span><span class="sxs-lookup"><span data-stu-id="d570f-150">101</span></span>|  
|<span data-ttu-id="d570f-151">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="d570f-151">LastName</span></span>|<span data-ttu-id="d570f-152">Smith</span><span class="sxs-lookup"><span data-stu-id="d570f-152">Smith</span></span>|<span data-ttu-id="d570f-153">Smith</span><span class="sxs-lookup"><span data-stu-id="d570f-153">Smith</span></span>|<span data-ttu-id="d570f-154">Smith</span><span class="sxs-lookup"><span data-stu-id="d570f-154">Smith</span></span>|  
|<span data-ttu-id="d570f-155">Imię</span><span class="sxs-lookup"><span data-stu-id="d570f-155">FirstName</span></span>|<span data-ttu-id="d570f-156">Robert</span><span class="sxs-lookup"><span data-stu-id="d570f-156">Bob</span></span>|<span data-ttu-id="d570f-157">Robert</span><span class="sxs-lookup"><span data-stu-id="d570f-157">Robert</span></span>|<span data-ttu-id="d570f-158">Robert</span><span class="sxs-lookup"><span data-stu-id="d570f-158">Bob</span></span>|  
  
 <span data-ttu-id="d570f-159">Aktualizacja powiedzie się, ponieważ oryginalne wartości, które ma Użytkownik2 pasuje do wartości w bazie danych w momencie aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="d570f-159">The update succeeds because the values in the database at the time of update match the original values that User2 has.</span></span>  
  
 <span data-ttu-id="d570f-160">O godzinie 13:05 Użytkownik1 zmiany "Bob" imię "Kuba" i podejmuje próbę zaktualizowania wiersza w tabeli.</span><span class="sxs-lookup"><span data-stu-id="d570f-160">At 1:05 p.m., User1 changes "Bob"'s first name to "James" and tries to update the row.</span></span>  
  
|<span data-ttu-id="d570f-161">Nazwa kolumny</span><span class="sxs-lookup"><span data-stu-id="d570f-161">Column name</span></span>|<span data-ttu-id="d570f-162">Oryginalna wartość</span><span class="sxs-lookup"><span data-stu-id="d570f-162">Original value</span></span>|<span data-ttu-id="d570f-163">Bieżąca wartość</span><span class="sxs-lookup"><span data-stu-id="d570f-163">Current value</span></span>|<span data-ttu-id="d570f-164">Wartość w bazie danych</span><span class="sxs-lookup"><span data-stu-id="d570f-164">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="d570f-165">IDKlienta</span><span class="sxs-lookup"><span data-stu-id="d570f-165">CustID</span></span>|<span data-ttu-id="d570f-166">101</span><span class="sxs-lookup"><span data-stu-id="d570f-166">101</span></span>|<span data-ttu-id="d570f-167">101</span><span class="sxs-lookup"><span data-stu-id="d570f-167">101</span></span>|<span data-ttu-id="d570f-168">101</span><span class="sxs-lookup"><span data-stu-id="d570f-168">101</span></span>|  
|<span data-ttu-id="d570f-169">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="d570f-169">LastName</span></span>|<span data-ttu-id="d570f-170">Smith</span><span class="sxs-lookup"><span data-stu-id="d570f-170">Smith</span></span>|<span data-ttu-id="d570f-171">Smith</span><span class="sxs-lookup"><span data-stu-id="d570f-171">Smith</span></span>|<span data-ttu-id="d570f-172">Smith</span><span class="sxs-lookup"><span data-stu-id="d570f-172">Smith</span></span>|  
|<span data-ttu-id="d570f-173">Imię</span><span class="sxs-lookup"><span data-stu-id="d570f-173">FirstName</span></span>|<span data-ttu-id="d570f-174">Robert</span><span class="sxs-lookup"><span data-stu-id="d570f-174">Bob</span></span>|<span data-ttu-id="d570f-175">Kuba</span><span class="sxs-lookup"><span data-stu-id="d570f-175">James</span></span>|<span data-ttu-id="d570f-176">Robert</span><span class="sxs-lookup"><span data-stu-id="d570f-176">Robert</span></span>|  
  
 <span data-ttu-id="d570f-177">W tym momencie Użytkownik1 napotka naruszenie optymistycznej współbieżności, ponieważ wartość w bazie danych ("Robert") nie jest już zgodny oryginalnej wartości, że Użytkownik1 oczekiwała ("Bob").</span><span class="sxs-lookup"><span data-stu-id="d570f-177">At this point, User1 encounters an optimistic concurrency violation because the value in the database ("Robert") no longer matches the original value that User1 was expecting ("Bob").</span></span> <span data-ttu-id="d570f-178">Naruszenie współbieżności umożliwia po prostu wiedzieć, że aktualizacja nie powiodła się.</span><span class="sxs-lookup"><span data-stu-id="d570f-178">The concurrency violation simply lets you know that the update failed.</span></span> <span data-ttu-id="d570f-179">Teraz decyzji musi można zastąpić zmiany dostarczonych przez Użytkownik2 ze zmianami dostarczone przez użytkownika Użytkownik1 lub Anuluj zmiany wprowadzone przez użytkownika Użytkownik1.</span><span class="sxs-lookup"><span data-stu-id="d570f-179">The decision now needs to be made whether to overwrite the changes supplied by User2 with the changes supplied by User1, or to cancel the changes by User1.</span></span>  
  
## <a name="testing-for-optimistic-concurrency-violations"></a><span data-ttu-id="d570f-180">Testowanie pod kątem naruszeń optymistycznej współbieżności</span><span class="sxs-lookup"><span data-stu-id="d570f-180">Testing for Optimistic Concurrency Violations</span></span>  
 <span data-ttu-id="d570f-181">Istnieje kilka technik testowania dla naruszenia optymistycznej współbieżności.</span><span class="sxs-lookup"><span data-stu-id="d570f-181">There are several techniques for testing for an optimistic concurrency violation.</span></span> <span data-ttu-id="d570f-182">Jeden polega na tym kolumny znaczników czasu w tabeli.</span><span class="sxs-lookup"><span data-stu-id="d570f-182">One involves including a timestamp column in the table.</span></span> <span data-ttu-id="d570f-183">Bazy danych często udostępniają funkcje sygnatury czasowej, który może służyć do identyfikowania datę i godzinę ostatniej aktualizacji rekordu.</span><span class="sxs-lookup"><span data-stu-id="d570f-183">Databases commonly provide timestamp functionality that can be used to identify the date and time when the record was last updated.</span></span> <span data-ttu-id="d570f-184">Ta technika kolumny znaczników czasu znajduje się w definicji tabeli.</span><span class="sxs-lookup"><span data-stu-id="d570f-184">Using this technique, a timestamp column is included in the table definition.</span></span> <span data-ttu-id="d570f-185">Przy każdej aktualizacji rekordu sygnatury czasowej jest aktualizowany w celu odzwierciedlenia bieżącej daty i godziny.</span><span class="sxs-lookup"><span data-stu-id="d570f-185">Whenever the record is updated, the timestamp is updated to reflect the current date and time.</span></span> <span data-ttu-id="d570f-186">W teście naruszeń optymistycznej współbieżności kolumny znaczników czasu jest zwracany za każde zapytanie zawartość tej tabeli.</span><span class="sxs-lookup"><span data-stu-id="d570f-186">In a test for optimistic concurrency violations, the timestamp column is returned with any query of the contents of the table.</span></span> <span data-ttu-id="d570f-187">Próba aktualizacji wartości znaczników czasu w bazie danych jest porównywany oryginalna wartość sygnatury czasowej w zmodyfikowanych wierszy.</span><span class="sxs-lookup"><span data-stu-id="d570f-187">When an update is attempted, the timestamp value in the database is compared to the original timestamp value contained in the modified row.</span></span> <span data-ttu-id="d570f-188">Jeśli są zgodne, aktualizacja jest wykonywana, a kolumny znaczników czasu jest aktualizowany przy użyciu bieżącego czasu w celu uwzględnienia tej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="d570f-188">If they match, the update is performed and the timestamp column is updated with the current time to reflect the update.</span></span> <span data-ttu-id="d570f-189">Jeśli nie są zgodne, ma nastąpiło naruszenie zasad optymistycznej współbieżności.</span><span class="sxs-lookup"><span data-stu-id="d570f-189">If they do not match, an optimistic concurrency violation has occurred.</span></span>  
  
 <span data-ttu-id="d570f-190">Sprawdź, czy wszystkie oryginalnej wartości kolumn w wierszu nadal odpowiadają występujące w bazie danych jest innej techniki testowania dla naruszenia optymistycznej współbieżności.</span><span class="sxs-lookup"><span data-stu-id="d570f-190">Another technique for testing for an optimistic concurrency violation is to verify that all the original column values in a row still match those found in the database.</span></span> <span data-ttu-id="d570f-191">Na przykład wziąć pod uwagę następujące zapytanie:</span><span class="sxs-lookup"><span data-stu-id="d570f-191">For example, consider the following query:</span></span>  
  
```  
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 <span data-ttu-id="d570f-192">Do testowania naruszenia optymistycznej współbieżności podczas aktualizowania wiersza w **Table1**, czy wystawiać następującą instrukcję aktualizacji:</span><span class="sxs-lookup"><span data-stu-id="d570f-192">To test for an optimistic concurrency violation when updating a row in **Table1**, you would issue the following UPDATE statement:</span></span>  
  
```  
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 <span data-ttu-id="d570f-193">Tak długo, jak oryginalne wartości są takie same wartości w bazie danych, aktualizacja jest wykonywana.</span><span class="sxs-lookup"><span data-stu-id="d570f-193">As long as the original values match the values in the database, the update is performed.</span></span> <span data-ttu-id="d570f-194">W przypadku modyfikacji wartości aktualizacji nie spowoduje zmiany wiersza, ponieważ klauzula WHERE nie będzie zawierał dopasowania.</span><span class="sxs-lookup"><span data-stu-id="d570f-194">If a value has been modified, the update will not modify the row because the WHERE clause will not find a match.</span></span>  
  
 <span data-ttu-id="d570f-195">Należy pamiętać, że zalecane jest zawsze zwracać unikatowe wartości klucza podstawowego w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="d570f-195">Note that it is recommended to always return a unique primary key value in your query.</span></span> <span data-ttu-id="d570f-196">W przeciwnym razie powyższych instrukcji UPDATE mogą aktualizować więcej niż jeden wiersz, która nie może być Twoich zamiarów.</span><span class="sxs-lookup"><span data-stu-id="d570f-196">Otherwise, the preceding UPDATE statement may update more than one row, which might not be your intent.</span></span>  
  
 <span data-ttu-id="d570f-197">Kolumny w źródle danych dopuszcza wartości null, może być konieczne rozszerzenie z klauzuli WHERE, która Wyszukaj pasujące odwołanie o wartości null w tabeli lokalnej i w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="d570f-197">If a column at your data source allows nulls, you may need to extend your WHERE clause to check for a matching null reference in your local table and at the data source.</span></span> <span data-ttu-id="d570f-198">Na przykład następująca instrukcja aktualizacji sprawdza, czy odwołanie o wartości null w wierszu lokalnego nadal odpowiada odwołanie o wartości null w źródle danych, lub że wartość w lokalnych wierszu nadal jest zgodna z wartością w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="d570f-198">For example, the following UPDATE statement verifies that a null reference in the local row still matches a null reference at the data source, or that the value in the local row still matches the value at the data source.</span></span>  
  
```  
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 <span data-ttu-id="d570f-199">Można również zastosować mniej restrykcyjne kryteria, korzystając z modelu optymistycznej współbieżności.</span><span class="sxs-lookup"><span data-stu-id="d570f-199">You may also choose to apply less restrictive criteria when using an optimistic concurrency model.</span></span> <span data-ttu-id="d570f-200">Na przykład za pomocą tylko kolumny klucza podstawowego w klauzuli WHERE powoduje, że dane zostaną zastąpione niezależnie od tego, czy inne kolumny zostały zaktualizowane od czasu ostatniej kwerendy.</span><span class="sxs-lookup"><span data-stu-id="d570f-200">For example, using only the primary key columns in the WHERE clause causes the data to be overwritten regardless of whether the other columns have been updated since the last query.</span></span> <span data-ttu-id="d570f-201">Klauzuli WHERE można również zastosować tylko do określonych kolumn, dane zostaną zastąpione, chyba że niektóre pola zostały zaktualizowane od czasu ostatniego skierowano.</span><span class="sxs-lookup"><span data-stu-id="d570f-201">You can also apply a WHERE clause only to specific columns, resulting in data being overwritten unless particular fields have been updated since they were last queried.</span></span>  
  
### <a name="the-dataadapterrowupdated-event"></a><span data-ttu-id="d570f-202">Zdarzenie DataAdapter.RowUpdated</span><span class="sxs-lookup"><span data-stu-id="d570f-202">The DataAdapter.RowUpdated Event</span></span>  
 <span data-ttu-id="d570f-203">**RowUpdated** zdarzenie <xref:System.Data.Common.DataAdapter> obiektu można użyć w połączeniu z techniki opisane wcześniej, aby zapewnić powiadomienia do aplikacji naruszeń optymistycznej współbieżności.</span><span class="sxs-lookup"><span data-stu-id="d570f-203">The **RowUpdated** event of the <xref:System.Data.Common.DataAdapter> object can be used in conjunction with the techniques described earlier, to provide notification to your application of optimistic concurrency violations.</span></span> <span data-ttu-id="d570f-204">**RowUpdated** występuje po każdej próby zaktualizowania **zmodyfikowane** wiersz z tabeli **zestawu danych**.</span><span class="sxs-lookup"><span data-stu-id="d570f-204">**RowUpdated** occurs after each attempt to update a **Modified** row from a **DataSet**.</span></span> <span data-ttu-id="d570f-205">Dzięki temu można dodać kod specjalnej obsługi, w tym przetwarzania po wystąpieniu wyjątku, dodawanie informacji o niestandardowych komunikatów o błędach, Dodawanie logiki ponawiania próby i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="d570f-205">This enables you to add special handling code, including processing when an exception occurs, adding custom error information, adding retry logic, and so on.</span></span> <span data-ttu-id="d570f-206"><xref:System.Data.Common.RowUpdatedEventArgs> Zwraca obiekt **RecordsAffected** właściwości zawierające liczbę wierszy objętych polecenia aktualizacji określonej dla zmodyfikowanych wierszy w tabeli.</span><span class="sxs-lookup"><span data-stu-id="d570f-206">The <xref:System.Data.Common.RowUpdatedEventArgs> object returns a **RecordsAffected** property containing the number of rows affected by a particular update command for a modified row in a table.</span></span> <span data-ttu-id="d570f-207">Przez ustawienie polecenia Aktualizuj w celu zbadania optymistycznej współbieżności **RecordsAffected** właściwości w związku z tym zwróci wartość 0, jeśli nastąpiło naruszenie optymistycznej współbieżności, ponieważ żadne rekordy nie zostały zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="d570f-207">By setting the update command to test for optimistic concurrency, the **RecordsAffected** property will, as a result, return a value of 0 when an optimistic concurrency violation has occurred, because no records were updated.</span></span> <span data-ttu-id="d570f-208">Jeśli jest to możliwe, jest zwracany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="d570f-208">If this is the case, an exception is thrown.</span></span> <span data-ttu-id="d570f-209">**RowUpdated** zdarzenie pozwala obsługiwać to wystąpienie i uniknąć wyjątek, ustawiając odpowiednią **RowUpdatedEventArgs.Status** wartości, takich jak  **UpdateStatus.SkipCurrentRow**.</span><span class="sxs-lookup"><span data-stu-id="d570f-209">The **RowUpdated** event enables you to handle this occurrence and avoid the exception by setting an appropriate **RowUpdatedEventArgs.Status** value, such as **UpdateStatus.SkipCurrentRow**.</span></span> <span data-ttu-id="d570f-210">Aby uzyskać więcej informacji na temat **RowUpdated** zdarzeń, zobacz [obsługi zdarzeń element DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="d570f-210">For more information about the **RowUpdated** event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
 <span data-ttu-id="d570f-211">Opcjonalnie można ustawić **DataAdapter.ContinueUpdateOnError** do **true**, przed wywołaniem **aktualizacji**i reagowanie na informacje o błędzie, przechowywane w **RowError** właściwości określonego wiersza, kiedy **aktualizacji** zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="d570f-211">Optionally, you can set **DataAdapter.ContinueUpdateOnError** to **true**, before calling **Update**, and respond to the error information stored in the **RowError** property of a particular row when the **Update** is completed.</span></span> <span data-ttu-id="d570f-212">Aby uzyskać więcej informacji, zobacz [informacje o błędzie wiersza](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md).</span><span class="sxs-lookup"><span data-stu-id="d570f-212">For more information, see [Row Error Information](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md).</span></span>  
  
## <a name="optimistic-concurrency-example"></a><span data-ttu-id="d570f-213">Przykład optymistycznej współbieżności</span><span class="sxs-lookup"><span data-stu-id="d570f-213">Optimistic Concurrency Example</span></span>  
 <span data-ttu-id="d570f-214">Poniżej przedstawiono prosty przykład, który ustawia **UpdateCommand** z **element DataAdapter** do testowania optymistycznej współbieżności, a następnie używa **RowUpdated** zdarzeń do testowania naruszeń optymistycznej współbieżności.</span><span class="sxs-lookup"><span data-stu-id="d570f-214">The following is a simple example that sets the **UpdateCommand** of a **DataAdapter** to test for optimistic concurrency, and then uses the **RowUpdated** event to test for optimistic concurrency violations.</span></span> <span data-ttu-id="d570f-215">W przypadku naruszenia optymistycznej współbieżności aplikacji ustawia **RowError** wiersza, aby odzwierciedlić naruszenia optymistycznej współbieżności wystawiony dla aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="d570f-215">When an optimistic concurrency violation is encountered, the application sets the **RowError** of the row that the update was issued for to reflect an optimistic concurrency violation.</span></span>  
  
 <span data-ttu-id="d570f-216">Należy pamiętać, że wartości parametrów przekazane do klauzuli WHERE polecenia aktualizacji są mapowane na **oryginalnego** wartości odpowiednich kolumnach.</span><span class="sxs-lookup"><span data-stu-id="d570f-216">Note that the parameter values passed to the WHERE clause of the UPDATE command are mapped to the **Original** values of their respective columns.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = dataSet.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then   
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName, connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)   
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d570f-217">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d570f-217">See Also</span></span>  
 [<span data-ttu-id="d570f-218">Trwa pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d570f-218">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="d570f-219">Aktualizowanie źródła danych za pomocą obiektów DataAdapter</span><span class="sxs-lookup"><span data-stu-id="d570f-219">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [<span data-ttu-id="d570f-220">Informacje o błędzie wiersza</span><span class="sxs-lookup"><span data-stu-id="d570f-220">Row Error Information</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 [<span data-ttu-id="d570f-221">Transakcje i współbieżność</span><span class="sxs-lookup"><span data-stu-id="d570f-221">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="d570f-222">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="d570f-222">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)