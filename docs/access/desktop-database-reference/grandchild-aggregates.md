---
title: 孙级聚合
TOCTitle: Grandchild aggregates
ms:assetid: ea5e2e1f-f3d5-f851-623a-a5d1385fe206
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250188(v=office.15)
ms:contentKeyID: 48548462
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a4c50898626488f909616977c6bb50c936434563
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722156"
---
# <a name="grandchild-aggregates"></a><span data-ttu-id="7c99e-102">孙级聚合</span><span class="sxs-lookup"><span data-stu-id="7c99e-102">Grandchild aggregates</span></span>


<span data-ttu-id="7c99e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7c99e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7c99e-104">创建 shape 命令的子句中的章节列可能有*章别名*（通常使用 AS 关键字）。</span><span class="sxs-lookup"><span data-stu-id="7c99e-104">The chapter column created in a clause of a shape command may be given a *chapter-alias name* (typically with the AS keyword).</span></span> <span data-ttu-id="7c99e-105">您可能使用的完全限定名称来标识包含的列的子标识任何定形**Recordset**的章节中的任何列。</span><span class="sxs-lookup"><span data-stu-id="7c99e-105">You may identify any column in any chapter of the shaped **Recordset** with a fully qualified name identifying the child containing the column.</span></span> <span data-ttu-id="7c99e-106">例如，如果父章，chap1，包含子一章，chap2，具有量列中，主动管理技术，则限定的名称将为 chap1.chap2.amt。限定的名可能然后用作聚合函数 （SUM、 平均、 MAX、 MIN、 计数、 STDEV 和或任何） 之一的参数。</span><span class="sxs-lookup"><span data-stu-id="7c99e-106">For example, if the parent chapter, chap1, contains a child chapter, chap2, that has an amount column, amt, then the qualified name would be chap1.chap2.amt. The qualified name may then be used as an argument to one of the aggregate functions (SUM, AVG, MAX, MIN, COUNT, STDEV, or ANY).</span></span>

