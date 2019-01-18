---
title: Recordset2.RecordCount 属性 (DAO)
TOCTitle: RecordCount Property
ms:assetid: 77852966-11e9-1773-6e58-53927b84c03b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196071(v=office.15)
ms:contentKeyID: 48545728
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052890
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: c23de433f26b5a54b3fee5cc69f67a07b53f8a3b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699259"
---
# <a name="recordset2recordcount-property-dao"></a><span data-ttu-id="bba69-102">Recordset2.RecordCount 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bba69-102">Recordset2.RecordCount property (DAO)</span></span>

<span data-ttu-id="bba69-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bba69-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bba69-p101">返回在 **[Recordset](recordset-object-dao.md)** 对象中访问的记录数，或者返回表类型 **Recordset** 对象或 **[TableDef](tabledef-object-dao.md)** 对象中的记录总数。只读 **Long**。</span><span class="sxs-lookup"><span data-stu-id="bba69-p101">Returns the number of records accessed in a **[Recordset](recordset-object-dao.md)** object, or the total number of records in a table-type **Recordset** object. or **[TableDef](tabledef-object-dao.md)** object. Read-only **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="bba69-107">语法</span><span class="sxs-lookup"><span data-stu-id="bba69-107">Syntax</span></span>

<span data-ttu-id="bba69-108">*表达式*。RecordCount</span><span class="sxs-lookup"><span data-stu-id="bba69-108">*expression* .RecordCount</span></span>

<span data-ttu-id="bba69-109">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bba69-109">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="bba69-110">注解</span><span class="sxs-lookup"><span data-stu-id="bba69-110">Remarks</span></span>

<span data-ttu-id="bba69-111">使用 **RecordCount** 属性可以了解 **Recordset** 或 **TableDef** 对象中已经访问的对象数。</span><span class="sxs-lookup"><span data-stu-id="bba69-111">Use the **RecordCount** property to find out how many records in a **Recordset** or **TableDef** object have been accessed.</span></span> <span data-ttu-id="bba69-112">**RecordCount**属性不指示多少记录包含在动态集类型、 快照类型或仅向前类型**Recordset**对象之前已经被访问过的所有记录。</span><span class="sxs-lookup"><span data-stu-id="bba69-112">The **RecordCount** property doesn't indicate how many records are contained in a dynaset–, snapshot–, or forward–only–type **Recordset** object until all records have been accessed.</span></span> <span data-ttu-id="bba69-113">一旦访问完最后一条记录， **RecordCount** 属性就会指示 **Recordset** 或 **TableDef** 对象中未被删除的记录的总数。</span><span class="sxs-lookup"><span data-stu-id="bba69-113">Once the last record has been accessed, the **RecordCount** property indicates the total number of undeleted records in the **Recordset** or **TableDef** object.</span></span> <span data-ttu-id="bba69-114">若要强制访问最后一条记录，请对 [Recordset](recordset2-movelast-method-dao.md) 对象使用 \*\*\*\*MoveLast\*\*\*\* 方法。</span><span class="sxs-lookup"><span data-stu-id="bba69-114">To force the last record to be accessed, use the **[MoveLast](recordset2-movelast-method-dao.md)** method on the **Recordset** object.</span></span> <span data-ttu-id="bba69-115">您还可以使用 SQL **Count** 函数确定查询将返回的大概记录数。</span><span class="sxs-lookup"><span data-stu-id="bba69-115">You can also use an SQL **Count** function to determine the approximate number of records your query will return.</span></span>

> [!NOTE]
> <span data-ttu-id="bba69-p103">[!注释] 使用 **MoveLast** 方法填充新打开的 **Recordset** 会对性能造成负面影响。除非在您打开 **Recordset** 时必须得到准确的 **RecordCount**，否则最好等到使用代码的其他部分填充完 **Recordset** 之后，再检查 **RecordCount** 属性。</span><span class="sxs-lookup"><span data-stu-id="bba69-p103">Using the **MoveLast** method to populate a newly opened **Recordset** negatively impacts performance. Unless it is necessary to have an accurate **RecordCount** as soon as you open a **Recordset**, it's better to wait until you populate the **Recordset** with other portions of code before checking the **RecordCount** property.</span></span>

