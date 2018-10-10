---
title: SQL 聚合函数 (SQL)
TOCTitle: SQL Aggregate Functions (SQL)
ms:assetid: 8866cd71-0216-25b4-6a6a-02cb7acad9a2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197054(v=office.15)
ms:contentKeyID: 48546136
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6c95c29a5864bd07590a494d10556b3f537c14b2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467582"
---
# <a name="sql-aggregate-functions-sql"></a><span data-ttu-id="759f9-102">SQL 聚合函数 (SQL)</span><span class="sxs-lookup"><span data-stu-id="759f9-102">SQL Aggregate Functions (SQL)</span></span>


<span data-ttu-id="759f9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="759f9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="759f9-p101">通过使用 SQL 聚合函数，可以确定数值集合的各种统计值。可以在 **QueryDef** 对象的 **SQL** 属性中的查询和聚合表达式内使用这些函数，或者在基于 SQL 查询创建 **Recordset** 对象时使用这些函数。</span><span class="sxs-lookup"><span data-stu-id="759f9-p101">Using the SQL aggregate functions, you can determine various statistics on sets of values. You can use these functions in a query and aggregate expressions in the **SQL** property of a **QueryDef** object or when creating a **Recordset** object based on an SQL query.</span></span>

<span data-ttu-id="759f9-106">**[Avg 函数](https://msdn.microsoft.com/library/ff822755\(v=office.15\))**</span><span class="sxs-lookup"><span data-stu-id="759f9-106">**[Avg Function](https://msdn.microsoft.com/library/ff822755\(v=office.15\))**</span></span>

<span data-ttu-id="759f9-107">**[Count 函数](https://msdn.microsoft.com/library/ff844748\(v=office.15\))**</span><span class="sxs-lookup"><span data-stu-id="759f9-107">**[Count Function](https://msdn.microsoft.com/library/ff844748\(v=office.15\))**</span></span>

<span data-ttu-id="759f9-108">**[First 函数和 Last 函数 (Microsoft Access SQL)](https://msdn.microsoft.com/library/ff197381\(v=office.15\))**</span><span class="sxs-lookup"><span data-stu-id="759f9-108">**[First, Last Functions](https://msdn.microsoft.com/library/ff197381\(v=office.15\))**</span></span>

<span data-ttu-id="759f9-109">**[Min 和 Max 函数 (Microsoft Access SQL)](https://msdn.microsoft.com/library/ff194490\(v=office.15\))**</span><span class="sxs-lookup"><span data-stu-id="759f9-109">**[Min, Max Functions](https://msdn.microsoft.com/library/ff194490\(v=office.15\))**</span></span>

<span data-ttu-id="759f9-110">**[StDev 和 StDevP 函数 (Microsoft Access SQL)](https://msdn.microsoft.com/library/ff197043\(v=office.15\))**</span><span class="sxs-lookup"><span data-stu-id="759f9-110">**[StDev, StDevP Functions](https://msdn.microsoft.com/library/ff197043\(v=office.15\))**</span></span>

<span data-ttu-id="759f9-111">**[Sum 函数](https://msdn.microsoft.com/library/ff844764\(v=office.15\))**</span><span class="sxs-lookup"><span data-stu-id="759f9-111">**[Sum Function](https://msdn.microsoft.com/library/ff844764\(v=office.15\))**</span></span>

<span data-ttu-id="759f9-112">**[Var 和 VarP 函数 (Microsoft Access SQL)](https://msdn.microsoft.com/library/ff192105\(v=office.15\))**</span><span class="sxs-lookup"><span data-stu-id="759f9-112">**[Var, VarP Functions](https://msdn.microsoft.com/library/ff192105\(v=office.15\))**</span></span>

