---
title: Fields.Append Method (DAO)
TOCTitle: Append Method
ms:assetid: a0e553ba-6a57-09af-3436-4f6ca3cbe561
ms:mtpsurl: https://msdn.microsoft.com/library/Ff820791(v=office.15)
ms:contentKeyID: 48546719
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 44d7b6c8c9c44b51f7771dd731b50848f1cbf175
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884819"
---
# <a name="fieldsappend-method-dao"></a><span data-ttu-id="b7ac1-102">Fields.Append Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="b7ac1-102">Fields.Append Method (DAO)</span></span>


<span data-ttu-id="b7ac1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b7ac1-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="b7ac1-104">将新的 **[Field](field-object-dao.md)** 添加到 **[Fields](fields-collection-dao.md)** 集合。</span><span class="sxs-lookup"><span data-stu-id="b7ac1-104">Adds a new **[Field](field-object-dao.md)** to the **[Fields](fields-collection-dao.md)** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7ac1-105">语法</span><span class="sxs-lookup"><span data-stu-id="b7ac1-105">Syntax</span></span>

<span data-ttu-id="b7ac1-106">*表达式*。追加 （***对象***）</span><span class="sxs-lookup"><span data-stu-id="b7ac1-106">*expression* .Append(***Object***)</span></span>

<span data-ttu-id="b7ac1-107">*表达式*一个代表**Fields**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="b7ac1-107">*expression* A variable that represents a **Fields** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="b7ac1-108">参数</span><span class="sxs-lookup"><span data-stu-id="b7ac1-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b7ac1-109">名称</span><span class="sxs-lookup"><span data-stu-id="b7ac1-109">Name</span></span></p></th>
<th><p><span data-ttu-id="b7ac1-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="b7ac1-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="b7ac1-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="b7ac1-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="b7ac1-112">说明</span><span class="sxs-lookup"><span data-stu-id="b7ac1-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7ac1-113">对象</span><span class="sxs-lookup"><span data-stu-id="b7ac1-113">Object</span></span></p></td>
<td><p><span data-ttu-id="b7ac1-114">必需</span><span class="sxs-lookup"><span data-stu-id="b7ac1-114">Required</span></span></p></td>
<td><p><span data-ttu-id="b7ac1-115"><strong>对象</strong></span><span class="sxs-lookup"><span data-stu-id="b7ac1-115"><strong>Object</strong></span></span></p></td>
<td><p><span data-ttu-id="b7ac1-116">一个对象变量，代表追加到集合的字段。</span><span class="sxs-lookup"><span data-stu-id="b7ac1-116">An object variable that represents the field being appended to the collection.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="b7ac1-117">注解</span><span class="sxs-lookup"><span data-stu-id="b7ac1-117">Remarks</span></span>

<span data-ttu-id="b7ac1-118">使用 **Append** 方法可以将新表添加到数据库中，将字段添加到表中，以及将字段添加到索引中。</span><span class="sxs-lookup"><span data-stu-id="b7ac1-118">You can use the **Append** method to add a new table to a database, add a field to a table, and add a field to an index.</span></span>

<span data-ttu-id="b7ac1-119">使用 **Delete** 方法删除追加的对象之前，该对象是存储在磁盘上的永久对象。</span><span class="sxs-lookup"><span data-stu-id="b7ac1-119">The appended object becomes a persistent object, stored on disk, until you delete it by using the **Delete** method.</span></span>

<span data-ttu-id="b7ac1-120">添加新对象会立即发生，但是，对于受数据库结构更改影响的其他任何集合，应使用 **Refresh** 方法。</span><span class="sxs-lookup"><span data-stu-id="b7ac1-120">The addition of a new object occurs immediately, but you should use the **Refresh** method on any other collections that may be affected by changes to the database structure.</span></span>

<span data-ttu-id="b7ac1-121">如果追加的对象不完整（例如，如果在将某个 **Index** 对象追加到 **Indexes** 集合之前，没有将任何 **Field** 对象追加到该对象的 **Fields** 集合），或者一个或多个从属对象中的属性集不正确，则使用 **Append** 方法会导致错误。</span><span class="sxs-lookup"><span data-stu-id="b7ac1-121">If the object you're appending isn't complete (such as when you haven't appended any **Field** objects to a **Fields** collection of an **Index** object before it's appended to an **Indexes** collection) or if the properties set in one or more subordinate objects are incorrect, using the **Append** method causes an error.</span></span> <span data-ttu-id="b7ac1-122">例如，如果没有指定字段类型，然后尝试**将 Field**对象追加到**Fields**集合中的**TableDef**对象使用**Append**方法触发一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="b7ac1-122">For example, if you haven’t specified a field type and then try to append the **Field** object to the **Fields** collection in a **TableDef** object, using the **Append** method triggers a run-time error.</span></span>

## <a name="example"></a><span data-ttu-id="b7ac1-123">示例</span><span class="sxs-lookup"><span data-stu-id="b7ac1-123">Example</span></span>

<span data-ttu-id="b7ac1-p102">此示例使用 **Append** 方法或 **Delete** 方法来修改 **TableDef** 的 **Fields** 集合。要使该过程运行，需要 AppendDeleteField 过程。</span><span class="sxs-lookup"><span data-stu-id="b7ac1-p102">This example uses either the **Append** method or the **Delete** method to modify the **Fields** collection of a **TableDef**. The AppendDeleteField procedure is required for this procedure to run.</span></span>

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
