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
ms.openlocfilehash: 573ec86a573697ebe52886535f8544bbaab61d7d
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861461"
---
# <a name="create-procedure-statement-microsoft-access-sql"></a>CREATE PROCEDURE 语句 (Microsoft Access SQL)

**适用于**： Access 2013 |Office 2013 

创建存储过程。

> [!NOTE]
> [!注释] Microsoft Access 数据库引擎不支持对非 Microsoft Jet 数据库引擎的数据库使用 CREATE PROCEDURE 语句或者任何 DDL 语句。

## <a name="syntax"></a>语法

CREATE PROCEDURE*过程* \[ *param1 datatype*\[， *param2 datatype*\[，...\] \]为 sqlstatement

CREATE PROCEDURE 语句包含以下部分：

|部分|说明|
|:---|:----------|
|*procedure*|过程名称。它必须遵循标准命名规则。|
|*param1*、*param2*|1 到 255 个字段名称或参数。例如：
<br/><br/>`CREATE PROCEDURE Sales_By_Country [Beginning Date] DateTime, [Ending Date] DateTime;`<br/><br/>有关参数的详细信息，请参阅[PARAMETERS](parameters-declaration-microsoft-access-sql.md)。|
|*数据类型*|主要 [Microsoft Access SQL 数据类型](sql-data-types.md)或其同义词之一。|
|*sqlstatement*|SQL 语句，如 SELECT、UPDATE、DELETE、INSERT、CREATE TABLE 和 DROP TABLE 等等。|


## <a name="remarks"></a>注解

SQL 过程由用于指定过程名的 PROCEDURE 子句、可选的参数定义列表和一个 SQL 语句组成。

过程名不能和现有表的名称相同。

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
