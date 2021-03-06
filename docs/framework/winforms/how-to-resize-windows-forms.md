---
title: 'Porady: zmienianie rozmiarów formularzy systemu Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
ms.openlocfilehash: 40a2ff3dcde9d0fbbc9a7e6c67430eb8313614e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521189"
---
# <a name="how-to-resize-windows-forms"></a>Porady: zmienianie rozmiarów formularzy systemu Windows
Rozmiar formularza Windows można określić na kilka sposobów. Można zmienić wysokość i szerokość formularza programowo, ustawiając nową wartość dla <xref:System.Windows.Forms.Form.Size%2A> właściwości lub dostosować <xref:System.Windows.Forms.Control.Height%2A> lub <xref:System.Windows.Forms.Control.Width%2A> właściwości indywidualnie. Jeśli używasz programu Visual Studio, możesz zmienić rozmiar przy użyciu programu Windows Forms Designer. Zobacz też [porady: zmiana rozmiaru Windows Forms przy użyciu projektanta](https://msdn.microsoft.com/library/37k2zkwx\(v=vs.110\)).  
  
### <a name="to-resize-a-form-programmatically"></a>Aby programowo zmienić rozmiar formularza  
  
-   Określ rozmiar formularza w czasie wykonywania, ustawiając <xref:System.Windows.Forms.Form.Size%2A> właściwości formularza.  
  
     Poniższy przykład kodu pokazuje rozmiar formularza, równa 100 x 100 pikseli.  
  
    ```vb  
    Form1.Size = New System.Drawing.Size(100, 100)  
    ```  
  
    ```csharp  
    Form1.Size = new System.Drawing.Size(100, 100);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(100, 100);  
    ```  
  
### <a name="to-change-form-width-and-height-programmatically"></a>Aby programowo zmienić wysokość i szerokość formularza  
  
-   Po <xref:System.Windows.Forms.Form.Size%2A> jest zdefiniowany, zmienić za pomocą formularza wysokość lub szerokość <xref:System.Windows.Forms.Control.Width%2A> lub <xref:System.Windows.Forms.Control.Height%2A> właściwości.  
  
     Poniższy przykład kodu pokazuje szerokość formularza, wartość 300 pikseli od lewej krawędzi formularza, natomiast wysokość pozostają stałe.  
  
    ```vb  
    Form1.Width = 300  
    ```  
  
    ```csharp  
    Form1.Width = 300;  
    ```  
  
    ```cpp  
    Form1->Width = 300;  
    ```  
  
     —lub—  
  
     Zmiana <xref:System.Drawing.Size.Width%2A> lub <xref:System.Drawing.Size.Height%2A> , ustawiając <xref:System.Windows.Forms.Form.Size%2A> właściwości.  
  
     Jednakże, jak pokazano w poniższym przykładzie kodu, to podejście jest bardziej skomplikowane niż ustawienie tylko <xref:System.Windows.Forms.Control.Width%2A> lub <xref:System.Windows.Forms.Control.Height%2A> właściwości.  
  
    ```vb  
    Form1.Size = New Size(300, Form1.Size.Height)  
    ```  
  
    ```csharp  
    Form1.Size = new Size(300, Form1.Size.Height);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(300, Form1->Size.Height);  
    ```  
  
### <a name="to-change-form-size-by-increments-programmatically"></a>Aby zmienić rozmiar formularza krokami programowe  
  
-   Aby zwiększyć rozmiar formularza, ustaw <xref:System.Drawing.Size.Width%2A> i <xref:System.Drawing.Size.Height%2A> właściwości.  
  
     Poniższy przykład kodu pokazuje szerokość formularza ustawiona na 200 pikseli szerszy niż bieżące ustawienie.  
  
    ```vb  
    Form1.Width += 200  
    ```  
  
    ```csharp  
    Form1.Width += 200;  
    ```  
  
    ```cpp  
    Form1->Width += 200;  
    ```  
  
    > [!CAUTION]
    >  Zawsze używaj <xref:System.Drawing.Size.Height%2A> lub <xref:System.Drawing.Size.Width%2A> właściwości do zmiany wymiar formularza, chyba że ustawiasz szerokość i wysokość wymiarów w tym samym czasie, ustawiając <xref:System.Windows.Forms.Form.Size%2A> nową właściwość <xref:System.Drawing.Size> struktury. <xref:System.Windows.Forms.Form.Size%2A> Właściwość zwraca <xref:System.Drawing.Size> struktury, która jest typem wartości. Nowa wartość nie można przypisać do właściwości typu wartości. W związku z tym nie zostanie skompilowany w poniższym przykładzie kodu.  
  
    ```vb  
    ' NOTE: CODE WILL NOT COMPILE  
    Dim f As New Form()  
    f.Size.Width += 100  
    ```  
  
    ```csharp  
    // NOTE: CODE WILL NOT COMPILE  
    Form f = new Form();  
    f.Size.Width += 100;  
    ```  
  
    ```cpp  
    // NOTE: CODE WILL NOT COMPILE  
    Form^ f = gcnew Form();  
    f->Size->X += 100;  
    ```  
  
## <a name="see-also"></a>Zobacz też  
 [Wprowadzenie do formularzy Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [Rozszerzanie aplikacji Windows Forms](../../../docs/framework/winforms/advanced/index.md)
