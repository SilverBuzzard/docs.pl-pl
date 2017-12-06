---
title: 'Porady: dodawanie do lub usuwanie z kolekcji kontrolek w czasie wykonywania'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b359679df68bf3caa9bab1bdbadedadcde45ac5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="bf905-102">Porady: dodawanie do lub usuwanie z kolekcji kontrolek w czasie wykonywania</span><span class="sxs-lookup"><span data-stu-id="bf905-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="bf905-103">Typowe zadania w projektowanie aplikacji są dodawanie formantów do oraz usuwanie kontrolek z dowolnego formantu kontenera na formularzach (takich jak <xref:System.Windows.Forms.Panel> lub <xref:System.Windows.Forms.GroupBox> formant lub nawet formularza).</span><span class="sxs-lookup"><span data-stu-id="bf905-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="bf905-104">W czasie projektowania formantów może być przeciągnięte bezpośrednio na panelu lub grupy.</span><span class="sxs-lookup"><span data-stu-id="bf905-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="bf905-105">W czasie wykonywania, obsługa tych kontrolek `Controls` kolekcji, która przechowuje informacje o kontrolki są umieszczane na nich.</span><span class="sxs-lookup"><span data-stu-id="bf905-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf905-106">Poniższy przykład kodu dotyczy żadnego formantu, który obsługuje kolekcji formantów w niej.</span><span class="sxs-lookup"><span data-stu-id="bf905-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="bf905-107">Aby dodać kontrolkę programistycznie do kolekcji</span><span class="sxs-lookup"><span data-stu-id="bf905-107">To add a control to a collection programmatically</span></span>  
  
1.  <span data-ttu-id="bf905-108">Utwórz wystąpienie formantu ma zostać dodana.</span><span class="sxs-lookup"><span data-stu-id="bf905-108">Create an instance of the control to be added.</span></span>  
  
2.  <span data-ttu-id="bf905-109">Ustaw właściwości nowej kontrolki.</span><span class="sxs-lookup"><span data-stu-id="bf905-109">Set properties of the new control.</span></span>  
  
3.  <span data-ttu-id="bf905-110">Dodawanie formantu do `Controls` kolekcji kontrolki nadrzędnej.</span><span class="sxs-lookup"><span data-stu-id="bf905-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="bf905-111">W poniższym przykładzie przedstawiono sposób tworzenia wystąpienia <xref:System.Windows.Forms.Button> formantu.</span><span class="sxs-lookup"><span data-stu-id="bf905-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="bf905-112">Wymaga to formularza z <xref:System.Windows.Forms.Panel> kontroli, a metoda obsługi zdarzeń dla przycisku tworzone `NewPanelButton_Click`, już istnieje.</span><span class="sxs-lookup"><span data-stu-id="bf905-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="bf905-113">Aby usunąć formanty programowo z kolekcji</span><span class="sxs-lookup"><span data-stu-id="bf905-113">To remove controls from a collection programmatically</span></span>  
  
1.  <span data-ttu-id="bf905-114">Usuń program obsługi zdarzeń z zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="bf905-114">Remove the event handler from the event.</span></span> <span data-ttu-id="bf905-115">W [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], użyj [RemoveHandler — instrukcja](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) — słowo kluczowe; na liście [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], użyj [-= — Operator (odwołanie w C#)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="bf905-115">In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], use the [RemoveHandler Statement](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) keyword; in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], use the [-= Operator (C# Reference)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span></span>  
  
2.  <span data-ttu-id="bf905-116">Użyj `Remove` do usunięcia z poziomu Panelu sterowania żądaną `Controls` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="bf905-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3.  <span data-ttu-id="bf905-117">Wywołanie <xref:System.Windows.Forms.Control.Dispose%2A> metodę, aby zwolnić wszystkie zasoby używane przez formant.</span><span class="sxs-lookup"><span data-stu-id="bf905-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bf905-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bf905-118">See Also</span></span>  
 <xref:System.Windows.Forms.Panel>  
 [<span data-ttu-id="bf905-119">Panel — formant</span><span class="sxs-lookup"><span data-stu-id="bf905-119">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)