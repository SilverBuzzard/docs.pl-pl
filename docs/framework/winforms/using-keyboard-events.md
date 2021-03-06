---
title: Używanie zdarzeń klawiatury
ms.date: 03/30/2017
helpviewer_keywords:
- KeyPress event [Windows Forms]
- keyboards [Windows Forms], keyboard events
- KeyUp event
- KeyDown event
- keyboard events
- events [Windows Forms], keyboard
ms.assetid: d3f3e14b-a459-4ee6-9875-8957e34f8ee9
ms.openlocfilehash: 2c6059e5d0957de09dd2c4832573c784935eb510
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786430"
---
# <a name="using-keyboard-events"></a>Używanie zdarzeń klawiatury
Większość programów Windows Forms przetwarzać dane wejściowe z klawiatury dzięki obsłudze zdarzeń klawiatury. Ten temat zawiera omówienie zdarzenia klawiatury, w tym informacji o tym, kiedy należy używać każdego zdarzenia i dane, która jest dostarczana dla każdego zdarzenia.  Zobacz też [Przegląd obsługi zdarzeń (Windows Forms)](https://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [Przegląd zdarzeń (systemu Windows Windows Forms)](https://msdn.microsoft.com/library/1h12f09z\(v=vs.110\)).  
  
## <a name="keyboard-events"></a>Zdarzenia klawiatury  
 Formularze Windows oferuje dwa zdarzenia, które występują, gdy użytkownik naciśnie klawisz i jedno zdarzenie, kiedy użytkownik zwolni klawisz:  
  
-   <xref:System.Windows.Forms.Control.KeyDown> Po wystąpieniu zdarzenia  
  
-   <xref:System.Windows.Forms.Control.KeyPress> Zdarzenie, które mogą wystąpić wiele razy, gdy użytkownik przechowuje szczegółów tego samego klucza.  
  
-   <xref:System.Windows.Forms.Control.KeyUp> Zdarzenie występuje, gdy po użytkownik zwolni klawisz.  
  
 Po naciśnięciu klawisza formularzy Windows określa, które zdarzenie, aby zgłosić oparte na tego, czy komunikatu z klawiatury określa znakowy klucz lub klucz fizycznych. Aby uzyskać więcej informacji o znak i kluczach fizycznych, zobacz [sposób działania wejście klawiatury](../../../docs/framework/winforms/how-keyboard-input-works.md).  
  
 W poniższej tabeli opisano zdarzenia klawiatury trzy.  
  
|Zdarzenia klawiatury|Opis|wyniki|  
|--------------------|-----------------|-------------|  
|<xref:System.Windows.Forms.Control.KeyDown>|To zdarzenie jest wywoływane, gdy użytkownik naciśnie klawisz fizycznych.|Obsługa <xref:System.Windows.Forms.Control.KeyDown> odbiera:<br /><br /> <ul><li>A <xref:System.Windows.Forms.KeyEventArgs> parametr, który zapewnia <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> właściwości (który określa przycisku klawiatury fizycznych).</li><li><xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> Właściwości (SHIFT, CTRL lub ALT).</li><li><xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> Właściwości, (które łączy klucza kodu i modyfikator). <xref:System.Windows.Forms.KeyEventArgs> Udostępnia również parametr:<br /><br /> <ul><li><xref:System.Windows.Forms.KeyEventArgs.Handled%2A> Właściwości można ustawić, aby uniemożliwić odbierania klucz podstawowy kontroli.</li><li><xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> Właściwość, która może służyć do pomijania <xref:System.Windows.Forms.Control.KeyPress> i <xref:System.Windows.Forms.Control.KeyUp> zdarzenia dla tego naciśnięcia klawisza.</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyPress>|To zdarzenie jest zgłaszane w przypadku klucza lub kluczy naciśnięty wynik w znaku. Na przykład użytkownik naciśnie klawisz SHIFT i małej litery "" klucze, które powoduje "" znak wielkiej litery.|<xref:System.Windows.Forms.Control.KeyPress> jest wywoływane po wykonaniu <xref:System.Windows.Forms.Control.KeyDown>.<br /><br /> <ul><li>Obsługa <xref:System.Windows.Forms.Control.KeyPress> odbiera:</li><li>A <xref:System.Windows.Forms.KeyPressEventArgs> parametr, który zawiera kod znaku klawisza, który został naciśnięty. Ten kod znaku jest unikatowy dla każdej kombinacji znaków klucza i klawisz modyfikujący.<br /><br />     Na przykład generuje "" klucz:<br /><br /> <ul><li>Kod znaku 65, jeśli jest wciśnięty klawisz SHIFT</li><li>Klawisz CAPS LOCK, 97, jeśli jest wciśnięty samodzielnie, lub</li><li>Do 1, jeśli jest wciśnięty klawisz CTRL.</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyUp>|To zdarzenie jest wywoływane, gdy użytkownik zwolni klawisz fizycznych.|Obsługa <xref:System.Windows.Forms.Control.KeyUp> odbiera:<br /><br /> <ul><li>A <xref:System.Windows.Forms.KeyEventArgs> parametru:<br /><br /> <ul><li>Co zapewnia <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> właściwości (który określa przycisku klawiatury fizycznych).</li><li><xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> Właściwości (SHIFT, CTRL lub ALT).</li><li><xref:System.Globalization.SortKey.KeyData%2A> Właściwości, (które łączy klucza kodu i modyfikator).</li></ul></li></ul>|  
  
## <a name="see-also"></a>Zobacz też  
 [Wprowadzanie z klawiatury w aplikacjach Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Działanie wprowadzania z klawiatury](../../../docs/framework/winforms/how-keyboard-input-works.md)  
 [Wprowadzanie za pomocą myszy w aplikacjach Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
