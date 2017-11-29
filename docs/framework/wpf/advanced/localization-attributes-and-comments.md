---
title: "Lokalizacja atrybutów i komentarzy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- localization [WPF], attributes
- localization [WPF], comments
ms.assetid: ead2d9ac-b709-4ec1-a924-39927a29d02f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5a603c854d389076d0054a43ebeb26f19145fa8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="localization-attributes-and-comments"></a><span data-ttu-id="1c153-102">Lokalizacja atrybutów i komentarzy</span><span class="sxs-lookup"><span data-stu-id="1c153-102">Localization Attributes and Comments</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="1c153-103">Lokalizacja komentarze są właściwościami, wewnątrz [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] kod źródłowy, dostarczone przez deweloperów do zapewnienia lokalizacji zasad i wskazówek dotyczących serwerów.</span><span class="sxs-lookup"><span data-stu-id="1c153-103"> localization comments are properties, inside [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] source code, supplied by developers to provide rules and hints for localization.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="1c153-104">Lokalizacja komentarze zawierają dwa zestawy informacji: atrybuty możliwości zlokalizowania i lokalizacja dowolne komentarze.</span><span class="sxs-lookup"><span data-stu-id="1c153-104"> localization comments contain two sets of information: localizability attributes and free-form localization comments.</span></span> <span data-ttu-id="1c153-105">Możliwość lokalizacji atrybuty są używane przez [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] lokalizacja interfejsu API, aby wskazać, zasobów, do których mają być lokalizowany.</span><span class="sxs-lookup"><span data-stu-id="1c153-105">Localizability attributes are used by the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Localization API to indicate which resources are to be localized.</span></span> <span data-ttu-id="1c153-106">Dowolne komentarze są wszystkie informacje, które chce dołączyć Autor aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1c153-106">Free-form comments are any information that the application author wants to include.</span></span>  
  

  
<a name="Localizer_Comments_"></a>   
## <a name="localization-comments"></a><span data-ttu-id="1c153-107">Komentarze w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1c153-107">Localization Comments</span></span>  
 <span data-ttu-id="1c153-108">Jeśli znaczników aplikacji Autorzy mają wymagania dotyczące określonych elementów w [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], takie jak ograniczenia dotyczące długość tekstu rodziny czcionek i rozmiar czcionki, ich przedstawienia tych informacji, aby wiadomość dla lokalizatorów z uwagi na [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] kodu.</span><span class="sxs-lookup"><span data-stu-id="1c153-108">If markup application authors have requirements for specific elements in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], such as constraints on text length, font family, or font size, they can convey this information to localizers with comments in the [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] code.</span></span> <span data-ttu-id="1c153-109">Proces dodawania komentarzy do kodu źródłowego, jest następujący:</span><span class="sxs-lookup"><span data-stu-id="1c153-109">The process for adding comments to source code is as follows:</span></span>  
  
1.  <span data-ttu-id="1c153-110">Deweloper aplikacji dodaje komentarz lokalizacji do [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] kod źródłowy.</span><span class="sxs-lookup"><span data-stu-id="1c153-110">Application developer adds localization comments to [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] source code.</span></span>  
  
2.  <span data-ttu-id="1c153-111">Podczas procesu kompilacji można określić w pliku .proj czy należy pozostawić komentarze dowolnych lokalizacji zestawu, paska się częścią komentarze lub paska limit wszystkie komentarze.</span><span class="sxs-lookup"><span data-stu-id="1c153-111">During the build process, you can specify in the .proj file whether to leave the free-form localization comments in the assembly, strip out part of the comments, or strip out all the comments.</span></span> <span data-ttu-id="1c153-112">Komentarze usunięta poza są umieszczane w oddzielnym pliku.</span><span class="sxs-lookup"><span data-stu-id="1c153-112">The stripped-out comments are placed in a separate file.</span></span> <span data-ttu-id="1c153-113">Można ją określić za pomocą opcji `LocalizationDirectivesToLocFile` tagu np:</span><span class="sxs-lookup"><span data-stu-id="1c153-113">You specify your option using a `LocalizationDirectivesToLocFile` tag, eg:</span></span>  
  
     <span data-ttu-id="1c153-114">`<LocalizationDirectivesToLocFile>`*wartość*`</LocalizationDirectivesToLocFile>`</span><span class="sxs-lookup"><span data-stu-id="1c153-114">`<LocalizationDirectivesToLocFile>` *value* `</LocalizationDirectivesToLocFile>`</span></span>  
  
