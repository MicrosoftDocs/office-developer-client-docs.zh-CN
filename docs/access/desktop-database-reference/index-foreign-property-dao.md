---
title: Index.Foreign 属性 (DAO)
TOCTitle: Foreign Property
ms:assetid: 81272436-a506-4b72-fd28-2d68e76d6d9b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196489(v=office.15)
ms:contentKeyID: 48545943
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052974
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 878a59d6c844c7c46cf1a38ee6e4ef165d6fca92
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926407"
---
# <a name="indexforeign-property-dao"></a><span data-ttu-id="8ca9f-102">Index.Foreign 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="8ca9f-102">Index.Foreign property (DAO)</span></span>

<span data-ttu-id="8ca9f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8ca9f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8ca9f-p101">返回一个值，该值指示某个 **[Index](index-object-dao.md)** 对象是否代表某个表中的外键（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="8ca9f-p101">Returns a value that indicates whether an **[Index](index-object-dao.md)** object represents a foreign key in a table (Microsoft Access workspaces only). .</span></span>

## <a name="syntax"></a><span data-ttu-id="8ca9f-106">语法</span><span class="sxs-lookup"><span data-stu-id="8ca9f-106">Syntax</span></span>

<span data-ttu-id="8ca9f-107">*表达式*。外</span><span class="sxs-lookup"><span data-stu-id="8ca9f-107">*expression* .Foreign</span></span>

<span data-ttu-id="8ca9f-108">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="8ca9f-108">*expression* A variable that represents an **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ca9f-109">注解</span><span class="sxs-lookup"><span data-stu-id="8ca9f-109">Remarks</span></span>

<span data-ttu-id="8ca9f-110">返回值是一个 **Boolean** 数据类型，如果 **Index** 代表一个外键，则返回 **True**。</span><span class="sxs-lookup"><span data-stu-id="8ca9f-110">The return value is a **Boolean** data type that returns **True** if the **Index** object represents a foreign key.</span></span>

<span data-ttu-id="8ca9f-111">外键包括外表中的一个或多个字段，这些字段可唯一地标识主表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="8ca9f-111">A foreign key consists of one or more fields in a foreign table that uniquely identify all rows in a primary table.</span></span>

<span data-ttu-id="8ca9f-112">当您创建实施参照完整性的关系时，Microsoft Access 数据库引擎可创建外表的 **Index** 对象并设置 **Foreign** 属性。</span><span class="sxs-lookup"><span data-stu-id="8ca9f-112">The Microsoft Access database engine creates an **Index** object for the foreign table and sets the **Foreign** property when you create a relationship that enforces referential integrity.</span></span>

## <a name="example"></a><span data-ttu-id="8ca9f-113">示例</span><span class="sxs-lookup"><span data-stu-id="8ca9f-113">Example</span></span>

<span data-ttu-id="8ca9f-p102">以下示例演示 **Foreign** 属性如何指示 **TableDef** 中的哪些 **Index** 对象是外键索引。这些索引是在创建 **Relation** 时由 Microsoft Access 数据库引擎创建的。外键索引的默认名称是主表名称加外表名称。若要使该过程运行，需要使用 ForeignOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="8ca9f-p102">This example shows how the **Foreign** property can indicate which **Index** objects in a **TableDef** are foreign key indexes. Such indexes are created by the Microsoft Access database engine when a **Relation** is created. The default name for the foreign key indexes is the name of the primary table plus the name of the foreign table. The ForeignOutput function is required for this procedure to run.</span></span>

```vb
    Sub ForeignX() 
     
     Dim dbsNorthwind As Database 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Print report on foreign key indexes from two 
     ' TableDef objects and a QueryDef object. 
     ForeignOutput .TableDefs!Products 
     ForeignOutput .TableDefs!Orders 
     ForeignOutput .TableDefs![Order Details] 
     
     .Close 
     End With 
     
    End Sub 
     
    Function ForeignOutput(tdfTemp As TableDef) 
     
     Dim idxLoop As Index 
     
     With tdfTemp 
     Debug.Print "Indexes in " & .Name & " TableDef" 
     ' Enumerate the Indexes collection of the specified 
     ' TableDef object. 
     For Each idxLoop In .Indexes 
     Debug.Print " " & idxLoop.Name 
     Debug.Print " Foreign = " & idxLoop.Foreign 
     Next idxLoop 
     End With 
     
    End Function
```
