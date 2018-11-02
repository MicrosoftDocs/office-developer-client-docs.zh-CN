---
title: Recordset2.CancelUpdate 方法 (DAO)
TOCTitle: CancelUpdate Method
ms:assetid: f741dec1-b9a4-506e-74ec-2bc309b0918e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836907(v=office.15)
ms:contentKeyID: 48548761
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 13516830ddb9cb22e8e50872b51743ea5d54ab98
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921486"
---
# <a name="recordset2cancelupdate-method-dao"></a><span data-ttu-id="23ff9-102">Recordset2.CancelUpdate 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="23ff9-102">Recordset2.CancelUpdate method (DAO)</span></span>


<span data-ttu-id="23ff9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="23ff9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="23ff9-104">取消 **[Recordset](recordset-object-dao.md)** 对象的任何待定更新。</span><span class="sxs-lookup"><span data-stu-id="23ff9-104">Cancels any pending updates for a **[Recordset](recordset-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="23ff9-105">语法</span><span class="sxs-lookup"><span data-stu-id="23ff9-105">Syntax</span></span>

<span data-ttu-id="23ff9-106">*表达式*。CancelUpdate (***UpdateType***)</span><span class="sxs-lookup"><span data-stu-id="23ff9-106">*expression* .CancelUpdate(***UpdateType***)</span></span>

<span data-ttu-id="23ff9-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="23ff9-107">*expression* A variable that represents a **Recordset2** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="23ff9-108">参数</span><span class="sxs-lookup"><span data-stu-id="23ff9-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="23ff9-109">名称</span><span class="sxs-lookup"><span data-stu-id="23ff9-109">Name</span></span></p></th>
<th><p><span data-ttu-id="23ff9-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="23ff9-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="23ff9-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="23ff9-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="23ff9-112">说明</span><span class="sxs-lookup"><span data-stu-id="23ff9-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23ff9-113">UpdateType</span><span class="sxs-lookup"><span data-stu-id="23ff9-113">UpdateType</span></span></p></td>
<td><p><span data-ttu-id="23ff9-114">可选</span><span class="sxs-lookup"><span data-stu-id="23ff9-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="23ff9-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="23ff9-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="23ff9-116">设置为<strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong>值之一。</span><span class="sxs-lookup"><span data-stu-id="23ff9-116">Set to one of the <strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong> values.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="23ff9-117"><EM>DbUpdateRegular</EM>和<EM>dbUpdateBatch</EM>值是仅当批更新启用有效。</span><span class="sxs-lookup"><span data-stu-id="23ff9-117">The <EM>dbUpdateRegular</EM> and <EM>dbUpdateBatch</EM> values are valid only if batch updating is enabled.</span></span></P>


</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="23ff9-118">注解</span><span class="sxs-lookup"><span data-stu-id="23ff9-118">Remarks</span></span>

<span data-ttu-id="23ff9-p101">可以使用 **CancelUpdate** 方法取消执行 **[Edit](recordset2-edit-method-dao.md)** 或 **[AddNew](recordset2-addnew-method-dao.md)** 操作后得到的任何待定更新。例如，如果用户调用了 **Edit** 或 **AddNew** 方法，但尚未调用 **Update** 方法， **CancelUpdate** 将取消 **Edit** 或 **AddNew** 被调用之后所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="23ff9-p101">You can use the **CancelUpdate** method to cancel any pending updates resulting from an **[Edit](recordset2-edit-method-dao.md)** or **[AddNew](recordset2-addnew-method-dao.md)** operation. For example, if a user invokes the **Edit** or **AddNew** method and hasn't yet invoked the **Update** method, **CancelUpdate** cancels any changes made after **Edit** or **AddNew** was invoked.</span></span>

<span data-ttu-id="23ff9-121">检查 [Recordset](recordset2-editmode-property-dao.md) 的 \*\*\*\*EditMode\*\*\*\* 属性，以确定是否存在可以取消的待定操作。</span><span class="sxs-lookup"><span data-stu-id="23ff9-121">Check the **[EditMode](recordset2-editmode-property-dao.md)** property of the **Recordset** to determine if there is a pending operation that can be canceled.</span></span>


> [!NOTE]
> <P><span data-ttu-id="23ff9-122">[!注释] 使用 <STRONG>CancelUpdate</STRONG> 方法的效果与在不使用 <STRONG><A href="recordset2-update-method-dao.md">Update</A></STRONG> 方法的情况下移到另一条记录的效果相同，但是当前记录不发生更改，且不更新各个属性（例如 <STRONG><A href="recordset2-bof-property-dao.md">BOF</A></STRONG> 和 <STRONG><A href="recordset2-eof-property-dao.md">EOF</A></STRONG> ）。</span><span class="sxs-lookup"><span data-stu-id="23ff9-122">Using the <STRONG>CancelUpdate</STRONG> method has the same effect as moving to another record without using the <STRONG><A href="recordset2-update-method-dao.md">Update</A></STRONG> method, except that the current record doesn't change, and various properties, such as <STRONG><A href="recordset2-bof-property-dao.md">BOF</A></STRONG> and <STRONG><A href="recordset2-eof-property-dao.md">EOF</A></STRONG>, aren't updated.</span></span></P>



## <a name="example"></a><span data-ttu-id="23ff9-123">示例</span><span class="sxs-lookup"><span data-stu-id="23ff9-123">Example</span></span>

<span data-ttu-id="23ff9-124">以下示例演示如何将 **CancelUpdate** 方法与 **AddNew** 方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="23ff9-124">This example shows how the **CancelUpdate** method is used with the **AddNew** method.</span></span>

```vb
    Sub CancelUpdateX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset2 
       Dim intCommand As Integer 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstEmployees = dbsNorthwind.OpenRecordset( _ 
          "Employees", dbOpenDynaset) 
     
       With rstEmployees 
          .AddNew 
          !FirstName = "Kimberly" 
          !LastName = "Bowen" 
          intCommand = MsgBox("Add new record for " & _ 
             !FirstName & " " & !LastName & "?", vbYesNo) 
          If intCommand = vbYes Then 
             .Update 
             MsgBox "Record added." 
             ' Delete new record because this is a  
             ' demonstration. 
             .Bookmark = .LastModified 
             .Delete 
          Else 
             .CancelUpdate 
             MsgBox "Record not added." 
          End If 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="23ff9-125">以下示例演示如何将 **CancelUpdate** 方法与 **Edit** 方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="23ff9-125">This example shows how the **CancelUpdate** method is used with the **Edit** method.</span></span>

```vb
Sub CancelUpdateX2() 
 
   Dim dbsNorthwind As Database 
   Dim rstEmployees As Recordset 
   Dim strFirst As String 
   Dim strLast As String 
   Dim intCommand As Integer 
 
   Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
   Set rstEmployees = dbsNorthwind.OpenRecordset( _ 
      "Employees", dbOpenDynaset) 
 
   With rstEmployees 
      strFirst = !FirstName 
      strLast = !LastName 
      .Edit 
      !FirstName = "Cora" 
      !LastName = "Edmonds" 
      intCommand = MsgBox("Replace current name with " & _ 
         !FirstName & " " & !LastName & "?", vbYesNo) 
      If intCommand = vbYes Then 
         .Update 
         MsgBox "Record modified." 
         ' Restore data because this is a demonstration. 
         .Bookmark = .LastModified 
         .Edit 
         !FirstName = strFirst 
         !LastName = strLast 
         .Update 
      Else 
         .CancelUpdate 
         MsgBox "Record not modified." 
      End If 
      .Close 
   End With 
 
   dbsNorthwind.Close 
 
End Sub 
 
```

