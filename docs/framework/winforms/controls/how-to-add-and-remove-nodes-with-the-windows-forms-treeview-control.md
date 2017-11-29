---
title: "Porady: dodawanie i usuwanie węzłów za pomocą kontrolki TreeView formularzy systemu Windows"
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
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41834f0bdfe800019c1f641d5b20147b10774221
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="a8a5c-102">Porady: dodawanie i usuwanie węzłów za pomocą kontrolki TreeView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="a8a5c-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="a8a5c-103">Formularze systemu Windows <xref:System.Windows.Forms.TreeView> formant przechowuje węzły najwyższego poziomu w jego <xref:System.Windows.Forms.TreeView.Nodes%2A> kolekcji.</span><span class="sxs-lookup"><span data-stu-id="a8a5c-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="a8a5c-104">Każdy <xref:System.Windows.Forms.TreeNode> również ma własną <xref:System.Windows.Forms.TreeNode.Nodes%2A> kolekcji do przechowywania węzły podrzędne.</span><span class="sxs-lookup"><span data-stu-id="a8a5c-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="a8a5c-105">Obie właściwości kolekcji są typu <xref:System.Windows.Forms.TreeNodeCollection>, który zawiera członków kolekcji standardowych, które umożliwiają dodawanie, usuwanie i rozmieszczanie węzłów w jeden poziom w hierarchii węzła.</span><span class="sxs-lookup"><span data-stu-id="a8a5c-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="a8a5c-106">Aby dodać węzły programowo</span><span class="sxs-lookup"><span data-stu-id="a8a5c-106">To add nodes programmatically</span></span>  
  
1.  <span data-ttu-id="a8a5c-107">Użyj <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> metody widok drzewa <xref:System.Windows.Forms.TreeView.Nodes%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="a8a5c-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="a8a5c-108">Usuwanie węzłów programowo</span><span class="sxs-lookup"><span data-stu-id="a8a5c-108">To remove nodes programmatically</span></span>  
  
1.  <span data-ttu-id="a8a5c-109">Użyj <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> metody widok drzewa <xref:System.Windows.Forms.TreeView.Nodes%2A> właściwości do jednego węzła, usuń lub <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> metodę, aby wyczyścić wszystkie węzły.</span><span class="sxs-lookup"><span data-stu-id="a8a5c-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing   
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a8a5c-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a8a5c-110">See Also</span></span>  
 [<span data-ttu-id="a8a5c-111">TreeView — formant</span><span class="sxs-lookup"><span data-stu-id="a8a5c-111">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="a8a5c-112">Informacje o formancie TreeView</span><span class="sxs-lookup"><span data-stu-id="a8a5c-112">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="a8a5c-113">Porady: ustawienie ikon dla formantu TreeView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="a8a5c-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="a8a5c-114">Porady: iterowanie wszystkich węzłów formantu TreeView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="a8a5c-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [<span data-ttu-id="a8a5c-115">Porady: Określanie, który węzeł TreeView został kliknięty</span><span class="sxs-lookup"><span data-stu-id="a8a5c-115">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [<span data-ttu-id="a8a5c-116">Porady: Dodawanie niestandardowych informacji do formantu TreeView lub ListView (formularze systemu Windows)</span><span class="sxs-lookup"><span data-stu-id="a8a5c-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)