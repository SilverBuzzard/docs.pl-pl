---
title: "Anulowanie pozostałych zadań asynchronicznych po jednym jest pełna (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: d3cebc74-c392-497b-b1e6-62a262eabe05
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fe65f81af28509c577e014353c43b72d34375459
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-c"></a><span data-ttu-id="7edd1-102">Anulowanie pozostałych zadań asynchronicznych po jednym jest pełna (C#)</span><span class="sxs-lookup"><span data-stu-id="7edd1-102">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>
<span data-ttu-id="7edd1-103">Za pomocą <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> metody razem z <xref:System.Threading.CancellationToken>, możesz anulować wszystkie pozostałe zadania po zakończeniu zadania.</span><span class="sxs-lookup"><span data-stu-id="7edd1-103">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="7edd1-104">`WhenAny` Metoda przyjmuje argument, który jest kolekcji zadań.</span><span class="sxs-lookup"><span data-stu-id="7edd1-104">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="7edd1-105">Metoda uruchamiania wszystkich zadań i zwraca jedno zadanie.</span><span class="sxs-lookup"><span data-stu-id="7edd1-105">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="7edd1-106">Pojedyncze zadanie zakończeniu po ukończeniu zadań w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="7edd1-106">The single task is complete when any task in the collection is complete.</span></span>  
  
 <span data-ttu-id="7edd1-107">W tym przykładzie pokazano, jak używać w połączeniu z tokenem anulowania `WhenAny` do przechowywania na pierwszym zadaniem Zakończ z kolekcji zadań i anulowanie pozostałych zadań.</span><span class="sxs-lookup"><span data-stu-id="7edd1-107">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="7edd1-108">Każde zadanie pobiera zawartość witryny sieci Web.</span><span class="sxs-lookup"><span data-stu-id="7edd1-108">Each task downloads the contents of a website.</span></span> <span data-ttu-id="7edd1-109">W przykładzie wyświetla długość zawartości pierwsza z nich do wykonania i anuluje inne pliki do pobrania.</span><span class="sxs-lookup"><span data-stu-id="7edd1-109">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7edd1-110">Uruchamianie przykładów, musi mieć program Visual Studio 2012 lub nowszej i .NET Framework 4.5 lub nowszej zainstalowany na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="7edd1-110">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="7edd1-111">Pobieranie przykładu</span><span class="sxs-lookup"><span data-stu-id="7edd1-111">Downloading the Example</span></span>  
 <span data-ttu-id="7edd1-112">Możesz pobrać pełną projekt Windows Presentation Foundation (WPF) z [próbki Async: poprawnie dostrajanie Twoja aplikacja](http://go.microsoft.com/fwlink/?LinkId=255046) , a następnie wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7edd1-112">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="7edd1-113">Dekompresja pobranego pliku, a następnie uruchom program Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7edd1-113">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="7edd1-114">Na pasku menu wybierz **pliku**, **Otwórz**, **projektu/rozwiązania**.</span><span class="sxs-lookup"><span data-stu-id="7edd1-114">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="7edd1-115">W **Otwórz projekt** okno dialogowe, otwórz folder, który zawiera przykładowy kod, który można zdekompresować, a następnie otwórz plik rozwiązania (sln) dla AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="7edd1-115">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>  
  
4.  <span data-ttu-id="7edd1-116">W **Eksploratora rozwiązań**, otwórz menu skrótów **CancelAfterOneTask** projektu, a następnie wybierz pozycję **Ustaw jako projekt startowy**.</span><span class="sxs-lookup"><span data-stu-id="7edd1-116">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="7edd1-117">Wybierz klawisz F5, aby uruchomić projekt.</span><span class="sxs-lookup"><span data-stu-id="7edd1-117">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="7edd1-118">Wybierz klucze Ctrl + F5, aby uruchomić projekt bez debugowania go.</span><span class="sxs-lookup"><span data-stu-id="7edd1-118">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="7edd1-119">Uruchom program kilka razy, aby sprawdzić, najpierw Zakończ różne pliki do pobrania.</span><span class="sxs-lookup"><span data-stu-id="7edd1-119">Run the program several times to verify that different downloads finish first.</span></span>  
  
 <span data-ttu-id="7edd1-120">Jeśli nie chcesz pobrać projekt, można przejrzeć plik MainWindow.xaml.cs na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="7edd1-120">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="7edd1-121">Tworzenie w przykładzie</span><span class="sxs-lookup"><span data-stu-id="7edd1-121">Building the Example</span></span>  
 <span data-ttu-id="7edd1-122">W przykładzie w tym temacie jest dodawany do projektu, który został napisany w [anulowanie zadania asynchronicznego lub listy zadań (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) anulować listy zadań.</span><span class="sxs-lookup"><span data-stu-id="7edd1-122">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="7edd1-123">W przykładzie użyto tego samego interfejsu użytkownika, mimo że **anulować** przycisk nie jest używana jawnie.</span><span class="sxs-lookup"><span data-stu-id="7edd1-123">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="7edd1-124">Do tworzenia przykładzie samodzielnie krok po kroku, postępuj zgodnie z instrukcjami w sekcji "Pobieranie Example", ale wybierz **CancelAListOfTasks** jako **projekt startowy**.</span><span class="sxs-lookup"><span data-stu-id="7edd1-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="7edd1-125">Dodaj zmiany w tym temacie do tego projektu.</span><span class="sxs-lookup"><span data-stu-id="7edd1-125">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="7edd1-126">W pliku MainWindow.xaml.cs **CancelAListOfTasks** projekt, uruchom przejście przez przeniesienie kroki przetwarzania dla każdej witryny sieci Web z pętli w `AccessTheWebAsync` do następującej metody asynchronicznej.</span><span class="sxs-lookup"><span data-stu-id="7edd1-126">In the MainWindow.xaml.cs file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>  
  
```csharp  
/ ***Bundle the processing steps for a website into one async method.  
async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
{  
    // GetAsync returns a Task<HttpResponseMessage>.   
    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
    // Retrieve the website contents from the HttpResponseMessage.  
    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
    return urlContents.Length;  
}  
```  
  
 <span data-ttu-id="7edd1-127">W `AccessTheWebAsync`, w tym przykładzie użyto kwerendy, <xref:System.Linq.Enumerable.ToArray%2A> metody i `WhenAny` metodę, aby utworzyć i uruchomić tablicy zadań.</span><span class="sxs-lookup"><span data-stu-id="7edd1-127">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="7edd1-128">Stosowanie `WhenAny` do tablicy zwraca pojedyncze zadanie, gdy oczekiwane, daje w wyniku pierwszego zadania do wykonania w tablicy zadań.</span><span class="sxs-lookup"><span data-stu-id="7edd1-128">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>  
  
 <span data-ttu-id="7edd1-129">Wprowadź następujące zmiany w `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="7edd1-129">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="7edd1-130">Gwiazdki oznaczyć zmiany w pliku kodu.</span><span class="sxs-lookup"><span data-stu-id="7edd1-130">Asterisks mark the changes in the code file.</span></span>  
  
1.  <span data-ttu-id="7edd1-131">Komentarz lub usunąć pętli.</span><span class="sxs-lookup"><span data-stu-id="7edd1-131">Comment out or delete the loop.</span></span>  
  
2.  <span data-ttu-id="7edd1-132">Utwórz kwerendę, która po wykonaniu tworzy kolekcję ogólnych zadań.</span><span class="sxs-lookup"><span data-stu-id="7edd1-132">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="7edd1-133">Każde wywołanie `ProcessURLAsync` zwraca <xref:System.Threading.Tasks.Task%601> gdzie `TResult` jest liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="7edd1-133">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
    ```csharp  
    // ***Create a query that, when executed, returns a collection of tasks.  
    IEnumerable<Task<int>> downloadTasksQuery =  
        from url in urlList select ProcessURLAsync(url, client, ct);  
    ```  
  
3.  <span data-ttu-id="7edd1-134">Wywołanie `ToArray` do wykonania zapytania i uruchamiania zadań.</span><span class="sxs-lookup"><span data-stu-id="7edd1-134">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="7edd1-135">Stosowanie `WhenAny` metody w następnym kroku może wykonać zapytania i uruchomić zadania bez użycia `ToArray`, ale inne metody nie mogą.</span><span class="sxs-lookup"><span data-stu-id="7edd1-135">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="7edd1-136">Najbezpieczniejszym rozwiązaniem jest jawnie wymusić wykonywania zapytania.</span><span class="sxs-lookup"><span data-stu-id="7edd1-136">The safest practice is to force execution of the query explicitly.</span></span>  
  
    ```csharp  
    // ***Use ToArray to execute the query and start the download tasks.   
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
    ```  
  
4.  <span data-ttu-id="7edd1-137">Wywołanie `WhenAny` w kolekcji zadań.</span><span class="sxs-lookup"><span data-stu-id="7edd1-137">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="7edd1-138">`WhenAny`Zwraca `Task(Of Task(Of Integer))` lub `Task<Task<int>>`.</span><span class="sxs-lookup"><span data-stu-id="7edd1-138">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="7edd1-139">Oznacza to `WhenAny` zwraca zadanie, które ocenia pojedynczej `Task(Of Integer)` lub `Task<int>` po jest oczekiwane.</span><span class="sxs-lookup"><span data-stu-id="7edd1-139">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="7edd1-140">Jednego zadania jest pierwszym zadaniem w kolekcji, aby zakończyć.</span><span class="sxs-lookup"><span data-stu-id="7edd1-140">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="7edd1-141">Zadanie, które zostało zakończone najpierw jest przypisany do `firstFinishedTask`.</span><span class="sxs-lookup"><span data-stu-id="7edd1-141">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="7edd1-142">Typ `firstFinishedTask` jest <xref:System.Threading.Tasks.Task%601> gdzie `TResult` jest liczbą całkowitą, ponieważ jest to typ zwracany `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="7edd1-142">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>  
  
    ```csharp  
    // ***Call WhenAny and then await the result. The task that finishes   
    // first is assigned to firstFinishedTask.  
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
    ```  
  
5.  <span data-ttu-id="7edd1-143">W tym przykładzie interesuje Cię tylko zadania, które kończy najpierw.</span><span class="sxs-lookup"><span data-stu-id="7edd1-143">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="7edd1-144">Dlatego należy używać <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> na anulowanie pozostałych zadań.</span><span class="sxs-lookup"><span data-stu-id="7edd1-144">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> to cancel the remaining tasks.</span></span>  
  
    ```csharp  
    // ***Cancel the rest of the downloads. You just want the first one.  
    cts.Cancel();  
    ```  
  
6.  <span data-ttu-id="7edd1-145">Na koniec await `firstFinishedTask` można pobrać długości pobieranej zawartości.</span><span class="sxs-lookup"><span data-stu-id="7edd1-145">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>  
  
    ```csharp  
    var length = await firstFinishedTask;  
    resultsTextBox.Text += String.Format("\r\nLength of the downloaded website:  {0}\r\n", length);  
    ```  
  
 <span data-ttu-id="7edd1-146">Uruchom program kilka razy, aby sprawdzić, najpierw Zakończ różne pliki do pobrania.</span><span class="sxs-lookup"><span data-stu-id="7edd1-146">Run the program several times to verify that different downloads finish first.</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="7edd1-147">Kompletny przykład</span><span class="sxs-lookup"><span data-stu-id="7edd1-147">Complete Example</span></span>  
 <span data-ttu-id="7edd1-148">Poniższy kod jest pełny plik MainWindow.xaml.cs dla przykładu.</span><span class="sxs-lookup"><span data-stu-id="7edd1-148">The following code is the complete MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="7edd1-149">Gwiazdki Oznacz elementy, które zostały dodane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="7edd1-149">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="7edd1-150">Zwróć uwagę, że musisz dodać odwołanie do <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="7edd1-150">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="7edd1-151">Można pobrać projektu z [próbki Async: poprawnie dostrajanie Twoja aplikacja](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="7edd1-151">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add a using directive and a reference for System.Net.Http.  
using System.Net.Http;  
  
// Add the following using directive.  
using System.Threading;  
  
namespace CancelAfterOneTask  
{  
    public partial class MainWindow : Window  
    {  
        // Declare a System.Threading.CancellationTokenSource.  
        CancellationTokenSource cts;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            resultsTextBox.Clear();  
  
            try  
            {  
                await AccessTheWebAsync(cts.Token);  
                resultsTextBox.Text += "\r\nDownload complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownload canceled.";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownload failed.";  
            }  
  
            // Set the CancellationTokenSource to null when the download is complete.  
            cts = null;  
        }  
  
        // You can still include a Cancel button if you want to.  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        // Provide a parameter for the CancellationToken.  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            // Call SetUpURLList to make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Comment out or delete the loop.  
            //foreach (var url in urlList)  
            //{  
            //    // GetAsync returns a Task<HttpResponseMessage>.   
            //    // Argument ct carries the message if the Cancel button is chosen.   
            //    // ***Note that the Cancel button can cancel all remaining downloads.  
            //    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            //    // Retrieve the website contents from the HttpResponseMessage.  
            //    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            //    resultsTextBox.Text +=  
            //        String.Format("\r\nLength of the downloaded string: {0}.\r\n", urlContents.Length);  
            //}  
  
            // ***Create a query that, when executed, returns a collection of tasks.  
            IEnumerable<Task<int>> downloadTasksQuery =  
                from url in urlList select ProcessURLAsync(url, client, ct);  
  
            // ***Use ToArray to execute the query and start the download tasks.   
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
  
            // ***Call WhenAny and then await the result. The task that finishes   
            // first is assigned to firstFinishedTask.  
            Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
  
            // ***Cancel the rest of the downloads. You just want the first one.  
            cts.Cancel();  
  
            // ***Await the first completed task and display the results.   
            // Run the program several times to demonstrate that different  
            // websites can finish first.  
            var length = await firstFinishedTask;  
            resultsTextBox.Text += String.Format("\r\nLength of the downloaded website:  {0}\r\n", length);  
        }  
  
        // ***Bundle the processing steps for a website into one async method.  
        async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
        {  
            // GetAsync returns a Task<HttpResponseMessage>.   
            HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            return urlContents.Length;  
        }  
  
        // Add a method that creates a list of web addresses.  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
    }  
    // Sample output:  
  
    // Length of the downloaded website:  158856  
  
    // Download complete.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7edd1-152">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7edd1-152">See Also</span></span>  
 <xref:System.Threading.Tasks.Task.WhenAny%2A>  
 [<span data-ttu-id="7edd1-153">Dostrajanie aplikacji Async (C#)</span><span class="sxs-lookup"><span data-stu-id="7edd1-153">Fine-Tuning Your Async Application (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)  
 [<span data-ttu-id="7edd1-154">Programowanie asynchroniczne z async i await (C#)</span><span class="sxs-lookup"><span data-stu-id="7edd1-154">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="7edd1-155">Próbka asynchronicznych: Dostrajanie aplikacji dokładnej</span><span class="sxs-lookup"><span data-stu-id="7edd1-155">Async Sample: Fine Tuning Your Application</span></span>](http://go.microsoft.com/fwlink/?LinkId=255046)