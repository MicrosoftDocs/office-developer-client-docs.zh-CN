---
title: Recordset2.AbsolutePosition 属性 (DAO)
TOCTitle: AbsolutePosition Property
ms:assetid: 91ca203f-0c80-67f4-e180-415b6af05030
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197637(v=office.15)
ms:contentKeyID: 48546358
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053074
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 6adf3e5ec2ec36163d4818411a1abc07e940b209
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922683"
---
# <a name="recordset2absoluteposition-property-dao"></a><span data-ttu-id="e0e91-102">Recordset2.AbsolutePosition 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e0e91-102">Recordset2.AbsolutePosition property (DAO)</span></span>


<span data-ttu-id="e0e91-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e0e91-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e0e91-104">设置或返回 **Recordset2** 对象的当前记录的相对记录编号。</span><span class="sxs-lookup"><span data-stu-id="e0e91-104">Sets or returns the relative record number of a **Recordset2** object's current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0e91-105">语法</span><span class="sxs-lookup"><span data-stu-id="e0e91-105">Syntax</span></span>

<span data-ttu-id="e0e91-106">*表达式*。AbsolutePosition</span><span class="sxs-lookup"><span data-stu-id="e0e91-106">*expression* .AbsolutePosition</span></span>

<span data-ttu-id="e0e91-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e0e91-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0e91-108">注解</span><span class="sxs-lookup"><span data-stu-id="e0e91-108">Remarks</span></span>

<span data-ttu-id="e0e91-p101">可以根据特定记录在动态集类型或快照类型 **Recordset2** 对象中的序号位置，使用 **AbsolutePosition** 属性将当前记录指针定位到该特定记录。还可以通过检查 **AbsolutePosition** 属性设置来确定当前记录编号。</span><span class="sxs-lookup"><span data-stu-id="e0e91-p101">You can use the **AbsolutePosition** property to position the current record pointer to a specific record based on its ordinal position in a dynaset- or snapshot-type **Recordset2** object. You can also determine the current record number by checking the **AbsolutePosition** property setting.</span></span>

<span data-ttu-id="e0e91-p102">由于 **AbsolutePosition** 属性值从零开始（即设置 0 引用 **Recordset2** 对象中的第一条记录），因此您不能将其设置为大于或等于填充记录数的值；如果这样做，会导致可捕获的错误。您可以通过检查 **RecordCount** 属性设置来确定 **Recordset2** 对象中填充的记录数。 **AbsolutePosition** 属性的最大允许设置为 **RecordCount** 属性的值减 1。</span><span class="sxs-lookup"><span data-stu-id="e0e91-p102">Because the **AbsolutePosition** property value is zero-based (that is, a setting of 0 refers to the first record in the **Recordset2** object), you cannot set it to a value greater than or equal to the number of populated records; doing so causes a trappable error. You can determine the number of populated records in the **Recordset2** object by checking the **RecordCount** property setting. The maximum allowable setting for the **AbsolutePosition** property is the value of the **RecordCount** property minus 1.</span></span>

<span data-ttu-id="e0e91-114">如果没有当前记录，作为**Recordset2**对象中任何记录时， **AbsolutePosition**返回-1。</span><span class="sxs-lookup"><span data-stu-id="e0e91-114">If there is no current record, as when there are no records in the **Recordset2** object, **AbsolutePosition** returns –1.</span></span> <span data-ttu-id="e0e91-115">如果删除了当前记录，则 **AbsolutePosition** 属性值将是不确定的，并且，当引用该记录时将会发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="e0e91-115">If the current record is deleted, the **AbsolutePosition** property value isn't defined, and a trappable error occurs if it's referenced.</span></span> <span data-ttu-id="e0e91-116">新记录将添加到序列的末尾。</span><span class="sxs-lookup"><span data-stu-id="e0e91-116">New records are added to the end of the sequence.</span></span>

