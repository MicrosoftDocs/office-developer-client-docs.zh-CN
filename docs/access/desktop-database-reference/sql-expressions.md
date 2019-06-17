---
title: SQL 表达式（Access 桌面数据库参考）
TOCTitle: SQL expressions
ms:assetid: 91722f18-8589-d9fc-79ef-0be4ab11f822
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197629(v=office.15)
ms:contentKeyID: 48546349
ms.date: 06/13/2019
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: f38932ed4744e5479c523446f9ab77065f4eb203
ms.sourcegitcommit: d0e1ce095a478d90411abb8c147eb9efe19ffa5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "34870862"
---
# <a name="sql-expressions"></a>SQL 表达式

**适用于**：Access 2013、Office 2013

SQL 表达式是构成 SQL 语句的全部或一部分的字符串。例如， **Recordset** 对象的 **FindFirst** 方法使用由 SQL [WHERE 子句](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql)中的选择条件所组成的 SQL 表达式。

Microsoft Access 数据库引擎利用 Microsoft Visual Basic for Applications（即 VBA）表达式服务来执行简单的算术运算和函数计算。 所有用于 Microsoft Access 数据库引擎 SQL 表达式的运算符（除了 **[Between](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/between-and-operator)**、**[In](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-operator-microsoft-access-sql)** 和 **[Like](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/like-operator-microsoft-access-sql)** 之外）都是由 VBA 表达式服务定义的。 

此外，VBA 表达式服务提供 100 多个可用于 SQL 表达式的 VBA 函数。 例如，可以在 Microsoft Access 查询设计视图中用这些 VBA 函数组成一个 SQL 查询，也可以在 SQL 查询中使用这些函数，并将这样的 SQL 查询用于 Microsoft Visual C++、Microsoft Visual Basic 和 Microsoft Excel 代码中的 DAO **OpenRecordset** 方法。

## <a name="see-also"></a>另请参阅

- [Access VBA 概念](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/concepts-access-vba-reference)
