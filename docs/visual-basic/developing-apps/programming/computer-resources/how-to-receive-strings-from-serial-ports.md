---
title: 'Porady: odbieranie ciągów z portów seryjnych w Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
ms.openlocfilehash: 9d71a725aeea684e27479a5d55728151426c4a52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588950"
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a>Porady: odbieranie ciągów z portów seryjnych w Visual Basic
W tym temacie opisano sposób użycia `My.Computer.Ports` na odbieranie ciągów z portów szeregowych komputera w języku Visual Basic.  
  
### <a name="to-receive-strings-from-the-serial-port"></a>Aby odbieranie ciągów z portu szeregowego  
  
1.  Inicjuje zwracany ciąg.  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]  
  
2.  Ustal, które portu szeregowego należy podać ciągi. W tym przykładzie założono jest `COM1`.  
  
3.  Użyj `My.Computer.Ports.OpenSerialPort` metodę, aby uzyskać odwołania do portu. Aby uzyskać więcej informacji, zobacz <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     `Try...Catch...Finally` Bloku umożliwia zamknięcie portu szeregowego, nawet jeśli generuje wyjątek. Cały kod, który manipuluje portu szeregowego powinny być wyświetlane w tym bloku.  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]  
  
4.  Utwórz `Do` pętli do odczytywania wierszy tekstu, dopóki nie są dostępne nie więcej wierszy.  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]  
  
5.  Użyj <xref:System.IO.Ports.SerialPort.ReadLine> metody można odczytać następnego wiersza dostępne tekstu z portu szeregowego.  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]  
  
6.  Użyj `If` instrukcji, aby ustalić, czy <xref:System.IO.Ports.SerialPort.ReadLine> metoda zwraca `Nothing` (co oznacza, że nie ma więcej tekstu jest dostępna). Jeśli aplikacja zwracać `Nothing`, zamknąć `Do` pętli.  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]  
  
7.  Dodaj `Else` za pomocą bloku `If` instrukcji do obsługi w przypadku, jeśli ciąg jest rzeczywiście do odczytu. Blok dołącza ciąg z portu szeregowego zwracany ciąg.  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]  
  
8.  Zwraca ciąg.  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]  
  
## <a name="example"></a>Przykład  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]  
  
 W tym przykładzie kodu jest również dostępny jako fragmentu kodu IntelliSense. Selektor wstawek kodu, znajduje się się w **sieć i łączność**. Aby uzyskać więcej informacji, zobacz [wstawki kodu](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 W tym przykładzie założono komputer korzysta z `COM1`.  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 W tym przykładzie założono komputer korzysta z `COM1`. Zapewnienia większej elastyczności kod powinna zezwalać użytkownikowi na wybranie wybranego portu szeregowego z listy dostępnych portów. Aby uzyskać więcej informacji, zobacz [porady: portów seryjnych dostępne Pokaż](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 W tym przykładzie użyto `Try...Catch...Finally` bloku, aby upewnić się, że aplikacja zamyka port i aby wykryć żadnych wyjątków przekroczenia limitu czasu. Aby uzyskać więcej informacji, zobacz [spróbuj... CATCH... Instrukcji finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>  
 [Instrukcje: modemy dostępowe powiązane z portami seryjnymi](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)  
 [Instrukcje: wysyłanie ciągów do portów seryjnych](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)  
 [Instrukcje: wyświetlanie dostępnych portów seryjnych](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
