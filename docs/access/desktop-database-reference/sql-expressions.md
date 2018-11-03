---
title: SQL 表达式 （Access 桌面数据库参考 （英文）
TOCTitle: SQL expressions
ms:assetid: 91722f18-8589-d9fc-79ef-0be4ab11f822
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197629(v=office.15)
ms:contentKeyID: 48546349
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 25b7d11430b730b6cedd1d8a084acd4984c5f292
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944147"
---
# <a name="sql-expressions"></a><span data-ttu-id="611e8-102">SQL 表达式</span><span class="sxs-lookup"><span data-stu-id="611e8-102">SQL expressions</span></span>


<span data-ttu-id="611e8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="611e8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="611e8-p101">SQL 表达式是构成 SQL 语句的全部或一部分的字符串。例如，**Recordset** 对象的 **FindFirst** 方法使用由 SQL [WHERE 子句](https://msdn.microsoft.com/library/ff195245\(v=office.15\))中的选择条件所组成的 SQL 表达式。</span><span class="sxs-lookup"><span data-stu-id="611e8-p101">An SQL expression is a string that makes up all or part of an SQL statement. For example, the**FindFirst** method on a **Recordset** object uses an SQL expression consisting of the selection criteria found in an SQL [WHERE clause](https://msdn.microsoft.com/library/ff195245\(v=office.15\)).</span></span>

<span data-ttu-id="611e8-106">Microsoft Access 数据库引擎使用 Microsoft Visual Basic for Applications (VBA） 表达式服务以执行简单的算术运算符和函数计算。</span><span class="sxs-lookup"><span data-stu-id="611e8-106">The Microsoft Access database engine uses the Microsoft Visual Basic for Applications (or VBA) expression service to perform simple arithmetic and function evaluation.</span></span> <span data-ttu-id="611e8-107">VBA 表达式服务定义所有 （除**[之间](https://msdn.microsoft.com/library/ff192436\(v=office.15\))**、**[中](https://msdn.microsoft.com/library/ff836369\(v=office.15\))**，并**[像](https://msdn.microsoft.com/library/ff195752\(v=office.15\))**） 的 Microsoft Access 数据库引擎 SQL 表达式中使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="611e8-107">All of the operators used in Microsoft Access database engine SQL expressions (except **[Between](https://msdn.microsoft.com/library/ff192436\(v=office.15\))**, **[In](https://msdn.microsoft.com/library/ff836369\(v=office.15\))**, and **[Like](https://msdn.microsoft.com/library/ff195752\(v=office.15\))**) are defined by the VBA expression service.</span></span> <span data-ttu-id="611e8-108">另外，VBA 表达式服务所提供的 100 多个 VBA 函数能够用于 SQL 表达式中。</span><span class="sxs-lookup"><span data-stu-id="611e8-108">In addition, the VBA expression service offers over 100 VBA functions that you can use in SQL expressions.</span></span> <span data-ttu-id="611e8-109">例如，您可以使用这些 VBA 函数撰写 Microsoft Access 查询设计视图中的 SQL 查询和还可以在 Microsoft Visual c + +、 Microsoft Visual Basic 中，和 Microsoft DAO **OpenRecordset**方法中的 SQL 查询中使用这些函数Excel 代码。</span><span class="sxs-lookup"><span data-stu-id="611e8-109">For example, you can use these VBA functions to compose an SQL query in the Microsoft Access query Design view, and you can also use these functions in an SQL query in the DAO **OpenRecordset** method in Microsoft Visual C++, Microsoft Visual Basic, and Microsoft Excel code.</span></span>

