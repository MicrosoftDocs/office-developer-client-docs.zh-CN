---
title: 调整形状 （访问桌面数据库参考 （英文）
TOCTitle: Reshaping
ms:assetid: 89c6a0d6-3bf4-36ae-26ec-d4e60f920490
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249605(v=office.15)
ms:contentKeyID: 48546174
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a051c62d73a36fed0832f17b1cb53b1641d4a152
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25889278"
---
# <a name="reshaping"></a><span data-ttu-id="4f27d-102">重构</span><span class="sxs-lookup"><span data-stu-id="4f27d-102">Reshaping</span></span>


<span data-ttu-id="4f27d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4f27d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4f27d-p101">可以向 Shape 命令的子句所创建的 **Recordset** 赋予一个*别名*（通常用 AS 关键字）。已构形的 **Recordset** 的别名可以在一个完全不同的命令中引用。即，您可以再次使用以前构形的 **Recordset**，也可以用新的 Shape 命令对其*重新构形*。为了支持此功能，ADO 提供了一个属性：[Reshape Name](reshape-name-property-dynamic-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="4f27d-p101">A **Recordset** created by a clause of a shape command may be assigned an *alias* name (typically with the AS keyword). The alias of a shaped **Recordset** can be referenced in an entirely different command. That is, you may reuse, or *reshape*, a previously shaped **Recordset** in a new shape command. To support this feature, ADO provides a property, [Reshape Name](reshape-name-property-dynamic-ado.md).</span></span>

<span data-ttu-id="4f27d-p102">重新构形具有两个主要功能，第一个功能是将现有的 **Recordset** 与新的父 **Recordset** 相关联。</span><span class="sxs-lookup"><span data-stu-id="4f27d-p102">Reshaping has two main functions. The first is to associate an existing **Recordset** with a new parent **Recordset**.</span></span>

## <a name="example"></a><span data-ttu-id="4f27d-110">示例</span><span class="sxs-lookup"><span data-stu-id="4f27d-110">Example</span></span>

```vb 
 
. . . 
rs1.Open "SHAPE {select * from Customers} " & _ 
 "APPEND ({select * from Orders} AS chapOrders " & _ 
 "RELATE CustomerID to CustomerID)", cn 
 
rs2.Open "SHAPE {select * from Employees} " & _ 
 "APPEND (chapOrders RELATE EmployeeID to EmployeeID)", cn 
. . . 
```

<span data-ttu-id="4f27d-111">第二个功能是允许进行非章节访问现有的子**Recordset**对象，使用语法`"SHAPE <recordset reshape name>"`。</span><span class="sxs-lookup"><span data-stu-id="4f27d-111">The second function is to enable non-chaptered access to existing child **Recordset** objects, using the syntax `"SHAPE <recordset reshape name>"`.</span></span>


> [!NOTE]
> <P><span data-ttu-id="4f27d-p103">[!注释] 不能向现有的 <STRONG>Recordset</STRONG> 追加列，不能用任何干扰性 COMPUTE 子句对参数化 <STRONG>Recordset</STRONG> 或 <STRONG>Recordset</STRONG> 对象进行重新构形，不能从正重新构形的 <STRONG>Recordset</STRONG> 对任何 <STRONG>Recordset</STRONG> 后代执行聚合运算。正重新构形的 <STRONG>Recordset</STRONG> 以及新 Shape 命令都必须使用同一个 <A href="connection-object-ado.md">Connection</A>。</span><span class="sxs-lookup"><span data-stu-id="4f27d-p103">You cannot append columns to an existing <STRONG>Recordset</STRONG>, reshape a parameterized <STRONG>Recordset</STRONG> or the <STRONG>Recordset</STRONG> objects in any intervening COMPUTE clause, or perform aggregate operations on any <STRONG>Recordset</STRONG> descendant from the <STRONG>Recordset</STRONG> being reshaped. The <STRONG>Recordset</STRONG> being reshaped and the new shape command must both use the same <A href="connection-object-ado.md">Connection</A>.</span></span></P>


