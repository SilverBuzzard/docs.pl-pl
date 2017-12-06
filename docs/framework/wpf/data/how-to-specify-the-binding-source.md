---
title: "Jak określić źródło wiążące"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 55d47757-2648-4a52-987f-b767953f168c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 05f77e8939b9b81a9e3861df6a44bc3585a0a504
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-binding-source"></a><span data-ttu-id="84991-102">Jak określić źródło wiążące</span><span class="sxs-lookup"><span data-stu-id="84991-102">How to: Specify the Binding Source</span></span>
<span data-ttu-id="84991-103">W powiązaniu danych powiązania obiektu źródłowego odwołuje się do obiektu, do którego można uzyskać danych.</span><span class="sxs-lookup"><span data-stu-id="84991-103">In data binding, the binding source object refers to the object you obtain your data from.</span></span> <span data-ttu-id="84991-104">W tym temacie opisano różne sposoby określania źródła powiązania.</span><span class="sxs-lookup"><span data-stu-id="84991-104">This topic describes the different ways of specifying the binding source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84991-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="84991-105">Example</span></span>  
 <span data-ttu-id="84991-106">Wspólne źródło są wiązane kilka właściwości, chcesz użyć `DataContext` właściwość, która umożliwia dogodny do ustalenia zakresu, w którym wszystkie właściwości powiązanych z danymi dziedziczą wspólne źródło.</span><span class="sxs-lookup"><span data-stu-id="84991-106">If you are binding several properties to a common source, you want to use the `DataContext` property, which provides a convenient way to establish a scope within which all data-bound properties inherit a common source.</span></span>  
  
 <span data-ttu-id="84991-107">W poniższym przykładzie kontekst danych jest określana w elemencie głównym aplikacji.</span><span class="sxs-lookup"><span data-stu-id="84991-107">In the following example, the data context is established on the root element of the application.</span></span> <span data-ttu-id="84991-108">Dzięki temu wszystkie elementy podrzędne dziedziczenia tego kontekstu danych.</span><span class="sxs-lookup"><span data-stu-id="84991-108">This allows all child elements to inherit that data context.</span></span> <span data-ttu-id="84991-109">Dane dla powiązania pochodzi z klasy danych niestandardowych, `NetIncome`, do których odwołuje się bezpośrednio za pomocą mapowania i podany klucz zasobów `incomeDataSource`.</span><span class="sxs-lookup"><span data-stu-id="84991-109">Data for the binding comes from a custom data class, `NetIncome`, referenced directly through a mapping and given the resource key of `incomeDataSource`.</span></span>  
  
 [!code-xaml[DirectionalBinding#DataContext1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext1)]  
[!code-xaml[DirectionalBinding#DataContext2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext2)]  
  
 <span data-ttu-id="84991-110">W poniższym przykładzie przedstawiono definicję `NetIncome` klasy.</span><span class="sxs-lookup"><span data-stu-id="84991-110">The following example shows the definition of the `NetIncome` class.</span></span>  
  
 [!code-csharp[DirectionalBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/billsdata.cs#dataobject)]
 [!code-vb[DirectionalBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DirectionalBinding/VisualBasic/NetIncome.vb#dataobject)]  
  
> [!NOTE]
>  <span data-ttu-id="84991-111">Powyższy przykład tworzy wystąpienie obiektu w znaczniku i używa go jako zasób.</span><span class="sxs-lookup"><span data-stu-id="84991-111">The above example instantiates the object in markup and uses it as a resource.</span></span> <span data-ttu-id="84991-112">Jeśli chcesz powiązać obiektu, który ma już wystąpienie w kodzie, musisz ustawić `DataContext` właściwości programowo.</span><span class="sxs-lookup"><span data-stu-id="84991-112">If you want to bind to an object that has already been instantiated in code, you need to set the `DataContext` property programmatically.</span></span> <span data-ttu-id="84991-113">Na przykład zobacz [upewnij dostępnych danych dla powiązania w języku XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="84991-113">For an example, see [Make Data Available for Binding in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).</span></span>  
  
 <span data-ttu-id="84991-114">Alternatywnie Jeśli chcesz określić źródło powiązania poszczególnych jawnie, dostępne są następujące opcje.</span><span class="sxs-lookup"><span data-stu-id="84991-114">Alternatively, if you want to specify the source on your individual bindings explicitly, you have the following options.</span></span> <span data-ttu-id="84991-115">Te pierwszeństwo kontekstu danych dziedziczone.</span><span class="sxs-lookup"><span data-stu-id="84991-115">These take precedence over the inherited data context.</span></span>  
  
|<span data-ttu-id="84991-116">Właściwość</span><span class="sxs-lookup"><span data-stu-id="84991-116">Property</span></span>|<span data-ttu-id="84991-117">Opis</span><span class="sxs-lookup"><span data-stu-id="84991-117">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Data.Binding.Source%2A>|<span data-ttu-id="84991-118">Ta właściwość umożliwia ustawione źródło na wystąpienie obiektu.</span><span class="sxs-lookup"><span data-stu-id="84991-118">You use this property to set the source to an instance of an object.</span></span> <span data-ttu-id="84991-119">Jeśli nie potrzebujesz funkcji ustalenia zakresu w kilka właściwości, które dziedziczą z tego samego kontekstu danych, możesz użyć <xref:System.Windows.Data.Binding.Source%2A> właściwości zamiast `DataContext` właściwości.</span><span class="sxs-lookup"><span data-stu-id="84991-119">If you do not need the functionality of establishing a scope in which several properties inherit the same data context, you can use the <xref:System.Windows.Data.Binding.Source%2A> property instead of the `DataContext` property.</span></span> <span data-ttu-id="84991-120">Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Data.Binding.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="84991-120">For more information, see <xref:System.Windows.Data.Binding.Source%2A>.</span></span>|  
|<xref:System.Windows.Data.Binding.RelativeSource%2A>|<span data-ttu-id="84991-121">Jest to przydatne, jeśli chcesz określić źródło względem gdzie to urządzenie docelowe powiązania.</span><span class="sxs-lookup"><span data-stu-id="84991-121">This is useful when you want to specify the source relative to where your binding target is.</span></span> <span data-ttu-id="84991-122">Niektóre typowe scenariusze, w których może używać tej właściwości jest należy powiązać jedną właściwość z elementu inną właściwość tego samego elementu, lub Jeśli powiązanie są definiowane w stylu lub w szablonie.</span><span class="sxs-lookup"><span data-stu-id="84991-122">Some common scenarios where you may use this property is when you want to bind one property of your element to another property of the same element or if you are defining a binding in a style or a template.</span></span> <span data-ttu-id="84991-123">Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Data.Binding.RelativeSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="84991-123">For more information, see <xref:System.Windows.Data.Binding.RelativeSource%2A>.</span></span>|  
|<xref:System.Windows.Data.Binding.ElementName%2A>|<span data-ttu-id="84991-124">Należy określić ciąg, który reprezentuje element, który chcesz utworzyć powiązania.</span><span class="sxs-lookup"><span data-stu-id="84991-124">You specify a string that represents the element you want to bind to.</span></span> <span data-ttu-id="84991-125">Jest to przydatne, jeśli chcesz powiązać z właściwością innego elementu w swojej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="84991-125">This is useful when you want to bind to the property of another element on your application.</span></span> <span data-ttu-id="84991-126">Na przykład, jeśli chcesz użyć <xref:System.Windows.Controls.Slider> mogą kontrolować jego wysokość formantem w aplikacji lub jeśli chcesz powiązać <xref:System.Windows.Controls.ContentControl.Content%2A> kontroli w celu <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> właściwości użytkownika <xref:System.Windows.Controls.ListBox> formantu.</span><span class="sxs-lookup"><span data-stu-id="84991-126">For example, if you want to use a <xref:System.Windows.Controls.Slider> to control the height of another control in your application, or if you want to bind the <xref:System.Windows.Controls.ContentControl.Content%2A> of your control to the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property of your <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="84991-127">Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Data.Binding.ElementName%2A>.</span><span class="sxs-lookup"><span data-stu-id="84991-127">For more information, see <xref:System.Windows.Data.Binding.ElementName%2A>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84991-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="84991-128">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.DataContext%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.DataContext%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="84991-129">Dziedziczenie wartości właściwości</span><span class="sxs-lookup"><span data-stu-id="84991-129">Property Value Inheritance</span></span>](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)  
 [<span data-ttu-id="84991-130">Omówienie powiązania danych</span><span class="sxs-lookup"><span data-stu-id="84991-130">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="84991-131">Przegląd deklaracji powiązania</span><span class="sxs-lookup"><span data-stu-id="84991-131">Binding Declarations Overview</span></span>](../../../../docs/framework/wpf/data/binding-declarations-overview.md)  
 [<span data-ttu-id="84991-132">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="84991-132">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)