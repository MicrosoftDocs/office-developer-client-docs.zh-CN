---
title: SQL 表达式 （Access 桌面数据库参考 （英文）
TOCTitle: SQL expressions
ms:assetid: 91722f18-8589-d9fc-79ef-0be4ab11f822
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197629(v=office.15)
ms:contentKeyID: 48546349
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 5bbe9718bfb18ced5f09d2a9396e1e0829d0d81b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710543"
---
# <a name="sql-expressions"></a>SQL 表达式

**适用于**： Access 2013、 Office 2013

SQL 表达式是构成 SQL 语句的全部或一部分的字符串。例如， **Recordset** 对象的 **FindFirst** 方法使用由 SQL [WHERE 子句](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql)中的选择条件所组成的 SQL 表达式。

Microsoft Access 数据库引擎使用 Microsoft Visual Basic for Applications (VBA） 表达式服务以执行简单的算术运算符和函数计算。 VBA 表达式服务定义所有 （除**[之间](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/and-operator)**、**[中](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-operator-microsoft-access-sql)**，并**[像](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/like-operator-microsoft-access-sql)**） 的 Microsoft Access 数据库引擎 SQL 表达式中使用的运算符。 另外，VBA 表达式服务所提供的 100 多个 VBA 函数能够用于 SQL 表达式中。 例如，您可以使用这些 VBA 函数撰写 Microsoft Access 查询设计视图中的 SQL 查询和还可以在 Microsoft Visual c + +、 Microsoft Visual Basic 中，和 Microsoft DAO **OpenRecordset**方法中的 SQL 查询中使用这些函数Excel 代码。

## <a name="see-also"></a>另请参阅

- [Access VBA 概念](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/concepts-access-vba-reference)
