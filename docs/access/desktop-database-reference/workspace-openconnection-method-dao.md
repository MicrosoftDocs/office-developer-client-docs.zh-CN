---
title: OpenConnection 方法 (DAO)
TOCTitle: OpenConnection Method
ms:assetid: 9d97f298-a2d5-3b91-2efd-57f06fbd4654
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198249(v=office.15)
ms:contentKeyID: 48546628
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 70bdded6c149aa7aff405c769ba4462a46c20dfd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308335"
---
# <a name="workspaceopenconnection-method-dao"></a>OpenConnection 方法 (DAO)

**适用于**：Access 2013、Office 2013

## <a name="syntax"></a>语法

*表达式*。OpenConnection (***Name***、 ***Options***、 ***ReadOnly***、 ***Connect***)

*表达式*一个代表**Workspace**对象的变量。

## <a name="parameters"></a>参数

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
<td><p><em>Name</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>一个字符串表达式。 请参阅“说明”中的讨论。</p></td>
</tr>
<tr class="even">
<td><p><em>Options</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>根据“说明”中的指定设置连接的各个选项。ODBC 驱动程序管理器根据此值向用户提示有关连接的信息，例如数据源名称 (DSN)、用户名和密码。</p></td>
</tr>
<tr class="odd">
<td><p><em>ReadOnly</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>
						如果连接针对只读访问权限打开，则为 <strong>True</strong>；如果连接针对读/写访问权限打开，则为 <strong>False</strong>（默认值）。</p></td>
</tr>
<tr class="even">
<td><p><em>Connect</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 ODBC 连接字符串。 请参阅此字符串的特定元素和语法的<strong><a href="connection-connect-property-dao.md">Connect</a></strong>属性。 预置&quot;的 ODBC;&quot;是必需的。</p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

Connection

## <a name="remarks"></a>注解

使用 **OpenConnection** 方法可在 ODBCDirect 工作区中建立与 ODBC 数据源的连接。 **OpenConnection** 方法类似于 **OpenDatabase**，但不完全相同。主要差别在于 **OpenConnection** 只在 ODBCDirect 工作区中可用。

如果在 connect 参数中指定了已注册的 ODBC 数据源名称 (DSN), 则 name 参数可以是任何有效的字符串, 并且还将提供**Connection**对象的**name**属性。 如果 connect 参数中不包含有效的 DSN, 则 name 必须引用有效的 ODBC DSN, 这也将是**name**属性。 如果 name 和 connect 都不包含有效的 DSN, 则可以通过 options 参数设置 ODBC 驱动程序管理器, 以提示用户输入所需的连接信息。 然后，通过提示而提供的 DSN 将会提供 **Name** 属性。

options 参数确定是否以及何时提示用户建立连接, 以及是否以异步方式打开连接。 可以使用下列常量之一。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbDriverNoPrompt</strong></p></td>
<td><p>ODBC 驱动程序管理器使用 <em>dbname</em> 和 <em>connect</em> 中提供的连接字符串。 如果不提供足够的信息，将发生运行时错误。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbDriverPrompt</strong></p></td>
<td><p>ODBC 驱动程序管理器显示“ODBC 数据源”<strong></strong>对话框，其中显示 <em>dbname</em> 或 <em>connect</em> 中提供的所有相关信息。连接字符串由用户通过对话框选择的 DSN 组成。如果用户未指定 DSN，将使用默认 DSN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>于 dbdrivercomplete</strong></p></td>
<td><p>默认值。如果 <em>connect</em> 参数包括完成连接所需的所有必要信息，ODBC 驱动程序管理器将使用 <em>connect</em> 中的字符串。否则，其表现与指定了 <strong>dbDriverPrompt</strong> 时相同。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbDriverCompleteRequired</strong></p></td>
<td><p>此选项的表现类似于 <strong>dbDriverComplete</strong>，不同之处在于，ODBC 驱动程序将禁止提示完成连接所不需要的任何信息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>即用 dbrunasync</strong></p></td>
<td><p>异步执行方法。 此常量可以与其他任何 <em>options</em> 常量一起使用。</p></td>
</tr>
</tbody>
</table>

<br/>

**OpenConnection** 返回包含有关连接的信息的 **Connection** 对象。 **Connection** 对象与 **[Database](database-object-dao.md)** 对象类似。主要差别在于 **Database** 对象通常代表数据库，尽管也可以使用它代表在 Microsoft Access 工作区中与 ODBC 数据源建立的连接。

## <a name="example"></a>示例

以下示例使用采用不同参数的 **OpenConnection** 方法打开三个不同的 **Connection** 对象。

