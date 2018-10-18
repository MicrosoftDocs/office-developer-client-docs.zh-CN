---
标题： 使用 Microsoft Access 用作 DDE 服务器 TOCTitle： 使用 Microsoft Access 用作 DDE 服务器 <<<<<<< 标头 ms:assetid: a3e82bf7-94b5-8eec-86bc-2d5387d66738 ms:mtpsurl: https://msdn.microsoft.com/library/Ff821067(v=office.15) ms:contentKeyID: 48546801 ms.date: 09/18/2015年 ===说明： Microsoft Access 支持动态数据交换 (DDE) 作为目标 （客户端） 应用程序或源 （服务器） 应用程序。  
ms:assetid: a3e82bf7-94b5-8eec-86bc-2d5387d66738 ms:mtpsurl: https://msdn.microsoft.com/library/Ff821067(v=office.15) ms:contentKeyID: 48546801 ms.date: 10/16/2018
>>>>>>> 主 mtps_version: office.15.aspx f1_keywords:
- vbaac10.chm5186349 f1_categories:
- Office.Version=v15
---

# <a name="use-microsoft-access-as-a-dde-server"></a>Microsoft Access 用作 DDE 服务器

**适用于**： Access 2013 |Office 2013 

Microsoft Access 以目标（客户端）应用程序或源（服务器）应用程序形式支持动态数据交换 (DDE)。例如，一个作为客户端的应用程序，如 Microsoft Word，可以通过 DDE 从一个作为服务器的 Microsoft Access 数据库请求数据。

> [!TIP]
> [!提示] 如果要从另一个应用程序中操纵 Microsoft Access 对象，可能需要考虑使用"自动化"。

<<<<<<< 标头 DDE 会话客户端和服务器之间建立在特定的主题。 主题可以是服务器应用程序所支持格式的数据文件，也可以是提供有关服务器应用程序本身信息的 System 主题。 开始了特定主题的对话后，只能传送与该主题相关的数据项。
=== DDE 对话客户端和服务器之间建立在特定的主题。 主题可以是服务器应用程序所支持格式的数据文件，也可以是提供有关服务器应用程序本身信息的 System 主题。 在特定的主题开始对话后，可以传送仅与该主题相关的数据项。
>>>>>>> master

例如，假定您正在运行 Microsoft Word，并要将一个特定的 Microsoft Access 数据库中的数据插入到文档中。通过使用 **DDEInitiate** 函数将 DDE 通道打开，并指定数据库文件名称作为主题，即可开始与 Microsoft Access 的 DDE 对话，然后就可以通过该通道将数据库中的数据传送给 Microsoft Word。

作为 DDE 服务器，Microsoft Access 支持以下主题：

<<<<<<< 标头
  - System 主题

  - 数据库的名称（*database* 主题）

  - 表的名称（*tablename* 主题）

  - 查询的名称（*queryname* 主题）

  - Microsoft Access SQL 字符串（*sqlstring* 主题）

建立了 DDE 对话后，可以使用 **DDEExecute** 语句将命令从客户端发送到服务器应用程序。Microsoft Access 在用作 DDE 服务器时，将以下命令均识别为有效命令：

  - 当前数据库中的宏名称。

  - 可在 Visual Basic 中使用 **DoCmd** 对象的某个方法执行的任何操作。

  - 仅用于 DDE 运算的 OpenDatabase 和 CloseDatabase 操作。（有关如何使用这些操作的示例，请参阅本主题后面部分的示例。）


> [!NOTE]
> <P>[!注释] 当将一个宏操作指定为 <STRONG>DDEExecute</STRONG> 语句时，该操作和所有参数均遵循 <STRONG>DoCmd</STRONG> 对象的语法且必须包含在方括号 ([ ]) 中。但支持 DDE 的应用程序并不识别 DDE 运算中的固有常量。同样，如果字符串包含逗号，则必须将该字符串参数包括在引号 (" ") 中。否则，就不需要引号。</P>



通过打开的 DDE 通道，客户端应用程序可以使用 **DDERequest** 函数向服务器应用程序请求文本数据。反之，客户端可以使用 **DDEPoke** 语句将数据发送到服务器应用程序。数据传送完后，客户端可以使用 **DDETerminate** 语句关闭 DDE 通道，或使用 **DDETerminateAll** 语句关闭所有打开的通道。


> [!NOTE]
> <P>[!注释] 当客户端应用程序通过 DDE 通道接收完数据后，应关闭该通道以节省内存资源。</P>


=======
- System 主题

- 数据库的名称（*database* 主题）

- 表的名称（*tablename* 主题）

- 查询的名称（*queryname* 主题）

