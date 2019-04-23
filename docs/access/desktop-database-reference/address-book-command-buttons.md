---
title: 通讯簿命令按钮
TOCTitle: Address Book command buttons
ms:assetid: bcea6f53-3e36-b067-03c2-b157ed02d41d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249908(v=office.15)
ms:contentKeyID: 48547422
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 09f2513a3c541c76352e773f7f2a8f0c24f78850
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282476"
---
# <a name="address-book-command-buttons"></a>通讯簿命令按钮


**适用于**：Access 2013、Office 2013


通讯簿应用程序包括以下命令按钮：

- **“查找”** 按钮，用于向数据库提交查询。

- “清除”**** 按钮，用于在开始新的搜索之前清除文本框中的内容。

- **“更新配置文件”** 按钮，用于保存对雇员记录所做的更改。

- **“取消更改”** 按钮，用于放弃更改。

## <a name="find-button"></a>“查找”按钮

单击 "**查找**" 按钮将激活 VBScript\_Find OnClick Sub 过程, 该过程将生成并发送 SQL 查询。 单击此按钮可填充数据网格。

## <a name="building-the-sql-query"></a>生成 SQL 查询

Find\_OnClick Sub 过程的第一部分通过将文本字符串追加到全局 SQL SELECT 语句来生成 SQL 查询 (一次一个短语)。 首先, 它将变量设置为 SQL SELECT 语句, 该语句请求数据源表中的所有数据行。 然后，子过程对页面上的四个输入框逐一进行扫描。

由于程序在生成 SQL 语句时使用单词, 因此查询是子字符串搜索, 而不是完全匹配。

例如, 如果 "**姓氏**" 框中包含条目 "高", 并且 "**标题**" 框中包含 "程序管理员" 条目, 则 SQL 语句 (值) 将会被读取:

```vb 
 
Select FirstName, LastName, Title, Email, Building, Room, Phone from Employee where lastname like 'Berge%' and title like 'Program Manager%' 
```

如果查询成功，则姓氏中包含文本“高”（如“高”和“高阳”），且职务中包含“程序管理员”（如“高级技术程序管理员”）的所有人都将显示在 HTML 数据网格中。

## <a name="preparing-and-sending-the-query"></a>准备和发送查询

Find\_OnClick Sub 过程的最后一部分由两个语句组成。 第一个语句为 RDS.DataControl 对象的 SQL 属性赋值以动态生成 SQL 查询。 第二个语句导致**RDS。rds.datacontrol**对象 () 查询数据库, 然后在网格中显示查询的新结果。

```vb 
 
Sub Find_OnClick 
 '... 
 DC1.SQL = myQuery 
 DC1.Refresh 
End Sub 
```

## <a name="update-profile-button"></a>“更新配置文件”按钮

单击 "**更新配置文件**" 按钮将激活\_VBScript Update OnClick Sub 过程, 该过程将执行 RDS。rds.datacontrol 对象的 () SubmitChanges 和 Refresh 方法。

```vb 
 
Sub Update_OnClick 
 DC1.SubmitChanges 
 DC1.Refresh 
End Sub 
```

当 DC1 时。SubmitChanges 执行时, 远程数据服务会将所有更新信息打包, 并通过 HTTP 将其发送到服务器。 The update is all-or-nothing; if a part of the update is unsuccessful, none of the changes is made, and a status message is returned. executes, the Remote Data Service packages all the update information and sends it to the server via HTTP. The update is all-or-nothing; if a part of the update is unsuccessful, none of the changes is made, and a status message is returned. DC1.在使用远程数据服务**SubmitChanges**之后, 不需要进行刷新, 但可确保使用最新的数据。

## <a name="cancel-changes-button"></a>“取消更改”按钮

单击 "**取消更改**" 将激活\_VBScript Cancel OnClick Sub 过程, 该过程将执行 RDS。rds.datacontrol 对象的 (CancelUpdate 方法。

```vb 
 
Sub Cancel_OnClick 
 DC1.CancelUpdate 
End Sub 
```

在执行此操作时, 它会丢弃用户自上一次查询或更新以来对数据网格上的员工记录所做的任何编辑。 它将还原原始值。

