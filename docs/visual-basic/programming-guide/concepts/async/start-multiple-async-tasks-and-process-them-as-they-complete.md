---
title: "Rozpoczynanie wielu zadań asynchronicznych i przetwarzanie ich w chwili zakończenia (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57ffb748-af40-4794-bedd-bdb7fea062de
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dfabe4619e5d73b554d91edb137ae1ce7d34b5ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a><span data-ttu-id="adfed-102">Rozpoczynanie wielu zadań asynchronicznych i przetwarzanie ich w chwili zakończenia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adfed-102">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>
<span data-ttu-id="adfed-103">Przy użyciu <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, można uruchomić wielu zadań jednocześnie i je jeden po drugim Przetwarzaj one jest ukończona, a nie ich przetworzyć w kolejności, w którym jest uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="adfed-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>  
  
 <span data-ttu-id="adfed-104">W poniższym przykładzie użyto zapytania, aby utworzyć kolekcję zadań.</span><span class="sxs-lookup"><span data-stu-id="adfed-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="adfed-105">Każde zadanie pobiera zawartość z określonej witryny sieci Web.</span><span class="sxs-lookup"><span data-stu-id="adfed-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="adfed-106">W każdej iteracji chwilę pętli, oczekiwano wywołania `WhenAny` zwraca zadanie w kolekcji zadań najpierw zakończy jej pobierania.</span><span class="sxs-lookup"><span data-stu-id="adfed-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="adfed-107">To zadanie jest usunięty z kolekcji i przetwarzane.</span><span class="sxs-lookup"><span data-stu-id="adfed-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="adfed-108">Pętla jest powtarzany do momentu Kolekcja nie zawiera więcej zadań.</span><span class="sxs-lookup"><span data-stu-id="adfed-108">The loop repeats until the collection contains no more tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adfed-109">Uruchamianie przykładów, musi mieć program Visual Studio 2012 lub nowszej i .NET Framework 4.5 lub nowszej zainstalowany na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="adfed-109">To run the examples, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="adfed-110">Pobieranie przykładu</span><span class="sxs-lookup"><span data-stu-id="adfed-110">Downloading the Example</span></span>  
 <span data-ttu-id="adfed-111">Możesz pobrać pełną projekt Windows Presentation Foundation (WPF) z [próbki Async: poprawnie dostrajanie Twoja aplikacja](http://go.microsoft.com/fwlink/?LinkId=255046) , a następnie wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="adfed-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="adfed-112">Dekompresja pobranego pliku, a następnie uruchom program Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="adfed-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="adfed-113">Na pasku menu wybierz **pliku**, **Otwórz**, **projektu/rozwiązania**.</span><span class="sxs-lookup"><span data-stu-id="adfed-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="adfed-114">W **Otwórz projekt** okno dialogowe, otwórz folder, który zawiera przykładowy kod, który można zdekompresować, a następnie otwórz plik rozwiązania (sln) dla AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="adfed-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="adfed-115">W **Eksploratora rozwiązań**, otwórz menu skrótów **ProcessTasksAsTheyFinish** projektu, a następnie wybierz pozycję **Ustaw jako projekt startowy**.</span><span class="sxs-lookup"><span data-stu-id="adfed-115">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="adfed-116">Wybierz klawisz F5, aby uruchomić projekt.</span><span class="sxs-lookup"><span data-stu-id="adfed-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="adfed-117">Wybierz klucze Ctrl + F5, aby uruchomić projekt bez debugowania go.</span><span class="sxs-lookup"><span data-stu-id="adfed-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="adfed-118">Uruchom projekt kilka razy, aby sprawdzić, czy pobrane długości nie zawsze są wyświetlane w tej samej kolejności.</span><span class="sxs-lookup"><span data-stu-id="adfed-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
 <span data-ttu-id="adfed-119">Jeśli nie chcesz pobrać projekt, można przejrzeć plik MainWindow.xaml.vb na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="adfed-119">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="adfed-120">Tworzenie w przykładzie</span><span class="sxs-lookup"><span data-stu-id="adfed-120">Building the Example</span></span>  
 <span data-ttu-id="adfed-121">W tym przykładzie dodaje kod, który został napisany w [anulowanie pozostałych zadań asynchronicznych po jednym jest kompletna (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) i używa tego samego interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="adfed-121">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) and uses the same UI.</span></span>  
  
 <span data-ttu-id="adfed-122">Do tworzenia przykładzie samodzielnie krok po kroku, postępuj zgodnie z instrukcjami w sekcji "Pobieranie Example", ale wybierz **CancelAfterOneTask** jako **projekt startowy**.</span><span class="sxs-lookup"><span data-stu-id="adfed-122">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAfterOneTask** as the **StartUp Project**.</span></span> <span data-ttu-id="adfed-123">Dodaj zmiany w tym temacie umożliwiają `AccessTheWebAsync` metody w tym projekcie.</span><span class="sxs-lookup"><span data-stu-id="adfed-123">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="adfed-124">Zmiany są oznaczone gwiazdki.</span><span class="sxs-lookup"><span data-stu-id="adfed-124">The changes are marked with asterisks.</span></span>  
  
 <span data-ttu-id="adfed-125">**CancelAfterOneTask** Projekt już zawiera zapytanie, które po wykonaniu tworzy kolekcję zadań.</span><span class="sxs-lookup"><span data-stu-id="adfed-125">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="adfed-126">Każde wywołanie `ProcessURLAsync` w poniższym kodzie zwraca <xref:System.Threading.Tasks.Task%601> gdzie `TResult` jest liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="adfed-126">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
```vb  
Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
    From url In urlList Select ProcessURLAsync(url, client, ct)  
```  
  
 <span data-ttu-id="adfed-127">W pliku MainWindow.xaml.vb projektu, wprowadź następujące zmiany do `AccessTheWebAsync` metody.</span><span class="sxs-lookup"><span data-stu-id="adfed-127">In the MainWindow.xaml.vb file of the  project, make the following changes to the `AccessTheWebAsync` method.</span></span>  
  
-   <span data-ttu-id="adfed-128">Wykonanie kwerendy, stosując <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> zamiast <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="adfed-128">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
    ```vb  
    Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
    ```  
  
-   <span data-ttu-id="adfed-129">Dodaj chwilę pętli, które wykonuje następujące czynności dla każdego zadania w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="adfed-129">Add a while loop that performs the following steps for each task in the collection.</span></span>  
  
    1.  <span data-ttu-id="adfed-130">Oczekujące na wywołanie `WhenAny` do identyfikowania pierwszego zadania w kolekcji, aby zakończyć jej pobierania.</span><span class="sxs-lookup"><span data-stu-id="adfed-130">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>  
  
        ```vb  
        Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
        ```  
  
    2.  <span data-ttu-id="adfed-131">To zadanie usuwa z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="adfed-131">Removes that task from the collection.</span></span>  
  
        ```vb  
        downloadTasks.Remove(firstFinishedTask)  
        ```  
  
    3.  <span data-ttu-id="adfed-132">Oczekujące na `firstFinishedTask`, który jest zwracany przez wywołanie do `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="adfed-132">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="adfed-133">`firstFinishedTask` Zmienna jest <xref:System.Threading.Tasks.Task%601> gdzie `TReturn` jest liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="adfed-133">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="adfed-134">Zadanie zostało już ukończone, ale należy poczekać na można pobrać długości pobrany witryny sieci Web, jak przedstawiono na poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="adfed-134">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span>  
  
        ```vb  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 <span data-ttu-id="adfed-135">Aby sprawdzić, czy pobrane długości nie zawsze są wyświetlane w tej samej kolejności należy uruchomić kilka razy projektu.</span><span class="sxs-lookup"><span data-stu-id="adfed-135">You should run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="adfed-136">Można użyć `WhenAny` w pętli, zgodnie z opisem w tym przykładzie, aby rozwiązać problemy z działaniem niewielkiej liczby zadań.</span><span class="sxs-lookup"><span data-stu-id="adfed-136">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="adfed-137">Jednak inne podejścia są bardziej wydajne, jeśli masz dużą liczbę zadań w celu przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="adfed-137">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="adfed-138">Aby uzyskać dodatkowe informacje i przykłady, zobacz [przetwarzania zadań jako zakończenie](http://go.microsoft.com/fwlink/?LinkId=260810).</span><span class="sxs-lookup"><span data-stu-id="adfed-138">For more information and examples, see [Processing Tasks as they complete](http://go.microsoft.com/fwlink/?LinkId=260810).</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="adfed-139">Kompletny przykład</span><span class="sxs-lookup"><span data-stu-id="adfed-139">Complete Example</span></span>  
 <span data-ttu-id="adfed-140">Następujący kod jest pełny tekst pliku MainWindow.xaml.vb dla przykładu.</span><span class="sxs-lookup"><span data-stu-id="adfed-140">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="adfed-141">Gwiazdki Oznacz elementy, które zostały dodane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="adfed-141">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="adfed-142">Zwróć uwagę, że musisz dodać odwołanie do <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="adfed-142">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="adfed-143">Można pobrać projektu z [próbki Async: poprawnie dostrajanie Twoja aplikacja](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="adfed-143">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            Await AccessTheWebAsync(cts.Token)  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' You can still include a Cancel button if you want to.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToList to execute the query and start the download tasks.   
        Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
  
        ' ***Add a loop to process the tasks one at a time until none remain.  
        While downloadTasks.Count > 0  
            ' ***Identify the first task that completes.  
            Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
            ' ***Remove the selected task from the list so that you don't  
            ' process it more than once.  
            downloadTasks.Remove(firstFinishedTask)  
  
            ' ***Await the first completed task and display the results.  
            Dim length = Await firstFinishedTask  
            resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        End While  
  
    End Function  
  
    ' Bundle the processing steps for a website into one async method.  
    Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        Return urlContents.Length  
    End Function  
  
    ' Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
End Class  
  
' Sample output:  
  
' Length of the download:  226093  
' Length of the download:  412588  
' Length of the download:  175490  
' Length of the download:  204890  
' Length of the download:  158855  
' Length of the download:  145790  
' Length of the download:  44908  
' Downloads complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="adfed-144">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="adfed-144">See Also</span></span>  
 <xref:System.Threading.Tasks.Task.WhenAny%2A>  
 [<span data-ttu-id="adfed-145">Dostrajanie aplikacji Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adfed-145">Fine-Tuning Your Async Application (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)  
 [<span data-ttu-id="adfed-146">Programowanie asynchroniczne z Async i Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adfed-146">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="adfed-147">Próbka asynchronicznych: Dostrajanie aplikacji dokładnej</span><span class="sxs-lookup"><span data-stu-id="adfed-147">Async Sample: Fine Tuning Your Application</span></span>](http://go.microsoft.com/fwlink/?LinkId=255046)