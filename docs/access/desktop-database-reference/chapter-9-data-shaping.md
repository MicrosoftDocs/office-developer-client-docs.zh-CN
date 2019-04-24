---
title: 第 9 章：数据成型
TOCTitle: 'Chapter 9: Data shaping'
ms:assetid: f66a319f-1b3d-c4a3-50b3-af1a47540832
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250253(v=office.15)
ms:contentKeyID: 48548739
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 43ad9d5e989bc1c6f4a54fb4882cfe3c3e357fd1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296421"
---
# <a name="chapter-9-data-shaping"></a>第 9 章：数据成型

**适用于**：Access 2013、Office 2013

*数据定形*使您能够查询数据源并返回表示两个或多个逻辑实体（层次结构）之间的父子关系的 [Recordset](recordset-object-ado.md)。 

分层关系的典型示例是客户和订单。 对于数据库中的每个顾客来说，可以有零个或更多个订单。 常规 SQL 可以使用 JOIN 语法检索数据，但是，对于给定的父子关系，冗余的父数据会在每个返回的记录中重复出现，因此这种方式可能效率低且不实用。 数据定形可以使父 **Recordset** 中的单个父记录与子 **Recordset** 中的多个子记录相关，从而避免了 JOIN 发生冗余。 很多人都会发现父子多 **Recordset** 编程模型比单个 **Recordset** JOIN 模型更简单且更容易使用。

数据定形语法还提供了其他功能。开发人员可以通过使用 NEW 关键字来描述父和子 **Recordsets** 的字段，即可在没有基础数据源的情况下创建新的 **Recordset** 对象。新的 **Recordset** 对象可以用数据进行填充，并进行永久存储。开发人员还可以对子字段执行各种计算或聚合（如 SUM、AVG 和 MAX）。数据定形还可以通过子 **Recordset** 创建父 **Recordset** ，方法是将子记录集中的记录分组，并对应于子记录集的每个组在父记录集中放置一行。

有关数据定形的详细信息，请参阅以下主题：

- [需要数据成型提供程序](required-providers-for-data-shaping.md)
- [Shape Compute 子句](shape-compute-clause.md)
- [构建层次记录集](fabricating-hierarchical-recordsets.md)
- [访问层次记录集中的行](accessing-rows-in-a-hierarchical-recordset.md)
- [Formal Shape语法](formal-shape-grammar.md)
- [Visual Basic for Applications 函数](visual-basic-for-applications-functions.md)
- [Shape Append 子句 (ADO)](shape-append-clause.md)
- [数据定形 (ADO)](data-shaping.md)
- [general 中的 Shape 命令 (ADO)](shape-commands-in-general.md)