- Microsoft Access SQL 字符串（*sqlstring* 主题）

已建立 DDE 会话后，您可以使用**DDEExecute**语句将命令从客户端发送到服务器应用程序。 Microsoft Access 在用作 DDE 服务器时，将以下命令均识别为有效命令：

- 当前数据库中的宏名称。

- 可在 Visual Basic 中使用 **DoCmd** 对象的某个方法执行的任何操作。

- 仅用于 DDE 运算的 OpenDatabase 和 CloseDatabase 操作。（有关如何使用这些操作的示例，请参阅本主题后面部分的示例。）

> [!NOTE]
> [!注释] 当将一个宏操作指定为 **DDEExecute** 语句时，该操作和所有参数均遵循 **DoCmd** 对象的语法且必须包含在方括号 ([ ]) 中。但支持 DDE 的应用程序并不识别 DDE 运算中的固有常量。同样，如果字符串包含逗号，则必须将该字符串参数包括在引号 (" ") 中。否则，就不需要引号。

通过打开的 DDE 通道，客户端应用程序可以使用 **DDERequest** 函数向服务器应用程序请求文本数据。 反之，客户端可以使用 **DDEPoke** 语句将数据发送到服务器应用程序。 数据传输完成后，客户端可使用**DDETerminate**语句关闭 DDE 通道或**DDETerminateAll**语句关闭所有打开的通道。

> [!NOTE]
> [!注释] 当客户端应用程序通过 DDE 通道接收完数据后，应关闭该通道以节省内存资源。
>>>>>>> master

下面的示例将演示如何用 Visual Basic 创建 Microsoft Word 过程，并将 Microsoft Access 用作 DDE 服务器。（必须正在运行 Microsoft Access，才能使该示例工作。）

```vb
    Sub AccessDDE() 
        Dim intChan1 As Integer, intChan2 As Integer 
        Dim strQueryData As String 
     
        ' Use System topic to open Northwind sample database. 
        ' Database must be open before using other DDE topics. 
        intChan1 = DDEInitiate("MSAccess", "System") 
        ' You may need to change this path to point to actual location 
        ' of Northwind sample database. 
        DDEExecute intChan1, "[OpenDatabase C:\Access\Samples\Northwind.mdb]" 
     
        ' Get all data from Ten Most Expensive Products query. 
        intChan2 = DDEInitiate("MSAccess", "Northwind.mdb;" _ 
            & "QUERY Ten Most Expensive Products") 
        strQueryData = DDERequest(intChan2, "All") 
        DDETerminate intChan2 
     
        ' Close database. 
        DDEExecute intChan1, "[CloseDatabase]" 
        DDETerminate intChan1 
     
        ' Print retrieved data to Debug Window. 
        Debug.Print strQueryData 
    End Sub
```

<a name="-head"></a><<<<<<< 标头
=======
<br/>

>>>>>>> 以下各节提供有关 Microsoft Access 支持的有效 DDE 主题的信息的主控形状。

## <a name="the-system-topic"></a>System 主题

<<<<<<< 标头 System 主题是标准的所有 Microsoft – 基于 Windows 的应用程序主题。 它提供有关支持的应用程序的其他主题的信息。 若要访问此信息，您的代码必须首先调用**DDEInitiate**函数与作为*topic*参数，然后使用*item*参数提供下列选项之一执行**DDERequest**语句。
=== System 主题是标准的所有 Microsoft – 基于 Windows 的应用程序主题。 它提供有关支持的应用程序的其他主题的信息。 若要访问此信息，您的代码必须首先调用**DDEInitiate**函数与*topic*参数，然后使用*item*参数提供下列选项之一执行**DDERequest**语句。
>>>>>>> master

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>返回</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SysItems</p></td>
<td><p>Microsoft Access 中 System 主题所支持的项目的列表。</p></td>
</tr>
<tr class="even">
<td><p>Formats</p></td>
<td><p>Microsoft Access 可以复制到“剪贴板”上的格式的列表。</p></td>
</tr>
<tr class="odd">
<td><p>Status</p></td>
<td><p>&quot;忙&quot;或&quot;准备&quot;。</p></td>
</tr>
<tr class="even">
<td><p>Topics</p></td>
<td><p>所有已打开的数据库的列表。</p></td>
</tr>
</tbody>
</table>

<a name="-head"></a><<<<<<< 标头
=======
<br/>
>>>>>>> master

下面的示例说明如何使用带有 System 主题的 **DDEInitiate** 和 **DDERequest** 函数：

