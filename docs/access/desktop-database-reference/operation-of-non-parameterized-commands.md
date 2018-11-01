---
title: 操作非参数化命令
TOCTitle: Operation of Non-Parameterized Commands
ms:assetid: 934740b1-07d0-140e-7c83-00feb34c01d1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249651(v=office.15)
ms:contentKeyID: 48546395
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a3e1799e5e40ffa3ffcd6698900b8678b309696e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885155"
---
# <a name="operation-of-non-parameterized-commands"></a>操作非参数化命令


**适用于**： Access 2013、 Office 2013

对于非参数化命令，在命令执行期间将执行所有提供程序命令，并创建 **Recordset** 。如果同步执行命令，则所有 **Recordset** 都将完全填充。如果选择异步填充模式，则 **Recordset** 的填充状态将取决于填充模式和 **Recordset** 的大小。

例如，*父命令*无法从客户表中，返回公司客户的**记录集**和*子命令*无法从 Orders 表返回**Recordset**的所有客户的订单。

```vb 
 
SHAPE {SELECT * FROM Customers} 
 APPEND ({SELECT * FROM Orders} AS chapOrders 
 RELATE customerID TO customerID) 
```

对于非参数化父子关系，每个父和子 **Recordset** 对象都必须共同拥有一个列，以便将它们关联在一起。 列命名建立关系子句，*父列*中第一个，然后选择*子列*。 列在其各自 **Recordset** 对象中可能有不同名称，但它们必须引用相同信息才能指定有意义的关系。 例如， **Customers** 和 **Orders** **Recordset** 对象都可以有 customerID 字段。 由于子 **Recordset** 的成员是由提供程序命令确定的，因此子 **Recordset** 有可能包含孤立行。 如果不进一步重新定形，这些孤立行将是不可访问的。

数据定形会向父 **Recordset** 追加章节列。 章节列中的值是对满足 RELATE 子句的子 **Recordset** 中的行的引用。 即，相同的值是给定的父行的章节子项的所有行的*子列*中的*父列*中。 在同一 RELATE 子句中使用多个 TO 子句时，将使用 AND 运算符对它们进行隐式组合。 如果 RELATE 子句中的父列不构成父 **Recordset** 的键，则单个子行可能有多个父行。

访问章节列中的引用时，ADO 将自动检索引用所表示的 **Recordset** 。注意，在非参数化命令中，尽管已经检索整个子 **Recordset** ，但章节只显示行的子集。

如果追加的列没有 *chapter-alias*，系统将自动为它生成名称。列的 [Field](field-object-ado.md) 对象将追加到 **Recordset** 对象的 [Fields](fields-collection-ado.md) 集合，并且它的数据类型将是 **adChapter**。

有关在分层 **Recordset** 中导航的信息，请参阅 [访问分层记录集中的行](accessing-rows-in-a-hierarchical-recordset.md)。

