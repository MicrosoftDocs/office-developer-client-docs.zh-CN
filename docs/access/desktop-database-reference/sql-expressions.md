---
title: SQL 表达式 （Access 桌面数据库参考 （英文）
TOCTitle: SQL Expressions
ms:assetid: 91722f18-8589-d9fc-79ef-0be4ab11f822
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197629(v=office.15)
ms:contentKeyID: 48546349
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 328804dc8186c082cf22d409b4071368af8873e2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465543"
---
# <a name="sql-expressions"></a>SQL 表达式


**适用于**： Access 2013 |Office 2013

SQL 表达式是构成 SQL 语句的全部或一部分的字符串。例如，**Recordset** 对象的 **FindFirst** 方法使用由 SQL [WHERE 子句](https://msdn.microsoft.com/library/ff195245\(v=office.15\))中的选择条件所组成的 SQL 表达式。

Microsoft Access 数据库引擎利用 Microsoft® Visual Basic® for Applications（即 VBA）表达式服务来执行简单的算术运算和函数计算。所有用于 Microsoft Access 数据库引擎 SQL 表达式的运算符（除了 **[Between](https://msdn.microsoft.com/library/ff192436\(v=office.15\))**、**[In](https://msdn.microsoft.com/library/ff836369\(v=office.15\))** 和 **[Like](https://msdn.microsoft.com/library/ff195752\(v=office.15\))** 之外）都是由 VBA 表达式服务定义的。另外，VBA 表达式服务所提供的 100 多个 VBA 函数能够用于 SQL 表达式中。例如，可以在 Microsoft Access 查询设计视图中用这些 VBA 函数组成一个 SQL 查询，也可以在 SQL 查询中使用这些函数，并将这样的 SQL 查询用于 Microsoft Visual C++®、Microsoft Visual Basic 和 Microsoft Excel 代码中的 DAO **OpenRecordset** 方法。

