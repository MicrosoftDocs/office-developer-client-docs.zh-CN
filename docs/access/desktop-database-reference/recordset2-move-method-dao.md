---
title: Recordset2.Move Method (DAO)
TOCTitle: Move Method
ms:assetid: df39c05e-c5f8-3b66-fa5f-c91b687c147d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835635(v=office.15)
ms:contentKeyID: 48548211
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8d99e8528c5f75a2f5c5d40834650eabbed2505d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468223"
---
# <a name="recordset2move-method-dao"></a><span data-ttu-id="d4cdd-102">Recordset2.Move Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="d4cdd-102">Recordset2.Move Method (DAO)</span></span>


<span data-ttu-id="d4cdd-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d4cdd-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d4cdd-104">移动 **[Recordset](recordset-object-dao.md)** 对象中的当前记录的位置。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-104">Moves the position of the current record in a **[Recordset](recordset-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="d4cdd-105">语法</span><span class="sxs-lookup"><span data-stu-id="d4cdd-105">Syntax</span></span>

<span data-ttu-id="d4cdd-106">*表达式*。移动 （***行***、 ***StartBookmark***）</span><span class="sxs-lookup"><span data-stu-id="d4cdd-106">*expression* .Move(***Rows***, ***StartBookmark***)</span></span>

<span data-ttu-id="d4cdd-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-107">*expression* A variable that represents a **Recordset2** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="d4cdd-108">参数</span><span class="sxs-lookup"><span data-stu-id="d4cdd-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d4cdd-109">名称</span><span class="sxs-lookup"><span data-stu-id="d4cdd-109">Name</span></span></p></th>
<th><p><span data-ttu-id="d4cdd-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="d4cdd-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="d4cdd-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="d4cdd-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="d4cdd-112">说明</span><span class="sxs-lookup"><span data-stu-id="d4cdd-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4cdd-113">行</span><span class="sxs-lookup"><span data-stu-id="d4cdd-113">Rows</span></span></p></td>
<td><p><span data-ttu-id="d4cdd-114">必需</span><span class="sxs-lookup"><span data-stu-id="d4cdd-114">Required</span></span></p></td>
<td><p><span data-ttu-id="d4cdd-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="d4cdd-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="d4cdd-p101">位置移动的行数。如果 rows 大于 0，则位置向前移（向文件的末尾处移动）。如果 rows 小于 0，则位置向后移（向文件的开头处移动）。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-p101">The number of rows the position will move. If rows is greater than 0, the position is moved forward (toward the end of the file). If rows is less than 0, the position is moved backward (toward the beginning of the file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4cdd-119">StartBookmark</span><span class="sxs-lookup"><span data-stu-id="d4cdd-119">StartBookmark</span></span></p></td>
<td><p><span data-ttu-id="d4cdd-120">可选</span><span class="sxs-lookup"><span data-stu-id="d4cdd-120">Optional</span></span></p></td>
<td><p><span data-ttu-id="d4cdd-121"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="d4cdd-121"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="d4cdd-p102">一个标识书签的值。如果指定了 startbookmark，则相对于此书签开始移动。否则，从当前记录开始移动。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-p102">A value identifying a bookmark. If you specify startbookmark, the move begins relative to this bookmark. Otherwise, Move begins from the current record.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="d4cdd-125">注解</span><span class="sxs-lookup"><span data-stu-id="d4cdd-125">Remarks</span></span>

<span data-ttu-id="d4cdd-p103">如果使用 **Move** 将当前记录指针定位在第一条记录之前，当前记录指针将移到文件的开头。如果 **Recordset** 不包含记录，并且它的 **[BOF](recordset2-bof-property-dao.md)** 属性为 **True**，则使用此方法后移会导致错误。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-p103">If you use **Move** to position the current record pointer before the first record, the current record pointer moves to the beginning of the file. If the **Recordset** contains no records and its **[BOF](recordset2-bof-property-dao.md)** property is **True**, using this method to move backward causes an error.</span></span>

<span data-ttu-id="d4cdd-p104">如果使用 **Move** 将当前记录指针定位在最后一条记录之后，当前记录指针将移到文件的末尾。如果 **Recordset** 不包含记录，并且它的 **[EOF](recordset2-eof-property-dao.md)** 属性为 **True**，则使用此方法前移会导致错误。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-p104">If you use **Move** to position the current record pointer after the last record, the current record pointer position moves to the end of the file. If the **Recordset** contains no records and its **[EOF](recordset2-eof-property-dao.md)** property is **True**, then using this method to move forward causes an error.</span></span>

