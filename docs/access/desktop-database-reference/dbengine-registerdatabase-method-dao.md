---
title: DBEngine.RegisterDatabase Method (DAO)
TOCTitle: RegisterDatabase Method
ms:assetid: ed87a694-2c89-0a78-5d8b-0cc7e09fadff
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836347(v=office.15)
ms:contentKeyID: 48548541
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052938
f1_categories:
- Office.Version=v15
ms.openlocfilehash: fcb8e675f488c0d69f4c0d0b6329c47085d51e26
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888620"
---
# <a name="dbengineregisterdatabase-method-dao"></a>DBEngine.RegisterDatabase Method (DAO)


**适用于**： Access 2013、 Office 2013


在 Windows 注册表中输入 ODBC 数据源的连接信息。在会话期间如果 ODBC 数据源已打开，则 ODBC 驱动程序需要连接信息。

## <a name="syntax"></a>语法

*表达式*。RegisterDatabase （***Dsn***、***驱动程序***、***无提示***、***属性***）

*表达式*一个代表**DBEngine**对象的变量。

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
<td><p>Dsn</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p><strong><a href="dbengine-opendatabase-method-dao.md">OpenDatabase</a></strong> 方法中使用的名称。该名称引用与数据源有关的描述性信息块。例如，如果数据源为 ODBC 远程数据库，则该名称可能是服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p>驱动程序</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>ODBC 驱动程序的名称。这不是 ODBC 驱动程序 DLL 文件的名称。</p></td>
</tr>
<tr class="odd">
<td><p>无提示</p></td>
<td><p>必需</p></td>
<td><p><strong>Boolean</strong></p></td>
<td><p><strong>True</strong>如果您不想要显示提示驱动程序特定信息; ODBC 驱动程序对话框或<strong>False</strong>如果您想要显示 ODBC 驱动程序对话框。 如果无提示是<strong>True</strong>、 属性必须包含所有必需的驱动程序特定信息或仍然显示的对话框。</p></td>
</tr>
<tr class="even">
<td><p>Attributes</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>要添加到 Windows 注册表的关键字列表。这些关键字是由回车符分隔的字符串。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

如果在使用 **RegisterDatabase** 方法时，已经在 Windows 注册表中注册了数据库（已输入了连接信息），则会更新连接信息。

如果出于任何原因 **RegisterDatabase** 方法失败，则不会对 Windows 注册表进行更改，同时会发生错误。

有关 ODBC 驱动程序（例如 SQL Server）的详细信息，请参阅随驱动程序提供的"帮助"文件。

## <a name="example"></a>示例

以下示例使用 **RegisterDatabase** 方法在 Windows 注册表中注册名称为"Publishers"的 Microsoft SQL Server 数据源。

```vb 
Sub RegisterDatabaseX() 
 
 Dim dbsRegister As Database 
 Dim strDescription As String 
 Dim strAttributes As String 
 Dim errLoop As Error 
 
 ' Build keywords string. 
 strDescription = InputBox( "Enter a description " & _ 
 "for the database to be registered.") 
 strAttributes = "Database=pubs" & _ 
 vbCr & "Description=" & strDescription & _ 
 vbCr & "OemToAnsi=No" & _ 
 vbCr & "Server=Server1" 
 
 ' Update Windows Registry. 
 On Error GoTo Err_Register 
 DBEngine.RegisterDatabase "Publishers", "SQL Server", _ 
 True, strAttributes 
 On Error GoTo 0 
 
 MsgBox "Use regedit.exe to view changes: " & _ 
 "HKEY_CURRENT_USER\" & _ 
 "Software\ODBC\ODBC.INI" 
 
 Exit Sub 
 
Err_Register: 
 
 ' Notify user of any errors that result from 
 ' the invalid data. 
 If DBEngine.Errors.Count > 0 Then 
 For Each errLoop In DBEngine.Errors 
 MsgBox "Error number: " & errLoop.Number & _ 
 vbCr & errLoop.Description 
 Next errLoop 
 End If 
 
 Resume Next 
 
End Sub 
 
```