```vb
    ' In Visual Basic, initiate DDE conversation with Microsoft Access. 
    Dim intChan1 As Integer, strResults As String 
    intChan1 = DDEInitiate("MSAccess", "System") 
    ' Request list of topics supported by System topic. 
    strResults = DDERequest(intChan1, "SysItems") 
    ' Run OpenDatabase action to open Northwind.mdb. 
    ' You may need to change this path to point to actual location 
    ' of Northwind sample database. 
    DDEExecute intChan1, "[OpenDatabase C:\Access\Samples\Northwind.mdb]"
```

## <a name="the-database-topic"></a>Database 主题

*Database*主题是数据库的一个现有的文件名。 您可以键入刚的基名称 (Northwind) 或其路径和.mdb 扩展名 (c:\\访问\\示例\\Northwind.mdb)。 在开始与该数据库的 DDE 对话以后，可以请求该数据库中的对象列表。

<<<<<<< 标头

> [!NOTE]
> <P>[!注释] 不能使用 DDE 来查询 Microsoft Access 工作组信息文件。</P>


=======
> [!NOTE]
> [!注释] 不能使用 DDE 来查询 Microsoft Access 工作组信息文件。
>>>>>>> master

*database* 主题支持以下项目。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>返回</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TableList</p></td>
<<<<<<< 标头
<td><p>表列表。</p></td>
</tr>
<tr class="even">
<td><p>QueryList</p></td>
<td><p>查询列表。</p></td>
</tr>
<tr class="odd">
<td><p>FormList</p></td>
<td><p>窗体列表。</p></td>
</tr>
<tr class="even">
<td><p>ReportList</p></td>
<td><p>报表列表。</p></td>
</tr>
<tr class="odd">
<td><p>MacroList</p></td>
<td><p>宏列表。</p></td>
</tr>
<tr class="even">
<td><p>ModuleList</p></td>
<td><p>模块列表。</p></td>
=======
<td><p>表的列表</p></td>
</tr>
<tr class="even">
<td><p>QueryList</p></td>
<td><p>查询列表</p></td>
</tr>
<tr class="odd">
<td><p>FormList</p></td>
<td><p>窗体列表</p></td>
</tr>
<tr class="even">
<td><p>ReportList</p></td>
<td><p>报表的列表</p></td>
</tr>
<tr class="odd">
<td><p>MacroList</p></td>
<td><p>宏列表</p></td>
</tr>
<tr class="even">
<td><p>ModuleList</p></td>
<td><p>模块列表</p></td>
>>>>>>>主控形状
</tr>
<tr class="odd">
<td><p>ViewList</p></td>
<td><p>视图列表。</p></td>
</tr>
<tr class="even">
<td><p>StoredProcedureList</p></td>
<td><p>存储过程列表。</p></td>
</tr>
<tr class="odd">
<td><p>DatabaseDiagramList</p></td>
<td><p>数据库图表列表。</p></td>
</tr>
</tbody>
</table>

<a name="-head"></a><<<<<<< 标头
=======
<br/>
>>>>>>> master

下面的示例显示如何从 Visual Basic 过程中打开"罗斯文"示例数据库中的"雇员"窗体：

```vb
    ' In Visual Basic, initiate DDE conversation with 
    ' Northwind sample database. 
    ' Make sure database is open. 
    intChan2 = DDEInitiate("MSAccess", "Northwind") 
    ' Request list of forms in Northwind sample database. 
    strResponse = DDERequest(intChan2, "FormList") 
    ' Run OpenForm action and arguments to open Employees form. 
    DDEExecute intChan2, "[OpenForm Employees,0,,,1,0]"
```

## <a name="the-table-topic"></a>表主题

这些主题使用以下语法：

_databasename_ ;**表**_tablename_

_databasename_ ;**查询**_查询_

_databasename_ ;**SQL**[ _sqlstring_ ]

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>部分</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>databasename</em></p></td>
<td><p>表或查询所在的数据库或 SQL 语句应用到的数据库的名称，后跟一个分号 (;)。数据库名称可以只是基本名称 (Northwind)，也可以外加完整路径和 .mdb 扩展名 (C:\Access\Samples\Northwind.mdb)。</p></td>
</tr>
<tr class="even">
<td><p><em>tablename</em></p></td>
<td><p>某个已有表的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>queryname</em></p></td>
<td><p>某个已有查询的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>sqlstring</em></p></td>
<td><p>最多 256 个字符之间，用分号结束有效的 SQL 语句。 Exchange 超过 256 个字符，忽略此参数，而是使用连续<strong>DDEPoke</strong>语句来建立 SQL 语句。 例如，以下 Visual Basic 代码使用 <strong>DDEPoke</strong> 语句来建立 SQL 语句，然后请求查询结果。</p></td>
</tr>
</tbody>
</table>

