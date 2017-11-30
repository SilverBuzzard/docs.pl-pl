---
title: "Jak utworzyć powiązanie w kodzie"
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
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6279de3b892d64bc48b4f67c9f08bd89dd1b7d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="38148-102">Jak utworzyć powiązanie w kodzie</span><span class="sxs-lookup"><span data-stu-id="38148-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="38148-103">W tym przykładzie pokazano, jak utworzyć i ustawić <xref:System.Windows.Data.Binding> w kodzie.</span><span class="sxs-lookup"><span data-stu-id="38148-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38148-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="38148-104">Example</span></span>  
 <span data-ttu-id="38148-105"><xref:System.Windows.FrameworkElement> Klasy i <xref:System.Windows.FrameworkContentElement> klasy ujawnia zarówno `SetBinding` metody.</span><span class="sxs-lookup"><span data-stu-id="38148-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="38148-106">Element, który dziedziczy z jednej z tych klas są wiązane, należy wywołać <xref:System.Windows.FrameworkElement.SetBinding%2A> metody bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="38148-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="38148-107">Poniższy przykład tworzy klasę o nazwie, `MyData`, który zawiera właściwości o nazwie `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="38148-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="38148-108">Poniższy przykład przedstawia sposób tworzenia obiektu wiązania, aby ustawić źródło wiązania.</span><span class="sxs-lookup"><span data-stu-id="38148-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="38148-109">W przykładzie użyto <xref:System.Windows.FrameworkElement.SetBinding%2A> powiązać <xref:System.Windows.Controls.TextBlock.Text%2A> właściwość `myText`, która jest <xref:System.Windows.Controls.TextBlock> sterowania do `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="38148-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="38148-110">Dla przykładu kompletny kod, zobacz [tylko kod przykładowy powiązanie](http://msdn.microsoft.com/en-us/764aaf0b-2216-4941-9548-9c98da18d1a6).</span><span class="sxs-lookup"><span data-stu-id="38148-110">For the complete code sample, see [Code-only Binding Sample](http://msdn.microsoft.com/en-us/764aaf0b-2216-4941-9548-9c98da18d1a6).</span></span>  
  
 <span data-ttu-id="38148-111">Zamiast wywoływać metodę <xref:System.Windows.FrameworkElement.SetBinding%2A>, można użyć <xref:System.Windows.Data.BindingOperations.SetBinding%2A> statycznej metody <xref:System.Windows.Data.BindingOperations> klasy.</span><span class="sxs-lookup"><span data-stu-id="38148-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="38148-112">Poniższy przykład, wywołania <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> zamiast <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> powiązać `myText` do `myDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="38148-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="38148-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="38148-113">See Also</span></span>  
 [<span data-ttu-id="38148-114">Omówienie powiązania danych</span><span class="sxs-lookup"><span data-stu-id="38148-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="38148-115">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="38148-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)