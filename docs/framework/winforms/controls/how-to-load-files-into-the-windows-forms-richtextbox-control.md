---
title: "Porady: ładowanie plików do formantu RichTextBox formularzy systemu Windows"
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
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ba0e2aec42fa3656b64140134efa27fe8e940e1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a><span data-ttu-id="6ee75-102">Porady: ładowanie plików do formantu RichTextBox formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="6ee75-102">How to: Load Files into the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="6ee75-103">Formularze systemu Windows <xref:System.Windows.Forms.RichTextBox> formant może wyświetlać zwykłego tekstu, jako zwykły tekst Unicode lub plik tekst sformatowany (RTF).</span><span class="sxs-lookup"><span data-stu-id="6ee75-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display a plain-text, Unicode plain-text, or Rich-Text-Format (RTF) file.</span></span> <span data-ttu-id="6ee75-104">Aby to zrobić, należy wywołać <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="6ee75-104">To do so, call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method.</span></span> <span data-ttu-id="6ee75-105">Można również użyć <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> metodę, aby załadować dane ze strumienia.</span><span class="sxs-lookup"><span data-stu-id="6ee75-105">You can also use the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method to load data from a stream.</span></span> <span data-ttu-id="6ee75-106">Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="6ee75-106">For more information, see <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-load-a-file-into-the-richtextbox-control"></a><span data-ttu-id="6ee75-107">Ładowanie pliku w formancie RichTextBox</span><span class="sxs-lookup"><span data-stu-id="6ee75-107">To load a file into the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="6ee75-108">Określanie ścieżki pliku, który można otworzyć za pomocą <xref:System.Windows.Forms.OpenFileDialog> składnika.</span><span class="sxs-lookup"><span data-stu-id="6ee75-108">Determine the path of the file to be opened using the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="6ee75-109">Aby uzyskać ogólne informacje, zobacz [openfiledialog — informacje o składniku](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6ee75-109">For an overview, see [OpenFileDialog Component Overview](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="6ee75-110">Wywołanie <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> metody <xref:System.Windows.Forms.RichTextBox> formantu, określając można załadować pliku i opcjonalnie typu pliku.</span><span class="sxs-lookup"><span data-stu-id="6ee75-110">Call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to load and optionally a file type.</span></span> <span data-ttu-id="6ee75-111">W poniższym przykładzie pliku do załadowania jest pobierana z <xref:System.Windows.Forms.OpenFileDialog> składnika <xref:System.Windows.Forms.FileDialog.FileName%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="6ee75-111">In the example below, the file to load is taken from the <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.FileDialog.FileName%2A> property.</span></span> <span data-ttu-id="6ee75-112">Wywołanie metody przy użyciu nazwy pliku jako jej argument tylko typu pliku zostanie zakłada się, że można RTF.</span><span class="sxs-lookup"><span data-stu-id="6ee75-112">If you call the method with a file name as its only argument, the file type will be assumed to be RTF.</span></span> <span data-ttu-id="6ee75-113">Aby określić plik innego typu, należy wywołać metodę o wartości <xref:System.Windows.Forms.RichTextBoxStreamType> wyliczenie jako drugi argument.</span><span class="sxs-lookup"><span data-stu-id="6ee75-113">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="6ee75-114">W poniższym przykładzie <xref:System.Windows.Forms.OpenFileDialog> składnika jest wyświetlany po kliknięciu przycisku.</span><span class="sxs-lookup"><span data-stu-id="6ee75-114">In the example below, the <xref:System.Windows.Forms.OpenFileDialog> component is shown when a button is clicked.</span></span> <span data-ttu-id="6ee75-115">Wybrany plik jest otwarty i wyświetlana w <xref:System.Windows.Forms.RichTextBox> formantu.</span><span class="sxs-lookup"><span data-stu-id="6ee75-115">The file selected is then opened and displayed in the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="6ee75-116">W tym przykładzie założono formularza znajduje się przycisk`btnOpenFile`.</span><span class="sxs-lookup"><span data-stu-id="6ee75-116">This example assumes a form has a button,`btnOpenFile`.</span></span>  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     <span data-ttu-id="6ee75-117">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Umieścić następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="6ee75-117">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6ee75-118">Aby uruchomić ten proces, używanego zestawu może wymagać poziom uprawnień przyznanych przez <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="6ee75-118">To run this process, your assembly may require a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="6ee75-119">Jeśli używasz w kontekście częściowego zaufania, proces może zgłosić wyjątek, ze względu na niewystarczające uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="6ee75-119">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="6ee75-120">Aby uzyskać więcej informacji, zobacz [podstawy zabezpieczeń dostępu kodu](../../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="6ee75-120">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee75-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6ee75-121">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="6ee75-122">RichTextBox — formant</span><span class="sxs-lookup"><span data-stu-id="6ee75-122">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="6ee75-123">Formanty do użycia w formularzach systemu Windows</span><span class="sxs-lookup"><span data-stu-id="6ee75-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)