3.  <span data-ttu-id="1c153-115">Dostępne są następujące wartości, które można przypisać:</span><span class="sxs-lookup"><span data-stu-id="1c153-115">The values that can be assigned are:</span></span>  
  
    -   <span data-ttu-id="1c153-116">**Brak** -komentarzy i atrybutów pozostają w zestawie, a ten sam plik jest generowany.</span><span class="sxs-lookup"><span data-stu-id="1c153-116">**None** - Both comments and attributes stay inside the assembly and no separate file is generated.</span></span>  
  
    -   <span data-ttu-id="1c153-117">**CommentsOnly** — usuwa tylko komentarze z zestawu i umieszcza je w oddzielne LocFile.</span><span class="sxs-lookup"><span data-stu-id="1c153-117">**CommentsOnly** - Strips only the comments from the assembly and places them in the separate LocFile.</span></span>  
  
    -   <span data-ttu-id="1c153-118">**Wszystkie** — usuwa zarówno komentarzy i atrybutów z zestawu i umieszcza je w oddzielne LocFile.</span><span class="sxs-lookup"><span data-stu-id="1c153-118">**All** - Strips both the comments and the attributes from the assembly and places them both in a separate LocFile.</span></span>  
  
4.  <span data-ttu-id="1c153-119">Gdy zlokalizowania zasobów są wyodrębniane z [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)], atrybuty możliwości zlokalizowania są przestrzegane przez [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)] lokalizacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="1c153-119">When localizable resources are extracted from [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)], the localizability attributes are respected by the [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)] Localization API.</span></span>  
  
5.  <span data-ttu-id="1c153-120">Pliki komentarza lokalizacji, zawierający tylko dowolne komentarze są włączone w procesie lokalizacji w późniejszym czasie.</span><span class="sxs-lookup"><span data-stu-id="1c153-120">Localization comment files, containing only free-form comments, are incorporated into the localization process at a later time.</span></span>  
  
 <span data-ttu-id="1c153-121">Poniższy przykład przedstawia sposób dodawać komentarze lokalizacja [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] pliku.</span><span class="sxs-lookup"><span data-stu-id="1c153-121">The following example shows how to add localization comments to a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file.</span></span>  
  
 `<TextBlock x:Id = "text01"`  
  
 `FontFamily = "Microsoft Sans Serif"`  
  
 `FontSize = "12"`  
  
 `Localization.Attributes = "$Content (Unmodifiable Readable Text)`  
  
 `FontFamily (Unmodifiable Readable)"`  
  
 `Localization.Comments = "$Content (Trademark)`  
  
 `FontSize (Trademark font size)" >`  
  
 `Microsoft`  
  
 `</TextBlock>`  
  
 <span data-ttu-id="1c153-122">W poprzednim przykładzie Localization.Attributes sekcja zawiera atrybuty lokalizacji i komentarze sekcji dowolnych Localization.Comments.</span><span class="sxs-lookup"><span data-stu-id="1c153-122">In the previous sample the Localization.Attributes section contains the localization attributes and the Localization.Comments section the free-form comments.</span></span> <span data-ttu-id="1c153-123">W poniższej tabeli przedstawiono atrybuty i komentarze i ich znaczenie do lokalizatora.</span><span class="sxs-lookup"><span data-stu-id="1c153-123">The following tables show the attributes and comments and their meaning to the localizer.</span></span>  
  
