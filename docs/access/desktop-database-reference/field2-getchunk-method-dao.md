---
title: Field2.GetChunk 方法 (DAO)
TOCTitle: GetChunk Method
ms:assetid: 5d3a66c0-8216-d701-0a91-b79fbbc822b8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194600(v=office.15)
ms:contentKeyID: 48545101
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1d3bf59549a37e728d26da2e5986e852235d6f77
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937447"
---
# <a name="field2getchunk-method-dao"></a><span data-ttu-id="20c05-102">Field2.GetChunk 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="20c05-102">Field2.GetChunk method (DAO)</span></span>


<span data-ttu-id="20c05-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="20c05-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="20c05-104">返回所有或一部分的**[Recordset](recordset-object-dao.md)** 对象的**[Fields](fields-collection-dao.md)** 集合中的**Memo**或**Long BinaryField2**对象的内容。</span><span class="sxs-lookup"><span data-stu-id="20c05-104">Returns all or a portion of the contents of a **Memo** or **Long BinaryField2** object in the **[Fields](fields-collection-dao.md)** collection of a **[Recordset](recordset-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="20c05-105">语法</span><span class="sxs-lookup"><span data-stu-id="20c05-105">Syntax</span></span>

<span data-ttu-id="20c05-106">*表达式*。GetChunk***偏移***(***字节***）</span><span class="sxs-lookup"><span data-stu-id="20c05-106">*expression* .GetChunk(***Offset***, ***Bytes***)</span></span>

<span data-ttu-id="20c05-107">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="20c05-107">*expression* A variable that represents a **Field2** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="20c05-108">参数</span><span class="sxs-lookup"><span data-stu-id="20c05-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="20c05-109">名称</span><span class="sxs-lookup"><span data-stu-id="20c05-109">Name</span></span></p></th>
<th><p><span data-ttu-id="20c05-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="20c05-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="20c05-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="20c05-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="20c05-112">说明</span><span class="sxs-lookup"><span data-stu-id="20c05-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20c05-113">Offset</span><span class="sxs-lookup"><span data-stu-id="20c05-113">Offset</span></span></p></td>
<td><p><span data-ttu-id="20c05-114">必需</span><span class="sxs-lookup"><span data-stu-id="20c05-114">Required</span></span></p></td>
<td><p><span data-ttu-id="20c05-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="20c05-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="20c05-116">开始复制前要跳过的字节数。</span><span class="sxs-lookup"><span data-stu-id="20c05-116">The number of bytes to skip before copying begins.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20c05-117">字节数</span><span class="sxs-lookup"><span data-stu-id="20c05-117">Bytes</span></span></p></td>
<td><p><span data-ttu-id="20c05-118">必需</span><span class="sxs-lookup"><span data-stu-id="20c05-118">Required</span></span></p></td>
<td><p><span data-ttu-id="20c05-119"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="20c05-119"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="20c05-120">要返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="20c05-120">The number of bytes you want to return.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="return-value"></a><span data-ttu-id="20c05-121">返回值</span><span class="sxs-lookup"><span data-stu-id="20c05-121">Return value</span></span>

<span data-ttu-id="20c05-122">Variant</span><span class="sxs-lookup"><span data-stu-id="20c05-122">Variant</span></span>

## <a name="remarks"></a><span data-ttu-id="20c05-123">注解</span><span class="sxs-lookup"><span data-stu-id="20c05-123">Remarks</span></span>

<span data-ttu-id="20c05-p101">将 **GetChunk** 返回的字节指定给变量。使用 **GetChunk** 每次返回总数据值的一部分。可以使用 **[AppendChunk](field-appendchunk-method-dao.md)** 方法重新组装片段。</span><span class="sxs-lookup"><span data-stu-id="20c05-p101">The bytes returned by **GetChunk** are assigned to variable. Use **GetChunk** to return a portion of the total data value at a time. You can use the **[AppendChunk](field-appendchunk-method-dao.md)** method to reassemble the pieces.</span></span>

<span data-ttu-id="20c05-127">如果 offset 为**0,getchunk**将从字段的第一个字节开始。</span><span class="sxs-lookup"><span data-stu-id="20c05-127">If offset is 0, **GetChunk** begins copying from the first byte of the field.</span></span>

<span data-ttu-id="20c05-128">如果 numbytes 大于字段中的字节数， **GetChunk**将返回字段中的实际剩余的字节数。</span><span class="sxs-lookup"><span data-stu-id="20c05-128">If numbytes is greater than the number of bytes in the field, **GetChunk** returns the actual number of remaining bytes in the field.</span></span>

> [!NOTE]
> <span data-ttu-id="20c05-p102">[!注释] 对文本使用 **Memo** 字段，只能在 **Long Binary** 字段中放置二进制数据。否则会导致不合需要的结果。</span><span class="sxs-lookup"><span data-stu-id="20c05-p102">Use a **Memo** field for text, and put binary data only in **Long Binary** fields. Doing otherwise will cause undesirable results.</span></span>

## <a name="example"></a><span data-ttu-id="20c05-131">示例</span><span class="sxs-lookup"><span data-stu-id="20c05-131">Example</span></span>

<span data-ttu-id="20c05-p103">以下示例使用 **AppendChunk** 和 **GetChunk** 方法，用来自其他记录的数据，以每次 32K 的形式填充 OLE 对象字段。在实际的应用程序中，用户可以使用与此类似的过程，将雇员记录（包括雇员的照片）从一个表复制到另一个表。在以下示例中，只是将记录复制回到同一个表。请注意，所有块操作将在单个 AddNew-Update 序列中发生。</span><span class="sxs-lookup"><span data-stu-id="20c05-p103">This example uses the **AppendChunk** and **GetChunk** methods to fill an OLE object field with data from another record, 32K at a time. In a real application, one might use a procedure like this to copy an employee record (including the employee's photo) from one table to another. In this example, the record is simply being copied back to same table. Note that all the chunk manipulation takes place within a single AddNew-Update sequence.</span></span>

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
     
    Function CopyLargeField(fldSource As Field2, _ 
     fldDestination As Field2) 
     
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
