---
title: "Wybór i używanie schowka za pomocą składnika DataGridView formularzy systemu Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 888fb1cbd960c006dc2705a2b0bd66c038a926f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="cfca6-102">Wybór i używanie schowka za pomocą składnika DataGridView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="cfca6-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cfca6-103">`DataGridView` Kontroli zapewnia różne opcje dotyczące konfigurowania, jak użytkownicy mogą wybrać komórek, wierszy i kolumn.</span><span class="sxs-lookup"><span data-stu-id="cfca6-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="cfca6-104">Na przykład można włączyć wybór jednego lub wielu, Zaznaczanie całego wierszy lub kolumn, gdy użytkownik kliknie komórek lub Zaznaczanie całego wierszy lub kolumn tylko wtedy, gdy użytkownik kliknie ich nagłówki, co umożliwia także zaznaczenie komórki.</span><span class="sxs-lookup"><span data-stu-id="cfca6-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="cfca6-105">Jeśli chcesz podać interfejsu użytkownika dla zaznaczenia, można wyłączyć zwykłej wybór i programowo obsłużyć wszystkie zaznaczenia.</span><span class="sxs-lookup"><span data-stu-id="cfca6-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="cfca6-106">Ponadto można umożliwić użytkownikom kopiowania wybranych wartości do Schowka.</span><span class="sxs-lookup"><span data-stu-id="cfca6-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfca6-107">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="cfca6-107">In This Section</span></span>  
 [<span data-ttu-id="cfca6-108">Tryby wyboru w formancie DataGridView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="cfca6-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="cfca6-109">Zawiera opis opcji użytkownika i wybór programowy w formancie.</span><span class="sxs-lookup"><span data-stu-id="cfca6-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="cfca6-110">Porady: Ustawianie trybu zaznaczania formantu DataGridView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="cfca6-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="cfca6-111">Opisuje sposób konfigurowania formant wyboru pojedynczy wiersz po kliknięciu komórki.</span><span class="sxs-lookup"><span data-stu-id="cfca6-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="cfca6-112">Porady: pobieranie wybranych komórek, wierszy i kolumn w formancie DataGridView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="cfca6-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="cfca6-113">Opisuje sposób pracy z wybranymi kolekcjami komórek, wierszy i kolumn.</span><span class="sxs-lookup"><span data-stu-id="cfca6-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="cfca6-114">Porady: umożliwianie użytkownikom kopiowania wielu komórek do Schowka systemu Windows do formantu DataGridView formularzy</span><span class="sxs-lookup"><span data-stu-id="cfca6-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="cfca6-115">Opisuje sposób włączania obsługi Schowka w formancie.</span><span class="sxs-lookup"><span data-stu-id="cfca6-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cfca6-116">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="cfca6-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="cfca6-117">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridView> formantu.</span><span class="sxs-lookup"><span data-stu-id="cfca6-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="cfca6-118">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="cfca6-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="cfca6-119">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="cfca6-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="cfca6-120">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> klasy.</span><span class="sxs-lookup"><span data-stu-id="cfca6-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="cfca6-121">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> klasy.</span><span class="sxs-lookup"><span data-stu-id="cfca6-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="cfca6-122">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> klasy.</span><span class="sxs-lookup"><span data-stu-id="cfca6-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfca6-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cfca6-123">See Also</span></span>  
 [<span data-ttu-id="cfca6-124">DataGridView — formant</span><span class="sxs-lookup"><span data-stu-id="cfca6-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="cfca6-125">Domyślna obsługa w formancie DataGridView formularzy systemu Windows myszy i klawiatury</span><span class="sxs-lookup"><span data-stu-id="cfca6-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)