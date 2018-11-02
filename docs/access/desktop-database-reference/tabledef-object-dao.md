---
title: TableDef 对象 (DAO)
TOCTitle: TableDef Object
ms:assetid: 715146b6-c62a-abff-28ee-e6bbe3c08adf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195790(v=office.15)
ms:contentKeyID: 48545582
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2670dadade6e934a1696251867d8ea67e8bbfc53
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927366"
---
# <a name="tabledef-object-dao"></a>TableDef 对象 (DAO)

**适用于**： Access 2013、 Office 2013

**TableDef** 对象代表基表或链接表的已存储定义（仅适用于 Microsoft Access 工作区）。

## <a name="remarks"></a>注解

通过使用 **TableDef** 对象及其方法和属性来操作表定义。例如，您可以进行下列操作：

- 检查数据库中的任何本地表、链接表或外部表的字段和索引结构。

- 使用 **Connect** 和 **SourceTableName** 属性设置或返回有关链接表的信息，并使用 **RefreshLink** 方法更新与链接表的连接。

- 使用 **ValidationRule** 和 **ValidationText** 属性设置或返回验证条件。

- 使用**OpenRecordset**方法创建表 –、 动态集类型、 动态 –、 快照类型或仅向前类型**Recordset**对象，根据表定义。

对于基表， **RecordCount** 属性包含指定数据库表中的记录数。 对于链接表， **RecordCount**属性设置始终为-1。

若要创建新的 **TableDef** 对象，请使用 **[CreateTableDef](database-createtabledef-method-dao.md)** 方法。

### <a name="to-add-a-field-to-a-table"></a>向表中添加字段

1.  确保基于表的任何 **[Recordset](recordset-object-dao.md)** 对象全都已关闭。

2.  使用 **CreateField** 方法创建 **Field** 对象变量，然后设置其属性。

3.  使用 **Append** 方法将 **Field** 对象添加到 **TableDef** 对象的 **Fields** 集合。

如果没有给 **TableDefs** 集合中的 **Field** 对象分配任何索引，则可以将其删除，但是会丢失字段的数据。

### <a name="to-create-a-table-that-is-ready-for-new-records-in-a-database"></a>创建可随时用作数据库中新记录的表

1.  使用 **CreateTableDef** 方法创建 **TableDef** 对象。

2.  设置该对象的属性。

3.  对于表中的每个字段，使用 **CreateField** 方法创建 **Field** 对象变量，然后设置其属性。

4.  使用 **Append** 方法，将字段添加到 **TableDef** 对象的 **Fields** 集合。

5.  使用 **Append** 方法，将新的 **TableDef** 对象添加到 **Database** 对象的 **TableDefs** 集合。

链接表由 **TableDef** 对象的 **SourceTableName** 和 **Connect** 属性连接到数据库。

### <a name="to-link-a-table-to-a-database"></a>将表链接到数据库

1.  使用 **CreateTableDef** 方法创建 **TableDef** 对象。

2.  设置该对象的 **Connect** 和 **SourceTableName** 属性（并且有选择地设置它的 **Attributes** 属性）。

3.  使用 **Append** 方法，将该对象添加到 **Database** 的 **TableDefs** 集合。

若要按照序号或 **Name** 属性设置来引用集合中的 **TableDef** 对象，可以使用下列任何一种语法形式：

**TableDefs**(0)

**TableDefs**("name")

**TableDefs**\!\[名称\]

## <a name="example"></a>示例

以下示例创建一个新的 **TableDef** 对象，并将其追加到 Northwind Database 对象的 **TableDefs** 集合。然后，该示例枚举 **TableDefs** 集合和新 **TableDef** 的 **Properties** 集合。

