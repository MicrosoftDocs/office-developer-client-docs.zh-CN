---
title: QueryDef 对象 (DAO)
TOCTitle: QueryDef Object
ms:assetid: 0b3d901c-345d-42a2-f5f1-fb09cc562e27
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845129(v=office.15)
ms:contentKeyID: 48543169
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: a94d34a2dbe8043e6db637b649f59047cf3f1dda
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301055"
---
# <a name="querydef-object-dao"></a>QueryDef 对象 (DAO)

**适用于**：Access 2013 | Office 2013 

**QueryDef** 对象是 Microsoft Access 数据库引擎数据库中的查询的存储定义。

## <a name="remarks"></a>说明

可以使用 **QueryDef** 对象定义查询。例如，您可以进行下列操作：

- 使用 **SQL** 属性设置或返回查询定义。

- 使用 **QueryDef** 对象的 **Parameters** 集合设置或返回查询参数。

- 使用 **Type** 属性返回一个值，该值指示查询是从现有表中选择记录、制作一个新表、将记录从一个表插入到另一个表、删除记录还是更新记录。

- 使用 **MaxRecords** 属性限制从查询返回的记录数。

- 使用 **ODBCTimeout** 属性指示查询返回记录之前需要等待的时间长短。 **ODBCTimeout** 属性可应用到访问开放式数据库连接 (ODBC) 数据的任何查询。

- 使用 **ReturnsRecords** 属性指示查询返回记录。 **ReturnsRecords** 属性仅对 SQL 传递查询有效。

- 使用 **Connect** 属性生成一个访问 ODC 数据库的 SQL 传递查询。

还可以创建临时 **QueryDef** 对象。与永久 **QueryDef** 对象不同，临时 **QueryDef** 对象不会被保存到磁盘，也不会被追加到 **QueryDefs** 集合。对于在运行时必须反复运行，但不需要在磁盘中保存的查询，使用临时 **QueryDef** 对象十分有用，对于在运行时需要创建其 SQL 字符串/语句的查询尤其如此。

可以将 Microsoft Access 工作区中的永久 **QueryDef** 对象视为编译的 SQL 语句。如果从永久 **QueryDef** 对象执行查询，则查询的运行速度比通过 **OpenRecordset** 方法运行等效 SQL 语句的速度更快。这是因为 Microsoft Access 数据库引擎在执行查询之前，不需要对其进行编译。

使用通过 Microsoft Access 数据库引擎访问的外部数据库引擎的本地 SQL 方言的首选方法是使用 **QueryDef** 对象。例如，可以创建一个 Microsoft SQL Server 查询，并将其存储在 **QueryDef** 对象中。如果需要使用非 Microsoft Access 数据库引擎 SQL 查询，必须提供一个指向外部数据源的 **Connect** 属性字符串。具有有效 **Connect** 属性的查询将绕过 Microsoft Access 数据库引擎，并将查询直接传递给外部数据库服务器，以进行处理。

要新建 **QueryDef** 对象，请使用 **CreateQueryDef** 方法。 在 Microsoft Access 工作区中，如果为  name 参数提供了字符串，或者将新的 **QueryDef** 对象的 **Name** 属性显式设置为非零长度字符串，那么将创建一个会自动追加到 **QueryDefs** 集合并保存到磁盘的永久 **QueryDef**。 提供零长度字符串作为  name 参数或将 **Name** 属性显式设置为零长度字符串将导致生成临时的 **QueryDef** 对象。

若要按照序号或 **Name** 属性设置来引用集合中的 **QueryDef** 对象，可以使用下列任何一种语法形式：

QueryDefs(0)

QueryDefs("name")

QueryDefs\!\[ name\]

仅可以按照分配给临时 **QueryDef** 对象的对象变量来引用这些对象。

