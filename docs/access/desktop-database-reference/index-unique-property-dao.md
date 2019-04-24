---
title: Index。 Unique 属性 (DAO)
TOCTitle: Unique Property
ms:assetid: a4486da5-8a1a-b4fc-0e07-e65cd2e726f6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821087(v=office.15)
ms:contentKeyID: 48546809
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052990
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 5c94200245b4736ad244cb37beec617a98d6c367
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291690"
---
# <a name="indexunique-property-dao"></a><span data-ttu-id="2b3d1-102">Index。 Unique 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="2b3d1-102">Index.Unique property (DAO)</span></span>

<span data-ttu-id="2b3d1-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="2b3d1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2b3d1-104">设置或返回一个值，该值指示 **[Index](index-object-dao.md)** 对象是否代表一个表的唯一（键）索引（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-104">Sets or returns a value that indicates whether an **[Index](index-object-dao.md)** object represents a unique (key) index for a table (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="2b3d1-105">语法</span><span class="sxs-lookup"><span data-stu-id="2b3d1-105">Syntax</span></span>

<span data-ttu-id="2b3d1-106">*表达式*。唯一</span><span class="sxs-lookup"><span data-stu-id="2b3d1-106">*expression* .Unique</span></span>

<span data-ttu-id="2b3d1-107">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-107">*expression* A variable that represents an **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b3d1-108">注解</span><span class="sxs-lookup"><span data-stu-id="2b3d1-108">Remarks</span></span>

<span data-ttu-id="2b3d1-109">该属性设置是可读写的，只有在对象追加到集合中后，它才变为只读。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-109">This property setting is read/write until the object is appended to a collection, after which it's read-only.</span></span>

<span data-ttu-id="2b3d1-p101">唯一索引包含一个或多个字段，这些字段可以按预定义的唯一顺序对表中的所有记录进行逻辑排列。如果索引由一个字段组成，则该字段中的值在整个表中必须是唯一的。如果索引包含多个字段，则每个字段中可以出现重复值，但是由所有索引字段中的值组成的每个组合必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-p101">A unique index consists of one or more fields that logically arrange all records in a table in a unique, predefined order. If the index consists of one field, values in that field must be unique for the entire table. If the index consists of more than one field, each field can contain duplicate values, but each combination of values from all the indexed fields must be unique.</span></span>

<span data-ttu-id="2b3d1-113">如果 **Index** 对象的 **Unique** 和 **[Primary](index-primary-property-dao.md)** 属性都设置为 **True**，则索引是唯一的，并且是主要索引：它按预定义的逻辑顺序唯一标识表中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-113">If both the **Unique** and **[Primary](index-primary-property-dao.md)** properties of an **Index** object are set to **True**, the index is unique and primary: It uniquely identifies all records in the table in a predefined, logical order.</span></span> <span data-ttu-id="2b3d1-114">如果 **Primary** 属性设置为 **False**，则索引是次要索引。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-114">If the **Primary** property is set to **False**, the index is a secondary index.</span></span> <span data-ttu-id="2b3d1-115">次要索引（键和非键）按预定义顺序对记录进行逻辑排列，但不作为表中记录的标识符。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-115">Secondary indexes (both key and nonkey) logically arrange records in a predefined order without serving as an identifier for records in the table.</span></span>

> [!NOTE]
> - <span data-ttu-id="2b3d1-116">您不必为表创建索引，但是在大型的未添加索引的表中，访问特定记录可能会花费很长时间。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-116">You don't have to create indexes for tables, but in large, unindexed tables, accessing a specific record can take a long time.</span></span>
> - <span data-ttu-id="2b3d1-117">从不含索引的表中检索的记录没有特定返回顺序。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-117">Records retrieved from tables without indexes are returned in no particular sequence.</span></span>
> - <span data-ttu-id="2b3d1-118">**index**对象中每个**[Field](field-object-dao.md)** 对象的**[Attributes](field-attributes-property-dao.md)** 属性决定了记录的顺序, 因此决定了用于该**索引**对象的访问技术。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-118">The **[Attributes](field-attributes-property-dao.md)** property of each **[Field](field-object-dao.md)** object in the **Index** object determines the order of records and consequently determines the access techniques to use for that **Index** object.</span></span>
> - <span data-ttu-id="2b3d1-119">唯一索引有助于优化记录的查找。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-119">A unique index helps optimize finding records.</span></span>
> - <span data-ttu-id="2b3d1-120">索引不会影响基表的物理顺序;索引仅影响当选择特定索引或 Microsoft Access 数据库引擎创建**Recordset**对象时, 表类型**[Recordset](recordset-object-dao.md)** 对象访问记录的方式。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-120">Indexes don't affect the physical order of a base table; indexes affect only how the records are accessed by the table-type **[Recordset](recordset-object-dao.md)** object when a particular index is chosen or when the Microsoft Access database engine creates **Recordset** objects.</span></span>

## <a name="example"></a><span data-ttu-id="2b3d1-121">示例</span><span class="sxs-lookup"><span data-stu-id="2b3d1-121">Example</span></span>

<span data-ttu-id="2b3d1-p103">以下示例将新 **Index** 对象的 **Unique** 属性设置为 **True**，并将 Index 追加到 Employees 表的 **Indexes** 集合中。然后，以下示例枚举 **TableDef** 的 **Indexes** 集合和每个 **Index** 的 **Properties** 集合。新 **Index** 只允许一个记录带有 **TableDef** 中的 Country、LastName 和 FirstName 的特定组合。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-p103">This example sets the **Unique** property of a new **Index** object to **True**, and appends the Index to the **Indexes** collection of the Employees table. It then enumerates the **Indexes** collection of the **TableDef** and the **Properties** collection of each **Index**. The new **Index** will only allow one record with a particular combination of Country, LastName, and FirstName in the **TableDef**.</span></span>

```vb
    Sub UniqueX() 
     
       Dim dbsNorthwind As Database 
       Dim tdfEmployees As TableDef 
       Dim idxNew As Index 
       Dim idxLoop As Index 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set tdfEmployees = dbsNorthwind!Employees 
     
       With tdfEmployees 
          ' Create and append new Index object to the Indexes  
          ' collection of the Employees table. 
          Set idxNew = .CreateIndex("NewIndex") 
     
          With idxNew 
             .Fields.Append .CreateField("Country") 
             .Fields.Append .CreateField("LastName") 
             .Fields.Append .CreateField("FirstName") 
             .Unique = True 
          End With 
     
          .Indexes.Append idxNew 
          .Indexes.Refresh 
     
          Debug.Print .Indexes.Count & " Indexes in " & _ 
             .Name & " TableDef" 
     
          ' Enumerate Indexes collection of Employees table. 
          For Each idxLoop In .Indexes 
             Debug.Print "  " & idxLoop.Name 
     
             ' Enumerate Properties collection of each Index  
             ' object. 
             For Each prpLoop In idxLoop.Properties 
                Debug.Print "    " & prpLoop.Name & _ 
                   " = " & IIf(prpLoop = "", "[empty]", prpLoop) 
             Next prpLoop 
     
          Next idxLoop 
     
          ' Delete new Index because this is a demonstration. 
          .Indexes.Delete idxNew.Name 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub
```