<br/>

下表列出了 TABLE *tablename*、QUERY *queryname* 和 SQL *sqlstring* 主题的有效项目。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>返回</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>All</p></td>
<td><p>表中的所有数据，包括字段名。</p></td>
</tr>
<tr class="even">
<td><p>Data</p></td>
<td><p>所有数据行，不含字段名。</p></td>
</tr>
<tr class="odd">
<td><p>FieldNames</p></td>
<td><p>字段名单行列表。</p></td>
</tr>
<tr class="even">
<td><p>FieldNames;T</p></td>
<<<<<<< 标头
<td><p>字段名（第一行）及其数据类型（第二行）的双行列表。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>下面是返回的值和它们代表的数据类型：</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><b>值</b></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>0</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>1</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>8</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>9</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>10</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>11</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>12</p></td>
=======
<td><p>字段名（第一行）及其数据类型（第二行）的双行列表。</p>
<p>下面是返回的值：</p>
<p>值</p>
<p><ul>
<li>0</li>
<li>1</li>
<li>2</li>
<li>3</li>
<li>4</li>
<li>5</li>
<li>6</li>
<li>7</li>
<li>8</li>
<li>9</li>
<li>10</li>
<li>11</li>
<li>12</li>
</ul>
</p>
</td>
>>>>>>>主控形状
</tr>
<tr class="even">
<td><p>NextRow</p></td>
<td><p>表或查询中下一行的数据。当打开一个通道时，NextRow 返回第一行中的数据。如果当前行是最后一条记录并运行 NextRow，则请求会失败。</p></td>
</tr>
<tr class="odd">
<td><p>PrevRow</p></td>
<td><p>表或查询中上一行的数据。如果 PrevRow 是新通道中的第一个请求，该表或查询的最后一行中的数据返回。如果第一条记录是当前行，则 PrevRow 请求会失败。</p></td>
</tr>
<tr class="even">
<td><p>FirstRow</p></td>
<td><p>表或查询中第一行的数据。</p></td>
</tr>
<tr class="odd">
<td><p>LastRow</p></td>
<td><p>表或查询中最后一行的数据。</p></td>
</tr>
<tr class="even">
<td><p>FieldCount</p></td>
<td><p>表或查询中字段的数目。</p></td>
</tr>
<tr class="odd">
<td><p>SQLText</p></td>
<td><p>表示表或查询的 SQL 语句。 对于表，此项返回的 SQL 语句形式&quot;选择`*`从<em>表</em>;&quot;.</p></td>
</tr>
<tr class="even">
<td><p>SQLText;<em>n</em></p></td>
<td><p>SQL 语句， <em>n</em>-字符块大小，表示表或查询，其中<em>n</em>是最多 256 的整数。 例如，假设查询由以下 SQL 语句： 项目&quot;SQLText; 7&quot;返回以下以制表符分隔的块： 项目&quot;SQLText; 7&quot;返回以下以制表符分隔的块：</p></td>
</tr>
</tbody>
</table>

<a name="-head"></a><<<<<<< 标头
=======
<br/>
>>>>>>> master

下面的示例显示在 Visual Basic 过程中如何使用 DDE 请求"罗斯文"示例数据库的表中的数据，并将该数据插入到文本文件中：

```vb
    Sub NorthwindDDE 
        Dim intChan1 As Integer, intChan2 As Integer, intChan3 As Integer 
        Dim strResp1 As Variant, strResp2 As Variant, strResp3 As Variant 
     
        ' In a Visual Basic module, get data from Categories table, 
        ' Catalog query, and Orders table in Northwind.mdb. 
        ' Make sure database is open first. 
        intChan1 = DDEInitiate("MSAccess", "Northwind;TABLE Shippers") 
        intChan2 = DDEInitiate("MSAccess", "Northwind;QUERY Catalog") 
        intChan3 = DDEInitiate("MSAccess", "Northwind;SQL SELECT * " _ 
            & "FROM Orders " _ 
            & "WHERE OrderID > 10050;") 
     
        strResp1 = DDERequest(intChan1, "All") 
        strResp2 = DDERequest(intChan2, "FieldNames;T") 
        strResp3 = DDERequest(intChan3, "FieldNames;T") 
        DDETerminate intChan1 
        DDETerminate intChan2 
        DDETerminate intChan3 
     
        ' Insert data into text file. 
        Open "C:\DATA.TXT" For Append As #1 
        Print #1, strResp1 
        Print #1, strResp2 
        Print #1, strResp3 
        Close #1 
    End Sub
```
