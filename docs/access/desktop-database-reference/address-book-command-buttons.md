---
title: 通讯簿命令按钮
TOCTitle: Address Book Command Buttons
ms:assetid: bcea6f53-3e36-b067-03c2-b157ed02d41d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249908(v=office.15)
ms:contentKeyID: 48547422
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e445414ead78bb5e1b05b3f3812e86f1d6c119ef
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869510"
---
# <a name="address-book-command-buttons"></a>通讯簿命令按钮


**适用于**： Access 2013、 Office 2013


通讯簿应用程序包括以下命令按钮：

  - “查找”按钮，用于向数据库提交查询。

  - **清除**的按钮，用于在开始新的搜索之前清除文本框。

  - “更新配置文件”按钮，用于保存对雇员记录所做的更改。

  - “取消更改”按钮，用于放弃更改。

## <a name="find-button"></a>"查找"按钮

单击**查找**按钮可激活 VBScript 查找\_OnClick Sub 过程，用于生成和发送 SQL 查询。 单击此按钮填充数据网格。

## <a name="building-the-sql-query"></a>生成 SQL 查询

查找的第一部分\_OnClick Sub 过程生成 SQL 查询，一次的某个短语，通过将文本字符串追加到全局 SQL SELECT 语句。 通过将变量设置为 SQL SELECT 语句中的数据源表从请求的数据的所有行开始。 然后，子过程对页面上的四个输入框逐一进行扫描。

由于程序使用构建 SQL 语句中的单词，查询将为子字符串搜索，而不是完全匹配。

例如，如果**姓氏**框中包含条目"姓氏"和**标题**框中包含条目"程序管理员"，将读取 SQL 语句 （的值）：

```vb 
 
Select FirstName, LastName, Title, Email, Building, Room, Phone from Employee where lastname like 'Berge%' and title like 'Program Manager%' 
```

如果查询成功，则姓氏中包含文本"高"（如"高"和"高阳"），且职务中包含"程序管理员"（如"高级技术程序管理员"）的所有人都将显示在 HTML 数据网格中。

## <a name="preparing-and-sending-the-query"></a>准备和发送查询

查找的最后一部分\_OnClick Sub 过程包括两个语句。 第一个语句为 RDS.DataControl 对象的 SQL 属性赋值以动态生成 SQL 查询。 第二个语句会导致**rds.DataControl**对象 （） 查询数据库，然后显示网格中的新查询的结果。

```vb 
 
Sub Find_OnClick 
 '... 
 DC1.SQL = myQuery 
 DC1.Refresh 
End Sub 
```

## <a name="update-profile-button"></a>"更新配置文件"按钮

单击**更新配置文件**按钮可激活 VBScript 更新\_OnClick Sub 过程，这将执行 rds.DataControl 对象 （） 的 SubmitChanges 和 Refresh 方法。

```vb 
 
Sub Update_OnClick 
 DC1.SubmitChanges 
 DC1.Refresh 
End Sub 
```

当 DC1。SubmitChanges 执行，远程数据服务包更新的所有信息并将其发送到服务器通过 HTTP。 更新是这;如果未成功更新的一部分，进行任何更改，并返回状态邮件。 执行时，远程数据服务包更新的所有信息并将其发送到服务器通过 HTTP。 更新是这;如果未成功更新的一部分，进行任何更改，并返回状态邮件。 DC1。与远程数据服务，**则 SubmitChanges**后，刷新不是必需，但它可以确保刷新数据。

## <a name="cancel-changes-button"></a>"取消更改"按钮

单击**取消更改**可激活 VBScript 取消\_OnClick Sub 过程，这将执行 rds.DataControl 对象的 （CancelUpdate 方法。

```vb 
 
Sub Cancel_OnClick 
 DC1.CancelUpdate 
End Sub 
```

当执行时，它将丢弃以来的最后一个查询或更新用户对数据网格上雇员记录所做的任何编辑。 它将还原的原始值。

