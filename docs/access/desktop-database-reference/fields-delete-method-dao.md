---
title: Fields.Delete 方法 (DAO)
TOCTitle: Delete Method
ms:assetid: a8e249e7-7526-3eff-a5cf-70cab2081970
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821417(v=office.15)
ms:contentKeyID: 48546913
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052868
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 8200d8ec7b10f33fe8bc1ef9faea122d3ff65409
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720987"
---
# <a name="fieldsdelete-method-dao"></a><span data-ttu-id="acff4-102">Fields.Delete 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="acff4-102">Fields.Delete method (DAO)</span></span>

<span data-ttu-id="acff4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="acff4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="acff4-104">从 **[Fields](field-object-dao.md)** 集合中删除 **[Field](fields-collection-dao.md)** 。</span><span class="sxs-lookup"><span data-stu-id="acff4-104">Deletes a **[Field](field-object-dao.md)** from the **[Fields](fields-collection-dao.md)** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="acff4-105">语法</span><span class="sxs-lookup"><span data-stu-id="acff4-105">Syntax</span></span>

<span data-ttu-id="acff4-106">*表达式*。删除 （***名称***）</span><span class="sxs-lookup"><span data-stu-id="acff4-106">*expression* .Delete(***Name***)</span></span>

<span data-ttu-id="acff4-107">*表达式*一个代表**Fields**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="acff4-107">*expression* A variable that represents a **Fields** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="acff4-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="acff4-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="acff4-109">Name</span><span class="sxs-lookup"><span data-stu-id="acff4-109">Name</span></span></p></th>
<th><p><span data-ttu-id="acff4-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="acff4-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="acff4-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="acff4-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="acff4-112">说明</span><span class="sxs-lookup"><span data-stu-id="acff4-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acff4-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="acff4-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="acff4-114">必需</span><span class="sxs-lookup"><span data-stu-id="acff4-114">Required</span></span></p></td>
<td><p><span data-ttu-id="acff4-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="acff4-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="acff4-116">要删除的字段。</span><span class="sxs-lookup"><span data-stu-id="acff4-116">The field to delete.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="acff4-117">注解</span><span class="sxs-lookup"><span data-stu-id="acff4-117">Remarks</span></span>

<span data-ttu-id="acff4-118">删除已存储的对象会立即发生，但是，对于受数据库结构更改影响的其他任何集合，应使用 **Refresh** 方法。</span><span class="sxs-lookup"><span data-stu-id="acff4-118">The deletion of a stored object occurs immediately, but you should use the **Refresh** method on any other collections that may be affected by changes to the database structure.</span></span>

## <a name="example"></a><span data-ttu-id="acff4-119">示例</span><span class="sxs-lookup"><span data-stu-id="acff4-119">Example</span></span>

<span data-ttu-id="acff4-p101">此示例使用 **Append** 方法或 **Delete** 方法来修改 **TableDef** 的 **Fields** 集合。要使该过程运行，需要 AppendDeleteField 过程。</span><span class="sxs-lookup"><span data-stu-id="acff4-p101">This example uses either the **Append** method or the **Delete** method to modify the **Fields** collection of a **TableDef**. The AppendDeleteField procedure is required for this procedure to run.</span></span>

```vb
    Sub AppendX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim fldLoop As Field 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind.TableDefs!Employees 
     
     ' Add three new fields. 
     AppendDeleteField tdfEmployees, "APPEND", _ 
     "E-mail", dbText, 50 
     AppendDeleteField tdfEmployees, "APPEND", _ 
     "Http", dbText, 80 
     AppendDeleteField tdfEmployees, "APPEND", _ 
     "Quota", dbInteger, 5 
     
     Debug.Print "Fields after Append" 
     Debug.Print , "Type", "Size", "Name" 
     
     ' Enumerate the Fields collection to show the new fields. 
     For Each fldLoop In tdfEmployees.Fields 
     Debug.Print , fldLoop.Type, fldLoop.Size, fldLoop.Name 
     Next fldLoop 
     
     ' Delete the newly added fields. 
     AppendDeleteField tdfEmployees, "DELETE", "E-mail" 
     AppendDeleteField tdfEmployees, "DELETE", "Http" 
     AppendDeleteField tdfEmployees, "DELETE", "Quota" 
     
     Debug.Print "Fields after Delete" 
     Debug.Print , "Type", "Size", "Name" 
     
     ' Enumerate the Fields collection to show that the new 
     ' fields have been deleted. 
     For Each fldLoop In tdfEmployees.Fields 
     Debug.Print , fldLoop.Type, fldLoop.Size, fldLoop.Name 
     Next fldLoop 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Sub AppendDeleteField(tdfTemp As TableDef, _ 
     strCommand As String, strName As String, _ 
     Optional varType, Optional varSize) 
     
     With tdfTemp 
     
     ' Check first to see if the TableDef object is 
     ' updatable. If it isn't, control is passed back to 
     ' the calling procedure. 
     If .Updatable = False Then 
     MsgBox "TableDef not Updatable! " & _ 
     "Unable to complete task." 
     Exit Sub 
     End If 
     
     ' Depending on the passed data, append or delete a 
     ' field to the Fields collection of the specified 
     ' TableDef object. 
     If strCommand = "APPEND" Then 
     .Fields.Append .CreateField(strName, _ 
     varType, varSize) 
     Else 
     If strCommand = "DELETE" Then .Fields.Delete _ 
     strName 
     End If 
     
     End With 
     
    End Sub
```