<span data-ttu-id="e0e91-p104">不应将该属性用作代理记录编号。仍然建议采用书签保留和返回到给定位置，而且这是在所有类型的 **Recordset2** 对象之间定位当前记录的唯一方法。特别是，当某记录之前的一条或多条记录被删除时，该记录的位置就会更改。如果再次重新创建 **Recordset2** 对象，也无法保证记录具有相同的绝对位置，这是因为除非使用带有 ORDER BY 子句的 SQL 语句来创建 **Recordset** 对象，否则该对象中的各个记录的顺序将是无法保证的。</span><span class="sxs-lookup"><span data-stu-id="e0e91-p104">You shouldn't use this property as a surrogate record number. Bookmarks are still the recommended way of retaining and returning to a given position and are the only way to position the current record across all types of **Recordset2** objects. In particular, the position of a record changes when one or more records preceding it are deleted. There is also no assurance that a record will have the same absolute position if the **Recordset2** object is re-created again because the order of individual records within a **Recordset** object isn't guaranteed unless it's created with an SQL statement by using an ORDER BY clause.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="e0e91-p105">对于新打开但尚未填充的 <STRONG>Recordset2</STRONG> 对象，如果将 <STRONG>AbsolutePosition</STRONG> 属性设置为大于零的值，则会导致可捕获的错误。请首先使用 <STRONG>MoveLast</STRONG> 方法填充 <STRONG>Recordset2</STRONG> 对象。</span><span class="sxs-lookup"><span data-stu-id="e0e91-p105">Setting the <STRONG>AbsolutePosition</STRONG> property to a value greater than zero on a newly opened but unpopulated <STRONG>Recordset2</STRONG> object causes a trappable error. Populate the <STRONG>Recordset2</STRONG> object first with the <STRONG>MoveLast</STRONG> method.</span></span></P>
> <LI>
> <P><span data-ttu-id="e0e91-123">仅向前类型<STRONG>Recordset2</STRONG>对象，或者对于从针对 Microsoft Access 数据库引擎连接的 ODBC 数据库的传递查询打开的<STRONG>Recordset2</STRONG>对象， <STRONG>AbsolutePosition</STRONG>属性不可用。</span><span class="sxs-lookup"><span data-stu-id="e0e91-123">The <STRONG>AbsolutePosition</STRONG> property isn't available on forward–only–type <STRONG>Recordset2</STRONG> objects, or on <STRONG>Recordset2</STRONG> objects opened from pass-through queries against Microsoft Access database engine-connected ODBC databases.</span></span></P></LI></UL>



## <a name="example"></a><span data-ttu-id="e0e91-124">示例</span><span class="sxs-lookup"><span data-stu-id="e0e91-124">Example</span></span>

<span data-ttu-id="e0e91-125">以下示例使用 **AbsolutePosition** 属性跟踪枚举 **Recordset2** 的所有记录的循环的进度。</span><span class="sxs-lookup"><span data-stu-id="e0e91-125">This example uses the **AbsolutePosition** property to track the progress of a loop that enumerates all the records of a **Recordset2**.</span></span>

```vb
    Sub AbsolutePositionX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset2 
       Dim strMessage As String 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       ' AbsolutePosition only works with dynasets or snapshots. 
       Set rstEmployees = _ 
          dbsNorthwind.OpenRecordset("Employees", _ 
          dbOpenSnapshot) 
     
       With rstEmployees 
          ' Populate Recordset. 
          .MoveLast 
          .MoveFirst 
     
          ' Enumerate Recordset. 
          Do While Not .EOF 
             ' Display current record information. Add 1 to  
             ' AbsolutePosition value because it is zero-based. 
             strMessage = "Employee: " & !LastName & vbCr & _ 
                "(record " & (.AbsolutePosition + 1) & _ 
                " of " & .RecordCount & ")" 
             If MsgBox(strMessage, vbOKCancel) = vbCancel _ 
                Then Exit Do 
             .MoveNext 
          Loop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub
```
