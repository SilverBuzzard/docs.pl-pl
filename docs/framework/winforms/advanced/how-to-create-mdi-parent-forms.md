---
title: "Porady: tworzenie formularzy nadrzędnych MDI"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f768e01981f75e5e322fd984e73ccf7b185c5e20
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="5c5a9-102">Porady: tworzenie formularzy nadrzędnych MDI</span><span class="sxs-lookup"><span data-stu-id="5c5a9-102">How to: Create MDI Parent Forms</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="5c5a9-103">W tym temacie używa <xref:System.Windows.Forms.MainMenu> formant, który został zastąpiony przez <xref:System.Windows.Forms.MenuStrip> formantu.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-103">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="5c5a9-104"><xref:System.Windows.Forms.MainMenu> Formantu są przechowywane dla zgodności z poprzednimi wersjami i użycia w przyszłości, jeśli zostanie wybrana.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-104">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span>  <span data-ttu-id="5c5a9-105">Informacje o tworzeniu MDI nadrzędnego formularza za pomocą <xref:System.Windows.Forms.MenuStrip>, zobacz [porady: tworzenie List okien MDI za pomocą elementu MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5c5a9-105">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>  
  
 <span data-ttu-id="5c5a9-106">Foundation aplikacji interfejsu wielu dokumentów (MDI) to formularza nadrzędnego MDI.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-106">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="5c5a9-107">Jest to formularz, który zawiera okien podrzędnych MDI, które są podrzędne windows, w którym użytkownik wchodzi w interakcję z aplikacją MDI.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-107">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="5c5a9-108">Tworzenie formularza nadrzędnego MDI jest łatwe, zarówno w narzędziu Projektant dla formularzy systemu Windows, jak i programowo.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-108">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="5c5a9-109">Aby utworzyć formularza nadrzędnego MDI w czasie projektowania</span><span class="sxs-lookup"><span data-stu-id="5c5a9-109">To create an MDI parent form at design time</span></span>  
  
1.  <span data-ttu-id="5c5a9-110">Utwórz projekt aplikacji systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-110">Create a Windows Application project.</span></span>  
  
2.  <span data-ttu-id="5c5a9-111">W **właściwości** ustaw <xref:System.Windows.Forms.Form.IsMdiContainer%2A> właściwości **true**.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-111">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>  
  
     <span data-ttu-id="5c5a9-112">Określa formularza jako kontenera okien podrzędnych MDI.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-112">This designates the form as an MDI container for child windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c5a9-113">Podczas ustawiania właściwości **właściwości** okna, można również ustawić `WindowState` właściwości **Maximized**, jeśli chcesz, ponieważ jest najłatwiejsza do manipulowania okien podrzędnych MDI formularz nadrzędny jest zmaksymalizowane.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-113">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="5c5a9-114">Ponadto należy pamiętać, że krawędzi formularza nadrzędnego MDI przejmą kolorów systemu (zestaw w Panelu sterowania systemu Windows), zamiast kolor tyłu można ustawić za pomocą <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-114">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>  
  
3.  <span data-ttu-id="5c5a9-115">Z **przybornika**, przeciągnij **MenuStrip** sterowania do formularza.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-115">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="5c5a9-116">Utwórz element menu najwyższego poziomu z **tekst** ustawioną właściwość **& pliku** z elementami podmenu o nazwie **& nowym** i **& Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-116">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="5c5a9-117">Również utworzyć wywołuje element menu najwyższego poziomu **& okna**.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-117">Also create a top-level menu item called **&Window**.</span></span>  
  
     <span data-ttu-id="5c5a9-118">Pierwszy menu utworzy i ukrywanie elementów menu w czasie wykonywania, i drugie menu będzie śledzenie okien podrzędnych MDI.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-118">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="5c5a9-119">W tym momencie utworzono nadrzędnego okna MDI.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-119">At this point, you have created an MDI parent window.</span></span>  
  
4.  <span data-ttu-id="5c5a9-120">Naciśnij klawisz **F5** do uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5c5a9-120">Press **F5** to run the application.</span></span> <span data-ttu-id="5c5a9-121">Informacji o tworzeniu formularz podrzędny MDI systemu windows, które działają w ramach formularza nadrzędnego MDI, zobacz [porady: tworzenie formularzy podrzędnych MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5c5a9-121">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5a9-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5c5a9-122">See Also</span></span>  
 [<span data-ttu-id="5c5a9-123">Aplikacje interfejsu wielu dokumentów (MDI)</span><span class="sxs-lookup"><span data-stu-id="5c5a9-123">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="5c5a9-124">Porady: tworzenie formularzy podrzędnych MDI</span><span class="sxs-lookup"><span data-stu-id="5c5a9-124">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="5c5a9-125">Porady: ustalić podrzędnego Active MDI</span><span class="sxs-lookup"><span data-stu-id="5c5a9-125">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="5c5a9-126">Porady: wysyłanie danych do Active MDI Child</span><span class="sxs-lookup"><span data-stu-id="5c5a9-126">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [<span data-ttu-id="5c5a9-127">Porady: Aranżowanie formularzy podrzędnych MDI</span><span class="sxs-lookup"><span data-stu-id="5c5a9-127">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)