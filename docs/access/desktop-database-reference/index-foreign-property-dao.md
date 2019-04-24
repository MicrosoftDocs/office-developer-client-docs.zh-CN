---
title: Index 外表属性 (DAO)
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
localization_priority: Normal
ms.openlocfilehash: a3c6adfaf9648147a763f997ce2a91aadc4f7637
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291815"
---
# <a name="indexforeign-property-dao"></a>Index 外表属性 (DAO)

**适用于**：Access 2013、Office 2013

返回一个值, 该值指示**[Index](index-object-dao.md)** 对象是否表示表中的外键 (仅适用于 Microsoft Access 工作区)。 .

## <a name="syntax"></a>语法

*表达式*。对外

*表达式*一个代表**Index**对象的变量。

## <a name="remarks"></a>注解

返回值是一个 **Boolean** 数据类型，如果 **Index** 代表一个外键，则返回 **True**。

外键包括外表中的一个或多个字段，这些字段可唯一地标识主表中的所有行。

当您创建实施参照完整性的关系时，Microsoft Access 数据库引擎可创建外表的 **Index** 对象并设置 **Foreign** 属性。

## <a name="example"></a>示例

以下示例演示 **Foreign** 属性如何指示 **TableDef** 中的哪些 **Index** 对象是外键索引。这些索引是在创建 **Relation** 时由 Microsoft Access 数据库引擎创建的。外键索引的默认名称是主表名称加外表名称。若要使该过程运行，需要使用 ForeignOutput 函数。

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
