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
# <a name="sql-expressions"></a><span data-ttu-id="28582-102">SQL 表达式</span><span class="sxs-lookup"><span data-stu-id="28582-102">SQL expressions</span></span>

<span data-ttu-id="28582-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="28582-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="28582-p101">SQL 表达式是构成 SQL 语句的全部或一部分的字符串。例如， **Recordset** 对象的 **FindFirst** 方法使用由 SQL [WHERE 子句](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql)中的选择条件所组成的 SQL 表达式。</span><span class="sxs-lookup"><span data-stu-id="28582-p101">An SQL expression is a string that makes up all or part of an SQL statement. For example, the **FindFirst** method on a **Recordset** object uses an SQL expression consisting of the selection criteria found in an SQL [WHERE clause](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql).</span></span>

<span data-ttu-id="28582-106">Microsoft Access 数据库引擎使用 Microsoft Visual Basic for Applications (VBA） 表达式服务以执行简单的算术运算符和函数计算。</span><span class="sxs-lookup"><span data-stu-id="28582-106">The Microsoft Access database engine uses the Microsoft Visual Basic for Applications (or VBA) expression service to perform simple arithmetic and function evaluation.</span></span> <span data-ttu-id="28582-107">VBA 表达式服务定义所有 （除**[之间](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/and-operator)**、**[中](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-operator-microsoft-access-sql)**，并**[像](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/like-operator-microsoft-access-sql)**） 的 Microsoft Access 数据库引擎 SQL 表达式中使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="28582-107">All of the operators used in Microsoft Access database engine SQL expressions (except **[Between](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/and-operator)**, **[In](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-operator-microsoft-access-sql)**, and **[Like](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/like-operator-microsoft-access-sql)**) are defined by the VBA expression service.</span></span> <span data-ttu-id="28582-108">另外，VBA 表达式服务所提供的 100 多个 VBA 函数能够用于 SQL 表达式中。</span><span class="sxs-lookup"><span data-stu-id="28582-108">In addition, the VBA expression service offers over 100 VBA functions that you can use in SQL expressions.</span></span> <span data-ttu-id="28582-109">例如，您可以使用这些 VBA 函数撰写 Microsoft Access 查询设计视图中的 SQL 查询和还可以在 Microsoft Visual c + +、 Microsoft Visual Basic 中，和 Microsoft DAO **OpenRecordset**方法中的 SQL 查询中使用这些函数Excel 代码。</span><span class="sxs-lookup"><span data-stu-id="28582-109">For example, you can use these VBA functions to compose an SQL query in the Microsoft Access query Design view, and you can also use these functions in an SQL query in the DAO **OpenRecordset** method in Microsoft Visual C++, Microsoft Visual Basic, and Microsoft Excel code.</span></span>

## <a name="see-also"></a><span data-ttu-id="28582-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28582-110">See also</span></span>

- [<span data-ttu-id="28582-111">Access VBA 概念</span><span class="sxs-lookup"><span data-stu-id="28582-111">Access VBA Concepts</span></span>](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/concepts-access-vba-reference)
