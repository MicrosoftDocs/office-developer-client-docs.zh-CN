---
title: Index.IgnoreNulls 属性 (DAO)
TOCTitle: IgnoreNulls Property
ms:assetid: f49f17b8-d7c1-18ab-07a8-e1be61488519
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836698(v=office.15)
ms:contentKeyID: 48548694
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052931
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 4fd7d7e1335e7acd5bc9733d8c13f690be68d82b
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926449"
---
# <a name="indexignorenulls-property-dao"></a><span data-ttu-id="46543-102">Index.IgnoreNulls 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="46543-102">Index.IgnoreNulls property (DAO)</span></span>


<span data-ttu-id="46543-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="46543-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="46543-104">设置或返回一个值，该值指示索引字段中包含 Null 值的记录是否具有索引项（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="46543-104">Sets or returns a value that indicates whether records that have Null values in their index fields have index entries (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="46543-105">语法</span><span class="sxs-lookup"><span data-stu-id="46543-105">Syntax</span></span>

<span data-ttu-id="46543-106">*表达式*。IgnoreNulls</span><span class="sxs-lookup"><span data-stu-id="46543-106">*expression* .IgnoreNulls</span></span>

<span data-ttu-id="46543-107">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="46543-107">*expression* A variable that represents an **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="46543-108">注解</span><span class="sxs-lookup"><span data-stu-id="46543-108">Remarks</span></span>

<span data-ttu-id="46543-109">对于尚未追加到集合的新 **[Index](index-object-dao.md)** 对象，该属性是可读写的；对于 [**Indexes**](indexes-collection-dao.md) 集合中的现有 **Index** 对象，该属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="46543-109">This property is read/write for a new **[Index](index-object-dao.md)** object not yet appended to a collection and read-only for an existing **Index** object in an **[Indexes](indexes-collection-dao.md)** collection.</span></span>

<span data-ttu-id="46543-p101">要加速搜索记录的过程，可以为字段定义一个索引。如果允许在索引字段中使用 **null** 项，并且希望有许多项为 **null**，可以将 **Index** 对象的 **IgnoreNulls** 属性设置为 **True**，以减少索引使用的存储空间量。</span><span class="sxs-lookup"><span data-stu-id="46543-p101">To speed up the process of searching for records, you can define an index for a field. If you allow **null** entries in an indexed field and expect many of the entries to be **null**, you can set the **IgnoreNulls** property for the **Index** object to **True** to reduce the amount of storage space that the index uses.</span></span>

<span data-ttu-id="46543-112">**IgnoreNulls** 属性设置和 **[Required](field-required-property-dao.md)** 属性设置共同确定包含 **null** 索引值的记录是否具有索引项。</span><span class="sxs-lookup"><span data-stu-id="46543-112">The **IgnoreNulls** property setting and the **[Required](field-required-property-dao.md)** property setting together determine whether a record with a **null** index value has an index entry.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="46543-113">如果 IgnoreNulls 是</span><span class="sxs-lookup"><span data-stu-id="46543-113">If IgnoreNulls is</span></span></p></th>
<th><p><span data-ttu-id="46543-114">并且 Required 是</span><span class="sxs-lookup"><span data-stu-id="46543-114">And Required is</span></span></p></th>
<th><p><span data-ttu-id="46543-115">则</span><span class="sxs-lookup"><span data-stu-id="46543-115">Then</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46543-116">True</span><span class="sxs-lookup"><span data-stu-id="46543-116">True</span></span></p></td>
<td><p><span data-ttu-id="46543-117">False</span><span class="sxs-lookup"><span data-stu-id="46543-117">False</span></span></p></td>
<td><p><span data-ttu-id="46543-118">索引字段中允许空值；未添加任何索引项。</span><span class="sxs-lookup"><span data-stu-id="46543-118">A null value is allowed in the index field; no index entry added.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46543-119">False</span><span class="sxs-lookup"><span data-stu-id="46543-119">False</span></span></p></td>
<td><p><span data-ttu-id="46543-120">False</span><span class="sxs-lookup"><span data-stu-id="46543-120">False</span></span></p></td>
<td><p><span data-ttu-id="46543-121">索引字段中允许 Null 值；已添加索引项。</span><span class="sxs-lookup"><span data-stu-id="46543-121">A null value is allowed in the index field; index entry added.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46543-122">True 或 False</span><span class="sxs-lookup"><span data-stu-id="46543-122">True or False</span></span></p></td>
<td><p><span data-ttu-id="46543-123">True</span><span class="sxs-lookup"><span data-stu-id="46543-123">True</span></span></p></td>
<td><p><span data-ttu-id="46543-124">索引字段中允许 Null 值；未添加任何索引项。</span><span class="sxs-lookup"><span data-stu-id="46543-124">A null value isn't allowed in the index field; no index entry added.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="example"></a><span data-ttu-id="46543-125">示例</span><span class="sxs-lookup"><span data-stu-id="46543-125">Example</span></span>

<span data-ttu-id="46543-126">以下示例根据用户输入将新的 **Index** 的 **IgnoreNulls** 属性设置为 **True** 或 **False**，然后在一个带有记录（该记录的键字段包含 **Null** 值）的 **Recordset** 上演示该效果。</span><span class="sxs-lookup"><span data-stu-id="46543-126">This example sets the **IgnoreNulls** property of a new **Index** to **True** or **False** based on user input, and then demonstrates the effect on a **Recordset** with a record whose key field contains a **Null** value.</span></span>

```vb
    Sub IgnoreNullsX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim idxNew As Index 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind!Employees 
     
     With tdfEmployees 
     ' Create a new Index object. 
     Set idxNew = .CreateIndex("NewIndex") 
     idxNew.Fields.Append idxNew.CreateField("Country") 
     
     ' Set the IgnoreNulls property of the new Index object 
     ' based on the user's input. 
     Select Case MsgBox("Set IgnoreNulls to True?", _ 
     vbYesNoCancel) 
     Case vbYes 
     idxNew.IgnoreNulls = True 
     Case vbNo 
     idxNew.IgnoreNulls = False 
     Case Else 
     dbsNorthwind.Close 
     End 
     End Select 
     
     ' Append the new Index object to the Indexes 
     ' collection of the Employees table. 
     .Indexes.Append idxNew 
     .Indexes.Refresh 
     End With 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     With rstEmployees 
     ' Add a new record to the Employees table. 
     .AddNew 
     !FirstName = "Gary" 
     !LastName = "Haarsager" 
     .Update 
     
     ' Use the new index to set the order of the records. 
     .Index = idxNew.Name 
     .MoveFirst 
     
     Debug.Print "Index = " & .Index & _ 
     ", IgnoreNulls = " & idxNew.IgnoreNulls 
     Debug.Print " Country - Name" 
     
     ' Enumerate the Recordset. The value of the 
     ' IgnoreNulls property will determine if the newly 
     ' added record appears in the output. 
     Do While Not .EOF 
     Debug.Print " " & _ 
     IIf(IsNull(!Country), "[Null]", !Country) & _ 
     " - " & !FirstName & " " & !LastName 
     .MoveNext 
     Loop 
     
     ' Delete new record because this is a demonstration. 
     .Index = "" 
     .Bookmark = .LastModified 
     .Delete 
     .Close 
     End With 
     
     ' Delete new Index because this is a demonstration. 
     tdfEmployees.Indexes.Delete idxNew.Name 
     dbsNorthwind.Close 
     
    End Sub
```
