---
title: 整形 (Access desktop database reference)
TOCTitle: Reshaping
ms:assetid: 89c6a0d6-3bf4-36ae-26ec-d4e60f920490
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249605(v=office.15)
ms:contentKeyID: 48546174
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c820e82669789d7c3806cc1fd38a2eb6844b722e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314775"
---
# <a name="reshaping"></a>重新成型

**适用于**：Access 2013、Office 2013

可以向 Shape 命令的子句所创建的 **Recordset** 赋予一个*别名*（通常用 AS 关键字）。已构形的 **Recordset** 的别名可以在一个完全不同的命令中引用。即，您可以再次使用以前构形的 **Recordset**，也可以用新的 Shape 命令对其*重新构形*。为了支持此功能，ADO 提供了一个属性：[Reshape Name](reshape-name-property-dynamic-ado.md)。

重新构形具有两个主要功能，第一个功能是将现有的 **Recordset** 与新的父 **Recordset** 相关联。

## <a name="example"></a>示例

```vb 
 
. . . 
rs1.Open "SHAPE {select * from Customers} " & _ 
 "APPEND ({select * from Orders} AS chapOrders " & _ 
 "RELATE CustomerID to CustomerID)", cn 
 
rs2.Open "SHAPE {select * from Employees} " & _ 
 "APPEND (chapOrders RELATE EmployeeID to EmployeeID)", cn 
. . . 
```

第二个函数是使用语法`"SHAPE <recordset reshape name>"`启用对现有子**Recordset**对象的非章节访问。

> [!NOTE]
> 不能向现有的 **Recordset** 追加列，不能用任何干扰性 COMPUTE 子句对参数化 **Recordset** 或 **Recordset** 对象进行重新构形，不能从正重新构形的 **Recordset** 对任何 **Recordset** 后代执行聚合运算。 正在重整形的**Recordset** , 并且 "新建 shape" 命令必须使用相同的 * *[Connection](connection-object-ado.md)对象。


