---
title: "Instrukcje: Tworzenie usługi przepływu pracy wywołującej inną usługę przepływu pracy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0a3b9f77445e8629fb67d099c6d7944044897fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a><span data-ttu-id="0807c-102">Instrukcje: Tworzenie usługi przepływu pracy wywołującej inną usługę przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="0807c-102">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>
<span data-ttu-id="0807c-103">Czasami jest niezbędne dla usługi przepływu pracy można uzyskać informacji z innej usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="0807c-103">It is sometimes necessary for a workflow service to obtain information from another workflow service.</span></span>  <span data-ttu-id="0807c-104">W tym temacie przedstawiono sposób wywoływania jednej usługi przepływu pracy z innej.</span><span class="sxs-lookup"><span data-stu-id="0807c-104">This topic demonstrates how to call one workflow service from another.</span></span> <span data-ttu-id="0807c-105">W tym temacie utworzymy dwie usługi przepływu pracy; jeden, który ma metodę, która odwraca ciągu wejściowego, a druga konwertujący ciągu wejściowego na wielkie litery, po wycofaniu ciąg, który używa pierwszej usługi.</span><span class="sxs-lookup"><span data-stu-id="0807c-105">In this topic, we’ll create two workflow services; one that has a method that reverses the input string, and another that converts the input string to uppercase after reversing the string that uses the first service.</span></span>  
  
### <a name="to-create-the-reverser-workflow-service"></a><span data-ttu-id="0807c-106">Aby utworzyć system usługi przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="0807c-106">To create the Reverser workflow service</span></span>  
  
1.  <span data-ttu-id="0807c-107">Uruchom [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] jako administrator.</span><span class="sxs-lookup"><span data-stu-id="0807c-107">Run [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] as an administrator.</span></span>  
  
2.  <span data-ttu-id="0807c-108">Wybierz **pliku**, **nowy projekt**.</span><span class="sxs-lookup"><span data-stu-id="0807c-108">Select **File**, **New Project**.</span></span> <span data-ttu-id="0807c-109">W obszarze **przepływu pracy** w węźle **zainstalowane szablony** okienku wybierz **aplikacji usługi przepływu pracy WCF**.</span><span class="sxs-lookup"><span data-stu-id="0807c-109">Under the **Workflow** node in the **Installed Templates** pane, select **WCF Workflow Service Application**.</span></span> <span data-ttu-id="0807c-110">Nazwa rozwiązania `NestedServices` , a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0807c-110">Name the solution `NestedServices` and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="0807c-111">W obszarze **serwerów**, upewnij się, że **użycia lokalnego serwera sieci Web usług IIS** jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="0807c-111">Under **Servers**, make sure that **Use Local IIS Web Server** is selected.</span></span> <span data-ttu-id="0807c-112">Kliknij przycisk **utworzyć katalog wirtualny**.</span><span class="sxs-lookup"><span data-stu-id="0807c-112">Click **Create Virtual Directory**.</span></span> <span data-ttu-id="0807c-113">Kliknij przycisk **OK** w okno dialogowe podając pomyślnie utworzono katalog wirtualny.</span><span class="sxs-lookup"><span data-stu-id="0807c-113">Click **OK** in the dialog box stating that the virtual directory was successfully created.</span></span>  
  
