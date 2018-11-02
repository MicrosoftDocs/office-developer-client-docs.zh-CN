---
title: Recordset.PercentPosition 属性 (DAO)
TOCTitle: PercentPosition Property
ms:assetid: aebbda44-ed72-7a6c-0cd5-28c8997d4d96
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821751(v=office.15)
ms:contentKeyID: 48547077
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 31f1cbf1f6bbc2f2c7ce855cccb667e71638b1b8
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929567"
---
# <a name="recordsetpercentposition-property-dao"></a><span data-ttu-id="c6509-102">Recordset.PercentPosition 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c6509-102">Recordset.PercentPosition property (DAO)</span></span>


<span data-ttu-id="c6509-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c6509-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c6509-104">设置或返回一个值，用于根据 [Recordset](recordset-object-dao.md) 中的记录百分比指示 \*\*\*\*Recordset\*\*\*\* 对象中当前记录的大概位置。</span><span class="sxs-lookup"><span data-stu-id="c6509-104">Sets or returns a value indicating the approximate location of the current record in the **[Recordset](recordset-object-dao.md)** object based on a percentage of the records in the **Recordset**.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6509-105">语法</span><span class="sxs-lookup"><span data-stu-id="c6509-105">Syntax</span></span>

<span data-ttu-id="c6509-106">*表达式*。PercentPosition</span><span class="sxs-lookup"><span data-stu-id="c6509-106">*expression* .PercentPosition</span></span>

<span data-ttu-id="c6509-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c6509-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6509-108">注解</span><span class="sxs-lookup"><span data-stu-id="c6509-108">Remarks</span></span>

<span data-ttu-id="c6509-p101">若要指示或更改 **Recordset** 对象中的当前记录的大概位置，可以检查或设置 **PercentPosition** 属性。当使用从基表直接打开的动态集类型或快照类型的 **Recordset** 对象时，在设置或检查 **PercentPosition** 属性之前，请首先通过移动到最后一条记录来填充 **Recordset** 对象。如果在完全填充 **Recordset** 对象之前使用 **PercentPosition** 属性，则移动量与 **[RecordCount](recordset-recordcount-property-dao.md)** 属性设置所指定的访问记录数相关。您可以使用 **[MoveLast](recordset-movelast-method-dao.md)** 方法来移动到最后一条记录。</span><span class="sxs-lookup"><span data-stu-id="c6509-p101">To indicate or change the approximate position of the current record in a **Recordset** object, you can check or set the **PercentPosition** property. When working with a dynaset- or snapshot-type **Recordset** object opened directly from a base table, first populate the **Recordset** object by moving to the last record before you set or check the **PercentPosition** property. If you use the **PercentPosition** property before fully populating the **Recordset** object, the amount of movement is relative to the number of records accessed as indicated by the **[RecordCount](recordset-recordcount-property-dao.md)** property setting. You can move to the last record by using the **[MoveLast](recordset-movelast-method-dao.md)** method.</span></span>


> [!NOTE]
> <P><span data-ttu-id="c6509-113">[!注释] 为什么不建议使用 <STRONG>PercentPosition</STRONG> 属性将当前记录移动到 <STRONG>Recordset</STRONG> 对象中的特定记录呢？这是因为 <STRONG><A href="recordset-bookmark-property-dao.md">Bookmark</A></STRONG> 属性更适合这项任务。</span><span class="sxs-lookup"><span data-stu-id="c6509-113">Using the <STRONG>PercentPosition</STRONG> property to move the current record to a specific record in a <STRONG>Recordset</STRONG> object isn't recommended?the <STRONG><A href="recordset-bookmark-property-dao.md">Bookmark</A></STRONG> property is better suited for this task.</span></span></P>



<span data-ttu-id="c6509-p102">一旦将 **PercentPosition** 属性设置为某个值，与该值对应的大概位置处的记录就成为当前记录，且 **PercentPosition** 属性重置为反映当前记录的大概位置的值。例如，如果 **Recordset** 对象只包含五条记录，而您将其 **PercentPosition** 属性值设置为 77，则从 **PercentPosition** 属性返回的值可能是 80，而不是 77。</span><span class="sxs-lookup"><span data-stu-id="c6509-p102">Once you set the **PercentPosition** property to a value, the record at the approximate position corresponding to that value becomes current, and the **PercentPosition** property is reset to a value that reflects the approximate position of the current record. For example, if your **Recordset** object contains only five records, and you set its **PercentPosition** property value to 77, the value returned from the **PercentPosition** property may be 80, not 77.</span></span>

<span data-ttu-id="c6509-116">**PercentPosition**属性应用于所有类型的**Recordset**对象，但仅向前类型**Recordset**对象或从针对远程数据库的传递查询打开的**Recordset**对象除外。</span><span class="sxs-lookup"><span data-stu-id="c6509-116">The **PercentPosition** property applies to all types of **Recordset** objects except for forward–only–type **Recordset** objects or **Recordset** objects opened from pass-through queries against remote databases.</span></span>

<span data-ttu-id="c6509-117">您可以将 **PercentPosition** 属性用于窗体或文本框上的滚动条，以指示 **Recordset** 对象中当前记录的位置。</span><span class="sxs-lookup"><span data-stu-id="c6509-117">You can use the **PercentPosition** property with a scroll bar on a form or text box to indicate the location of the current record in a **Recordset** object.</span></span>

## <a name="example"></a><span data-ttu-id="c6509-118">示例</span><span class="sxs-lookup"><span data-stu-id="c6509-118">Example</span></span>

<span data-ttu-id="c6509-119">以下示例使用 **PercentPosition** 属性显示当前记录指针相对于 **Recordset** 起点的位置。</span><span class="sxs-lookup"><span data-stu-id="c6509-119">This example uses the **PercentPosition** property to show the position of the current record pointer relative to the beginning of the **Recordset**.</span></span>

```vb
    Sub PercentPositionX() 
     
     Dim dbsNorthwind As Database 
     Dim rstProducts As Recordset 
     Dim strFind As String 
     Dim strMessage As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     ' PercentPosition only works with dynasets or snapshots. 
     Set rstProducts = dbsNorthwind.OpenRecordset( _ 
     "SELECT ProductName FROM Products " & _ 
     "ORDER BY ProductName", dbOpenSnapshot) 
     
     With rstProducts 
     ' Populate the Recordset. 
     .MoveLast 
     .MoveFirst 
     
     Do While True 
     ' Show current record information and ask user 
     ' for input. 
     strMessage = "Product: " & !ProductName & vbCr & _ 
     "The record pointer is " & _ 
     Format(.PercentPosition, "##0.0") & _ 
     "% from the " & vbCr & _ 
     "beginning of the Recordset." & vbCr & _ 
     "Please enter a character search string " & _ 
     "for a product name." 
     strFind = Trim(InputBox(strMessage)) 
     If strFind = "" Then Exit Do 
     
     ' Try to find a record matching the search string. 
     .FindFirst "ProductName >= '" & strFind & "'" 
     If .NoMatch Then .MoveLast 
     Loop 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub
```
