---
title: Field.Size 属性 (DAO)
TOCTitle: Size Property
ms:assetid: 15e25201-87b6-f62f-ff18-259414a47891
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845510(v=office.15)
ms:contentKeyID: 48543419
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052878
f1_categories:
- Office.Version=v15
ms.openlocfilehash: e1e7d124e06331a043a28c71bcdc9707c4664738
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25931328"
---
# <a name="fieldsize-property-dao"></a><span data-ttu-id="43b36-102">Field.Size 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="43b36-102">Field.Size property (DAO)</span></span>


<span data-ttu-id="43b36-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="43b36-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="43b36-104">设置或返回一个值，该值指示 **[Field](field-object-dao.md)** 对象的最大大小（以字节计）。</span><span class="sxs-lookup"><span data-stu-id="43b36-104">Sets or returns a value that indicates the maximum size, in bytes, of a **[Field](field-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="43b36-105">语法</span><span class="sxs-lookup"><span data-stu-id="43b36-105">Syntax</span></span>

<span data-ttu-id="43b36-106">*表达式*。大小</span><span class="sxs-lookup"><span data-stu-id="43b36-106">*expression* .Size</span></span>

<span data-ttu-id="43b36-107">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="43b36-107">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="43b36-108">注解</span><span class="sxs-lookup"><span data-stu-id="43b36-108">Remarks</span></span>

<span data-ttu-id="43b36-109">对于尚未追加到 **[Fields](fields-collection-dao.md)** 集合中的对象，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="43b36-109">For an object not yet appended to the **[Fields](fields-collection-dao.md)** collection, this property is read/write.</span></span>

<span data-ttu-id="43b36-p101">对于包含字符数据的字段（"备注"类型的字段除外）， **Size** 属性指示字段可以保存的最大字符数。对于数字字段， **Size** 属性指示需要多少字节的存储区。</span><span class="sxs-lookup"><span data-stu-id="43b36-p101">For fields (other than Memo type fields) that contain character data, the **Size** property indicates the maximum number of characters that the field can hold. For numeric fields, the **Size** property indicates how many bytes of storage are required.</span></span>

<span data-ttu-id="43b36-112">**Size** 属性的用法取决于包含 **Field** 对象所追加到的 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="43b36-112">Use of the **Size** property depends on the object that contains the **Fields** collection to which the **Field** object is appended, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="43b36-113">对象追加到</span><span class="sxs-lookup"><span data-stu-id="43b36-113">Object appended to</span></span></p></th>
<th><p><span data-ttu-id="43b36-114">用法</span><span class="sxs-lookup"><span data-stu-id="43b36-114">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43b36-115"><strong>Index</strong></span><span class="sxs-lookup"><span data-stu-id="43b36-115"><strong>Index</strong></span></span></p></td>
<td><p><span data-ttu-id="43b36-116">不支持</span><span class="sxs-lookup"><span data-stu-id="43b36-116">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43b36-117"><strong>QueryDef</strong></span><span class="sxs-lookup"><span data-stu-id="43b36-117"><strong>QueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="43b36-118">只读</span><span class="sxs-lookup"><span data-stu-id="43b36-118">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43b36-119"><strong>Recordset</strong></span><span class="sxs-lookup"><span data-stu-id="43b36-119"><strong>Recordset</strong></span></span></p></td>
<td><p><span data-ttu-id="43b36-120">只读</span><span class="sxs-lookup"><span data-stu-id="43b36-120">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43b36-121"><strong>Relation</strong></span><span class="sxs-lookup"><span data-stu-id="43b36-121"><strong>Relation</strong></span></span></p></td>
<td><p><span data-ttu-id="43b36-122">不支持</span><span class="sxs-lookup"><span data-stu-id="43b36-122">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43b36-123"><strong>TableDef</strong></span><span class="sxs-lookup"><span data-stu-id="43b36-123"><strong>TableDef</strong></span></span></p></td>
<td><p><span data-ttu-id="43b36-124">只读</span><span class="sxs-lookup"><span data-stu-id="43b36-124">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="43b36-p102">当创建数据类型非"文本"的 **Field** 对象时， **[Type](field-type-property-dao.md)** 属性设置自动确定 **Size** 属性设置；您不需要对其进行设置。对于数据类型为"文本"的 **Field** 对象，可以将 **Size** 设置为不超过最大文本大小的任何整数（对于 Microsoft Access 数据库，最大文本大小为 255）。如果不设置大小，则字段将为数据库所允许的大小。</span><span class="sxs-lookup"><span data-stu-id="43b36-p102">When you create a **Field** object with a data type other than Text, the **[Type](field-type-property-dao.md)** property setting automatically determines the **Size** property setting; you don't need to set it. For a **Field** object with the Text data type, however, you can set **Size** to any integer up to the maximum text size (255 for Microsoft Access databases). If you do not set the size, the field will be as large as the database allows.</span></span>

<span data-ttu-id="43b36-p103">对于"长二进制"和"备注" **Field** 对象， **Size** 始终设置为 0。使用 [Field](field-fieldsize-property-dao.md) 对象的 \*\*\*\*FieldSize\*\*\*\* 属性可以确定特定记录的数据大小。"长二进制"或"备注"字段的最大大小仅受系统资源或数据库允许的最大大小的限制。</span><span class="sxs-lookup"><span data-stu-id="43b36-p103">For Long Binary and Memo **Field** objects, **Size** is always set to 0. Use the **[FieldSize](field-fieldsize-property-dao.md)** property of the **Field** object to determine the size of the data in a specific record. The maximum size of a Long Binary or Memo field is limited only by your system resources or the maximum size that the database allows.</span></span>

## <a name="example"></a><span data-ttu-id="43b36-131">示例</span><span class="sxs-lookup"><span data-stu-id="43b36-131">Example</span></span>

<span data-ttu-id="43b36-132">以下示例通过枚举 Employees 表中的 **Field** 对象的名称和大小来演示 **Size** 属性。</span><span class="sxs-lookup"><span data-stu-id="43b36-132">This example demonstrates the **Size** property by enumerating the names and sizes of the **Field** objects in the Employees table.</span></span>

```vb
    Sub SizeX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim fldNew As Field 
     Dim fldLoop As Field 
     
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
