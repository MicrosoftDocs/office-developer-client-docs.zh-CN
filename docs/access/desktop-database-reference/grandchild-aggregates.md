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
# <a name="grandchild-aggregates"></a>孙级聚合


**适用于**：Access 2013、Office 2013

在 Shape 命令子句中创建的“章节”列可能会被赋予一个 *chapter-alias name*（通常使用 AS 关键字）。您可以用标识包含列的子记录集的完整名称来标识定形 **Recordset** 的任何章节中的任何列。例如，如果父章节 chap1 包含子章节 chap2，而后者具有一个数量列 amt，则限定名称为 chap1.chap2.amt。随后，该限定名称可以用作任一聚合函数（如 SUM、AVG、MAX、MIN、COUNT、STDEV 或 ANY）的参数。