|<span data-ttu-id="1c153-124">Atrybuty lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1c153-124">Localization attributes</span></span>|<span data-ttu-id="1c153-125">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="1c153-125">Meaning</span></span>|  
|-----------------------------|-------------|  
|<span data-ttu-id="1c153-126">$Content (unmodifiable czytelnej)</span><span class="sxs-lookup"><span data-stu-id="1c153-126">$Content (Unmodifiable Readable Text)</span></span>|<span data-ttu-id="1c153-127">Nie można zmodyfikować zawartość elementu blok tekstu.</span><span class="sxs-lookup"><span data-stu-id="1c153-127">Contents of the TextBlock element cannot be modified.</span></span> <span data-ttu-id="1c153-128">Wiadomość dla lokalizatorów nie można zmienić słowa "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="1c153-128">Localizers cannot change the word "Microsoft".</span></span> <span data-ttu-id="1c153-129">Zawartość jest widoczna (elementu Readable) do lokalizatora.</span><span class="sxs-lookup"><span data-stu-id="1c153-129">The content is visible (Readable) to the localizer.</span></span> <span data-ttu-id="1c153-130">Do kategorii zawartości jest tekst.</span><span class="sxs-lookup"><span data-stu-id="1c153-130">The category of the content is text.</span></span>|  
|<span data-ttu-id="1c153-131">FontFamily (Unmodifiable do odczytu)</span><span class="sxs-lookup"><span data-stu-id="1c153-131">FontFamily (Unmodifiable Readable)</span></span>|<span data-ttu-id="1c153-132">Nie można zmienić właściwości rodziny czcionek elementu blok tekstu, ale jest widoczny dla lokalizatora.</span><span class="sxs-lookup"><span data-stu-id="1c153-132">The font family property of the TextBlock element cannot be changed but it is visible to the localizer.</span></span>|  
  
|<span data-ttu-id="1c153-133">Lokalizacja dowolne komentarze</span><span class="sxs-lookup"><span data-stu-id="1c153-133">Localization free-form comments</span></span>|<span data-ttu-id="1c153-134">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="1c153-134">Meaning</span></span>|  
|--------------------------------------|-------------|  
|<span data-ttu-id="1c153-135">$Content (znak towarowy)</span><span class="sxs-lookup"><span data-stu-id="1c153-135">$Content (Trademark)</span></span>|<span data-ttu-id="1c153-136">Autor aplikacji lokalizatora informuje, że zawartość w elemencie blok tekstu jest zastrzeżonym znakiem towarowym firmy.</span><span class="sxs-lookup"><span data-stu-id="1c153-136">The application author tells the localizer that the content in the TextBlock element is a trademark.</span></span>|  
|<span data-ttu-id="1c153-137">FontSize (znak towarowy rozmiar czcionki)</span><span class="sxs-lookup"><span data-stu-id="1c153-137">FontSize (Trademark font size)</span></span>|<span data-ttu-id="1c153-138">Autor aplikacji wskazuje, że właściwość rozmiar czcionki, należy wykonać rozmiar znaków towarowych.</span><span class="sxs-lookup"><span data-stu-id="1c153-138">The application author indicates that the font size property should follow the standard trademark size.</span></span>|  
  
### <a name="localizability-attributes"></a><span data-ttu-id="1c153-139">Możliwość lokalizacji atrybutów</span><span class="sxs-lookup"><span data-stu-id="1c153-139">Localizability Attributes</span></span>  
 <span data-ttu-id="1c153-140">Informacje zawarte w Localization.Attributes zawiera listę par: Nazwa docelowej wartości i wartości skojarzone możliwości zlokalizowania.</span><span class="sxs-lookup"><span data-stu-id="1c153-140">The information in Localization.Attributes contains a list of pairs: the targeted value name and the associated localizability values.</span></span> <span data-ttu-id="1c153-141">Nazwa docelowego może być nazwa właściwości lub specjalną nazwą $Content.</span><span class="sxs-lookup"><span data-stu-id="1c153-141">The target name can be a property name or the special $Content name.</span></span> <span data-ttu-id="1c153-142">Jeśli jest to nazwa właściwości, wartość docelowa jest wartość właściwości.</span><span class="sxs-lookup"><span data-stu-id="1c153-142">If it is a property name, the targeted value is the value of the property.</span></span> <span data-ttu-id="1c153-143">Jeśli jest $Content wartość docelowa jest zawartość elementu.</span><span class="sxs-lookup"><span data-stu-id="1c153-143">If it is $Content, the target value is the content of the element.</span></span>  
  
 <span data-ttu-id="1c153-144">Istnieją trzy typy atrybutów:</span><span class="sxs-lookup"><span data-stu-id="1c153-144">There are three types of attributes:</span></span>  
  
