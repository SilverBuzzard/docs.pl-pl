---
title: Ograniczenia elementu DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fb1fd2c7aa057fcc83c82ab9d72129db2cac680e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="datatable-constraints"></a><span data-ttu-id="c99b1-102">Ograniczenia elementu DataTable</span><span class="sxs-lookup"><span data-stu-id="c99b1-102">DataTable Constraints</span></span>
<span data-ttu-id="c99b1-103">Ograniczenia umożliwiają wymuszenie zastosowania ograniczenia dotyczące danych w <xref:System.Data.DataTable>, aby zapewnić integralność danych.</span><span class="sxs-lookup"><span data-stu-id="c99b1-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="c99b1-104">Ograniczenie jest automatyczne reguły, kolumny lub powiązane kolumny określa sposób postępowania przypadku jakiś sposób zmiany wartości wiersza.</span><span class="sxs-lookup"><span data-stu-id="c99b1-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="c99b1-105">Wymuszone są ograniczenia podczas `System.Data.DataSet.EnforceConstraints` właściwość <xref:System.Data.DataSet> jest **true**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="c99b1-106">Na przykład kodu, który pokazuje, jak ustawić `EnforceConstraints` właściwości, zobacz <xref:System.Data.DataSet.EnforceConstraints%2A> temat referencyjny.</span><span class="sxs-lookup"><span data-stu-id="c99b1-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="c99b1-107">Istnieją dwa rodzaje ograniczeń ADO.NET: <xref:System.Data.ForeignKeyConstraint> i <xref:System.Data.UniqueConstraint>.</span><span class="sxs-lookup"><span data-stu-id="c99b1-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="c99b1-108">Domyślnie oba ograniczenia są tworzone automatycznie podczas tworzenia relacji między co najmniej dwie tabele, dodając <xref:System.Data.DataRelation> do **zestawu danych**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="c99b1-109">Jednak wyłączyć to zachowanie, określając **createConstraints** = **false** podczas tworzenia powiązania.</span><span class="sxs-lookup"><span data-stu-id="c99b1-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="c99b1-110">Element ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="c99b1-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="c99b1-111">A **ForeignKeyConstraint** wymusza stosowanie reguł dotyczących sposobu propagacji aktualizacji i usunięć w tabelach pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="c99b1-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="c99b1-112">Na przykład, jeśli wartość w wierszu jedna tabela jest zaktualizowane lub usunięty i tej samej wartości jest również używana w jednej lub więcej powiązanych tabel **ForeignKeyConstraint** Określa, co się stanie w tabelach pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="c99b1-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="c99b1-113"><xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> i <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> właściwości **ForeignKeyConstraint** definiowania akcji do wykonania, kiedy użytkownik próbuje usunąć lub zaktualizować wiersza powiązanej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c99b1-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="c99b1-114">W poniższej tabeli opisano różne ustawienia dostępne dla **DeleteRule** i **elementu UpdateRule** właściwości **ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="c99b1-115">Ustawienie reguły</span><span class="sxs-lookup"><span data-stu-id="c99b1-115">Rule setting</span></span>|<span data-ttu-id="c99b1-116">Opis</span><span class="sxs-lookup"><span data-stu-id="c99b1-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="c99b1-117">**Kaskadowo**</span><span class="sxs-lookup"><span data-stu-id="c99b1-117">**Cascade**</span></span>|<span data-ttu-id="c99b1-118">Usuń lub zaktualizuj powiązane wiersze.</span><span class="sxs-lookup"><span data-stu-id="c99b1-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="c99b1-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="c99b1-119">**SetNull**</span></span>|<span data-ttu-id="c99b1-120">Ustaw wartości w powiązane wiersze do **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="c99b1-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="c99b1-121">**SetDefault**</span></span>|<span data-ttu-id="c99b1-122">Ustaw wartości w powiązane wiersze do wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="c99b1-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="c99b1-123">**Brak**</span><span class="sxs-lookup"><span data-stu-id="c99b1-123">**None**</span></span>|<span data-ttu-id="c99b1-124">Podejmij żadnej akcji na powiązane wiersze.</span><span class="sxs-lookup"><span data-stu-id="c99b1-124">Take no action on related rows.</span></span> <span data-ttu-id="c99b1-125">Domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="c99b1-125">This is the default.</span></span>|  
  
 <span data-ttu-id="c99b1-126">A **ForeignKeyConstraint** można ograniczyć, również są propagowane, zmiany powiązane kolumny.</span><span class="sxs-lookup"><span data-stu-id="c99b1-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="c99b1-127">W zależności od właściwości ustawione dla **ForeignKeyConstraint** kolumny, jeśli **EnforceConstraints** właściwość **DataSet** jest **true**, wykonywania pewnych operacji na wierszu nadrzędny spowoduje powstanie Wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="c99b1-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="c99b1-128">Na przykład jeśli **DeleteRule** właściwość **ForeignKeyConstraint** jest **Brak**, nie można usunąć wiersza nadrzędnego, jeśli ma ona żadnych wierszy podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="c99b1-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="c99b1-129">Można utworzyć ograniczenia klucza obcego między jednej kolumny lub tablica kolumn za pomocą **ForeignKeyConstraint** konstruktora.</span><span class="sxs-lookup"><span data-stu-id="c99b1-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="c99b1-130">Przekaż powstałe w ten sposób **ForeignKeyConstraint** do obiektu **Dodaj** metody tabeli **ograniczenia** właściwość, która jest **ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="c99b1-131">Można również przekazać argumenty konstruktora do kilku przeciążeń **Dodaj** metody **ConstraintCollection** utworzyć **ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="c99b1-132">Podczas tworzenia **ForeignKeyConstraint**, można przekazać **DeleteRule** i **elementu UpdateRule** wartości do konstruktora jako argumenty, lub można ustawić je jako właściwości jako następujący przykład (gdzie **DeleteRule** ma wartość **Brak**).</span><span class="sxs-lookup"><span data-stu-id="c99b1-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a><span data-ttu-id="c99b1-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="c99b1-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="c99b1-134">Zmiany wiersze mogą być akceptowane przy użyciu **AcceptChanges** metody lub używając anulowane **RejectChanges** metody **DataSet**, **DataTable**, lub **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="c99b1-135">Gdy **DataSet** zawiera **ForeignKeyConstraints**, wywoływanie **AcceptChanges** lub **RejectChanges** metody wymusza  **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="c99b1-136">**AcceptRejectRule** właściwość **ForeignKeyConstraint** Określa, jakie działania zostaną wykonane w elemencie podrzędnym wiersze, kiedy **AcceptChanges** lub  **RejectChanges** jest wywoływana w wierszu nadrzędnej.</span><span class="sxs-lookup"><span data-stu-id="c99b1-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="c99b1-137">W poniższej tabeli wymieniono dostępne ustawienia **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="c99b1-138">Ustawienie reguły</span><span class="sxs-lookup"><span data-stu-id="c99b1-138">Rule setting</span></span>|<span data-ttu-id="c99b1-139">Opis</span><span class="sxs-lookup"><span data-stu-id="c99b1-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="c99b1-140">**Kaskadowo**</span><span class="sxs-lookup"><span data-stu-id="c99b1-140">**Cascade**</span></span>|<span data-ttu-id="c99b1-141">Zaakceptuj lub Odrzuć zmiany do wierszy podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="c99b1-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="c99b1-142">**Brak**</span><span class="sxs-lookup"><span data-stu-id="c99b1-142">**None**</span></span>|<span data-ttu-id="c99b1-143">Nie zająć się wierszy podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="c99b1-143">Take no action on child rows.</span></span> <span data-ttu-id="c99b1-144">Domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="c99b1-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="c99b1-145">Przykład</span><span class="sxs-lookup"><span data-stu-id="c99b1-145">Example</span></span>  
 <span data-ttu-id="c99b1-146">Poniższy przykład tworzy <xref:System.Data.ForeignKeyConstraint>, ustawia niektóre jego właściwości, w tym <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>i dodaje go do <xref:System.Data.ConstraintCollection> z <xref:System.Data.DataTable> obiektu.</span><span class="sxs-lookup"><span data-stu-id="c99b1-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="c99b1-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="c99b1-147">UniqueConstraint</span></span>  
 <span data-ttu-id="c99b1-148">**UniqueConstraint** obiektu, który można przypisać do jednej kolumny lub tablica kolumn w **DataTable**, zapewnia, że wszystkie dane w określonej kolumnie lub kolumnach są unikatowe w każdym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c99b1-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="c99b1-149">Ograniczenia unique dla kolumny lub tablica kolumn można utworzyć przy użyciu **UniqueConstraint** konstruktora.</span><span class="sxs-lookup"><span data-stu-id="c99b1-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="c99b1-150">Przekaż powstałe w ten sposób **UniqueConstraint** do obiektu **Dodaj** metody tabeli **ograniczenia** właściwość, która jest **ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="c99b1-151">Można również przekazać argumenty konstruktora do kilku przeciążeń **Dodaj** metody **ConstraintCollection** utworzyć **UniqueConstraint**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="c99b1-152">Podczas tworzenia **UniqueConstraint** dla kolumny lub kolumn, można opcjonalnie określić kolumny lub kolumn, czy klucz podstawowy.</span><span class="sxs-lookup"><span data-stu-id="c99b1-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="c99b1-153">Można również utworzyć ograniczenia unique dla kolumny, ustawiając **Unique** właściwości kolumny do **true**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="c99b1-154">Możesz też ustawienie **Unique** właściwości pojedynczej kolumny do **false** usuwa unikatowego ograniczenia, które mogą istnieć.</span><span class="sxs-lookup"><span data-stu-id="c99b1-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="c99b1-155">Definiowanie kolumny lub kolumn jako klucz podstawowy dla tabeli automatycznie spowoduje utworzenie unikatowego ograniczenia dla określonej kolumny lub kolumn.</span><span class="sxs-lookup"><span data-stu-id="c99b1-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="c99b1-156">Usunięcie kolumny z **PrimaryKey** właściwość **DataTable**, **UniqueConstraint** zostanie usunięta.</span><span class="sxs-lookup"><span data-stu-id="c99b1-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="c99b1-157">Poniższy przykład tworzy **UniqueConstraint** 2 kolumny **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c99b1-158">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c99b1-158">See Also</span></span>  
 <xref:System.Data.DataRelation>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.ForeignKeyConstraint>  
 <xref:System.Data.UniqueConstraint>  
 [<span data-ttu-id="c99b1-159">Definicja schematu tabeli DataTable</span><span class="sxs-lookup"><span data-stu-id="c99b1-159">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="c99b1-160">Zbiory danych, DataTables i DataViews</span><span class="sxs-lookup"><span data-stu-id="c99b1-160">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="c99b1-161">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="c99b1-161">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)