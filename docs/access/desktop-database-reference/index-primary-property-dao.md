---
title: Index.Primary Property (DAO)
TOCTitle: Primary Property
ms:assetid: 90eda1cb-cf7f-9682-9b74-81c27a37af16
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197416(v=office.15)
ms:contentKeyID: 48546336
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052908
f1_categories:
- Office.Version=v15
ms.openlocfilehash: efaf00dc54068c6ce7c2991613b9485bcbdf41c7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25891238"
---
# <a name="indexprimary-property-dao"></a><span data-ttu-id="02391-102">Index.Primary Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="02391-102">Index.Primary Property (DAO)</span></span>


<span data-ttu-id="02391-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="02391-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="02391-104">设置或返回一个值，该值指示 **[Index](index-object-dao.md)** 对象是否代表了对一个表的主键索引（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="02391-104">Sets or returns a value that indicates whether an **[Index](index-object-dao.md)** object represents a primary key index for a table (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="02391-105">语法</span><span class="sxs-lookup"><span data-stu-id="02391-105">Syntax</span></span>

<span data-ttu-id="02391-106">*表达式*。主</span><span class="sxs-lookup"><span data-stu-id="02391-106">*expression* .Primary</span></span>

<span data-ttu-id="02391-107">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="02391-107">*expression* A variable that represents an **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="02391-108">注解</span><span class="sxs-lookup"><span data-stu-id="02391-108">Remarks</span></span>

<span data-ttu-id="02391-p101">对于新的尚未追加到集合中的 **Index** 对象而言， **Primary** 属性设置是可读写的，对于 [**Indexes**](indexes-collection-dao.md) 集合中的 **Index** 对象而言，该属性设置是只读的。如果 **Index** 对象追加到 **[TableDef](tabledef-object-dao.md)** 对象，但是 **TableDef** 对象不追加到 **[TableDefs](tabledefs-collection-dao.md)** 集合中，则 **Index** 属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="02391-p101">The **Primary** property setting is read/write for a new **Index** object not yet appended to a collection and read-only for an existing **Index** object in an **[Indexes](indexes-collection-dao.md)** collection. If the **Index** object is appended to the **[TableDef](tabledef-object-dao.md)** object but the **TableDef** object isn't appended to the **[TableDefs](tabledefs-collection-dao.md)** collection, the **Index** property is read/write.</span></span>

<span data-ttu-id="02391-p102">主键索引包含一个或多个字段，这些字段可以按预定义的顺序唯一地对表中的所有记录进行标识。由于索引字段必须唯一，因此 [Index](index-unique-property-dao.md) 对象的 \*\*\*\*Unique\*\*\*\* 属性设置为 **True**。如果主键索引包含多个字段，则每个字段可以包含重复值，但是由所有索引字段中的值组成的每个组合则必须是唯一的。主键索引由表的键组成，包含的字段通常与主键所包含的相同。</span><span class="sxs-lookup"><span data-stu-id="02391-p102">A primary key index consists of one or more fields that uniquely identify all records in a table in a predefined order. Because the index field must be unique, the **[Unique](index-unique-property-dao.md)** property of the **Index** object is set to **True**. If the primary key index consists of more than one field, each field can contain duplicate values, but each combination of values from all the indexed fields must be unique. A primary key index consists of a key for the table and usually contains the same fields as the primary key.</span></span>


> [!NOTE]
> <P><span data-ttu-id="02391-p103">[!注释] 您不必为表创建索引，但是在未添加索引的大型表中，访问特定记录可能会花费很长时间。 <A href="field-attributes-property-dao.md">Index</A> 对象中每个 <A href="field-object-dao.md"><STRONG>Field</STRONG></A> 对象的 <STRONG><STRONG>Attributes</STRONG></STRONG> 属性决定了记录的顺序，因此决定了对该索引使用的访问技术。当在数据库中创建新表时，最好对唯一标识每条记录的一个或多个字段创建索引，然后将 <STRONG>Index</STRONG> 对象的 <STRONG>Primary</STRONG> 属性设置为 <STRONG>True</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="02391-p103">You don't have to create indexes for tables, but in large, unindexed tables, accessing a specific record can take a long time. The <STRONG><A href="field-attributes-property-dao.md">Attributes</A></STRONG> property of each <STRONG><A href="field-object-dao.md">Field</A></STRONG> object in the <STRONG>Index</STRONG> object determines the order of records and consequently determines the access techniques to use for that index. When you create a new table in your database, it's a good idea to create an index on one or more fields that uniquely identify each record, and then set the <STRONG>Primary</STRONG> property of the <STRONG>Index</STRONG> object to <STRONG>True</STRONG>.</span></span></P>



<span data-ttu-id="02391-118">当设置表的主键时，该主键被自动定义为表的主键索引。</span><span class="sxs-lookup"><span data-stu-id="02391-118">When you set a primary key for a table, the primary key is automatically defined as the primary key index for the table.</span></span>

## <a name="example"></a><span data-ttu-id="02391-119">示例</span><span class="sxs-lookup"><span data-stu-id="02391-119">Example</span></span>

<span data-ttu-id="02391-p104">以下示例使用 **Primary** 属性将新 **TableDef** 中的新 **Index** 指定为该表的主要 **Index**。请注意，将 **Primary** 属性设置为 **True** 会自动将 **Unique** 和 **Required** 属性也设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="02391-p104">This example uses the **Primary** property to designate a new **Index** in a new **TableDef** as the primary **Index** for that table. Note that setting the **Primary** property to **True** automatically sets **Unique** and **Required** properties to **True** as well.</span></span>

```vb
    Sub PrimaryX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfNew As TableDef 
     Dim idxNew As Index 
     Dim idxLoop As Index 
     Dim fldLoop As Field 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Create and append a new TableDef object to the 
     ' TableDefs collection of the Northwind database. 
     Set tdfNew = dbsNorthwind.CreateTableDef("NewTable") 
     tdfNew.Fields.Append tdfNew.CreateField("NumField", _ 
     dbLong, 20) 
     tdfNew.Fields.Append tdfNew.CreateField("TextField", _ 
     dbText, 20) 
     dbsNorthwind.TableDefs.Append tdfNew 
     
     With tdfNew 
     ' Create and append a new Index object to the 
     ' Indexes collection of the new TableDef object. 
     Set idxNew = .CreateIndex("NumIndex") 
     idxNew.Fields.Append idxNew.CreateField("NumField") 
     idxNew.Primary = True 
     .Indexes.Append idxNew 
     Set idxNew = .CreateIndex("TextIndex") 
     idxNew.Fields.Append idxNew.CreateField("TextField") 
     .Indexes.Append idxNew 
     
     Debug.Print .Indexes.Count & " Indexes in " & _ 
     .Name & " TableDef" 
     
     ' Enumerate Indexes collection. 
     For Each idxLoop In .Indexes 
     
     With idxLoop 
     Debug.Print " " & .Name 
     
     ' Enumerate Fields collection of each Index 
     ' object. 
     Debug.Print " Fields" 
     For Each fldLoop In .Fields 
     Debug.Print " " & fldLoop.Name 
     Next fldLoop 
     
     ' Enumerate Properties collection of each 
     ' Index object. 
     Debug.Print " Properties" 
     For Each prpLoop In .Properties 
     Debug.Print " " & prpLoop.Name & _ 
     " = " & IIf(prpLoop = "", "[empty]", _ 
     prpLoop) 
     Next prpLoop 
     End With 
     
     Next idxLoop 
     
     End With 
     
     dbsNorthwind.TableDefs.Delete tdfNew.Name 
     dbsNorthwind.Close 
     
    End Sub
```
