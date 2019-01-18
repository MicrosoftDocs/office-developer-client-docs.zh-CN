---
title: Field.AppendChunk 方法 (DAO)
TOCTitle: AppendChunk Method
ms:assetid: f98c6862-fecf-06cb-a7c0-42b0d3150a06
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837014(v=office.15)
ms:contentKeyID: 48548819
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b1ce1c359582194ce87dfaf4f409be4303486e09
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712657"
---
# <a name="fieldappendchunk-method-dao"></a><span data-ttu-id="9cca7-102">Field.AppendChunk 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9cca7-102">Field.AppendChunk method (DAO)</span></span>

<span data-ttu-id="9cca7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9cca7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9cca7-104">将字符串表达式中的数据追加到 **[Recordset](field-object-dao.md)** 中的"备注"或"长二进制"型 **[Field](recordset-object-dao.md)** 对象。</span><span class="sxs-lookup"><span data-stu-id="9cca7-104">Appends data from a string expression to a Memo or Long Binary **[Field](field-object-dao.md)** object in a **[Recordset](recordset-object-dao.md)**.</span></span>

## <a name="syntax"></a><span data-ttu-id="9cca7-105">语法</span><span class="sxs-lookup"><span data-stu-id="9cca7-105">Syntax</span></span>

<span data-ttu-id="9cca7-106">*表达式*。AppendChunk (***Val***)</span><span class="sxs-lookup"><span data-stu-id="9cca7-106">*expression* .AppendChunk(***Val***)</span></span>

<span data-ttu-id="9cca7-107">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="9cca7-107">*expression* A variable that represents a **Field** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="9cca7-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="9cca7-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9cca7-109">Name</span><span class="sxs-lookup"><span data-stu-id="9cca7-109">Name</span></span></p></th>
<th><p><span data-ttu-id="9cca7-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="9cca7-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="9cca7-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="9cca7-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="9cca7-112">说明</span><span class="sxs-lookup"><span data-stu-id="9cca7-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cca7-113"><em>Val</em></span><span class="sxs-lookup"><span data-stu-id="9cca7-113"><em>Val</em></span></span></p></td>
<td><p><span data-ttu-id="9cca7-114">必需</span><span class="sxs-lookup"><span data-stu-id="9cca7-114">Required</span></span></p></td>
<td><p><span data-ttu-id="9cca7-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="9cca7-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="9cca7-116">一个 Variant（String 子类型）类型的表达式或变量，其中包含要追加到 <strong>Field</strong> 对象的数据。</span><span class="sxs-lookup"><span data-stu-id="9cca7-116">A Variant (String subtype) expression or variable containing the data you want to append to the <strong>Field</strong> object.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="9cca7-117">注解</span><span class="sxs-lookup"><span data-stu-id="9cca7-117">Remarks</span></span>

<span data-ttu-id="9cca7-118">可以使用 **AppendChunk** 和 **[GetChunk](field-getchunk-method-dao.md)** 方法访问"备注"或"长二进制"型字段中的数据的子集。</span><span class="sxs-lookup"><span data-stu-id="9cca7-118">You can use the **AppendChunk** and **[GetChunk](field-getchunk-method-dao.md)** methods to access subsets of data in a Memo or Long Binary field.</span></span>

<span data-ttu-id="9cca7-p101">在处理"备注"和"长二进制"型字段时，还可以使用这些方法来节省字符串空间。某些操作（如复制）涉及到临时字符串。如果字符串空间有限，可能需要处理字段的某些块而不是整个字段。</span><span class="sxs-lookup"><span data-stu-id="9cca7-p101">You can also use these methods to conserve string space when you work with Memo and Long Binary fields. Certain operations (copying, for example) involve temporary strings. If string space is limited, you may need to work with chunks of a field instead of the entire field.</span></span>

<span data-ttu-id="9cca7-122">在使用 **AppendChunk** 时如果不存在当前记录，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="9cca7-122">If there is no current record when you use **AppendChunk**, an error occurs.</span></span>

> [!NOTE]
> <span data-ttu-id="9cca7-p102">初始的 **AppendChunk** 操作（ **[Edit](recordset-edit-method-dao.md)** 或 **[AddNew](recordset-addnew-method-dao.md)** 调用之后）只是将数据置于字段内，并覆盖任何现有的数据。然后同一 **Edit** 或 **AddNew** 会话中的后续 **AppendChunk** 调用将其添加到现有数据。</span><span class="sxs-lookup"><span data-stu-id="9cca7-p102">The initial **AppendChunk** operation (after an **[Edit](recordset-edit-method-dao.md)** or **[AddNew](recordset-addnew-method-dao.md)** call) will simply place the data in the field, overwriting any existing data. Subsequent **AppendChunk** calls within the same **Edit** or **AddNew** session will then add to the existing data.</span></span>

## <a name="example"></a><span data-ttu-id="9cca7-125">示例</span><span class="sxs-lookup"><span data-stu-id="9cca7-125">Example</span></span>

<span data-ttu-id="9cca7-p103">以下示例使用 **AppendChunk** 和 **GetChunk** 方法，用来自其他记录的数据，以每次 32K 的形式填充 OLE 对象字段。在实际的应用程序中，用户可以使用与此类似的过程，将雇员记录（包括雇员的照片）从一个表复制到另一个表。在以下示例中，只是将记录复制回到同一个表。请注意，所有块操作将在单个 AddNew-Update 序列中发生。</span><span class="sxs-lookup"><span data-stu-id="9cca7-p103">This example uses the **AppendChunk** and **GetChunk** methods to fill an OLE object field with data from another record, 32K at a time. In a real application, one might use a procedure like this to copy an employee record (including the employee's photo) from one table to another. In this example, the record is simply being copied back to same table. Note that all the chunk manipulation takes place within a single AddNew-Update sequence.</span></span>

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
