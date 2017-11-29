---
title: "Porady: powiązanie formantu formularzy systemu Windows z typem"
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
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ffde36d9644dade3372292a6fb3961cbbfb6a5da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a><span data-ttu-id="483db-102">Porady: powiązanie formantu formularzy systemu Windows z typem</span><span class="sxs-lookup"><span data-stu-id="483db-102">How to: Bind a Windows Forms Control to a Type</span></span>
<span data-ttu-id="483db-103">Podczas tworzenia formantów, które współdziałają z danymi będą czasami jest konieczne do wiązania kontrolki typu, a nie obiektu.</span><span class="sxs-lookup"><span data-stu-id="483db-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="483db-104">Taka sytuacja wystąpi szczególnie w czasie projektowania, gdy dane mogą nie być dostępne, ale formantów powiązanych z danymi nadal konieczne jest wyświetlenie informacji dotyczących interfejsu publicznego typu.</span><span class="sxs-lookup"><span data-stu-id="483db-104">This situation arises especially at design time, when data may not be available, but your data-bound controls still need to display information from a type's public interface.</span></span> <span data-ttu-id="483db-105">Na przykład może powiązać <xref:System.Windows.Forms.DataGridView> kontrolować obiektem udostępnianych przez usługi sieci Web i chcesz <xref:System.Windows.Forms.DataGridView> formantu etykiety kolumn w czasie projektowania z elementem członkowskim nazwy typu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="483db-105">For example, you may bind a <xref:System.Windows.Forms.DataGridView> control to an object exposed by a Web service and want the <xref:System.Windows.Forms.DataGridView> control to label its columns at design time with the member names of a custom type.</span></span>  
  
 <span data-ttu-id="483db-106">Łatwo można powiązać formant do typu z <xref:System.Windows.Forms.BindingSource> składnika.</span><span class="sxs-lookup"><span data-stu-id="483db-106">You can easily bind a control to a type with the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="483db-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="483db-107">Example</span></span>  
 <span data-ttu-id="483db-108">Poniższy przykład kodu pokazuje, jak można powiązać <xref:System.Windows.Forms.DataGridView> formantu niestandardowego typu przy użyciu <xref:System.Windows.Forms.BindingSource> składnika.</span><span class="sxs-lookup"><span data-stu-id="483db-108">The following code example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a custom type by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="483db-109">Po uruchomieniu przykładzie można zauważyć <xref:System.Windows.Forms.DataGridView> etykietą kolumny, które odzwierciedlać właściwości `Customer` obiektu, zanim formant został wypełniony danymi.</span><span class="sxs-lookup"><span data-stu-id="483db-109">When you run the example, you'll notice the <xref:System.Windows.Forms.DataGridView> has labeled columns that reflect the properties of a `Customer` object, before the control is populated with data.</span></span> <span data-ttu-id="483db-110">Przykład znajduje się przycisk Dodaj klienta do dodawania danych do <xref:System.Windows.Forms.DataGridView> formantu.</span><span class="sxs-lookup"><span data-stu-id="483db-110">The example has an Add Customer button to add data to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="483db-111">Po kliknięciu przycisku Nowy `Customer` obiekt jest dodawany do <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="483db-111">When you click the button, a new `Customer` object is added to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="483db-112">W przypadku rzeczywistych danych może można uzyskać przez wywołanie do usługi sieci Web lub innego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="483db-112">In a real-world scenario, the data might be obtained by a call to a Web service or other data source.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="483db-113">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="483db-113">Compiling the Code</span></span>  
 <span data-ttu-id="483db-114">Ten przykład wymaga:</span><span class="sxs-lookup"><span data-stu-id="483db-114">This example requires:</span></span>  
  
-   <span data-ttu-id="483db-115">Odwołania do zestawów systemu i System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="483db-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="483db-116">Informacji dotyczących tworzenia tego przykładu z wiersza polecenia dla [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] lub [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], zobacz [tworzenie z wiersza polecenia](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) lub [kompilowania z wiersza polecenia csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="483db-116">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="483db-117">Można także utworzyć tym przykładzie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] przez wklejenie kodu do nowego projektu.</span><span class="sxs-lookup"><span data-stu-id="483db-117">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="483db-118">Zobacz też [porady: kompilowanie i uruchamianie pełną Windows formularze kodu przykład za pomocą programu Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="483db-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483db-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="483db-119">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="483db-120">BindingSource — składnik</span><span class="sxs-lookup"><span data-stu-id="483db-120">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)