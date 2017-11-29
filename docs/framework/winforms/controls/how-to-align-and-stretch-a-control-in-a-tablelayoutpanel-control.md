---
title: "Porady: wyrównywanie i rozciąganie formantu w formancie TableLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 043adb68b88ab031cea3de1206d1f2c4252b75d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="f68f4-102">Porady: wyrównywanie i rozciąganie formantu w formancie TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="f68f4-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>
<span data-ttu-id="f68f4-103">Wyrównywanie i rozciąganie kontrolek w <xref:System.Windows.Forms.TableLayoutPanel> z <xref:System.Windows.Forms.Control.Anchor%2A> i <xref:System.Windows.Forms.Control.Dock%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="f68f4-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f68f4-104">Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania.</span><span class="sxs-lookup"><span data-stu-id="f68f4-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f68f4-105">Aby zmienić ustawienia, wybierz **Import i eksport ustawień** na **narzędzia** menu.</span><span class="sxs-lookup"><span data-stu-id="f68f4-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f68f4-106">Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f68f4-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-align-and-stretch-a-control"></a><span data-ttu-id="f68f4-107">Wyrównanie i rozciąganie formantu</span><span class="sxs-lookup"><span data-stu-id="f68f4-107">To align and stretch a control</span></span>  
  
1.  <span data-ttu-id="f68f4-108">Przeciągnij <xref:System.Windows.Forms.TableLayoutPanel> kontrolować z **przybornika** na formularzu.</span><span class="sxs-lookup"><span data-stu-id="f68f4-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="f68f4-109">Przeciągnij <xref:System.Windows.Forms.Button> kontrolować z **przybornika** do lewej górnej komórki <xref:System.Windows.Forms.TableLayoutPanel> formantu.</span><span class="sxs-lookup"><span data-stu-id="f68f4-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="f68f4-110"><xref:System.Windows.Forms.Button> Kontroli jest wyśrodkowywana w komórce.</span><span class="sxs-lookup"><span data-stu-id="f68f4-110">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>  
  
3.  <span data-ttu-id="f68f4-111">Ustaw wartość <xref:System.Windows.Forms.Button> formantu <xref:System.Windows.Forms.Control.Anchor%2A> właściwości `Left,Right`.</span><span class="sxs-lookup"><span data-stu-id="f68f4-111">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="f68f4-112"><xref:System.Windows.Forms.Button> Kontrolować odcinkach odpowiadający szerokość komórki.</span><span class="sxs-lookup"><span data-stu-id="f68f4-112">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>  
  
4.  <span data-ttu-id="f68f4-113">Ustaw wartość <xref:System.Windows.Forms.Button> formantu <xref:System.Windows.Forms.Control.Anchor%2A> właściwości `Top,Bottom`.</span><span class="sxs-lookup"><span data-stu-id="f68f4-113">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="f68f4-114"><xref:System.Windows.Forms.Button> Kontrolować odcinkach odpowiadający wysokość komórki.</span><span class="sxs-lookup"><span data-stu-id="f68f4-114">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>  
  
5.  <span data-ttu-id="f68f4-115">Ustaw wartość <xref:System.Windows.Forms.Button> formantu <xref:System.Windows.Forms.Control.Dock%2A> właściwości <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="f68f4-115">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="f68f4-116"><xref:System.Windows.Forms.Button> Kontroli rozwijany do wypełnienia komórki.</span><span class="sxs-lookup"><span data-stu-id="f68f4-116">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>  
  
6.  <span data-ttu-id="f68f4-117">Ustaw wartość <xref:System.Windows.Forms.Button> formantu <xref:System.Windows.Forms.Control.Dock%2A> właściwości <xref:System.Windows.Forms.DockStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="f68f4-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="f68f4-118"><xref:System.Windows.Forms.Button> Kontroli, przywracając jego oryginalny rozmiar i przechodzi do lewego górnego rogu komórki.</span><span class="sxs-lookup"><span data-stu-id="f68f4-118">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="f68f4-119">**Projektant formularzy systemu Windows** ustawił <xref:System.Windows.Forms.Control.Anchor%2A> właściwości `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="f68f4-119">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>  
  
7.  <span data-ttu-id="f68f4-120">Ustaw wartość <xref:System.Windows.Forms.Button> formantu <xref:System.Windows.Forms.Control.Anchor%2A> właściwości `Bottom,Right`.</span><span class="sxs-lookup"><span data-stu-id="f68f4-120">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="f68f4-121"><xref:System.Windows.Forms.Button> Formant przechodzi do prawego dolnego rogu komórki.</span><span class="sxs-lookup"><span data-stu-id="f68f4-121">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>  
  
8.  <span data-ttu-id="f68f4-122">Ustaw wartość <xref:System.Windows.Forms.Button> formantu <xref:System.Windows.Forms.Control.Anchor%2A> właściwości <xref:System.Windows.Forms.AnchorStyles.None>.</span><span class="sxs-lookup"><span data-stu-id="f68f4-122">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="f68f4-123"><xref:System.Windows.Forms.Button> Formant przechodzi do Centrum komórki.</span><span class="sxs-lookup"><span data-stu-id="f68f4-123">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68f4-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f68f4-124">See Also</span></span>  
 [<span data-ttu-id="f68f4-125">TableLayoutPanel — formant</span><span class="sxs-lookup"><span data-stu-id="f68f4-125">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)