<span data-ttu-id="bba69-p104">由于应用程序删除了动态集类型 **Recordset** 对象中的记录，因此 **RecordCount** 属性的值将减小。但是，其他用户删除的记录不受 **RecordCount** 属性的影响，除非当前记录定位到已删除的记录。如果执行的事务处理影响 **RecordCount** 属性设置，之后您又回滚了该事务，则 **RecordCount** 属性将不会反映其余记录的实际数目。</span><span class="sxs-lookup"><span data-stu-id="bba69-p104">As your application deletes records in a dynaset-type **Recordset** object, the value of the **RecordCount** property decreases. However, records deleted by other users aren't reflected by the **RecordCount** property until the current record is positioned to a deleted record. If you execute a transaction that affects the **RecordCount** property setting and you subsequently roll back the transaction, the **RecordCount** property won't reflect the actual number of remaining records.</span></span>

<span data-ttu-id="bba69-121">快照 – 或向前仅类型**Recordset**对象的**RecordCount**属性不受基础表中的更改。</span><span class="sxs-lookup"><span data-stu-id="bba69-121">The **RecordCount** property of a snapshot– or forward–only–type **Recordset** object isn't affected by changes in the underlying tables.</span></span>

<span data-ttu-id="bba69-122">如果 **Recordset** 或 **TableDef** 对象不含记录，则其 **RecordCount** 属性设置为 0。</span><span class="sxs-lookup"><span data-stu-id="bba69-122">A **Recordset** or **TableDef** object with no records has a **RecordCount** property setting of 0.</span></span>

<span data-ttu-id="bba69-123">对 [Recordset](recordset2-requery-method-dao.md) 对象使用 \*\*\*\*Requery\*\*\*\* 方法将会重置 **RecordCount** 属性，如同重新执行查询一样。</span><span class="sxs-lookup"><span data-stu-id="bba69-123">Using the **[Requery](recordset2-requery-method-dao.md)** method on a **Recordset** object resets the **RecordCount** property just as if the query were re-executed.</span></span>

## <a name="example"></a><span data-ttu-id="bba69-124">示例</span><span class="sxs-lookup"><span data-stu-id="bba69-124">Example</span></span>

<span data-ttu-id="bba69-125">以下示例演示填充不同类型的 **Recordsets** 之前和之后的 **RecordCount** 属性。</span><span class="sxs-lookup"><span data-stu-id="bba69-125">This example demonstrates the **RecordCount** property with different types of **Recordsets** before and after they're populated.</span></span>

```vb
    Sub RecordCountX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset2 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Open table-type Recordset and show RecordCount 
     ' property. 
     Set rstEmployees = .OpenRecordset("Employees") 
     Debug.Print _ 
     "Table-type recordset from Employees table" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     rstEmployees.Close 
     
     ' Open dynaset-type Recordset and show RecordCount 
     ' property before populating the Recordset. 
     Set rstEmployees = .OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     Debug.Print "Dynaset-type recordset " & _ 
     "from Employees table before MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     
     ' Show the RecordCount property after populating the 
     ' Recordset. 
     rstEmployees.MoveLast 
     Debug.Print "Dynaset-type recordset " & _ 
     "from Employees table after MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     rstEmployees.Close 
     
     ' Open snapshot-type Recordset and show RecordCount 
     ' property before populating the Recordset. 
     Set rstEmployees = .OpenRecordset("Employees", _ 
     dbOpenSnapshot) 
     Debug.Print "Snapshot-type recordset " & _ 
     "from Employees table before MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     
     ' Show the RecordCount property after populating the 
     ' Recordset. 
     rstEmployees.MoveLast 
     Debug.Print "Snapshot-type recordset " & _ 
     "from Employees table after MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     rstEmployees.Close 
     
     ' Open forward-only-type Recordset and show 
     ' RecordCount property before populating the 
     ' Recordset. 
     Set rstEmployees = .OpenRecordset("Employees", _ 
     dbOpenForwardOnly) 
     Debug.Print "Forward-only-type recordset " & _ 
     "from Employees table before MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     
     ' Show the RecordCount property after calling the 
     ' MoveNext method. 
     rstEmployees.MoveNext 
     Debug.Print "Forward-only-type recordset " & _ 
     "from Employees table after MoveNext" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     rstEmployees.Close 
     
     .Close 
     End With 
     
    End Sub
```
