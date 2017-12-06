---
title: Style i szablony menu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e007ae09e57353446feb13b3693e62c985f522d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="287ae-102">Style i szablony menu</span><span class="sxs-lookup"><span data-stu-id="287ae-102">Menu Styles and Templates</span></span>
<span data-ttu-id="287ae-103">W tym temacie opisano, style i szablonów dla <xref:System.Windows.Controls.Menu> formantu.</span><span class="sxs-lookup"><span data-stu-id="287ae-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="287ae-104">Można zmodyfikować domyślne <xref:System.Windows.Controls.ControlTemplate> umożliwiają unikatowego wyglądu formantu.</span><span class="sxs-lookup"><span data-stu-id="287ae-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="287ae-105">Aby uzyskać więcej informacji, zobacz [Dostosowywanie wyglądu formant tworząc ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="287ae-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="287ae-106">Elementy menu</span><span class="sxs-lookup"><span data-stu-id="287ae-106">Menu Parts</span></span>  
 <span data-ttu-id="287ae-107"><xref:System.Windows.Controls.Menu> Formant nie ma żadnych części o nazwie.</span><span class="sxs-lookup"><span data-stu-id="287ae-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="287ae-108">Po utworzeniu <xref:System.Windows.Controls.ControlTemplate> dla <xref:System.Windows.Controls.Menu>, szablon może zawierać <xref:System.Windows.Controls.ItemsPresenter> w <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="287ae-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="287ae-109">( <xref:System.Windows.Controls.ItemsPresenter> Wyświetla każdy element <xref:System.Windows.Controls.Menu>; <xref:System.Windows.Controls.ScrollViewer> włącza przewijanie w kontrolce).</span><span class="sxs-lookup"><span data-stu-id="287ae-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="287ae-110">Jeśli <xref:System.Windows.Controls.ItemsPresenter> nie jest bezpośrednim elementem podrzędnym elementu <xref:System.Windows.Controls.ScrollViewer>, musisz podać <xref:System.Windows.Controls.ItemsPresenter> nazwę, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="287ae-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="287ae-111">Stany menu</span><span class="sxs-lookup"><span data-stu-id="287ae-111">Menu States</span></span>  
 <span data-ttu-id="287ae-112">W poniższej tabeli wymieniono stany wizualne dla <xref:System.Windows.Controls.Menu> formantu.</span><span class="sxs-lookup"><span data-stu-id="287ae-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="287ae-113">Nazwa stanu wizualnego</span><span class="sxs-lookup"><span data-stu-id="287ae-113">VisualState Name</span></span>|<span data-ttu-id="287ae-114">Nazwa VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="287ae-114">VisualStateGroup Name</span></span>|<span data-ttu-id="287ae-115">Opis</span><span class="sxs-lookup"><span data-stu-id="287ae-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="287ae-116">Prawidłowe</span><span class="sxs-lookup"><span data-stu-id="287ae-116">Valid</span></span>|<span data-ttu-id="287ae-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="287ae-117">ValidationStates</span></span>|<span data-ttu-id="287ae-118">Używa kontrolki <xref:System.Windows.Controls.Validation> klasy i <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> jest dołączona właściwość `false`.</span><span class="sxs-lookup"><span data-stu-id="287ae-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="287ae-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="287ae-119">InvalidFocused</span></span>|<span data-ttu-id="287ae-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="287ae-120">ValidationStates</span></span>|<span data-ttu-id="287ae-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant ma fokus.</span><span class="sxs-lookup"><span data-stu-id="287ae-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="287ae-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="287ae-122">InvalidUnfocused</span></span>|<span data-ttu-id="287ae-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="287ae-123">ValidationStates</span></span>|<span data-ttu-id="287ae-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant nie ma fokusa.</span><span class="sxs-lookup"><span data-stu-id="287ae-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="287ae-125">Elementy MenuItem</span><span class="sxs-lookup"><span data-stu-id="287ae-125">MenuItem Parts</span></span>  
 <span data-ttu-id="287ae-126">W poniższej tabeli wymieniono nazwanego części dla <xref:System.Windows.Controls.Menu> formantu.</span><span class="sxs-lookup"><span data-stu-id="287ae-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="287ae-127">Część</span><span class="sxs-lookup"><span data-stu-id="287ae-127">Part</span></span>|<span data-ttu-id="287ae-128">Typ</span><span class="sxs-lookup"><span data-stu-id="287ae-128">Type</span></span>|<span data-ttu-id="287ae-129">Opis</span><span class="sxs-lookup"><span data-stu-id="287ae-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="287ae-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="287ae-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="287ae-131">Obszar podmenu.</span><span class="sxs-lookup"><span data-stu-id="287ae-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="287ae-132">Po utworzeniu <xref:System.Windows.Controls.ControlTemplate> dla <xref:System.Windows.Controls.MenuItem>, szablon może zawierać <xref:System.Windows.Controls.ItemsPresenter> w <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="287ae-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="287ae-133">( <xref:System.Windows.Controls.ItemsPresenter> Wyświetla każdy element <xref:System.Windows.Controls.MenuItem>; <xref:System.Windows.Controls.ScrollViewer> włącza przewijanie w kontrolce).</span><span class="sxs-lookup"><span data-stu-id="287ae-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="287ae-134">Jeśli <xref:System.Windows.Controls.ItemsPresenter> nie jest bezpośrednim elementem podrzędnym elementu <xref:System.Windows.Controls.ScrollViewer>, musisz podać <xref:System.Windows.Controls.ItemsPresenter> nazwę, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="287ae-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="287ae-135">Stany MenuItem</span><span class="sxs-lookup"><span data-stu-id="287ae-135">MenuItem States</span></span>  
 <span data-ttu-id="287ae-136">W poniższej tabeli wymieniono stany wizualne dla <xref:System.Windows.Controls.MenuItem> formantu.</span><span class="sxs-lookup"><span data-stu-id="287ae-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="287ae-137">Nazwa stanu wizualnego</span><span class="sxs-lookup"><span data-stu-id="287ae-137">VisualState Name</span></span>|<span data-ttu-id="287ae-138">Nazwa VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="287ae-138">VisualStateGroup Name</span></span>|<span data-ttu-id="287ae-139">Opis</span><span class="sxs-lookup"><span data-stu-id="287ae-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="287ae-140">Prawidłowe</span><span class="sxs-lookup"><span data-stu-id="287ae-140">Valid</span></span>|<span data-ttu-id="287ae-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="287ae-141">ValidationStates</span></span>|<span data-ttu-id="287ae-142">Używa kontrolki <xref:System.Windows.Controls.Validation> klasy i <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> jest dołączona właściwość `false`.</span><span class="sxs-lookup"><span data-stu-id="287ae-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="287ae-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="287ae-143">InvalidFocused</span></span>|<span data-ttu-id="287ae-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="287ae-144">ValidationStates</span></span>|<span data-ttu-id="287ae-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant ma fokus.</span><span class="sxs-lookup"><span data-stu-id="287ae-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="287ae-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="287ae-146">InvalidUnfocused</span></span>|<span data-ttu-id="287ae-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="287ae-147">ValidationStates</span></span>|<span data-ttu-id="287ae-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant nie ma fokusa.</span><span class="sxs-lookup"><span data-stu-id="287ae-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="287ae-149">Przykład ControlTemplate elementu MenuItem i menu</span><span class="sxs-lookup"><span data-stu-id="287ae-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="287ae-150">Poniższy przykład przedstawia sposób definiowania <xref:System.Windows.Controls.ControlTemplate> dla <xref:System.Windows.Controls.Menu> formantu.</span><span class="sxs-lookup"><span data-stu-id="287ae-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="287ae-151">Poniższy przykład przedstawia sposób definiowania <xref:System.Windows.Controls.ControlTemplate> dla <xref:System.Windows.Controls.MenuItem> formantu.</span><span class="sxs-lookup"><span data-stu-id="287ae-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="287ae-152">W poniższym przykładzie zdefiniowano `MenuScrollViewer`, która jest używana w poprzednim przykładzie.</span><span class="sxs-lookup"><span data-stu-id="287ae-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="287ae-153"><xref:System.Windows.Controls.ControlTemplate> Przykładach użyto co najmniej jeden z następujących zasobów.</span><span class="sxs-lookup"><span data-stu-id="287ae-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="287ae-154">Pełny przykład, zobacz [style próbki ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="287ae-154">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287ae-155">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="287ae-155">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="287ae-156">Style formantu i szablony</span><span class="sxs-lookup"><span data-stu-id="287ae-156">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="287ae-157">Dostosowywanie formantu</span><span class="sxs-lookup"><span data-stu-id="287ae-157">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="287ae-158">Style i tworzenia szablonów</span><span class="sxs-lookup"><span data-stu-id="287ae-158">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="287ae-159">Dostosowywanie wyglądu formant tworząc ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="287ae-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)