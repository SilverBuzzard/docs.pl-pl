---
title: "Porady: grupowanie elementów w formancie ListView formularzy systemu Windows przy użyciu narzędzia Projektant"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 97c9dc3a12227d3c9bfd64c97be61e69b50d2bbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="48437-102">Porady: grupowanie elementów w formancie ListView formularzy systemu Windows przy użyciu narzędzia Projektant</span><span class="sxs-lookup"><span data-stu-id="48437-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="48437-103">Funkcji grupowania <xref:System.Windows.Forms.ListView> kontroli umożliwia wyświetlanie zestawów powiązanych elementów w grupach.</span><span class="sxs-lookup"><span data-stu-id="48437-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="48437-104">Grupy te są oddzielone na ekranie nagłówki poziomy grupy, które zawierają tytuły grupy.</span><span class="sxs-lookup"><span data-stu-id="48437-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="48437-105">Można użyć <xref:System.Windows.Forms.ListView> grupy, aby łatwiej nawigowanie po dużych list przez alfabetycznie, grupowanie elementów według daty lub logiczne grupowanie.</span><span class="sxs-lookup"><span data-stu-id="48437-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="48437-106">Na poniższej ilustracji przedstawiono niektóre zgrupowane elementy.</span><span class="sxs-lookup"><span data-stu-id="48437-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="48437-107">![Widok listy grup](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="48437-107">![ListView Groups](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span></span>  
  
 <span data-ttu-id="48437-108">Poniższa procedura wymaga **aplikacji systemu Windows** projekt zawierający formularz <xref:System.Windows.Forms.ListView> formantu.</span><span class="sxs-lookup"><span data-stu-id="48437-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="48437-109">Informacje o konfigurowaniu tych projektu, zobacz [jak: utworzyć projekt aplikacji systemu Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) i [porady: dodawanie formantów do formularzy systemu Windows](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="48437-109">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
 <span data-ttu-id="48437-110">Aby włączyć grupowanie, należy najpierw utworzyć co najmniej jeden <xref:System.Windows.Forms.ListViewGroup> obiektów w Projektancie lub programowo.</span><span class="sxs-lookup"><span data-stu-id="48437-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="48437-111">Po zdefiniowaniu grupy elementów można przypisać do niej.</span><span class="sxs-lookup"><span data-stu-id="48437-111">Once a group has been defined, you can assign items to it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48437-112"><xref:System.Windows.Forms.ListView>grupy są dostępne tylko na [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] podczas wywołania aplikacji <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="48437-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="48437-113">W starszych systemach operacyjnych dowolny kod odnoszących się do grupy nie ma wpływu i grup nie będą wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="48437-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="48437-114">Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="48437-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
>   
>  <span data-ttu-id="48437-115">Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania.</span><span class="sxs-lookup"><span data-stu-id="48437-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="48437-116">Aby zmienić ustawienia, wybierz **Import i eksport ustawień** na **narzędzia** menu.</span><span class="sxs-lookup"><span data-stu-id="48437-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="48437-117">Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="48437-117">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="48437-118">Aby dodać lub usunąć grupy w Projektancie</span><span class="sxs-lookup"><span data-stu-id="48437-118">To add or remove groups in the designer</span></span>  
  
1.  <span data-ttu-id="48437-119">W **właściwości** okna, kliknij przycisk **wielokropka** (![VisualStudioEllipsesButton — zrzut ekranu](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) znajdujący się obok <xref:System.Windows.Forms.ListView.Groups%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="48437-119">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>  
  
     <span data-ttu-id="48437-120">**Edytora kolekcji ListViewGroup** pojawi się.</span><span class="sxs-lookup"><span data-stu-id="48437-120">The **ListViewGroup Collection Editor** appears.</span></span>  
  
2.  <span data-ttu-id="48437-121">Aby dodać grupę, kliknij przycisk **Dodaj** przycisku.</span><span class="sxs-lookup"><span data-stu-id="48437-121">To add a group, click the **Add** button.</span></span> <span data-ttu-id="48437-122">Następnie można ustawić właściwości nowej grupy, takie jak <xref:System.Windows.Forms.ListViewGroup.Header%2A> i <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="48437-122">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="48437-123">Aby usunąć grupę, zaznacz go i kliknij przycisk **Usuń** przycisku.</span><span class="sxs-lookup"><span data-stu-id="48437-123">To remove a group, select it and click the **Remove** button.</span></span>  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="48437-124">Aby przypisać elementy w grupach w Projektancie</span><span class="sxs-lookup"><span data-stu-id="48437-124">To assign items to groups in the designer</span></span>  
  
1.  <span data-ttu-id="48437-125">W **właściwości** okna, kliknij przycisk **wielokropka** (![VisualStudioEllipsesButton — zrzut ekranu](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) znajdujący się obok <xref:System.Windows.Forms.ListView.Items%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="48437-125">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="48437-126">**Edytora kolekcji ListViewItem** pojawi się.</span><span class="sxs-lookup"><span data-stu-id="48437-126">The **ListViewItem Collection Editor** appears.</span></span>  
  
2.  <span data-ttu-id="48437-127">Aby dodać nowy element, kliknij przycisk **Dodaj** przycisku.</span><span class="sxs-lookup"><span data-stu-id="48437-127">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="48437-128">Następnie można ustawić właściwości nowy element, taki jak <xref:System.Windows.Forms.ListViewItem.Text%2A> i <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="48437-128">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
3.  <span data-ttu-id="48437-129">Wybierz <xref:System.Windows.Forms.ListViewItem.Group%2A> właściwości i wybierz grupę z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="48437-129">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48437-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="48437-130">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [<span data-ttu-id="48437-131">ListView — formant</span><span class="sxs-lookup"><span data-stu-id="48437-131">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="48437-132">Informacje o formancie ListView</span><span class="sxs-lookup"><span data-stu-id="48437-132">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="48437-133">Funkcje systemu Windows XP i formantów formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="48437-133">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="48437-134">Porady: Dodawanie i usuwanie elementów za pomocą systemu Windows formantu ListView formularzy</span><span class="sxs-lookup"><span data-stu-id="48437-134">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)