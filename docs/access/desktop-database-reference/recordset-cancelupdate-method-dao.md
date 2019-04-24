---
title: CancelUpdate 方法 (DAO)
TOCTitle: CancelUpdate method
ms:assetid: efc4f60b-876f-5e11-37fd-0fbbf225b15b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836421(v=office.15)
ms:contentKeyID: 48548590
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053072
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 5950154d8896678889af01254104a2ac0dfef4cc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300677"
---
# <a name="recordsetcancelupdate-method-dao"></a><span data-ttu-id="7ba3c-102">CancelUpdate 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="7ba3c-102">Recordset.CancelUpdate method (DAO)</span></span>

<span data-ttu-id="7ba3c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7ba3c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7ba3c-104">取消 **[Recordset](recordset-object-dao.md)** 对象的任何待定更新。</span><span class="sxs-lookup"><span data-stu-id="7ba3c-104">Cancels any pending updates for a **[Recordset](recordset-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ba3c-105">语法</span><span class="sxs-lookup"><span data-stu-id="7ba3c-105">Syntax</span></span>

<span data-ttu-id="7ba3c-106">*表达式*。CancelUpdate (***UpdateType***)</span><span class="sxs-lookup"><span data-stu-id="7ba3c-106">*expression* .CancelUpdate(***UpdateType***)</span></span>

<span data-ttu-id="7ba3c-107">*表达式*一个代表**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="7ba3c-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="7ba3c-108">参数</span><span class="sxs-lookup"><span data-stu-id="7ba3c-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7ba3c-109">名称</span><span class="sxs-lookup"><span data-stu-id="7ba3c-109">Name</span></span></p></th>
<th><p><span data-ttu-id="7ba3c-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="7ba3c-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="7ba3c-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="7ba3c-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="7ba3c-112">说明</span><span class="sxs-lookup"><span data-stu-id="7ba3c-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ba3c-113"><em>UpdateType</em></span><span class="sxs-lookup"><span data-stu-id="7ba3c-113"><em>UpdateType</em></span></span></p></td>
<td><p><span data-ttu-id="7ba3c-114">可选</span><span class="sxs-lookup"><span data-stu-id="7ba3c-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="7ba3c-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="7ba3c-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="7ba3c-116">设置为<strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong>值之一。</span><span class="sxs-lookup"><span data-stu-id="7ba3c-116">Set to one of the <strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong> values.</span></span></p><p><span data-ttu-id="7ba3c-117"><strong>注意</strong>: <EM>dbUpdateRegular</EM>和<EM>dbUpdateBatch</EM>值仅在启用批更新时有效。</span><span class="sxs-lookup"><span data-stu-id="7ba3c-117"><strong>NOTE</strong>: The <EM>dbUpdateRegular</EM> and <EM>dbUpdateBatch</EM> values are valid only if batch updating is enabled.</span></span></p>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="7ba3c-118">注解</span><span class="sxs-lookup"><span data-stu-id="7ba3c-118">Remarks</span></span>

<span data-ttu-id="7ba3c-p101">可以使用 **CancelUpdate** 方法取消执行 **[Edit](recordset-edit-method-dao.md)** 或 **[AddNew](recordset-addnew-method-dao.md)** 操作后得到的任何待定更新。例如，如果用户调用了 **Edit** 或 **AddNew** 方法，但尚未调用 **Update** 方法， **CancelUpdate** 将取消 **Edit** 或 **AddNew** 被调用之后所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="7ba3c-p101">You can use the **CancelUpdate** method to cancel any pending updates resulting from an **[Edit](recordset-edit-method-dao.md)** or **[AddNew](recordset-addnew-method-dao.md)** operation. For example, if a user invokes the **Edit** or **AddNew** method and hasn't yet invoked the **Update** method, **CancelUpdate** cancels any changes made after **Edit** or **AddNew** was invoked.</span></span>

<span data-ttu-id="7ba3c-121">检查**Recordset**的**[EditMode](recordset-editmode-property-dao.md)** 属性, 以确定是否存在可以取消的挂起操作。</span><span class="sxs-lookup"><span data-stu-id="7ba3c-121">Check the **[EditMode](recordset-editmode-property-dao.md)** property of the **Recordset** to determine if there is a pending operation that can be canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="7ba3c-122">[!注释] 使用 **CancelUpdate** 方法的效果与在不使用 **[Update](recordset-update-method-dao.md)** 方法的情况下移到另一条记录的效果相同，但是当前记录不发生更改，且不更新各个属性（例如 **[BOF](recordset-bof-property-dao.md)** 和 **[EOF](recordset-eof-property-dao.md)** ）。</span><span class="sxs-lookup"><span data-stu-id="7ba3c-122">Using the **CancelUpdate** method has the same effect as moving to another record without using the **[Update](recordset-update-method-dao.md)** method, except that the current record doesn't change, and various properties, such as **[BOF](recordset-bof-property-dao.md)** and **[EOF](recordset-eof-property-dao.md)**, aren't updated.</span></span>


## <a name="example"></a><span data-ttu-id="7ba3c-123">示例</span><span class="sxs-lookup"><span data-stu-id="7ba3c-123">Example</span></span>

<span data-ttu-id="7ba3c-124">以下示例演示如何将 **CancelUpdate** 方法与 **AddNew** 方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="7ba3c-124">This example shows how the **CancelUpdate** method is used with the **AddNew** method.</span></span>

```vb
    Sub CancelUpdateX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset 
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

<span data-ttu-id="7ba3c-125">以下示例演示如何将 **CancelUpdate** 方法与 **Edit** 方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="7ba3c-125">This example shows how the **CancelUpdate** method is used with the **Edit** method.</span></span>

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

