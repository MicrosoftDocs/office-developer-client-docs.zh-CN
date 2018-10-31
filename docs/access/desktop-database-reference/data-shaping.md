---
title: Data Shaping （访问桌面数据库参考 （英文）
TOCTitle: Data Shaping
ms:assetid: 650571cc-6874-2cdb-dd76-0804d1cc4e38
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249390(v=office.15)
ms:contentKeyID: 48545305
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 686c860ef9d8975b02391fedcea8f4b6f4e0b9bb
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862294"
---
# <a name="data-shaping"></a>数据成型


**适用于**： Access 2013 |Office 2013

通过数据定形，可以定义定形 **Recordset** 的列、列所代表的实体之间的关系以及在 **Recordset** 中填充数据的方式。

定形 **Recordset** 的列可能包含来自数据提供程序（如 Microsoft SQL Server）的数据、对其他 **Recordset** 的引用、从 **Recordset** 单行计算派生的值或从针对整个 **Recordset** 列的操作派生的值；这些列也可能是新创建的空列。

在检索包含对其他 **Recordset** 的引用的列的值时，ADO 自动返回引用所表示的实际 **Recordset**。包含其他 **Recordset** 的 **Recordset** 称为分层记录集。分层记录集体现了*父子*关系，其中*父*是包含的记录集，而*子*是被包含的记录集。引用 **Recordset** 实际上是引用子记录集的子集，称为*章节*。单个父记录集可以引用多个子 **Recordset**。

通过 Shape 命令语法，可以通过编程方式创建定形 **Recordset** 。随后，可以通过编程方式或适当的可视控件访问 **Recordset** 的组件。Shape 命令的发布类似于其他所有 ADO 命令文本。

您可以通过两种方式使用 Shape 命令来生成分层 **Recordset** 对象。第一种方式是将子 **Recordset** 追加到父 **Recordset** 。通常，父记录集和子记录集至少共同具有一列：父记录集某行中该列的值与子记录集所有行中该列的值相等。

第二种方式是从子 **Recordset** 生成父 **Recordset** 。首先对子 **Recordset** 中的记录进行分组（通常使用 BY 子句），然后对于子记录集中生成的每个组，在父 **Recordset** 中添加一行。如果省略 BY 子句，则整个子 **Recordset** 为单个组，父 **Recordset** 将只包含一行。这可用于对整个子 **Recordset** 计算"总计"。

无论父 **Recordset** 采用何种方式构成，都将包含"章节"列，用于将其与子 **Recordset** 关联。如果愿意，父 **Recordset** 中的列还可以包含对子记录集行进行运算的聚合函数（如 SUM、MIN、MAX 等）。父子 **Recordset** 中的列都可以包含针对 **Recordset** 中行的表达式，也可以是一开始为空的新列。

分层 **Recordset** 对象可以嵌套至任何深度（即，创建子 **Recordset** 对象的子 **Recordset** 对象，依此类推）。

可以通过编程方式或适当的可视控件访问定形 **Recordset** 的 **Recordset** 组件。

有关 Shape 命令及生成的层次结构示例，请参阅"使用 Data Shaping Service for OLE DB：深入了解"。

本节包括下列主题：

- [重新构形](reshaping.md)

- [孙聚合](grandchild-aggregates.md)

- [参数化命令与干扰性 COMPUTE 命令](parameterized-commands-with-intervening-compute-commands.md)

- [持久化分层记录集](persisting-hierarchical-recordsets.md)