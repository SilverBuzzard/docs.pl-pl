---
title: 'Porady: pokazywanie listy czcionek przy użyciu składnika FontDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: fe291df1648da5002ce3173a68208bbad659705d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536501"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>Porady: pokazywanie listy czcionek przy użyciu składnika FontDialog
[FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) składnika umożliwia użytkownikom wybierz czcionkę, a także zmienić aspektów wyświetlanej takie jak wagi i rozmiaru.  
  
 Czcionka zaznaczona w oknie dialogowym jest zwracany w <xref:System.Windows.Forms.FontDialog.Font%2A> właściwości. W związku z tym wykorzystaniu czcionki wybrane przez użytkownika jest tak proste, jak odczytywania właściwości.  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>Aby wybrać właściwości czcionki przy użyciu składnika FontDialog  
  
1.  Wyświetlać przy użyciu — okno dialogowe <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metody.  
  
2.  Użyj <xref:System.Windows.Forms.DialogResult> właściwości, aby określić sposób zamknięcia okna dialogowego.  
  
3.  Użyj <xref:System.Windows.Forms.FontDialog.Font%2A> właściwości można ustawić żądanego czcionki.  
  
     W poniższym przykładzie <xref:System.Windows.Forms.Button> formantu <xref:System.Windows.Forms.Control.Click> obsługi zdarzeń otwiera <xref:System.Windows.Forms.FontDialog> składnika. Gdy czcionki jest wybrany, a użytkownik kliknie **OK**, <xref:System.Windows.Forms.FontDialog.Font%2A> właściwość <xref:System.Windows.Forms.TextBox> formantu, który znajduje się w formularzu ma ustawioną wartość wybranej czcionki. W przykładzie założono formularz zawiera <xref:System.Windows.Forms.Button> kontroli, <xref:System.Windows.Forms.TextBox> kontroli, a <xref:System.Windows.Forms.FontDialog> składnika.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     (Visual C# i [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) umieścić następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.FontDialog>  
 [FontDialog, składnik](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