**链接提供者：**[UtterAccess](https://www.utteraccess.com) 社区。 UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。

- [查询：文档 SQL 到 Word](https://www.utteraccess.com/wiki/index.php/queries:_document_sql_to_word)

## <a name="example"></a>示例

以下示例创建一个新的 **QueryDef** 对象，并将其追加到 Northwind **Database** 对象的 **QueryDefs** 集合。然后，该示例枚举 **QueryDefs** 集合和新 **QueryDef** 的 **Properties** 集合。

```vb
    Sub QueryDefX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfNew As QueryDef 
       Dim qdfLoop As QueryDef 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' Create new QueryDef object. Because it has a  
       ' name, it is automatically appended to the  
       ' QueryDefs collection. 
       Set qdfNew = dbsNorthwind.CreateQueryDef("NewQueryDef", _ 
             "SELECT * FROM Categories") 
     
       With dbsNorthwind 
          Debug.Print .QueryDefs.Count & _ 
             " QueryDefs in " & .Name 
     
          ' Enumerate QueryDefs collection. 
          For Each qdfLoop In .QueryDefs 
             Debug.Print "  " & qdfLoop.Name 
          Next qdfLoop 
     
          With qdfNew 
             Debug.Print "Properties of " & .Name 
     
             ' Enumerate Properties collection of new  
             ' QueryDef object. 
             For Each prpLoop In .Properties 
                On Error Resume Next 
                Debug.Print "  " & prpLoop.Name & " - " & _ 
                   IIf(prpLoop = "", "[empty]", prpLoop) 
                On Error Goto 0 
             Next prpLoop 
          End With 
     
          ' Delete new QueryDef because this is a  
          ' demonstration. 
          .QueryDefs.Delete qdfNew.Name 
          .Close 
       End With 
     
    End Sub 
```

<br/>

以下示例使用 **CreateQueryDef** 方法创建并执行临时和永久的 **QueryDef**。若要使该过程运行，需要使用 GetrstTemp 函数。

```vb
    Sub CreateQueryDefX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfTemp As QueryDef 
       Dim qdfNew As QueryDef 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       With dbsNorthwind 
          ' Create temporary QueryDef. 
          Set qdfTemp = .CreateQueryDef("", _ 
             "SELECT * FROM Employees") 
          ' Open Recordset and print report. 
          GetrstTemp qdfTemp 
          ' Create permanent QueryDef. 
          Set qdfNew = .CreateQueryDef("NewQueryDef", _ 
             "SELECT * FROM Categories") 
          ' Open Recordset and print report. 
          GetrstTemp qdfNew 
          ' Delete new QueryDef because this is a demonstration. 
          .QueryDefs.Delete qdfNew.Name 
          .Close 
       End With 
     
    End Sub 
     
    Function GetrstTemp(qdfTemp As QueryDef) 
     
       Dim rstTemp As Recordset 
     
       With qdfTemp 
          Debug.Print .Name 
          Debug.Print "  " & .SQL 
          ' Open Recordset from QueryDef. 
          Set rstTemp = .OpenRecordset(dbOpenSnapshot) 
     
          With rstTemp 
             ' Populate Recordset and print number of records. 
             .MoveLast 
             Debug.Print "  Number of records = " & _ 
                .RecordCount 
             Debug.Print 
             .Close 
          End With 
     
       End With 
     
    End Function 
```

<br/>

以下示例演示如何替换保存的查询中的结构化查询语言 (SQL) 语句。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    ‘To change the Where clause in a saved query  
    Dim qdf as QueryDef
    Dim db as Database
    Set db = CurrentDB
    Set qdf = db.QueryDefs("YourQueryName")
    qdf.SQL = ReplaceWhereClause(qdf.SQL, strYourNewWhereClause)
    set qdf = Nothing
    set db = Nothing
    
    Public Function ReplaceWhereClause(strSQL As Variant, strNewWHERE As Variant)
    On Error GoTo Error_Handler
    
    ‘This subroutine accepts a valid SQL string and Where clause, and
    ‘returns the same SQL statement with the original Where clause (if any)
    ‘replaced by the passed in Where clause.
    ‘
    ‘INPUT:
    ‘ strSQL valid SQL string to change
    ‘OUTPUT:
    ‘ strNewWHERE New WHERE clause to insert into SQL statement
    ‘
        Dim strSELECT As String, strWhere As String
        Dim strOrderBy As String, strGROUPBY As String, strHAVING As String
    
        Call ParseSQL(strSQL, strSELECT, strWhere, strOrderBy, _
            strGROUPBY, strHAVING)
    
        ReplaceWhereClause = strSELECT &""& strNewWHERE &""_
            & strGROUPBY &""& strHAVING &""& strOrderBy
    
        Exit_Procedure:
            Exit Function
    
        Error_Handler:
            MsgBox (Err.Number & ": " & Err.Description)
            Resume Exit_Procedure
    
    End Function
```

