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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292144"
---
# <a name="grandchild-aggregates"></a><span data-ttu-id="46bf7-102">孙级聚合</span><span class="sxs-lookup"><span data-stu-id="46bf7-102">Grandchild aggregates</span></span>


<span data-ttu-id="46bf7-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="46bf7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="46bf7-p101">在 Shape 命令子句中创建的“章节”列可能会被赋予一个 *chapter-alias name*（通常使用 AS 关键字）。您可以用标识包含列的子记录集的完整名称来标识定形 **Recordset** 的任何章节中的任何列。例如，如果父章节 chap1 包含子章节 chap2，而后者具有一个数量列 amt，则限定名称为 chap1.chap2.amt。随后，该限定名称可以用作任一聚合函数（如 SUM、AVG、MAX、MIN、COUNT、STDEV 或 ANY）的参数。</span><span class="sxs-lookup"><span data-stu-id="46bf7-p101">The chapter column created in a clause of a shape command may be given a *chapter-alias name* (typically with the AS keyword). You may identify any column in any chapter of the shaped **Recordset** with a fully qualified name identifying the child containing the column. For example, if the parent chapter, chap1, contains a child chapter, chap2, that has an amount column, amt, then the qualified name would be chap1.chap2.amt. The qualified name may then be used as an argument to one of the aggregate functions (SUM, AVG, MAX, MIN, COUNT, STDEV, or ANY).</span></span>