```vb
    Sub TableDefX() 
     
       Dim dbsNorthwind As Database 
       Dim tdfNew As TableDef 
       Dim tdfLoop As TableDef 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' Create new TableDef object, append Field objects  
       ' to its Fields collection, and append TableDef  
       ' object to the TableDefs collection of the  
       ' Database object. 
       Set tdfNew = dbsNorthwind.CreateTableDef("NewTableDef") 
       tdfNew.Fields.Append tdfNew.CreateField("Date", dbDate) 
       dbsNorthwind.TableDefs.Append tdfNew 
     
       With dbsNorthwind 
          Debug.Print .TableDefs.Count & _ 
             " TableDefs in " & .Name 
     
          ' Enumerate TableDefs collection. 
          For Each tdfLoop In .TableDefs 
             Debug.Print "  " & tdfLoop.Name 
          Next tdfLoop 
     
          With tdfNew 
             Debug.Print "Properties of " & .Name 
     
             ' Enumerate Properties collection of new 
             ' TableDef object, only printing properties 
             ' with non-empty values. 
             For Each prpLoop In .Properties 
                Debug.Print "  " & prpLoop.Name & " - " & _ 
                   IIf(prpLoop = "", "[empty]", prpLoop) 
             Next prpLoop 
     
          End With 
     
          ' Delete new TableDef since this is a  
          ' demonstration. 
          .TableDefs.Delete tdfNew.Name 
          .Close 
       End With 
     
    End Sub 
```

<br/>

以下示例在 Northwind 数据库中创建一个新的 **TableDef** 对象。

```vb 
Sub CreateTableDefX() 
 
   Dim dbsNorthwind As Database 
   Dim tdfNew As TableDef 
   Dim prpLoop As Property 
 
   Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
   ' Create a new TableDef object. 
   Set tdfNew = dbsNorthwind.CreateTableDef("Contacts") 
 
   With tdfNew 
      ' Create fields and append them to the new TableDef  
      ' object. This must be done before appending the  
      ' TableDef object to the TableDefs collection of the  
      ' Northwind database. 
      .Fields.Append .CreateField("FirstName", dbText) 
      .Fields.Append .CreateField("LastName", dbText) 
      .Fields.Append .CreateField("Phone", dbText) 
      .Fields.Append .CreateField("Notes", dbMemo) 
 
      Debug.Print "Properties of new TableDef object " & _ 
         "before appending to collection:" 
 
      ' Enumerate Properties collection of new TableDef  
      ' object. 
      For Each prpLoop In .Properties 
         On Error Resume Next 
         If prpLoop <> "" Then Debug.Print "  " & _ 
           prpLoop.Name & " = " & prpLoop 
         On Error GoTo 0 
      Next prpLoop 
 
      ' Append the new TableDef object to the Northwind  
      ' database. 
      dbsNorthwind.TableDefs.Append tdfNew 
 
      Debug.Print "Properties of new TableDef object " & _ 
         "after appending to collection:" 
 
      ' Enumerate Properties collection of new TableDef  
      ' object. 
      For Each prpLoop In .Properties 
         On Error Resume Next 
         If prpLoop <> "" Then Debug.Print "  " & _ 
           prpLoop.Name & " = " & prpLoop 
         On Error GoTo 0 
      Next prpLoop 
 
   End With 
 
   ' Delete new TableDef object since this is a  
   ' demonstration. 
   dbsNorthwind.TableDefs.Delete "Contacts" 
 
   dbsNorthwind.Close 
```

<br/>

下面的示例演示如何创建计算的字段。 CreateField 方法创建一个名为**FullName**字段。 然后表达式属性设置为计算字段的值的表达式。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    Sub CreateCalculatedField()
        Dim dbs As DAO.Database
        Dim tdf As DAO.TableDef
        Dim fld As DAO.Field2
        
        ' get the database
        Set dbs = CurrentDb()
        
        ' create the table
        Set tdf = dbs.CreateTableDef("tblContactsCalcField")
        
        ' create the fields: first name, last name
        tdf.Fields.Append tdf.CreateField("FirstName", dbText, 20)
        tdf.Fields.Append tdf.CreateField("LastName", dbText, 20)
        
        ' create the calculated field: full name
        Set fld = tdf.CreateField("FullName", dbText, 50)
        fld.Expression = "[FirstName] & "" "" & [LastName]"
        tdf.Fields.Append fld
        
        ' append the table and cleanup
        dbs.TableDefs.Append tdf
        
    Cleanup:
        Set fld = Nothing
        Set tdf = Nothing
        Set dbs = Nothing
    End Sub
```