4.  <span data-ttu-id="0807c-114">W Eksploratorze rozwiązań, Zmień nazwę Service1.xamlx do `StringReverserService.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="0807c-114">In Solution Explorer, rename Service1.xamlx to `StringReverserService.xamlx`.</span></span>  
  
5.  <span data-ttu-id="0807c-115">Na **właściwości projektu** dla nowego projektu kliknij pozycję **Web** kartę. Ustaw **Akcja uruchamiania** do **określonej strony**i wybierz StringReverserService.xamlx jako strony, aby rozpocząć.</span><span class="sxs-lookup"><span data-stu-id="0807c-115">On the **Project Properties** page for the new project, click the **Web** tab. Set the **Start Action** to **Specific Page**, and select StringReverserService.xamlx as the page to start.</span></span>  
  
6.  <span data-ttu-id="0807c-116">Otwórz w Projektancie StringReverserService.xamlx i usuń istniejącą `ReceiveRequest` i `SendReply` działania, a następnie przeciągnij `ReceiveAndSendReply` działania do istniejącego działania sekwencji.</span><span class="sxs-lookup"><span data-stu-id="0807c-116">Open StringReverserService.xamlx in the designer and delete the existing `ReceiveRequest` and `SendReply` activities, and then drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="0807c-117">Ustaw **OperationName** do ReverseString.</span><span class="sxs-lookup"><span data-stu-id="0807c-117">Set the **OperationName** to ReverseString.</span></span>  
  
    2.  <span data-ttu-id="0807c-118">Ustaw **ServiceContractName** do IReverseString.</span><span class="sxs-lookup"><span data-stu-id="0807c-118">Set the **ServiceContractName** to IReverseString.</span></span>  
  
    3.  <span data-ttu-id="0807c-119">Wybierz **CanCreateInstance** pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="0807c-119">Select the **CanCreateInstance** check box.</span></span>  
  
7.  <span data-ttu-id="0807c-120">Wybierz **SequentialService** działania, a następnie kliknij przycisk **zmienne** u dołu projektanta.</span><span class="sxs-lookup"><span data-stu-id="0807c-120">Select the **SequentialService** activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="0807c-121">Utwórz dwa nowe zmienne o nazwach StringToReverse i ReversedStringToReturn typu String.</span><span class="sxs-lookup"><span data-stu-id="0807c-121">Create two new variables named StringToReverse and ReversedStringToReturn of type String.</span></span>  
  
8.  <span data-ttu-id="0807c-122">Kliknij przycisk **Definiuj** łącze w **Receive** działania.</span><span class="sxs-lookup"><span data-stu-id="0807c-122">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="0807c-123">Kliknij przycisk **parametry**i Utwórz parametr o nazwie InputString typu ciąg, który przypisuje StringToReverse.</span><span class="sxs-lookup"><span data-stu-id="0807c-123">Click the  **Parameters**, and create a parameter named InputString of type String that assigns to StringToReverse.</span></span>  
  
9. <span data-ttu-id="0807c-124">Kliknij przycisk **Definiuj** łącze w **SendReplyToReceive** działania.</span><span class="sxs-lookup"><span data-stu-id="0807c-124">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="0807c-125">Kliknij przycisk **parametry**i Utwórz parametr o nazwie ReversedString typu ciąg, przypisane do ReversedStringToReturn.</span><span class="sxs-lookup"><span data-stu-id="0807c-125">Click the **Parameters**, and create a parameter named ReversedString of type String, assigned to ReversedStringToReturn.</span></span>  
  
10. <span data-ttu-id="0807c-126">Aby zaimplementować logiki dla usługi, Utwórz nową klasę w projekcie o nazwie StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="0807c-126">To implement the logic for the service, create a new class in the project called StringLibrary.</span></span>  <span data-ttu-id="0807c-127">Zastąp definicję klasy następującym kodem.</span><span class="sxs-lookup"><span data-stu-id="0807c-127">Replace the class definition with the following code.</span></span>  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. <span data-ttu-id="0807c-128">Aby wywołać metodę ReverseString w danych wejściowych, przeciągnij **InvokeMethod** działania z przybornika do odstęp między **Receive** i **SendReply** działań.</span><span class="sxs-lookup"><span data-stu-id="0807c-128">To call the ReverseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="0807c-129">Ustaw właściwości działania w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="0807c-129">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="0807c-130">**MethodName**: ReverseString</span><span class="sxs-lookup"><span data-stu-id="0807c-130">**MethodName**: ReverseString</span></span>  
  
    2.  <span data-ttu-id="0807c-131">**Wynik**: ReversedStringToReturn</span><span class="sxs-lookup"><span data-stu-id="0807c-131">**Result**: ReversedStringToReturn</span></span>  
  
    3.  <span data-ttu-id="0807c-132">**Parametry**: Utwórz nowy parametr z **kierunek** z In, **typu** ciągu, a **wartość** z StringToReverse.</span><span class="sxs-lookup"><span data-stu-id="0807c-132">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToReverse.</span></span>  
  
    4.  <span data-ttu-id="0807c-133">**Element TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="0807c-133">**TargetType**: NestedServices.StringLibrary</span></span>  
  
12. <span data-ttu-id="0807c-134">Przetestuj usługę, naciskając klawisz F5.</span><span class="sxs-lookup"><span data-stu-id="0807c-134">Test the service by pressing F5.</span></span> <span data-ttu-id="0807c-135">W kliencie testowym WCF, która jest wyświetlana kliknij dwukrotnie metodę ReverseString().</span><span class="sxs-lookup"><span data-stu-id="0807c-135">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="0807c-136">W okienku żądania wprowadź `Sample` dla wartości parametru InputString.</span><span class="sxs-lookup"><span data-stu-id="0807c-136">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="0807c-137">Kliknij przycisk **wywołania**.</span><span class="sxs-lookup"><span data-stu-id="0807c-137">Click **Invoke**.</span></span> <span data-ttu-id="0807c-138">Usługa powinna zwrócić "elpmaS".</span><span class="sxs-lookup"><span data-stu-id="0807c-138">The service should return "elpmaS".</span></span>  
  
### <a name="to-create-the-uppercaser-workflow-service"></a><span data-ttu-id="0807c-139">Aby utworzyć UpperCaser usługi przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="0807c-139">To create the UpperCaser workflow service</span></span>  
  
1.  <span data-ttu-id="0807c-140">Kliknij prawym przyciskiem myszy projekt NestedServices i wybierz **Dodaj**, **nowy element**.</span><span class="sxs-lookup"><span data-stu-id="0807c-140">Right-click the NestedServices project and select **Add**, **New Item**.</span></span> <span data-ttu-id="0807c-141">W **przepływu pracy** węzła, wybierz opcję **usługi przepływu pracy WCF**i nadaj nazwę nowej usługi `UpperCaserService`.</span><span class="sxs-lookup"><span data-stu-id="0807c-141">In the **Workflow** node, select **WCF Workflow Service**, and name the new service `UpperCaserService`.</span></span> <span data-ttu-id="0807c-142">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="0807c-142">Click **Add**.</span></span> <span data-ttu-id="0807c-143">To należy dodać nową usługę przepływu pracy o nazwie UpperCaserService.xamlx do projektu.</span><span class="sxs-lookup"><span data-stu-id="0807c-143">This should add a new workflow service called UpperCaserService.xamlx to the project.</span></span>  
  
2.  <span data-ttu-id="0807c-144">Otwórz w Projektancie UpperCaserService.xamlx i usuń istniejącą **ReceiveRequest** i `SendReply` działania i przeciągnij `ReceiveAndSendReply` działania do istniejącego działania sekwencji.</span><span class="sxs-lookup"><span data-stu-id="0807c-144">Open UpperCaserService.xamlx in the designer and delete the existing **ReceiveRequest** and `SendReply` activities, and drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="0807c-145">Ustaw **OperationName** do UpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="0807c-145">Set the **OperationName** to UpperCaseString.</span></span>  
  
    2.  <span data-ttu-id="0807c-146">Ustaw **ServiceContractName** do IUpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="0807c-146">Set the **ServiceContractName** to IUpperCaseString.</span></span>  
  
    3.  <span data-ttu-id="0807c-147">Wybierz **CanCreateInstance** pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="0807c-147">Select the **CanCreateInstance** check box.</span></span>  
  
3.  <span data-ttu-id="0807c-148">Wybierz działanie SequentialService, a następnie kliknij przycisk **zmienne** u dołu projektanta.</span><span class="sxs-lookup"><span data-stu-id="0807c-148">Select the SequentialService activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="0807c-149">Utwórz trzy nowe zmienne o nazwach StringToUpper, StringToReverse i StringToReturn typu String.</span><span class="sxs-lookup"><span data-stu-id="0807c-149">Create three new variables named StringToUpper, StringToReverse, and StringToReturn of type String.</span></span>  
  
4.  <span data-ttu-id="0807c-150">Kliknij przycisk **Definiuj** łącze w **Receive** działania.</span><span class="sxs-lookup"><span data-stu-id="0807c-150">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="0807c-151">Kliknij przycisk **parametry**i Utwórz parametr o nazwie InputString typu ciąg, który przypisuje StringToUpper.</span><span class="sxs-lookup"><span data-stu-id="0807c-151">Click the **Parameters**, and create a parameter named InputString of type String that assigns to StringToUpper.</span></span>  
  
5.  <span data-ttu-id="0807c-152">Kliknij przycisk **Definiuj** łącze w **SendReplyToReceive** działania.</span><span class="sxs-lookup"><span data-stu-id="0807c-152">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="0807c-153">Kliknij przycisk **parametry**i Utwórz parametr o nazwie ModifiedString typu ciąg, przypisane do StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="0807c-153">Click the **Parameters**, and create a parameter named ModifiedString of type String, assigned to StringToReturn.</span></span>  
  
6.  <span data-ttu-id="0807c-154">Aby zaimplementować logiki dla usługi, utworzenie nowej metody w klasie StringLibrary, używając następującego kodu.</span><span class="sxs-lookup"><span data-stu-id="0807c-154">To implement the logic for the service, create a new method in the StringLibrary class using the following code.</span></span>  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  <span data-ttu-id="0807c-155">Aby wywołać metodę UpperCaseString w danych wejściowych, przeciągnij **InvokeMethod** działania z przybornika do odstęp między **Receive** i **SendReply** działań.</span><span class="sxs-lookup"><span data-stu-id="0807c-155">To call the UpperCaseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="0807c-156">Ustaw właściwości działania w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="0807c-156">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="0807c-157">**MethodName**: UpperCaseString</span><span class="sxs-lookup"><span data-stu-id="0807c-157">**MethodName**: UpperCaseString</span></span>  
  
    2.  <span data-ttu-id="0807c-158">**Wynik**: StringToReverse</span><span class="sxs-lookup"><span data-stu-id="0807c-158">**Result**: StringToReverse</span></span>  
  
    3.  <span data-ttu-id="0807c-159">**Parametry**: Utwórz nowy parametr z **kierunek** z In, **typu** ciągu, a **wartość** z StringToUpper.</span><span class="sxs-lookup"><span data-stu-id="0807c-159">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToUpper.</span></span>  
  
    4.  <span data-ttu-id="0807c-160">**Element TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="0807c-160">**TargetType**: NestedServices.StringLibrary</span></span>  
  
8.  <span data-ttu-id="0807c-161">Teraz Zadzwonimy pierwszej usługi zmodyfikowany ciąg.</span><span class="sxs-lookup"><span data-stu-id="0807c-161">We’ll now call the first service on the modified string.</span></span> <span data-ttu-id="0807c-162">Kliknij prawym przyciskiem myszy projekt i wybierz **Dodaj odwołanie do usługi**.</span><span class="sxs-lookup"><span data-stu-id="0807c-162">Right-click the project and select **Add Service Reference**.</span></span> <span data-ttu-id="0807c-163">Dodaj odwołania do usługi z usługą w http://localhost/NestedServices/StringReverserService.xamlx i skompiluj projekt do tworzenia działań niestandardowych do uzyskania dostępu do pierwszej usługi sieci Web.</span><span class="sxs-lookup"><span data-stu-id="0807c-163">Add a service reference to the service at http://localhost/NestedServices/StringReverserService.xamlx and build the project to create a custom activity to access the first Web service.</span></span>  
  
9. <span data-ttu-id="0807c-164">Przeciągnij wystąpienie nowego działania przepływu pracy, między **InvokeMethod** działania i **SendReplyToReceive** działań.</span><span class="sxs-lookup"><span data-stu-id="0807c-164">Drag an instance of the new activity onto the workflow, between the **InvokeMethod** activity and the **SendReplyToReceive** activities.</span></span> <span data-ttu-id="0807c-165">Przypisz zmiennej StringToReverse z właściwością InputString nowe działanie i zmiennej StringToReturn właściwości StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="0807c-165">Assign the variable StringToReverse to the InputString property of the new activity, and the variable StringToReturn to the StringToReturn property.</span></span>  
  
10. <span data-ttu-id="0807c-166">Otwórz stronę właściwości dla projektu NestedServices i zmień **określonej strony** w **Web** kartę, aby UpperCaserService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="0807c-166">Open the Properties page for the NestedServices project, and change the **Specific Page** in the **Web** tab to UpperCaserService.xamlx.</span></span>  
  
11. <span data-ttu-id="0807c-167">Przetestuj usługę, naciskając klawisz F5.</span><span class="sxs-lookup"><span data-stu-id="0807c-167">Test the service by pressing F5.</span></span> <span data-ttu-id="0807c-168">W kliencie testowym WCF, która jest wyświetlana kliknij dwukrotnie metodę ReverseString().</span><span class="sxs-lookup"><span data-stu-id="0807c-168">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="0807c-169">W okienku żądania wprowadź `Sample` dla wartości parametru InputString.</span><span class="sxs-lookup"><span data-stu-id="0807c-169">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="0807c-170">Kliknij przycisk **wywołania**.</span><span class="sxs-lookup"><span data-stu-id="0807c-170">Click **Invoke**.</span></span> <span data-ttu-id="0807c-171">Usługa powinna zwrócić "ELPMAS".</span><span class="sxs-lookup"><span data-stu-id="0807c-171">The service should return "ELPMAS".</span></span>  
  
### <a name="to-create-a-client-to-call-the-services"></a><span data-ttu-id="0807c-172">Aby utworzyć klienta do wywołania usługi</span><span class="sxs-lookup"><span data-stu-id="0807c-172">To create a client to call the services</span></span>  
  
1.  <span data-ttu-id="0807c-173">Dodaj nowy projekt aplikacji konsoli o nazwie klienta do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="0807c-173">Add a new Console application project called Client to the solution.</span></span>  
  
2.  <span data-ttu-id="0807c-174">Kliknij prawym przyciskiem myszy projekt klienta i wybierz **Dodaj odwołanie do usługi**.</span><span class="sxs-lookup"><span data-stu-id="0807c-174">Right-click the Client project and select **Add Service Reference**.</span></span> <span data-ttu-id="0807c-175">W wyświetlonym oknie kliknij **odnajdowania**.</span><span class="sxs-lookup"><span data-stu-id="0807c-175">In the window that appears, click **Discover**.</span></span> <span data-ttu-id="0807c-176">Wybierz StringReverserService.xamlx, a następnie wprowadź ReverseService jako obszar nazw.</span><span class="sxs-lookup"><span data-stu-id="0807c-176">Select StringReverserService.xamlx, and enter ReverseService as the namespace.</span></span>  <span data-ttu-id="0807c-177">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0807c-177">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="0807c-178">Zastąp metodę Main, w pliku Program.cs następującym kodem.</span><span class="sxs-lookup"><span data-stu-id="0807c-178">Replace the Main method in Program.cs with the following code.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```