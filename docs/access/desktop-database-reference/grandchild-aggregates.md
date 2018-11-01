---
title: 孙聚合
TOCTitle: Grandchild Aggregates
ms:assetid: ea5e2e1f-f3d5-f851-623a-a5d1385fe206
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250188(v=office.15)
ms:contentKeyID: 48548462
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7c5ab45412b0524bcef14a952f5c5bbe0953278c
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873528"
---
# <a name="grandchild-aggregates"></a>孙聚合


**适用于**： Access 2013、 Office 2013

创建 shape 命令的子句中的章节列可能有*章别名*（通常使用 AS 关键字）。 您可能使用的完全限定名称来标识包含的列的子标识任何定形**Recordset**的章节中的任何列。 例如，如果父章，chap1，包含子一章，chap2，具有量列中，主动管理技术，则限定的名称将为 chap1.chap2.amt。限定的名可能然后用作聚合函数 （SUM、 平均、 MAX、 MIN、 计数、 STDEV 和或任何） 之一的参数。

