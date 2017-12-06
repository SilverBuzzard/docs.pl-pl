---
title: "Porady: zmienianie wyglądu składnika TabControl formularzy systemu Windows"
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
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b244930f0837d3b1d548e0f7a8c77dd80e1ce039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="99bf8-102">Porady: zmienianie wyglądu składnika TabControl formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="99bf8-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="99bf8-103">Można zmienić wygląd kart w formularzach systemu Windows za pomocą właściwości <xref:System.Windows.Forms.TabControl> i <xref:System.Windows.Forms.TabPage> obiektów, które składają się na poszczególnych kartach w formancie.</span><span class="sxs-lookup"><span data-stu-id="99bf8-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="99bf8-104">Przez ustawienie tych właściwości, można wyświetlanie obrazów na kartach, wyświetlić karty w pionie zamiast w poziomie, wyświetlane wiele wierszy kart i włączyć lub wyłączyć karty programowo.</span><span class="sxs-lookup"><span data-stu-id="99bf8-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="99bf8-105">Aby wyświetlić ikony na części etykiety karty</span><span class="sxs-lookup"><span data-stu-id="99bf8-105">To display an icon on the label part of a tab</span></span>  
  
1.  <span data-ttu-id="99bf8-106">Dodaj <xref:System.Windows.Forms.ImageList> sterowania do formularza.</span><span class="sxs-lookup"><span data-stu-id="99bf8-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2.  <span data-ttu-id="99bf8-107">Dodawanie obrazów do listy obrazów.</span><span class="sxs-lookup"><span data-stu-id="99bf8-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="99bf8-108">Aby uzyskać więcej informacji na temat list obrazów, zobacz [składnika ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) i [porady: Dodawanie lub usuwanie obrazów za pomocą składnika ImageList formularzy systemu Windows](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="99bf8-108">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3.  <span data-ttu-id="99bf8-109">Ustaw <xref:System.Windows.Forms.TabControl.ImageList%2A> właściwość <xref:System.Windows.Forms.TabControl> do <xref:System.Windows.Forms.ImageList> formantu.</span><span class="sxs-lookup"><span data-stu-id="99bf8-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4.  <span data-ttu-id="99bf8-110">Ustaw <xref:System.Windows.Forms.TabPage.ImageIndex%2A> właściwość <xref:System.Windows.Forms.TabPage> do indeksu odpowiedniego obrazu na liście.</span><span class="sxs-lookup"><span data-stu-id="99bf8-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="99bf8-111">Aby utworzyć wiele wierszy kart</span><span class="sxs-lookup"><span data-stu-id="99bf8-111">To create multiple rows of tabs</span></span>  
  
1.  <span data-ttu-id="99bf8-112">Dodaj liczba kart, które mają.</span><span class="sxs-lookup"><span data-stu-id="99bf8-112">Add the number of tab pages you want.</span></span>  
  
2.  <span data-ttu-id="99bf8-113">Ustaw <xref:System.Windows.Forms.TabControl.Multiline%2A> właściwość <xref:System.Windows.Forms.TabControl> do `true`.</span><span class="sxs-lookup"><span data-stu-id="99bf8-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3.  <span data-ttu-id="99bf8-114">Jeśli karty nie są już wyświetlane w wielu wierszach, ustaw <xref:System.Windows.Forms.Control.Width%2A> właściwość <xref:System.Windows.Forms.TabControl> być mniejsza niż wszystkich kart.</span><span class="sxs-lookup"><span data-stu-id="99bf8-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="99bf8-115">Aby zorganizować karty boku formantu</span><span class="sxs-lookup"><span data-stu-id="99bf8-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="99bf8-116">Ustaw <xref:System.Windows.Forms.TabControl.Alignment%2A> właściwość <xref:System.Windows.Forms.TabControl> do <xref:System.Windows.Forms.TabAlignment.Left> lub <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="99bf8-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="99bf8-117">Aby programowo włączyć lub wyłączyć wszystkie formanty na karcie</span><span class="sxs-lookup"><span data-stu-id="99bf8-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1.  <span data-ttu-id="99bf8-118">Ustaw <xref:System.Windows.Forms.TabPage.Enabled%2A> właściwość <xref:System.Windows.Forms.TabPage> do `true` lub `false`.</span><span class="sxs-lookup"><span data-stu-id="99bf8-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="99bf8-119">Aby wyświetlić karty jako przyciski</span><span class="sxs-lookup"><span data-stu-id="99bf8-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="99bf8-120">Ustaw <xref:System.Windows.Forms.TabControl.Appearance%2A> właściwość <xref:System.Windows.Forms.TabControl> do <xref:System.Windows.Forms.TabAppearance.Buttons> lub <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span><span class="sxs-lookup"><span data-stu-id="99bf8-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99bf8-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="99bf8-121">See Also</span></span>  
 [<span data-ttu-id="99bf8-122">TabControl — formant</span><span class="sxs-lookup"><span data-stu-id="99bf8-122">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="99bf8-123">Informacje o formancie TabControl</span><span class="sxs-lookup"><span data-stu-id="99bf8-123">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="99bf8-124">Porady: Dodawanie formantu do strony karty</span><span class="sxs-lookup"><span data-stu-id="99bf8-124">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="99bf8-125">Porady: wyłączanie kart</span><span class="sxs-lookup"><span data-stu-id="99bf8-125">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="99bf8-126">Porady: Dodawanie i usuwanie kart za pomocą formantu TabControl formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="99bf8-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)