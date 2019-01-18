---
title: PROCEDURE 子句 (Microsoft Access SQL)
TOCTitle: PROCEDURE clause (Microsoft Access SQL)
ms:assetid: a718802c-9260-88d5-ec29-d5e5594927b0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821342(v=office.15)
ms:contentKeyID: 48546872
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277578
dev_langs:
- sql
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 72f31c71e710cca79695a7221f0e033d18d2f420
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726314"
---
# <a name="procedure-clause-microsoft-access-sql"></a>PROCEDURE 子句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

定义查询的名称和可选参数。

> [!NOTE]
> [!注释] PROCEDURE 子句已经被 PROCEDURE 语句所取代。虽然现在仍然支持 PROCEDURE 子句，但是 PROCEDURE 语句提供了兼容 PROCEDURE 子句的超集，并且它是推荐使用的语法。

## <a name="syntax"></a>语法

过程*名称* \[ *param1 datatype*\[， *param2 datatype*\[，...\]\]

PROCEDURE 子句包含以下部分：

|部分 |说明 |
|:----|:-----------|
|*name* |过程名称。它必须遵循标准命名规则。|
|*param1*、*param2* |一个或多个字段名或者参数。例如：
<br/><br/>`PROCEDURE Sales_By_Country [Beginning Date] DateTime, [Ending Date] DateTime;`<br/><br/>有关参数的详细信息，请参阅[parameters](parameters-declaration-microsoft-access-sql.md)。|
|*数据类型* | 主要 [Microsoft Access SQL 数据类型](sql-data-types.md)或其同义词之一。 |


## <a name="remarks"></a>说明

SQL 过程由 PROCEDURE 子句（指定该过程的名称）、可选的参数定义列表和一个 SQL 语句组成。 例如，该过程获取\_部件\_可能运行检索指定的部件数目的查询数。

> [!NOTE]
> - 如果子句包含多个字段定义 （即， *param-datatype*对），请使用逗号分隔它们。
> - PROCEDURE 子句的后面必须跟随 SQL 语句（例如，[SELECT](select-statement-microsoft-access-sql.md) 或 [UPDATE](update-statement-microsoft-access-sql.md) 语句）。

## <a name="example"></a>示例

本示例将查询命名为 CategoryList，并调用 EnumFields 过程，您可以在 SELECT 语句示例中找到。

```vb
    Sub ProcedureX() 
     
        Dim dbs As Database, rst As Recordset 
        Dim qdf As QueryDef, strSql As String 
         
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
         
        strSql = "PROCEDURE CategoryList; " _ 
            & "SELECT DISTINCTROW CategoryName, " _ 
            & "CategoryID FROM Categories " _ 
            & "ORDER BY CategoryName;" 
         
        ' Create a named QueryDef based on the SQL 
        ' statement. 
        Set qdf = dbs.CreateQueryDef("NewQry", strSql) 
     
        ' Create a temporary snapshot-type Recordset. 
        Set rst = qdf.OpenRecordset(dbOpenSnapshot) 
     
        ' Populate the Recordset. 
        rst.MoveLast 
                 
        ' Call EnumFields to print the contents of the  
        ' Recordset. Pass the Recordset object and desired 
        ' field width. 
        EnumFields rst, 15 
         
        ' Delete the QueryDef because this is a 
        ' demonstration. 
        dbs.QueryDefs.Delete "NewQry" 
         
        dbs.Close 
     
    End Sub
```
