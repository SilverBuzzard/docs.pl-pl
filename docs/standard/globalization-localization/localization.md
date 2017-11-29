---
title: Lokalizacja
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a><span data-ttu-id="782c9-102">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="782c9-102">Localization</span></span>
<span data-ttu-id="782c9-103">Lokalizacja jest proces tłumaczenie zasobów aplikacji na zlokalizowane wersje każdego kultury, która aplikacja będzie obsługiwać.</span><span class="sxs-lookup"><span data-stu-id="782c9-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="782c9-104">Należy przejść do kroku lokalizacji, dopiero po ukończeniu [sprawdzenie](../../../docs/standard/globalization-localization/localizability-review.md) krok, aby sprawdzić, czy uniwersalnych aplikacji jest gotowa do lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="782c9-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>  
  
 <span data-ttu-id="782c9-105">Aplikacja jest gotowa do lokalizacji jest podzielone na dwa bloki pojęciach, blok, który zawiera wszystkie elementy interfejsu użytkownika i bloku, który zawiera kod wykonywalny.</span><span class="sxs-lookup"><span data-stu-id="782c9-105">An application that is ready for localization is separated into two conceptual blocks, a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="782c9-106">Blok interfejs użytkownika zawiera tylko Lokalizowalny interfejsu użytkownika elementów, takich jak ciągów, komunikaty o błędach, okien dialogowych, menu i zasoby osadzone, i tak dalej dla kultury neutralnej.</span><span class="sxs-lookup"><span data-stu-id="782c9-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="782c9-107">Blok kodu zawiera kod w aplikacji mają być używane przez wszystkich obsługiwanych języków.</span><span class="sxs-lookup"><span data-stu-id="782c9-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="782c9-108">Środowisko uruchomieniowe języka wspólnego obsługuje model zasobów zestawu satelity oddzielający kod wykonywalny aplikacji z jego zasobów.</span><span class="sxs-lookup"><span data-stu-id="782c9-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="782c9-109">Aby uzyskać więcej informacji o implementacji tego modelu, zobacz [zasobów w aplikacjach pulpitu](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="782c9-109">For more information about implementing this model, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="782c9-110">Dla każdego zlokalizowanej wersji aplikacji Dodaj nowy zestaw satelity, który zawiera blok interfejsu użytkownika zlokalizowanych przetłumaczyć odpowiedni język dla kulturze docelowej.</span><span class="sxs-lookup"><span data-stu-id="782c9-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="782c9-111">Blok kodu dla wszystkich języków powinny być takie same.</span><span class="sxs-lookup"><span data-stu-id="782c9-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="782c9-112">Kombinacja zlokalizowanej wersji blok interfejsu użytkownika z bloku kodu tworzy zlokalizowanej wersji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="782c9-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>  
  
 <span data-ttu-id="782c9-113">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Dostarcza Edytor zasobów formularzy systemu Windows (Winres.exe), który pozwala na szybkie lokalizowanie formularzy systemu Windows dla docelowej kultur.</span><span class="sxs-lookup"><span data-stu-id="782c9-113">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="782c9-114">Aby dowiedzieć się, jak za pomocą tego narzędzia, zobacz [Winres.exe (Edytor zasobów formularzy systemu Windows)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="782c9-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782c9-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="782c9-115">See Also</span></span>  
 [<span data-ttu-id="782c9-116">Lokalizacja i globalizacja</span><span class="sxs-lookup"><span data-stu-id="782c9-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="782c9-117">Sprawdzenie możliwości lokalizacji</span><span class="sxs-lookup"><span data-stu-id="782c9-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 [<span data-ttu-id="782c9-118">Globalizacja</span><span class="sxs-lookup"><span data-stu-id="782c9-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="782c9-119">Zasoby w aplikacjach klasycznych</span><span class="sxs-lookup"><span data-stu-id="782c9-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)