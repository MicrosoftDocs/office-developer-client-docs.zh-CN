---
title: Recordset.Seek Method (DAO)
TOCTitle: Seek Method
ms:assetid: ef83d909-c962-b016-7d33-36eacdc25c2c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836416(v=office.15)
ms:contentKeyID: 48548585
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053061
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 86d8769749ec4733398c3b89aa12fc4077a14ed1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468703"
---
# <a name="recordsetseek-method-dao"></a>Recordset.Seek Method (DAO)

**适用于**： Access 2013 |Office 2013

在已建立索引的表类型 **Recordset** 对象中查找符合当前索引的指定条件的记录，并使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。Seek （***比较*** ***Key1***、 ***Key2***、 ***Key3***、 ***Key4***、 ***Key5***、 ***Key6***、 ***Key7***、 ***Key8***、 ***Key9***、 ***Key10***、 ***Key11***、 ***Key12***、 ***Key13***）

*表达式*一个表示**Recordset**对象的变量。

### <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Comparison</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>下列字符串表达式之一： &lt;， &lt;=、 =、 &gt;=，或&gt;。</p></td>
</tr>
<tr class="even">
<td><p>Key1，Key2...Key13</p></td>
<td><p>必需</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>与 <strong>Recordset</strong> 对象当前索引中的字段对应的一个或多个值，该索引由它的 <strong>Index</strong> 属性设置指定。最多可使用 13 个 key 参数。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

在使用 **Seek** 之前，必须使用 **Index** 属性设置当前索引。如果索引标识了一个非唯一的键字段， **Seek** 将查找第一个符合条件的记录。

**Seek**方法通过指定的键字段搜索，并查找满足指定相比较的条件和 key1 的第一个记录。 一旦找到，它就会使该记录成为当前记录，同时将 **NoMatch** 属性设置为 **False**。 如果 **Seek** 方法未能找到匹配项， **NoMatch** 属性将设置为 **True**，并且当前记录不确定。

如果 comparison 是等于 （=），大于或等于 (\>=)，或大于 (\>)、 从索引的开头开始**Seek**和向前搜索。

如果 comparison 是小于 (\<) 或小于或等于 (\<=)， **Seek**启动末尾的索引和往回搜索。 但是，如果索引的末尾有重复的索引项， **Seek** 将从重复项中的任一项开始往后搜索。

必须为索引中定义的所有字段指定值。 如果将 **Seek** 用于多列索引，并且没有为索引中的每个字段指定 comparison 值，则无法在 comparison 中使用等于 (=) 运算符。 这是因为某些条件字段 （key2、 key3，等等） 将默认为 Null，可能不匹配。 因此，仅当除查找的键字段外，所有字段均为 **null** 的记录时，等于运算符才能正常工作。 建议您使用大于或等于 (\>=) 运算符相反。

在 key1 参数必须是当前索引中的对应字段的字段数据类型相同。 例如，如果当前索引引用 （如雇员 ID) 的数字字段，key1 必须为数字。 同样，如果当前索引引用 （如姓氏） 的文本字段，key1 必须是字符串。

使用 **Seek** 时不一定要有当前记录。

可以使用 **[Indexes](indexes-collection-dao.md)** 集合枚举现有索引。

要在动态集类型或快照类型的 **Recordset** 中查找一个符合特定条件且没有被现有索引覆盖的记录，请使用 **[Find](recordset-findfirst-method-dao.md)** 方法。要包括所有记录而不仅仅是符合特定条件的那些记录，请使用 **[Move](recordset-movefirst-method-dao.md)** 方法在记录间移动。

不能对链接表使用 **Seek** 方法，原因是不能将链接表打开为表类型 **Recordset** 对象。但是，如果使用 **[OpenDatabase](dbengine-opendatabase-method-dao.md)** 方法直接打开一个可安装的 ISAM（非 ODBC）数据库，则可以对该数据库中的表使用 **Seek**。

## <a name="example"></a>示例

以下示例通过允许用户根据 ID 编号搜索产品，来演示 **Seek** 方法。

