---
title: Field2.Size 属性 (DAO)
TOCTitle: Size Property
ms:assetid: e252759a-cea9-25cb-667d-80b422fbf97e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835700(v=office.15)
ms:contentKeyID: 48548282
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f1467414729f4ea82bc2779eeb2bd162465b5ccd
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699035"
---
# <a name="field2size-property-dao"></a><span data-ttu-id="da145-102">Field2.Size 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="da145-102">Field2.Size property (DAO)</span></span>


<span data-ttu-id="da145-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="da145-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="da145-104">设置或返回一个值，该值指示 **Field2** 对象的最大大小（以字节计）。</span><span class="sxs-lookup"><span data-stu-id="da145-104">Sets or returns a value that indicates the maximum size, in bytes, of a **Field2** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="da145-105">语法</span><span class="sxs-lookup"><span data-stu-id="da145-105">Syntax</span></span>

<span data-ttu-id="da145-106">*表达式*。大小</span><span class="sxs-lookup"><span data-stu-id="da145-106">*expression* .Size</span></span>

<span data-ttu-id="da145-107">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="da145-107">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="da145-108">注解</span><span class="sxs-lookup"><span data-stu-id="da145-108">Remarks</span></span>

<span data-ttu-id="da145-109">对于尚未追加到 **[Fields](fields-collection-dao.md)** 集合中的对象，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="da145-109">For an object not yet appended to the **[Fields](fields-collection-dao.md)** collection, this property is read/write.</span></span>

<span data-ttu-id="da145-p101">对于包含字符数据的字段（"备注"类型字段除外）， **Size** 属性指示字段可以保存的最大字符数。对于数字字段， **Size** 属性指示需要多少字节的存储区。</span><span class="sxs-lookup"><span data-stu-id="da145-p101">For fields (other than Memo type fields) that contain character data, the **Size** property indicates the maximum number of characters that the field can hold. For numeric fields, the **Size** property indicates how many bytes of storage are required.</span></span>

<span data-ttu-id="da145-112">**Size** 属性的用法取决于包含 **Field2** 对象所追加到的 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="da145-112">Use of the **Size** property depends on the object that contains the **Fields** collection to which the **Field2** object is appended, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="da145-113">对象追加到</span><span class="sxs-lookup"><span data-stu-id="da145-113">Object appended to</span></span></p></th>
<th><p><span data-ttu-id="da145-114">用法</span><span class="sxs-lookup"><span data-stu-id="da145-114">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da145-115"><strong>索引</strong></span><span class="sxs-lookup"><span data-stu-id="da145-115"><strong>Index</strong></span></span></p></td>
<td><p><span data-ttu-id="da145-116">不支持</span><span class="sxs-lookup"><span data-stu-id="da145-116">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da145-117"><strong>QueryDef</strong></span><span class="sxs-lookup"><span data-stu-id="da145-117"><strong>QueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="da145-118">只读</span><span class="sxs-lookup"><span data-stu-id="da145-118">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da145-119"><strong>Recordset</strong></span><span class="sxs-lookup"><span data-stu-id="da145-119"><strong>Recordset</strong></span></span></p></td>
<td><p><span data-ttu-id="da145-120">只读</span><span class="sxs-lookup"><span data-stu-id="da145-120">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da145-121"><strong>Relation</strong></span><span class="sxs-lookup"><span data-stu-id="da145-121"><strong>Relation</strong></span></span></p></td>
<td><p><span data-ttu-id="da145-122">不支持</span><span class="sxs-lookup"><span data-stu-id="da145-122">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da145-123"><strong>TableDef</strong></span><span class="sxs-lookup"><span data-stu-id="da145-123"><strong>TableDef</strong></span></span></p></td>
<td><p><span data-ttu-id="da145-124">只读</span><span class="sxs-lookup"><span data-stu-id="da145-124">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="da145-p102">在创建一个数据类型不是"文本"的 **Field2** 对象时， **Type** 属性设置将自动确定 **Size** 属性设置；您不需要对其进行设置。但是，对于数据类型为"文本"的 **Field2** 对象，可以将 **Size** 设置为最大文本大小以下的任何整数（对于 Microsoft Access 数据库，最大文本大小为 255）。如果不设置大小，则字段将为数据库所允许的大小。</span><span class="sxs-lookup"><span data-stu-id="da145-p102">When you create a **Field2** object with a data type other than Text, the **Type** property setting automatically determines the **Size** property setting; you don't need to set it. For a **Field2** object with the Text data type, however, you can set **Size** to any integer up to the maximum text size (255 for Microsoft Access database engine databases). If you do not set the size, the field will be as large as the database allows.</span></span>

<span data-ttu-id="da145-p103">对于"长二进制"和"备注" **Field2** 对象， **Size** 始终设置为 0。使用 **Field2** 对象的 **FieldSize** 属性可以确定特定记录中的数据大小。"长二进制"或"备注"字段的最大大小只受系统资源或数据库允许的最大大小的限制。</span><span class="sxs-lookup"><span data-stu-id="da145-p103">For Long Binary and Memo **Field2** objects, **Size** is always set to 0. Use the **FieldSize** property of the **Field2** object to determine the size of the data in a specific record. The maximum size of a Long Binary or Memo field is limited only by your system resources or the maximum size that the database allows.</span></span>

## <a name="example"></a><span data-ttu-id="da145-131">示例</span><span class="sxs-lookup"><span data-stu-id="da145-131">Example</span></span>

<span data-ttu-id="da145-132">以下示例通过枚举 Employees 表中的 **Field2** 对象的名称和大小来演示 **Size** 属性。</span><span class="sxs-lookup"><span data-stu-id="da145-132">This example demonstrates the **Size** property by enumerating the names and sizes of the **Field2** objects in the Employees table.</span></span>

```vb
    Sub SizeX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim fldNew As Field2 
     Dim fldLoop As Field2 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind.TableDefs!Employees 
     
     With tdfEmployees 
     
     ' Create and append a new Field object to the 
     ' Employees table. 
     Set fldNew = .CreateField("FaxPhone") 
     fldNew.Type = dbText 
     fldNew.Size = 20 
     .Fields.Append fldNew 
     
     Debug.Print "TableDef: " & .Name 
     Debug.Print " Field.Name - Field.Type - Field.Size" 
     
     ' Enumerate Fields collection; print field names, 
     ' types, and sizes. 
     For Each fldLoop In .Fields 
     Debug.Print " " & fldLoop.Name & " - " & _ 
     fldLoop.Type & " - " & fldLoop.Size 
     Next fldLoop 
     
     ' Delete new field because this is a demonstration. 
     .Fields.Delete fldNew.Name 
     
     End With 
     
     dbsNorthwind.Close 
     
    End Sub
```
