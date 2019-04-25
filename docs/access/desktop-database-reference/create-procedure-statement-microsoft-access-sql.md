---
title: CREATE PROCEDURE 语句 (Microsoft Access SQL)
TOCTitle: CREATE PROCEDURE statement (Microsoft Access SQL)
ms:assetid: 1fbb5267-9862-bfb4-6436-176152d7a6cd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845861(v=office.15)
ms:contentKeyID: 48543649
ms.date: 10/18/2018
mtps_version: v=office.15
dev_langs:
- sql
localization_priority: Priority
ms.openlocfilehash: f223e164bd36a6a1a76140a28dd57cd2005e4a20
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295400"
---
# <a name="create-procedure-statement-microsoft-access-sql"></a>CREATE PROCEDURE 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013 

创建存储过程。

> [!NOTE]
> Microsoft Access 数据库引擎不支持对非 Microsoft Jet 数据库引擎的数据库使用 CREATE PROCEDURE 语句或者任何 DDL 语句。

## <a name="syntax"></a>语法

CREATE PROCEDURE *procedure* \[*param1 datatype*\[, *param2 datatype*\[, …\]\] AS sqlstatement

CREATE PROCEDURE 语句包含以下部分：

|Part|说明|
|:---|:----------|
|*procedure*|过程的名称。 它必须遵循标准命名规则。|
|*param1*、*param2*|从 1 到 255 个字段名或参数。 例如：<br/><br/>`CREATE PROCEDURE Sales_By_Country [Beginning Date] DateTime, [Ending Date] DateTime;`<br/><br/>有关参数的详细信息，请参阅 [PARAMETERS](parameters-declaration-microsoft-access-sql.md)。|
|*datatype*|主要 [Microsoft Access SQL 数据类型](sql-data-types.md)或其同义词之一。|
|*sqlstatement*|SQL 语句，如 SELECT、UPDATE、DELETE、INSERT、CREATE TABLE、DROP TABLE 等。|


## <a name="remarks"></a>说明

SQL 过程包含一个 PROCEDURE 子句（该子句指定过程的名称）、参数定义的可选列表和单个 SQL 语句。

过程名称不能与现有表的名称相同。

## <a name="example"></a>示例

本示例将查询命名为 CategoryList，并调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。

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