```vb
    Sub SeekX() 
     
       Dim dbsNorthwind As Database 
       Dim rstProducts As Recordset 
       Dim intFirst As Integer 
       Dim intLast As Integer 
       Dim strMessage As String 
       Dim strSeek As String 
       Dim varBookmark As Variant 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       ' You must open a table-type Recordset to use an index,  
       ' and hence the Seek method. 
       Set rstProducts = _ 
          dbsNorthwind.OpenRecordset("Products", dbOpenTable) 
     
       With rstProducts 
          ' Set the index. 
          .Index = "PrimaryKey" 
     
          ' Get the lowest and highest product IDs. 
          .MoveLast 
          intLast = !ProductID 
          .MoveFirst 
          intFirst = !ProductID 
     
          Do While True 
             ' Display current record information and ask user  
             ' for ID number. 
             strMessage = "Product ID: " & !ProductID & vbCr & _ 
                "Name: " & !ProductName & vbCr & vbCr & _ 
                "Enter a product ID between " & intFirst & _ 
                " and " & intLast & "." 
             strSeek = InputBox(strMessage) 
     
             If strSeek = "" Then Exit Do 
     
             ' Store current bookmark in case the Seek fails. 
             varBookmark = .Bookmark 
     
             .Seek "=", Val(strSeek) 
     
             ' Return to the current record if the Seek fails. 
             If .NoMatch Then 
                MsgBox "ID not found!" 
                .Bookmark = varBookmark 
             End If 
          Loop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

以下示例使用 **NoMatch** 属性确定 **Seek** 和 **FindFirst** 是否成功，如果未成功，则提供相应的反馈。若要使该过程运行，需要使用 SeekMatch 和 FindMatch 过程。

```vb
    Sub NoMatchX() 
     
       Dim dbsNorthwind As Database 
       Dim rstProducts As Recordset 
       Dim rstCustomers As Recordset 
       Dim strMessage As String 
       Dim strSeek As String 
       Dim strCountry As String 
       Dim varBookmark As Variant 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       ' Default is dbOpenTable; required if Index property will  
       ' be used. 
       Set rstProducts = dbsNorthwind.OpenRecordset("Products") 
     
       With rstProducts 
          .Index = "PrimaryKey" 
     
          Do While True 
             ' Show current record information; ask user for  
             ' input. 
             strMessage = "NoMatch with Seek method" & vbCr & _ 
                "Product ID: " & !ProductID & vbCr & _ 
                "Product Name: " & !ProductName & vbCr & _ 
                "NoMatch = " & .NoMatch & vbCr & vbCr & _ 
                "Enter a product ID." 
             strSeek = InputBox(strMessage) 
             If strSeek = "" Then Exit Do 
     
             ' Call procedure that seeks for a record based on  
             ' the ID number supplied by the user. 
             SeekMatch rstProducts, Val(strSeek) 
          Loop 
     
          .Close 
       End With 
     
       Set rstCustomers = dbsNorthwind.OpenRecordset( _ 
          "SELECT CompanyName, Country FROM Customers " & _ 
          "ORDER BY CompanyName", dbOpenSnapshot) 
     
       With rstCustomers 
     
          Do While True 
             ' Show current record information; ask user for  
             ' input. 
             strMessage = "NoMatch with FindFirst method" & _ 
                vbCr & "Customer Name: " & !CompanyName & _ 
                vbCr & "Country: " & !Country & vbCr & _ 
                "NoMatch = " & .NoMatch & vbCr & vbCr & _ 
                "Enter country on which to search." 
             strCountry = Trim(InputBox(strMessage)) 
             If strCountry = "" Then Exit Do 
     
             ' Call procedure that finds a record based on  
             ' the country name supplied by the user. 
             FindMatch rstCustomers, _ 
                "Country = '" & strCountry & "'" 
          Loop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
     
    Sub SeekMatch(rstTemp As Recordset, _ 
       intSeek As Integer) 
     
       Dim varBookmark As Variant 
       Dim strMessage As String 
     
       With rstTemp 
          ' Store current record location. 
          varBookmark = .Bookmark 
          .Seek "=", intSeek 
     
          ' If Seek method fails, notify user and return to the  
          ' last current record. 
          If .NoMatch Then 
             strMessage = _ 
                "Not found! Returning to current record." & _ 
                vbCr & vbCr & "NoMatch = " & .NoMatch 
             MsgBox strMessage 
             .Bookmark = varBookmark 
          End If 
     
       End With 
     
    End Sub 
     
    Sub FindMatch(rstTemp As Recordset, _ 
       strFind As String) 
     
       Dim varBookmark As Variant 
       Dim strMessage As String 
     
       With rstTemp 
          ' Store current record location. 
          varBookmark = .Bookmark 
          .FindFirst strFind 
     
          ' If Find method fails, notify user and return to the  
          ' last current record. 
          If .NoMatch Then 
             strMessage = _ 
                "Not found! Returning to current record." & _ 
                vbCr & vbCr & "NoMatch = " & .NoMatch 
             MsgBox strMessage 
             .Bookmark = varBookmark 
          End If 
     
       End With 
     
    End Sub 
```

<br/>

下面的示例演示如何使用 Seek 方法来查找链接表中的记录。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    Sub TestSeek()
        ' Get the path to the external database that contains
        ' the tblCustomers table we're going to search.
        Dim strMyExternalDatabase
        Dim dbs    As DAO.Database
        Dim dbsExt As DAO.Database
        Dim rst    As DAO.Recordset
        Dim tdf    As DAO.TableDef
        
        Set dbs = CurrentDb()
        Set tdf = dbs.TableDefs("tblCustomers")
        strMyExternalDatabase = Mid(tdf.Connect, 11)
        
        'Open the database that contains the table that is linked
        Set dbsExt = OpenDatabase(strMyExternalDatabase)
        
        'Open a table-type recordset against the external table
        Set rst = dbsExt.OpenRecordset("tblCustomers", dbOpenTable)
        
        'Specify which index to search on
        rst.Index = "PrimaryKey"
        
        'Specify the criteria
        rst.Seek "=", 123
        
        'Check the result
        If rst.NoMatch Then
            MsgBox "Record not found."
        Else
            MsgBox "Customer name: " & rst!CustName
        End If
        
        rst.Close
        dbs.Close
        dbsExt.Close
        Set rst = Nothing
        Set tdf = Nothing
        Set dbs = Nothing
        
        
    End Sub
```