-   <span data-ttu-id="1c153-145">**Kategoria**.</span><span class="sxs-lookup"><span data-stu-id="1c153-145">**Category**.</span></span> <span data-ttu-id="1c153-146">Określa, czy wartość należy modyfikować za pomocą narzędzia lokalizatora.</span><span class="sxs-lookup"><span data-stu-id="1c153-146">This specifies whether a value should be modifiable from a localizer tool.</span></span> <span data-ttu-id="1c153-147">Zobacz <xref:System.Windows.LocalizabilityAttribute.Category%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c153-147">See <xref:System.Windows.LocalizabilityAttribute.Category%2A>.</span></span>  
  
-   <span data-ttu-id="1c153-148">**Czytelność**.</span><span class="sxs-lookup"><span data-stu-id="1c153-148">**Readability**.</span></span> <span data-ttu-id="1c153-149">Określa, czy narzędzie lokalizatora należy odczytać (i wyświetlić) wartość.</span><span class="sxs-lookup"><span data-stu-id="1c153-149">This specifies whether a localizer tool should read (and display) a value.</span></span> <span data-ttu-id="1c153-150">Zobacz <xref:System.Windows.LocalizabilityAttribute.Readability%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c153-150">See <xref:System.Windows.LocalizabilityAttribute.Readability%2A>.</span></span>  
  
-   <span data-ttu-id="1c153-151">**Modifiability**.</span><span class="sxs-lookup"><span data-stu-id="1c153-151">**Modifiability**.</span></span> <span data-ttu-id="1c153-152">To ustawienie określa, czy narzędzie lokalizatora daje wartość ma zostać zmodyfikowana.</span><span class="sxs-lookup"><span data-stu-id="1c153-152">This specifies whether a localizer tool allows a value to be modified.</span></span> <span data-ttu-id="1c153-153">Zobacz <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c153-153">See <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>.</span></span>  
  
 <span data-ttu-id="1c153-154">Te atrybuty można określić w dowolnej kolejności rozdzielonych spacją.</span><span class="sxs-lookup"><span data-stu-id="1c153-154">These attributes can be specified in any order delimited by a space.</span></span> <span data-ttu-id="1c153-155">W przypadku, gdy określono zduplikowane atrybuty, ostatniego atrybutu spowoduje zastąpienie pierwszych.</span><span class="sxs-lookup"><span data-stu-id="1c153-155">In case duplicate attributes are specified, the last attribute will override former ones.</span></span> <span data-ttu-id="1c153-156">Na przykład Localization.Attributes = "Unmodifiable modyfikowalnymi" Ustawia Modifiability do Modifiable, ponieważ jest to ostatnia wartość.</span><span class="sxs-lookup"><span data-stu-id="1c153-156">For example, Localization.Attributes = "Unmodifiable Modifiable" sets Modifiability to Modifiable because it is the last value.</span></span>  
  
 <span data-ttu-id="1c153-157">Modifiability i czytelność nie wymaga wyjaśnień.</span><span class="sxs-lookup"><span data-stu-id="1c153-157">Modifiability and Readability are self-explanatory.</span></span> <span data-ttu-id="1c153-158">Atrybut kategorii udostępnia wstępnie zdefiniowane kategorie ułatwiające lokalizatora podczas tłumaczenia tekstu.</span><span class="sxs-lookup"><span data-stu-id="1c153-158">The Category attribute provides predefined categories that help the localizer when translating text.</span></span> <span data-ttu-id="1c153-159">Kategorie, takie jak przyznanie tekst etykiety i tytuł lokalizatora informacje o sposobie tłumaczenie tekstu.</span><span class="sxs-lookup"><span data-stu-id="1c153-159">Categories, such as, Text, Label, and Title give the localizer information about how to translate the text.</span></span> <span data-ttu-id="1c153-160">Istnieje również specjalne kategorii: Brak, Dziedzicz Ignoruj i NeverLocalize.</span><span class="sxs-lookup"><span data-stu-id="1c153-160">There are also special categories: None, Inherit, Ignore, and NeverLocalize.</span></span>  
  
 <span data-ttu-id="1c153-161">W poniższej tabeli przedstawiono znaczenie specjalne kategorii.</span><span class="sxs-lookup"><span data-stu-id="1c153-161">The following table shows the meaning of the special categories.</span></span>  
  