```vb 
Sub OpenConnectionX() 
 
 Dim wrkODBC As Workspace 
 Dim conPubs As Connection 
 Dim conPubs2 As Connection 
 Dim conPubs3 As Connection 
 Dim conLoop As Connection 
 
 ' Create ODBCDirect Workspace object. 
 Set wrkODBC = CreateWorkspace("NewODBCWorkspace", _ 
 "admin", "", dbUseODBC) 
 
 ' Open Connection object using supplied information in 
 ' the connect string. If this information were 
 ' insufficient, you could trap for an error rather than 
 ' go to an ODBC Driver Manager dialog box. 
 MsgBox "Opening Connection1..." 
 
 ' Note: The DSN referenced below must be set to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set conPubs = wrkODBC.OpenConnection("Connection1", _ 
 dbDriverNoPrompt, , _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 ' Open read-only Connection object based on information 
 ' you enter in the ODBC Driver Manager dialog box. 
 MsgBox "Opening Connection2..." 
 Set conPubs2 = wrkODBC.OpenConnection("Connection2", _ 
 dbDriverPrompt, True, "ODBC;DSN=Publishers;") 
 
 ' Open read-only Connection object by entering only the 
 ' missing information in the ODBC Driver Manager dialog 
 ' box. 
 MsgBox "Opening Connection3..." 
 Set conPubs3 = wrkODBC.OpenConnection("Connection3", _ 
 dbDriverCompleteRequired, True, _ 
 "ODBC;DATABASE=pubs;DSN=Publishers;") 
 
 ' Enumerate the Connections collection. 
 For Each conLoop In wrkODBC.Connections 
 Debug.Print "Connection properties for " & _ 
 conLoop.Name & ":" 
 
 With conLoop 
 ' Print property values by explicitly calling each 
 ' Property object; the Connection object does not 
 ' support a Properties collection. 
 Debug.Print " Connect = " & .Connect 
 ' Property actually returns a Database object. 
 Debug.Print " Database[.Name] = " & _ 
 .Database.Name 
 Debug.Print " Name = " & .Name 
 Debug.Print " QueryTimeout = " & .QueryTimeout 
 Debug.Print " RecordsAffected = " & _ 
 .RecordsAffected 
 Debug.Print " StillExecuting = " & _ 
 .StillExecuting 
 Debug.Print " Transactions = " & .Transactions 
 Debug.Print " Updatable = " & .Updatable 
 End With 
 
 Next conLoop 
 
 conPubs.Close 
 conPubs2.Close 
 conPubs3.Close 
 wrkODBC.Close 
 
End Sub 
 
```

<br/>

以下示例通过打开一个 Microsoft Access **Database** 对象和两个 ODBCDirect **Connection** 对象，并列出每个对象可用的属性，来演示 **Connection** 对象和 **Connections** 集合。

```vb 
Sub ConnectionObjectX() 
 
 Dim wrkAcc as Workspace 
 Dim dbsNorthwind As Database 
 Dim wrkODBC As Workspace 
 Dim conPubs As Connection 
 Dim conPubs2 As Connection 
 Dim conLoop As Connection 
 Dim prpLoop As Property 
 
 ' Open Microsoft Access Database object. 
 Set wrkAcc = CreateWorkspace("NewWorkspace", _ 
 "admin", "", dbUseJet) 
 Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
 
 ' Create ODBCDirect Workspace object and open Connection 
 ' objects. 
 Set wrkODBC = CreateWorkspace("NewODBCWorkspace", _ 
 "admin", "", dbUseODBC) 
 
 ' Note: The DSNs referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set conPubs = wrkODBC.OpenConnection("Connection1", , , _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 Set conPubs2 = wrkODBC.OpenConnection("Connection2", , _ 
 True, "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 Debug.Print "Database properties:" 
 
 With dbsNorthwind 
 ' Enumerate Properties collection of Database object. 
 For Each prpLoop In .Properties 
 On Error Resume Next 
 Debug.Print " " & prpLoop.Name & " = " & _ 
 prpLoop.Value 
 On Error GoTo 0 
 Next prpLoop 
 End With 
 
 ' Enumerate the Connections collection. 
 For Each conLoop In wrkODBC.Connections 
 Debug.Print "Connection properties for " & _ 
 conLoop.Name & ":" 
 
 With conLoop 
 ' Print property values by explicitly calling each 
 ' Property object; the Connection object does not 
 ' support a Properties collection. 
 Debug.Print " Connect = " & .Connect 
 ' Property actually returns a Database object. 
 Debug.Print " Database[.Name] = " & _ 
 .Database.Name 
 Debug.Print " Name = " & .Name 
 Debug.Print " QueryTimeout = " & .QueryTimeout 
 Debug.Print " RecordsAffected = " & _ 
 .RecordsAffected 
 Debug.Print " StillExecuting = " & _ 
 .StillExecuting 
 Debug.Print " Transactions = " & .Transactions 
 Debug.Print " Updatable = " & .Updatable 
 End With 
 
 Next conLoop 
 
 dbsNorthwind.Close 
 conPubs.Close 
 conPubs2.Close 
 wrkAcc.Close 
 wrkODBC.Close 
 
End Sub 
 
```