<span data-ttu-id="d4cdd-130">如果 **BOF** 和 **EOF** 属性中的一个为 **True**，并且您试图在不使用有效书签的情况下使用 **Move** 方法，将会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-130">If either the **BOF** or **EOF** property is **True** and you attempt to use the **Move** method without a valid bookmark, a run-time error occurs.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="d4cdd-p105">如果对仅向前类型的 <STRONG>Recordset</STRONG> 对象使用 <STRONG>Move</STRONG>，则行参数必须是正整数，并且不允许使用书签。这意识着您只能前移。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-p105">When you use <STRONG>Move</STRONG> on a forward-only-type <STRONG>Recordset</STRONG> object, the rows argument must be a positive integer and bookmarks aren't allowed. This means you can only move forward.</span></span></P>
> <LI>
> <P><span data-ttu-id="d4cdd-133">若要使 <STRONG>Recordset</STRONG> 中的第一条、最后一条、下一条或上一条记录成为当前记录，请使用 <STRONG>MoveFirst</STRONG>、 <STRONG>MoveLast</STRONG>、 <STRONG>MoveNext</STRONG> 和 <STRONG>MovePrevious</STRONG> 方法之一。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-133">To make the first, last, next, or previous record in a <STRONG>Recordset</STRONG> the current record, use either the <STRONG>MoveFirst</STRONG>, <STRONG>MoveLast</STRONG>, <STRONG>MoveNext</STRONG>, or <STRONG>MovePrevious</STRONG> method.</span></span></P>
> <LI>
> <P><span data-ttu-id="d4cdd-p106">在行等于 0 的情况下使用 <STRONG>Move</STRONG> 是检索当前记录的基础数据的简易方法。如果要确保当前记录具有基表中的最新数据，使用此方法十分有用。它还会取消任何待定的 <STRONG><A href="recordset2-edit-method-dao.md">Edit</A></STRONG> 或 <STRONG><A href="recordset-addnew-method-dao.md">AddNew</A></STRONG> 调用。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-p106">Using <STRONG>Move</STRONG> with rows equal to 0 is an easy way to retrieve the underlying data for the current record. This is useful if you want to make sure that the current record has the most recent data from the base tables. It will also cancel any pending <STRONG><A href="recordset2-edit-method-dao.md">Edit</A></STRONG> or <STRONG><A href="recordset-addnew-method-dao.md">AddNew</A></STRONG> calls.</span></span></P></LI></UL>



## <a name="example"></a><span data-ttu-id="d4cdd-137">示例</span><span class="sxs-lookup"><span data-stu-id="d4cdd-137">Example</span></span>

<span data-ttu-id="d4cdd-138">以下示例使用 **Move** 方法基于用户输入来定位记录指针。</span><span class="sxs-lookup"><span data-stu-id="d4cdd-138">This example uses the **Move** method to position the record pointer based on user input.</span></span>

```vb
    Sub MoveX() 
     
       Dim dbsNorthwind As Database 
       Dim rstSuppliers As Recordset2 
       Dim varBookmark As Variant 
       Dim strCommand As String 
       Dim lngMove As Long 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstSuppliers = _ 
          dbsNorthwind.OpenRecordset("SELECT CompanyName, " & _ 
          "City, Country FROM Suppliers ORDER BY CompanyName", _ 
          dbOpenDynaset) 
     
       With rstSuppliers 
          ' Populate recordset. 
          .MoveLast 
          .MoveFirst 
     
          Do While True 
             ' Display information about current record and ask  
             ' how many records to move. 
             strCommand = InputBox( _ 
                "Record " & (.AbsolutePosition + 1) & " of " & _ 
                .RecordCount & vbCr & "Company: " & _ 
                !CompanyName & vbCr & "Location: " & !City & _ 
                ", " & !Country & vbCr & vbCr & _ 
                "Enter number of records to Move " & _ 
                "(positive or negative).") 
     
             If strCommand = "" Then Exit Do 
     
             ' Store bookmark in case the Move doesn't work. 
             varBookmark = .Bookmark 
     
             ' Move method requires parameter of data type Long. 
             lngMove = CLng(strCommand) 
             .Move lngMove 
     
             ' Trap for BOF or EOF. 
             If .BOF Then 
                MsgBox "Too far backward! " & _ 
                   "Returning to current record." 
                .Bookmark = varBookmark 
             End If 
             If .EOF Then 
                MsgBox "Too far forward! " & _ 
                   "Returning to current record." 
                .Bookmark = varBookmark 
             End If 
          Loop 
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub
```