|<span data-ttu-id="1c153-162">Kategoria</span><span class="sxs-lookup"><span data-stu-id="1c153-162">Category</span></span>|<span data-ttu-id="1c153-163">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="1c153-163">Meaning</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="1c153-164">Brak</span><span class="sxs-lookup"><span data-stu-id="1c153-164">None</span></span>|<span data-ttu-id="1c153-165">Wartość docelowa ma nie określonych kategorii.</span><span class="sxs-lookup"><span data-stu-id="1c153-165">Targeted value has no defined category.</span></span>|  
|<span data-ttu-id="1c153-166">Dziedziczenie</span><span class="sxs-lookup"><span data-stu-id="1c153-166">Inherit</span></span>|<span data-ttu-id="1c153-167">Wartość docelowa dziedziczy kategorii po swoim obiekcie nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="1c153-167">Targeted value inherits its category from its parent.</span></span>|  
|<span data-ttu-id="1c153-168">Ignoruj</span><span class="sxs-lookup"><span data-stu-id="1c153-168">Ignore</span></span>|<span data-ttu-id="1c153-169">Wartość docelowa jest ignorowany w procesie lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1c153-169">Targeted value is ignored in the localization process.</span></span> <span data-ttu-id="1c153-170">Ignoruj dotyczy tylko bieżącej wartości.</span><span class="sxs-lookup"><span data-stu-id="1c153-170">Ignore affects only the current value.</span></span> <span data-ttu-id="1c153-171">Nie wpłynie węzłów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="1c153-171">It will not affect child nodes.</span></span>|  
|<span data-ttu-id="1c153-172">NeverLocalize</span><span class="sxs-lookup"><span data-stu-id="1c153-172">NeverLocalize</span></span>|<span data-ttu-id="1c153-173">Bieżąca wartość nie może być lokalizowany.</span><span class="sxs-lookup"><span data-stu-id="1c153-173">Current value cannot be localized.</span></span> <span data-ttu-id="1c153-174">Ta kategoria jest dziedziczona przez elementy podrzędne danego elementu.</span><span class="sxs-lookup"><span data-stu-id="1c153-174">This category is inherited by the children of an element.</span></span>|  
  
<a name="Localization_Comments"></a>   
## <a name="localization-comments"></a><span data-ttu-id="1c153-175">Komentarze w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1c153-175">Localization Comments</span></span>  
 <span data-ttu-id="1c153-176">Localization.Comments zawiera dowolnych ciągów dotyczące wartości docelowych.</span><span class="sxs-lookup"><span data-stu-id="1c153-176">Localization.Comments contains free-form strings concerning the targeted value.</span></span> <span data-ttu-id="1c153-177">Deweloperzy aplikacji można dodać informacje umożliwiają wiadomość dla lokalizatorów podpowiedź sposób przekształcania tekstu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1c153-177">Application developers can add information to give localizers hints about how the applications text should be translated.</span></span> <span data-ttu-id="1c153-178">Format komentarzy może być dowolnym ciągiem otoczona "()".</span><span class="sxs-lookup"><span data-stu-id="1c153-178">The format of the comments can be any string surrounded by "()".</span></span> <span data-ttu-id="1c153-179">Użyj "\\' Aby wprowadzić znaków.</span><span class="sxs-lookup"><span data-stu-id="1c153-179">Use '\\' to escape characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c153-180">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1c153-180">See Also</span></span>  
 [<span data-ttu-id="1c153-181">Globalizacja dla WPF</span><span class="sxs-lookup"><span data-stu-id="1c153-181">Globalization for WPF</span></span>](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [<span data-ttu-id="1c153-182">Umożliwia utworzenie przycisk Automatyczny układ</span><span class="sxs-lookup"><span data-stu-id="1c153-182">Use Automatic Layout to Create a Button</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [<span data-ttu-id="1c153-183">Użyj siatki układu automatycznego</span><span class="sxs-lookup"><span data-stu-id="1c153-183">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)  
 [<span data-ttu-id="1c153-184">Lokalizowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="1c153-184">Localize an Application</span></span>](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)