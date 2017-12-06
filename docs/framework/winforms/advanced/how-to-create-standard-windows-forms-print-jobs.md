---
title: "Porady: tworzenie standardowych zadań drukowania formularzy systemu Windows"
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
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c2b0ce30f76fe7f8cbdc156c4a8ff5abffafae10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="8f48d-102">Porady: tworzenie standardowych zadań drukowania formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8f48d-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="8f48d-103">Podstawę drukowanie w formularzach systemu Windows jest <xref:System.Drawing.Printing.PrintDocument> składnik — w szczególności <xref:System.Drawing.Printing.PrintDocument.PrintPage> zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8f48d-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="8f48d-104">Pisanie kodu do obsługi <xref:System.Drawing.Printing.PrintDocument.PrintPage> zdarzeń, można określić wydruku i jak go wydrukować.</span><span class="sxs-lookup"><span data-stu-id="8f48d-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="8f48d-105">Aby utworzyć zadanie drukowania</span><span class="sxs-lookup"><span data-stu-id="8f48d-105">To create a print job</span></span>  
  
1.  <span data-ttu-id="8f48d-106">Dodaj <xref:System.Drawing.Printing.PrintDocument> składnika do formularza.</span><span class="sxs-lookup"><span data-stu-id="8f48d-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="8f48d-107">Napisać kod obsługujący <xref:System.Drawing.Printing.PrintDocument.PrintPage> zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8f48d-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="8f48d-108">Konieczne będzie kodu logiki drukowania.</span><span class="sxs-lookup"><span data-stu-id="8f48d-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="8f48d-109">Ponadto należy określić materiały do drukowania.</span><span class="sxs-lookup"><span data-stu-id="8f48d-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="8f48d-110">W poniższym przykładzie kodu, przykładowe grafiki w kształcie czerwonym prostokątem jest tworzony w <xref:System.Drawing.Printing.PrintDocument.PrintPage> obsługi zdarzeń do działania jako materiały do drukowania.</span><span class="sxs-lookup"><span data-stu-id="8f48d-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="8f48d-111">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] i [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) umieścić następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8f48d-111">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     <span data-ttu-id="8f48d-112">Można również napisać kod dla <xref:System.Drawing.Printing.PrintDocument.BeginPrint> i <xref:System.Drawing.Printing.PrintDocument.EndPrint> zdarzeń może obejmować całkowitą reprezentującą łączną liczbą stron do drukowania, który jest zmniejszana, jak drukuje każdej strony.</span><span class="sxs-lookup"><span data-stu-id="8f48d-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8f48d-113">Możesz dodać <xref:System.Windows.Forms.PrintDialog> składnika do formularza zapewnia interfejs czyste i wydajne użytkownika (UI) dla użytkowników.</span><span class="sxs-lookup"><span data-stu-id="8f48d-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="8f48d-114">Ustawienie <xref:System.Windows.Forms.PrintDialog.Document%2A> właściwość <xref:System.Windows.Forms.PrintDialog> umożliwia składnika można ustawić właściwości powiązanych z print dokumentu pracuje w formularzu.</span><span class="sxs-lookup"><span data-stu-id="8f48d-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="8f48d-115">Aby uzyskać więcej informacji na temat <xref:System.Windows.Forms.PrintDialog> składników, zobacz [składnika PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8f48d-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="8f48d-116">Aby uzyskać więcej informacji o specyfice formularzy systemu Windows zadania drukowania, łącznie ze sposobem tworzenia zadania drukowania programowo, zobacz <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="8f48d-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f48d-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8f48d-117">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="8f48d-118">Obsługa drukowania w formularzach systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8f48d-118">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)