---
title: 'Porady: powiązanie formantu formularzy systemu Windows z typem'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: fdf2134d487787404cccbde1ba0f8c95cb6a4a3d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503908"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a>Porady: powiązanie formantu formularzy systemu Windows z typem
Podczas tworzenia formantów, które współdziałają z danymi będą czasami jest konieczne do wiązania kontrolki typu, a nie obiekt. Sytuacja ta pojawia się szczególnie w czasie projektowania, gdy dane nie mogą być dostępne, ale formantów powiązanych z danymi potrzebują do wyświetlania informacji z interfejsu publicznego typu. Na przykład może związać <xref:System.Windows.Forms.DataGridView> sterowania do obiektu udostępnianych przez usługi sieci Web i chcesz <xref:System.Windows.Forms.DataGridView> kontrolki etykiety kolumn w czasie projektowania z elementem członkowskim nazwy typu niestandardowego.  
  
 Można łatwo powiązać formant do typu z <xref:System.Windows.Forms.BindingSource> składnika.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu pokazuje, jak powiązać <xref:System.Windows.Forms.DataGridView> kontrolki typu niestandardowego za pomocą <xref:System.Windows.Forms.BindingSource> składnika. Po uruchomieniu tego przykładu, można zauważyć <xref:System.Windows.Forms.DataGridView> etykietą kolumn, które odzwierciedlają właściwości `Customer` obiektu, zanim kontrolka jest wypełniana danymi. W przykładzie przedstawiono przycisk Dodaj klienta, aby dodać dane do <xref:System.Windows.Forms.DataGridView> kontroli. Po kliknięciu przycisku Nowy `Customer` obiekt jest dodawany do <xref:System.Windows.Forms.BindingSource>. W rzeczywistych scenariuszy dane mogą uzyskać przez wywołanie usługi sieci Web lub innego źródła danych.  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   Odwołania do zestawów System i przestrzeń nazw System.Windows.Forms.  
  
 Aby dowiedzieć się, jak tworzyć aplikacje w tym przykładzie z wiersza polecenia dla języka Visual Basic lub Visual C#, zobacz [tworzenie z wiersza polecenia](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) lub [wiersza polecenia tworzenia przy użyciu csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Można także utworzyć tego przykładu w programie Visual Studio, wklejając kod do nowego projektu.  Zobacz też [porady: kompilowanie i uruchamianie pełną Windows Forms kodu przykładzie przy użyciu programu Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [BindingSource, składnik](../../../../docs/framework/winforms/controls/bindingsource-component.md)
