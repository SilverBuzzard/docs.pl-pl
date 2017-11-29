---
title: "x:Uid — dyrektywa"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
caps.latest.revision: "12"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 4d49e9630b481b2daf103feabd225dd5ef0c8ca2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="xuid-directive"></a><span data-ttu-id="5c348-102">x:Uid — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="5c348-102">x:Uid Directive</span></span>
<span data-ttu-id="5c348-103">Zawiera unikatowy identyfikator dla elementów kodu znaczników.</span><span class="sxs-lookup"><span data-stu-id="5c348-103">Provides a unique identifier for markup elements.</span></span> <span data-ttu-id="5c348-104">W wielu scenariuszach ten unikatowy identyfikator jest używany przez XAML lokalizacja procesów i narzędzi.</span><span class="sxs-lookup"><span data-stu-id="5c348-104">In many scenarios, this unique identifier is used by XAML localization processes and tools.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="5c348-105">Użycie atrybutu języka XAML</span><span class="sxs-lookup"><span data-stu-id="5c348-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="5c348-106">Wartości XAML</span><span class="sxs-lookup"><span data-stu-id="5c348-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`identifier`|<span data-ttu-id="5c348-107">Utworzony ręcznie lub automatycznie wygenerowany ciąg, który powinien być unikatowy w pliku podczas jest interpretowany przez `x:Uid` konsumenta.</span><span class="sxs-lookup"><span data-stu-id="5c348-107">A manually created or autogenerated string that should be unique in a file when it is interpreted by an `x:Uid` consumer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c348-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5c348-108">Remarks</span></span>  
 <span data-ttu-id="5c348-109">W [MS-XAML] `x:Uid` jest zdefiniowany dyrektywą.</span><span class="sxs-lookup"><span data-stu-id="5c348-109">In [MS-XAML], `x:Uid` is defined as a directive.</span></span> <span data-ttu-id="5c348-110">Aby uzyskać więcej informacji, zobacz [ \[MS XAML\] sekcji 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="5c348-110">For more information, see [\[MS-XAML\] Section 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
 <span data-ttu-id="5c348-111">`x:Uid`jest odrębny z `x:Name` zarówno z powodu podane scenariusz lokalizacja XAML i tak, aby identyfikatorów, które są używane do lokalizacji nie ma żadnych zależności na skutki modelu programowania `x:Name`.</span><span class="sxs-lookup"><span data-stu-id="5c348-111">`x:Uid` is discrete from `x:Name` both because of the stated XAML localization scenario and so that identifiers that are used for localization have no dependencies on the programming model implications of `x:Name`.</span></span> <span data-ttu-id="5c348-112">Ponadto `x:Name` podlega XAML namescope; jednak `x:Uid` nie podlega żadnych koncepcji zdefiniowane języka XAML wymuszania unikatowości.</span><span class="sxs-lookup"><span data-stu-id="5c348-112">Also, `x:Name` is governed by the XAML namescope; however, `x:Uid` is not governed by any XAML language defined concept of uniqueness enforcement.</span></span> <span data-ttu-id="5c348-113">Aby wymusić unikatowość nie powinny procesorów XAML szeroko (procesorów, które nie są częścią procesu lokalizacja) `x:Uid` wartości.</span><span class="sxs-lookup"><span data-stu-id="5c348-113">XAML processors in a broad sense (processors that are not part of the localization process) are not expected to enforce uniqueness of `x:Uid` values.</span></span> <span data-ttu-id="5c348-114">Odpowiedzialność jest koncepcyjnie na inicjatorem wartości.</span><span class="sxs-lookup"><span data-stu-id="5c348-114">That responsibility is conceptually on the originator of the values.</span></span> <span data-ttu-id="5c348-115">Oczekuje unikatowość `x:Uid` wartości w ramach jednego źródła XAML jest uzasadnione dla konsumentów wartości, takich jak globalizacja dedykowanych procesów lub narzędzia.</span><span class="sxs-lookup"><span data-stu-id="5c348-115">The expectation of uniqueness of `x:Uid` values within a single XAML source is reasonable for consumers of the values, such as dedicated globalization processes or tools.</span></span> <span data-ttu-id="5c348-116">Model typowe unikatowości jest to, że `x:Uid` wartości są unikatowe w obrębie pliku kodowany w formacie XML, reprezentujący XAML.</span><span class="sxs-lookup"><span data-stu-id="5c348-116">The typical uniqueness model is that `x:Uid` values are unique within an XML-encoded file that represents XAML.</span></span>  
  
 <span data-ttu-id="5c348-117">Narzędzia, które posiadają znaczne wiedzę na temat określonego schematu XAML mogą być stosowane `x:Uid` tylko w przypadku true Lokalizowalny ciągi, a nie we wszystkich przypadkach, gdy napotkano wartości ciągu tekstowego w znaczniku.</span><span class="sxs-lookup"><span data-stu-id="5c348-117">Tools that have significant knowledge of a particular XAML schema can choose to apply `x:Uid` only for true localizable strings, instead of for all cases where a text string value is encountered in markup.</span></span>  
  
 <span data-ttu-id="5c348-118">Struktury można określić określonej właściwości w modelu obiektów, ich jako alias dla `x:Uid` przez zastosowanie atrybutu <xref:System.Windows.Markup.UidPropertyAttribute> typowi definiującego.</span><span class="sxs-lookup"><span data-stu-id="5c348-118">Frameworks can specify a particular property in their object model to be an alias for `x:Uid` by applying the attribute <xref:System.Windows.Markup.UidPropertyAttribute> to the defining type.</span></span> <span data-ttu-id="5c348-119">Jeśli platforma określa określonej właściwości, nie jest prawidłową określić ich obu `x:Uid` i element członkowski aliasem w tym samym obiekcie.</span><span class="sxs-lookup"><span data-stu-id="5c348-119">If a framework specifies a particular property, it is not valid to specify both `x:Uid` and the aliased member on the same object.</span></span> <span data-ttu-id="5c348-120">Jeśli oba `x:Uid` i podano elementu członkowskiego aliasu, interfejsu API programu .NET Framework XAML Services zwykle zgłasza <xref:System.Xaml.XamlDuplicateMemberException> dla tej sprawy.</span><span class="sxs-lookup"><span data-stu-id="5c348-120">If both `x:Uid` and the aliased member are specified, the .NET Framework XAML Services API typically throws <xref:System.Xaml.XamlDuplicateMemberException> for this case.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="5c348-121">Uwagi dotyczące użycia WPF</span><span class="sxs-lookup"><span data-stu-id="5c348-121">WPF Usage Notes</span></span>  
 <span data-ttu-id="5c348-122">Aby uzyskać więcej informacji o roli `x:Uid` w procesie lokalizacji WPF i w postaci BAML XAML, zobacz [globalizacji dla WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md) lub<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A></span><span class="sxs-lookup"><span data-stu-id="5c348-122">For more information about the role of `x:Uid` in the WPF localization process and in the BAML form of XAML, see [Globalization for WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md) or <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c348-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5c348-123">See Also</span></span>  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
 <xref:Microsoft.Build.Tasks.Windows.UidManager>  
 [<span data-ttu-id="5c348-124">Globalizacja dla WPF</span><span class="sxs-lookup"><span data-stu-id="5c348-124">Globalization for WPF</span></span>](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)