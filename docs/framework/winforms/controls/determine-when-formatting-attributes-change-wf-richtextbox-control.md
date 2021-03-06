---
title: 'Porady: ustalenie, kiedy zmieniono atrybuty formatowania w formancie RichTextBox formularzy systemu Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: 789a0a25c65185b101ef427ff62871fa490c7f1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525217"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Porady: ustalenie, kiedy zmieniono atrybuty formatowania w formancie RichTextBox formularzy systemu Windows
Użycia formularzy systemu Windows <xref:System.Windows.Forms.RichTextBox> formant jest formatowanie tekstu z atrybutów, takich jak opcje czcionki lub style. Aplikacja może być konieczne śledzić wszystkie zmiany w tekście formatowanie na potrzeby wyświetlania paska narzędzi, jak wiele aplikacji edytora tekstu.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Do reagowania na zmiany w formatowaniu atrybutów  
  
1.  Pisanie kodu <xref:System.Windows.Forms.RichTextBox.SelectionChanged> obsługi zdarzeń do wykonywania odpowiednich akcji w zależności od wartości atrybutu. Poniższy przykład umożliwia zmianę wygląd przycisku paska narzędzi w zależności od wartości <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> właściwości. Przycisk paska narzędzi będą aktualizowane po przeniesieniu punktu wstawiania w formancie.  
  
     W poniższym przykładzie założono formularza z <xref:System.Windows.Forms.RichTextBox> kontroli i <xref:System.Windows.Forms.ToolBar> formant, który zawiera przycisk paska narzędzi. Aby uzyskać więcej informacji na temat paski narzędzi i przycisków paska narzędzi, zobacz [porady: dodawanie przycisków do formantu ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox, kontrolka](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Kontrolki do użycia w formularzach Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
