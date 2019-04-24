---
title: GetChunk 方法 (DAO)
TOCTitle: GetChunk Method
ms:assetid: b8984e79-54f7-8052-85a3-d12033daf7a1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822448(v=office.15)
ms:contentKeyID: 48547328
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052871
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: c7eabceb1f7c130e349428aeb6b2dc079fe4319d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293096"
---
# <a name="fieldgetchunk-method-dao"></a><span data-ttu-id="c0c73-102">GetChunk 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c0c73-102">Field.GetChunk method (DAO)</span></span>

<span data-ttu-id="c0c73-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c0c73-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c0c73-104">返回**[Recordset](recordset-object-dao.md)** 对象的**[Fields](fields-collection-dao.md)** 集合中的 **"备注"** 或 "**长二进制**"**[字段](field-object-dao.md)** 对象的全部或部分内容。</span><span class="sxs-lookup"><span data-stu-id="c0c73-104">Returns all or a portion of the contents of a **Memo** or **Long Binary** **[Field](field-object-dao.md)** object in the **[Fields](fields-collection-dao.md)** collection of a **[Recordset](recordset-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0c73-105">语法</span><span class="sxs-lookup"><span data-stu-id="c0c73-105">Syntax</span></span>

<span data-ttu-id="c0c73-106">*表达式*。GetChunk (***偏移量***、***字节数***)</span><span class="sxs-lookup"><span data-stu-id="c0c73-106">*expression* .GetChunk(***Offset***, ***Bytes***)</span></span>

<span data-ttu-id="c0c73-107">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c0c73-107">*expression* A variable that represents a **Field** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="c0c73-108">参数</span><span class="sxs-lookup"><span data-stu-id="c0c73-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c0c73-109">名称</span><span class="sxs-lookup"><span data-stu-id="c0c73-109">Name</span></span></p></th>
<th><p><span data-ttu-id="c0c73-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="c0c73-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="c0c73-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="c0c73-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="c0c73-112">说明</span><span class="sxs-lookup"><span data-stu-id="c0c73-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0c73-113"><em>Offset</em></span><span class="sxs-lookup"><span data-stu-id="c0c73-113"><em>Offset</em></span></span></p></td>
<td><p><span data-ttu-id="c0c73-114">必需</span><span class="sxs-lookup"><span data-stu-id="c0c73-114">Required</span></span></p></td>
<td><p><span data-ttu-id="c0c73-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="c0c73-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="c0c73-116">开始复制前要跳过的字节数。</span><span class="sxs-lookup"><span data-stu-id="c0c73-116">The number of bytes to skip before copying begins.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0c73-117"><em>单位</em></span><span class="sxs-lookup"><span data-stu-id="c0c73-117"><em>Bytes</em></span></span></p></td>
<td><p><span data-ttu-id="c0c73-118">必需</span><span class="sxs-lookup"><span data-stu-id="c0c73-118">Required</span></span></p></td>
<td><p><span data-ttu-id="c0c73-119"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="c0c73-119"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="c0c73-120">要返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="c0c73-120">The number of bytes you want to return.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="c0c73-121">返回值</span><span class="sxs-lookup"><span data-stu-id="c0c73-121">Return value</span></span>

<span data-ttu-id="c0c73-122">Variant</span><span class="sxs-lookup"><span data-stu-id="c0c73-122">Variant</span></span>

## <a name="remarks"></a><span data-ttu-id="c0c73-123">注解</span><span class="sxs-lookup"><span data-stu-id="c0c73-123">Remarks</span></span>

<span data-ttu-id="c0c73-p101">将 **GetChunk** 返回的字节指定给变量。使用 **GetChunk** 每次返回总数据值的一部分。可以使用 **[AppendChunk](field-appendchunk-method-dao.md)** 方法重新组装片段。</span><span class="sxs-lookup"><span data-stu-id="c0c73-p101">The bytes returned by **GetChunk** are assigned to variable. Use **GetChunk** to return a portion of the total data value at a time. You can use the **[AppendChunk](field-appendchunk-method-dao.md)** method to reassemble the pieces.</span></span>

<span data-ttu-id="c0c73-127">如果 offset 为 0, **GetChunk**将从字段的第一个字节开始复制。</span><span class="sxs-lookup"><span data-stu-id="c0c73-127">If offset is 0, **GetChunk** begins copying from the first byte of the field.</span></span>

<span data-ttu-id="c0c73-128">如果 numbytes 大于字段中的字节数, 则**GetChunk**将返回字段中剩余的实际字节数。</span><span class="sxs-lookup"><span data-stu-id="c0c73-128">If numbytes is greater than the number of bytes in the field, **GetChunk** returns the actual number of remaining bytes in the field.</span></span>

> [!NOTE]
> <span data-ttu-id="c0c73-129">[!注释] 对文本使用 **Memo** 字段，只能在 **Long Binary** 字段中放置二进制数据。</span><span class="sxs-lookup"><span data-stu-id="c0c73-129">Use a **Memo** field for text, and put binary data only in **Long Binary** fields.</span></span> <span data-ttu-id="c0c73-130">否则会导致不合需要的结果。</span><span class="sxs-lookup"><span data-stu-id="c0c73-130">Doing otherwise will cause undesirable results.</span></span>

## <a name="example"></a><span data-ttu-id="c0c73-131">示例</span><span class="sxs-lookup"><span data-stu-id="c0c73-131">Example</span></span>

<span data-ttu-id="c0c73-p103">以下示例使用 **AppendChunk** 和 **GetChunk** 方法，用来自其他记录的数据，以每次 32K 的形式填充 OLE 对象字段。在实际的应用程序中，用户可以使用与此类似的过程，将雇员记录（包括雇员的照片）从一个表复制到另一个表。在以下示例中，只是将记录复制回到同一个表。请注意，所有块操作将在单个 AddNew-Update 序列中发生。</span><span class="sxs-lookup"><span data-stu-id="c0c73-p103">This example uses the **AppendChunk** and **GetChunk** methods to fill an OLE object field with data from another record, 32K at a time. In a real application, one might use a procedure like this to copy an employee record (including the employee's photo) from one table to another. In this example, the record is simply being copied back to same table. Note that all the chunk manipulation takes place within a single AddNew-Update sequence.</span></span>

```vb
    Sub AppendChunkX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim rstEmployees2 As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Open two recordsets from the Employees table. 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     Set rstEmployees2 = rstEmployees.Clone 
     
     ' Add a new record to the first Recordset and copy the 
     ' data from a record in the second Recordset. 
     With rstEmployees 
     .AddNew 
     !FirstName = rstEmployees2!FirstName 
     !LastName = rstEmployees2!LastName 
     CopyLargeField rstEmployees2!Photo, !Photo 
     .Update 
     
     ' Delete new record because this is a demonstration. 
     .Bookmark = .LastModified 
     .Delete 
     .Close 
     End With 
     
     rstEmployees2.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Function CopyLargeField(fldSource As Field, _ 
     fldDestination As Field) 
     
     ' Set size of chunk in bytes. 
     Const conChunkSize = 32768 
     
     Dim lngOffset As Long 
     Dim lngTotalSize As Long 
     Dim strChunk As String 
     
     ' Copy the photo from one Recordset to the other in 32K 
     ' chunks until the entire field is copied. 
     lngTotalSize = fldSource.FieldSize 
     Do While lngOffset < lngTotalSize 
     strChunk = fldSource.GetChunk(lngOffset, conChunkSize) 
     fldDestination.AppendChunk strChunk 
     lngOffset = lngOffset + conChunkSize 
     Loop 
     
    End Function
```
