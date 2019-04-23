---
title: 非参数化命令的操作
TOCTitle: Operation of non-parameterized commands
ms:assetid: 934740b1-07d0-140e-7c83-00feb34c01d1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249651(v=office.15)
ms:contentKeyID: 48546395
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 720cbaf346b64d4d23b1e3314b06ba941e78b700
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288264"
---
# <a name="operation-of-non-parameterized-commands"></a><span data-ttu-id="0d1f4-102">非参数化命令的操作</span><span class="sxs-lookup"><span data-stu-id="0d1f4-102">Operation of non-parameterized commands</span></span>


<span data-ttu-id="0d1f4-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0d1f4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0d1f4-p101">对于非参数化命令，在命令执行期间将执行所有提供程序命令，并创建 **Recordset** 。如果同步执行命令，则所有 **Recordset** 都将完全填充。如果选择异步填充模式，则 **Recordset** 的填充状态将取决于填充模式和 **Recordset** 的大小。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-p101">For non-parameterized commands, all of the provider commands are executed and the **Recordsets** are created during command execution. If the command is executed synchronously, all of the **Recordsets** will be fully populated. If an asynchronous population mode was selected, the populated state of the **Recordsets** will depend on the population mode and the size of the **Recordsets**.</span></span>

<span data-ttu-id="0d1f4-107">例如，*父命令*可以从 Customers（客户）表返回公司顾客的 **Recordset**，并且该*子命令*可以从 Orders（订单）表返回所有顾客订单的 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-107">For example, the *parent-command* could return a **Recordset** of customers for a company from a Customers table, and the *child-command* could return a **Recordset** of orders for all customers from an Orders table.</span></span>

```vb 
 
SHAPE {SELECT * FROM Customers} 
 APPEND ({SELECT * FROM Orders} AS chapOrders 
 RELATE customerID TO customerID) 
```

<span data-ttu-id="0d1f4-108">对于非参数化父子关系，每个父和子 **Recordset** 对象都必须共同拥有一个列，以便将它们关联在一起。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-108">For non-parameterized parent-child relationships, each parent and child **Recordset** object must have a column in common to associate them.</span></span> <span data-ttu-id="0d1f4-109">对列的命名在 RELATE 子句中完成，首先命名*父列*然后命名*子列*。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-109">The columns are named in the RELATE clause, *parent-column* first and then *child-column*.</span></span> <span data-ttu-id="0d1f4-110">列在其各自 **Recordset** 对象中可能有不同名称，但它们必须引用相同信息才能指定有意义的关系。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-110">The columns may have different names in their respective **Recordset** objects but must refer to the same information in order to specify a meaningful relation.</span></span> <span data-ttu-id="0d1f4-111">例如， **Customers** 和 **Orders** **Recordset** 对象都可以有 customerID 字段。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-111">For example, the **Customers** and **Orders** **Recordset** objects could both have a customerID field.</span></span> <span data-ttu-id="0d1f4-112">由于子 **Recordset** 的成员是由提供程序命令确定的，因此子 **Recordset** 有可能包含孤立行。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-112">Because the membership of the child **Recordset** is determined by the provider command, it is possible for the child **Recordset** to contain orphaned rows.</span></span> <span data-ttu-id="0d1f4-113">如果不进一步重新定形，这些孤立行将是不可访问的。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-113">These orphaned rows are inaccessible without further reshaping.</span></span>

<span data-ttu-id="0d1f4-p103">数据定形会向父 **Recordset** 追加章节列。章节列中的值是对满足 RELATE 子句的子 **Recordset** 中的行的引用。就是说，在给定父行的*父列*中具有与在章节子项的所有行的*子列*中相同的值。在同一 RELATE 子句中使用多个 TO 子句时，将使用 AND 运算符对它们进行隐式组合。如果 RELATE 子句中的父列不构成父 **Recordset** 的键，则单个子行可能有多个父行。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-p103">Data shaping appends a chapter column to the parent **Recordset**. The values in the chapter column are references to rows in the child **Recordset**, which satisfy the RELATE clause. That is, the same value is in the *parent-column* of a given parent row as is in the *child-column* of all the rows of the chapter child. When multiple TO clauses are used in the same RELATE clause, they are implicitly combined using an AND operator. If the parent columns in the relate clause do not constitute a key to the parent **Recordset**, a single child row may have multiple parent rows.</span></span>

<span data-ttu-id="0d1f4-p104">访问章节列中的引用时，ADO 将自动检索引用所表示的 **Recordset** 。注意，在非参数化命令中，尽管已经检索整个子 **Recordset** ，但章节只显示行的子集。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-p104">When you access the reference in the chapter column, ADO automatically retrieves the **Recordset** represented by the reference. Note that in a non-parameterized command, although the entire child **Recordset** has been retrieved, the chapter only presents a subset of rows.</span></span>

<span data-ttu-id="0d1f4-p105">如果追加的列没有 *chapter-alias*，系统将自动为它生成名称。列的 [Field](field-object-ado.md) 对象将追加到 **Recordset** 对象的 [Fields](fields-collection-ado.md) 集合，并且它的数据类型将是 **adChapter**。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-p105">If the appended column has no *chapter-alias*, a name will be generated for it automatically. A [Field](field-object-ado.md) object for the column will be appended to the **Recordset** object's [Fields](fields-collection-ado.md) collection, and its data type will be **adChapter**.</span></span>

<span data-ttu-id="0d1f4-123">有关在分层 **Recordset** 中导航的信息，请参阅 [访问分层记录集中的行](accessing-rows-in-a-hierarchical-recordset.md)。</span><span class="sxs-lookup"><span data-stu-id="0d1f4-123">For information about navigating a hierarchical **Recordset**, see [Accessing Rows in a Hierarchical Recordset](accessing-rows-in-a-hierarchical-recordset.md).</span></span>

