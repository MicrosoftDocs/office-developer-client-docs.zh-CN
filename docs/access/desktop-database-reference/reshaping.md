---
title: 调整形状 （访问桌面数据库参考 （英文）
TOCTitle: Reshaping
ms:assetid: 89c6a0d6-3bf4-36ae-26ec-d4e60f920490
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249605(v=office.15)
ms:contentKeyID: 48546174
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c820e82669789d7c3806cc1fd38a2eb6844b722e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711900"
---
# <a name="reshaping"></a><span data-ttu-id="6adba-102">重新成型</span><span class="sxs-lookup"><span data-stu-id="6adba-102">Reshaping</span></span>

<span data-ttu-id="6adba-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6adba-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6adba-p101">可以向 Shape 命令的子句所创建的 **Recordset** 赋予一个*别名*（通常用 AS 关键字）。已构形的 **Recordset** 的别名可以在一个完全不同的命令中引用。即，您可以再次使用以前构形的 **Recordset**，也可以用新的 Shape 命令对其*重新构形*。为了支持此功能，ADO 提供了一个属性：[Reshape Name](reshape-name-property-dynamic-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="6adba-p101">A **Recordset** created by a clause of a shape command may be assigned an *alias* name (typically with the AS keyword). The alias of a shaped **Recordset** can be referenced in an entirely different command. That is, you may reuse, or *reshape*, a previously shaped **Recordset** in a new shape command. To support this feature, ADO provides a property, [Reshape Name](reshape-name-property-dynamic-ado.md).</span></span>

<span data-ttu-id="6adba-p102">重新构形具有两个主要功能，第一个功能是将现有的 **Recordset** 与新的父 **Recordset** 相关联。</span><span class="sxs-lookup"><span data-stu-id="6adba-p102">Reshaping has two main functions. The first is to associate an existing **Recordset** with a new parent **Recordset**.</span></span>

## <a name="example"></a><span data-ttu-id="6adba-110">示例</span><span class="sxs-lookup"><span data-stu-id="6adba-110">Example</span></span>

```vb 
 
. . . 
rs1.Open "SHAPE {select * from Customers} " & _ 
 "APPEND ({select * from Orders} AS chapOrders " & _ 
 "RELATE CustomerID to CustomerID)", cn 
 
rs2.Open "SHAPE {select * from Employees} " & _ 
 "APPEND (chapOrders RELATE EmployeeID to EmployeeID)", cn 
. . . 
```

<span data-ttu-id="6adba-111">第二个功能是允许进行非章节访问现有的子**Recordset**对象，使用语法`"SHAPE <recordset reshape name>"`。</span><span class="sxs-lookup"><span data-stu-id="6adba-111">The second function is to enable non-chaptered access to existing child **Recordset** objects, using the syntax `"SHAPE <recordset reshape name>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="6adba-112">[!注释] 不能向现有的 **Recordset** 追加列，不能用任何干扰性 COMPUTE 子句对参数化 **Recordset** 或 **Recordset** 对象进行重新构形，不能从正重新构形的 **Recordset** 对任何 **Recordset** 后代执行聚合运算。</span><span class="sxs-lookup"><span data-stu-id="6adba-112">You cannot append columns to an existing **Recordset**, reshape a parameterized **Recordset** or the **Recordset** objects in any intervening COMPUTE clause, or perform aggregate operations on any **Recordset** descendant from the **Recordset** being reshaped.</span></span> <span data-ttu-id="6adba-113">改变了形状的**Recordset**和新的形状命令都必须使用相同 \* \*[Connection](connection-object-ado.md)对象。</span><span class="sxs-lookup"><span data-stu-id="6adba-113">The **Recordset** being reshaped and the new shape command must both use the same \*\*[Connection](connection-object-ado.md) object.</span></span>


