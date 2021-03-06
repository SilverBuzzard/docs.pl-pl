---
title: 'Porady: testowanie zachowania UserControl w czasie wykonywania'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 40ec136a86b52dcb007d15d5a2917212745961f2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512212"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Porady: testowanie zachowania UserControl w czasie wykonywania
Podczas opracowywania <xref:System.Windows.Forms.UserControl>, należy przetestować jej zachowanie w czasie wykonywania. Można utworzyć projekt oddzielną aplikację z systemem Windows i umieść swój formant na formularzu testu, ale ta procedura jest wygodne. Szybciej i łatwiej metodą jest użycie **UserControl — kontener testowy** dostarczane przez program Visual Studio. Ten kontener testowy uruchamia się bezpośrednio z Twojego Projekt Biblioteka formantów Windows.  
  
> [!IMPORTANT]
>  Dla kontenera testów, które można załadować usługi <xref:System.Windows.Forms.UserControl>, kontrolka musi mieć co najmniej jeden konstruktor publiczny.  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
> [!NOTE]
>  Kontrolki języka Visual C++ nie można przetestować za pomocą **UserControl — kontener testowy**.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>Aby testowanie zachowania UserControl w czasie wykonywania  
  
1.  Utwórz projekt Biblioteka formantów Windows o nazwie **TestContainerExample**. Aby uzyskać więcej informacji, zobacz [szablon biblioteki kontrolki Windows](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  W **Windows Forms Designer**, przeciągnij <xref:System.Windows.Forms.Label> z kontrolować **przybornika** na powierzchnię projektowania formantu.  
  
3.  Naciśnij klawisz F5, aby skompilować projekt i uruchomić **UserControl — kontener testowy**. Kontener testu, który jest wyświetlany za pomocą usługi <xref:System.Windows.Forms.UserControl> w **(wersja zapoznawcza)** okienka.  
  
4.  Wybierz <xref:System.Windows.Forms.Control.BackColor%2A> właściwości wyświetlane w <xref:System.Windows.Forms.PropertyGrid> kontroli po prawej stronie **Podgląd** okienka. Zmień jej wartość na `ControlDark`. Sprawdź, czy kontrolka zmienia kolor ciemniejszego. Spróbuj zmienić wartości innych właściwości i obserwuj wpływ na Twoją kontrolą.  
  
5.  Kliknij przycisk **kontrolki użytkownika wypełnienia dokowania** poniższe pole wyboru **Podgląd** okienka. Sprawdź, czy zmieni się rozmiar kontrolki do wypełnienia okienka. Zmień rozmiar kontenera testu i obserwować zmiany rozmiaru za pomocą okienka kontrolki.  
  
6.  Zamknij kontener testu.  
  
7.  Dodaj inną kontrolkę użytkownika do **TestContainerExample** projektu. Aby uzyskać więcej informacji, zobacz [NIB: instrukcje: Dodawanie istniejących elementów do projektu](https://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
8.  W **Windows Forms Designer**, przeciągnij <xref:System.Windows.Forms.Button> z kontrolować **przybornika** na powierzchnię projektowania formantu.  
  
9. Naciśnij klawisz F5, aby skompilować projekt i uruchomić kontener testu.  
  
10. Kliknij przycisk **wybierz kontrolkę użytkownika** <xref:System.Windows.Forms.ComboBox> Aby przełączyć się między formantami dwóch użytkowników.  
  
## <a name="testing-user-controls-from-another-project"></a>Testowanie kontrolki użytkownika z innego projektu  
 Możesz przetestować kontrolki użytkownika z innych projektów w kontenerze testów bieżącego projektu.  
  
#### <a name="to-test-user-controls-from-another-project"></a>Aby przetestować kontrolki użytkownika z innego projektu  
  
1.  Utwórz projekt Biblioteka formantów Windows o nazwie **TestContainerExample2**. Aby uzyskać więcej informacji, zobacz [szablon biblioteki kontrolki Windows](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  W **Windows Forms Designer**, przeciągnij <xref:System.Windows.Forms.RadioButton> z kontrolować **przybornika** na powierzchnię projektowania formantu.  
  
3.  Naciśnij klawisz F5, aby skompilować projekt i uruchomić kontener testu. Kontener testu, który jest wyświetlany za pomocą usługi <xref:System.Windows.Forms.UserControl> w **(wersja zapoznawcza)** okienka.  
  
4.  Kliknij przycisk **obciążenia** przycisku.  
  
5.  W **Otwórz** okno dialogowe, przejdź do **TestContainerExample**.dll, która utworzoną w poprzedniej procedurze. Wybierz **TestContainerExample**.dll i kliknij przycisk **Otwórz** przycisk, aby załadować kontrolki użytkownika  
  
6.  Użyj **wybierz kontrolkę użytkownika** <xref:System.Windows.Forms.ComboBox> Aby przełączyć się między formantami dwóch użytkowników z **TestContainerExample** projektu.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.UserControl>  
 [Instrukcje: tworzenie kontrolek złożonych](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [Przewodnik: tworzenie kontrolki złożonej za pomocą języka Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [Przewodnik: tworzenie kontrolki złożonej za pomocą języka Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [Projektant kontrolki użytkownika](https://msdn.microsoft.com/library/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
