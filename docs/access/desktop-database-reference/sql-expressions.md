---
title: SQL 表达式（Access 桌面数据库参考）
TOCTitle: SQL expressions
ms:assetid: 91722f18-8589-d9fc-79ef-0be4ab11f822
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197629(v=office.15)
ms:contentKeyID: 48546349
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 5bbe9718bfb18ced5f09d2a9396e1e0829d0d81b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308566"
---
# <a name="sql-expressions"></a><span data-ttu-id="0e2d1-102">SQL 表达式</span><span class="sxs-lookup"><span data-stu-id="0e2d1-102">SQL expressions</span></span>

<span data-ttu-id="0e2d1-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0e2d1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0e2d1-p101">SQL 表达式是构成 SQL 语句的全部或一部分的字符串。例如， **Recordset** 对象的 **FindFirst** 方法使用由 SQL [WHERE 子句](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql)中的选择条件所组成的 SQL 表达式。</span><span class="sxs-lookup"><span data-stu-id="0e2d1-p101">An SQL expression is a string that makes up all or part of an SQL statement. For example, the **FindFirst** method on a **Recordset** object uses an SQL expression consisting of the selection criteria found in an SQL [WHERE clause](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql).</span></span>

<span data-ttu-id="0e2d1-106">Microsoft Access 数据库引擎利用 Microsoft Visual Basic for Applications（即 VBA）表达式服务来执行简单的算术运算和函数计算。</span><span class="sxs-lookup"><span data-stu-id="0e2d1-106">The Microsoft Access database engine uses the Microsoft® Visual Basic® for Applications (or VBA) expression service to perform simple arithmetic and function evaluation.</span></span> <span data-ttu-id="0e2d1-107">所有用于 Microsoft Access 数据库引擎 SQL 表达式的运算符（除了 **[Between](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/and-operator)**、**[In](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-operator-microsoft-access-sql)** 和 **[Like](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/like-operator-microsoft-access-sql)** 之外）都是由 VBA 表达式服务定义的。</span><span class="sxs-lookup"><span data-stu-id="0e2d1-107">All of the operators used in Microsoft Access database engine SQL expressions (except  Between ,  In , and  Like ) are defined by the VBA expression service.</span></span> <span data-ttu-id="0e2d1-108">此外，VBA 表达式服务提供 100 多个可用于 SQL 表达式的 VBA 函数。</span><span class="sxs-lookup"><span data-stu-id="0e2d1-108">In addition, the VBA expression service offers over 100 VBA functions that you can use in SQL expressions.</span></span> <span data-ttu-id="0e2d1-109">例如，可以在 Microsoft Access 查询设计视图中用这些 VBA 函数组成一个 SQL 查询，也可以在 SQL 查询中使用这些函数，并将这样的 SQL 查询用于 Microsoft Visual C++、Microsoft Visual Basic 和 Microsoft Excel 代码中的 DAO **OpenRecordset** 方法。</span><span class="sxs-lookup"><span data-stu-id="0e2d1-109">For example, you can use these VBA functions to compose an SQL query in the Microsoft Access query Design view, and you can also use these functions in an SQL query in the DAO **OpenRecordset** method in Microsoft Visual C++®, Microsoft Visual Basic, and Microsoft Excel code.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e2d1-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e2d1-110">See also</span></span>

- [<span data-ttu-id="0e2d1-111">Access VBA 概念</span><span class="sxs-lookup"><span data-stu-id="0e2d1-111">Access VBA Concepts</span></span>](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/concepts-access-vba-reference)
