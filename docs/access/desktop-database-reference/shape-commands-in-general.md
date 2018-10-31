---
title: 常用 Shape 命令
TOCTitle: Shape Commands in General
ms:assetid: ad555aa7-bc64-b495-a98d-e927061a5809
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249814(v=office.15)
ms:contentKeyID: 48547039
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5cf2dc58ee3fa9205b9657366d8706b64b0aa58a
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861027"
---
# <a name="shape-commands-in-general"></a><span data-ttu-id="11649-102">常用的 Shape 命令</span><span class="sxs-lookup"><span data-stu-id="11649-102">Shape Commands in General</span></span>


<span data-ttu-id="11649-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="11649-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="11649-104">数据定形用于定义已构形 **Recordset** 的列、列所表示的实体之间的关系以及用数据填充 **Recordset** 的方式。</span><span class="sxs-lookup"><span data-stu-id="11649-104">Data shaping defines the columns of a shaped **Recordset**, the relationships between the entities represented by the columns, and the manner in which the **Recordset** is populated with data.</span></span>

<span data-ttu-id="11649-105">已构形的 **Recordset** 可能由以下类型的列组成。</span><span class="sxs-lookup"><span data-stu-id="11649-105">A shaped **Recordset** may consist of the following types of columns.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="11649-106">列类型</span><span class="sxs-lookup"><span data-stu-id="11649-106">Column type</span></span></p></th>
<th><p><span data-ttu-id="11649-107">说明</span><span class="sxs-lookup"><span data-stu-id="11649-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11649-108">data</span><span class="sxs-lookup"><span data-stu-id="11649-108">data</span></span></p></td>
<td><p><span data-ttu-id="11649-109">由查询命令返回给数据提供程序、表或以前定形的 <strong>Recordset</strong> 的 <strong>Recordset</strong> 中的字段。</span><span class="sxs-lookup"><span data-stu-id="11649-109">Fields from a <strong>Recordset</strong> returned by a query command to a data provider, table, or previously shaped <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11649-110">章节</span><span class="sxs-lookup"><span data-stu-id="11649-110">chapter</span></span></p></td>
<td><p><span data-ttu-id="11649-p101">对另一个称为<em>章节</em>的 <strong>Recordset</strong> 的引用。章节列使您可以定义<em>父子</em>关系，其中<em>父</em>是包含章节列的 <strong>Recordset</strong>，而<em>子</em>是章节所表示的 <strong>Recordset</strong>。</span><span class="sxs-lookup"><span data-stu-id="11649-p101">A reference to another <strong>Recordset</strong>, called a <em>chapter</em>. Chapter columns make it possible to define a <em>parent-child</em> relationship where the <em>parent</em> is the <strong>Recordset</strong> containing the chapter column and the <em>child</em> is the <strong>Recordset</strong> represented by the chapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11649-113">聚合</span><span class="sxs-lookup"><span data-stu-id="11649-113">aggregate</span></span></p></td>
<td><p><span data-ttu-id="11649-p102">列的值是通过对子 <strong>Recordset</strong> 的所有行或所有行的某列执行<em>聚合函数</em>而产生的。（请参阅以下主题中的“聚合函数”：<a href="aggregate-functions-the-calc-function-and-the-new-keyword.md">聚合函数、CALC 函数和 NEW 关键字</a>。）</span><span class="sxs-lookup"><span data-stu-id="11649-p102">The value of the column is derived by executing an <em>aggregate function</em> on all the rows or a column of all the rows of a child <strong>Recordset</strong>. (See Aggregate Functions in the following topic, <a href="aggregate-functions-the-calc-function-and-the-new-keyword.md">Aggregate Functions, the CALC Function, and the NEW Keyword</a>.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11649-116">计算表达式</span><span class="sxs-lookup"><span data-stu-id="11649-116">calculated expression</span></span></p></td>
<td><p><span data-ttu-id="11649-p103">列的值是通过对 <strong>Recordset</strong> 的同一行中的列计算 Visual Basic for Applications 表达式而产生的。表达式是 CALC 函数的参数。（请参阅以下主题中的“计算表达式”：<a href="aggregate-functions-the-calc-function-and-the-new-keyword.md">聚合函数、CALC 函数和 NEW 关键字</a>以及 <a href="visual-basic-for-applications-functions.md">Visual Basic for Applications 函数</a>）。</span><span class="sxs-lookup"><span data-stu-id="11649-p103">The value of the column is derived by calculating a Visual Basic for Applications expression on columns in the same row of the <strong>Recordset</strong>. The expression is the argument to the CALC function. (See Calculated Expression in the following topic, <a href="aggregate-functions-the-calc-function-and-the-new-keyword.md">Aggregate Functions, the CALC Function, and the NEW Keyword</a> and in <a href="visual-basic-for-applications-functions.md">Visual Basic for Applications Functions</a>.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11649-120">新建</span><span class="sxs-lookup"><span data-stu-id="11649-120">new</span></span></p></td>
<td><p><span data-ttu-id="11649-p104">构造的空字段，可以随后用数据填充这些字段。列用是用 NEW 关键字进行定义的。（请参阅以下主题中的“NEW 关键字”：<a href="aggregate-functions-the-calc-function-and-the-new-keyword.md">聚合函数、CALC 函数和 NEW 关键字</a>）。</span><span class="sxs-lookup"><span data-stu-id="11649-p104">Empty, fabricated fields, which may be populated with data at a later time. The column is defined with the NEW keyword. (See NEW keyword in the following topic, <a href="aggregate-functions-the-calc-function-and-the-new-keyword.md">Aggregate Functions, the CALC Function, and the NEW Keyword</a>.)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11649-p105">shape 命令可能包含子句，用于指定针对基础数据提供程序的、将返回 **Recordset** 对象的查询命令。查询的语法取决于基础数据提供程序的要求。通常，这是结构化查询语言 (SQL)，尽管 ADO 不需要使用任何特定的查询语言。</span><span class="sxs-lookup"><span data-stu-id="11649-p105">A shape command may contain a clause specifying a query command to an underlying data provider that will return a **Recordset** object. The query's syntax depends on the requirements of the underlying data provider. This will usually be Structured Query Language (SQL), although ADO does not require the use of any particular query language.</span></span>

<span data-ttu-id="11649-p106">可以使用 SQL JOIN 子句来使两个表相关；但是，分层 **Recordset** 可能会更有效地表示信息。由 JOIN 创建的 **Recordset** 的每个行会冗余地重复一个表中的信息。对于每个多子 **Recordset** 对象，分层 **Recordset** 只有一个父 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="11649-p106">You could use a SQL JOIN clause to relate two tables; however, a hierarchical **Recordset** may represent the information more efficiently. Each row of a **Recordset** created by a JOIN repeats information redundantly from one of the tables. A hierarchical **Recordset** has only one parent **Recordset** for each of multiple child **Recordset** objects.</span></span>

<span data-ttu-id="11649-130"><<<<<<< 标头 Shape 命令可以由**Recordset**对象或通过设置[Command](command-object-ado.md)对象的[CommandText](commandtext-property-ado.md)属性，然后调用[Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\))方法颁发。</span><span class="sxs-lookup"><span data-stu-id="11649-130"><<<<<<< HEAD Shape commands can be issued by **Recordset** objects or by setting the [CommandText](commandtext-property-ado.md) property of the [Command](command-object-ado.md) object and then calling the [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) method.</span></span>
<span data-ttu-id="11649-131">=== 由**Recordset**对象或通过设置[Command](command-object-ado.md)对象的[CommandText](commandtext-property-ado.md)属性，然后调用[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command)方法，可以发出 shape 命令。</span><span class="sxs-lookup"><span data-stu-id="11649-131">======= Shape commands can be issued by **Recordset** objects or by setting the [CommandText](commandtext-property-ado.md) property of the [Command](command-object-ado.md) object and then calling the [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) method.</span></span>
>>>>>>> <span data-ttu-id="11649-132">母版</span><span class="sxs-lookup"><span data-stu-id="11649-132">master</span></span>

<span data-ttu-id="11649-133">Shape 命令可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="11649-133">Shape commands can be nested.</span></span> <span data-ttu-id="11649-134">即*父命令*或*子命令*本身可能是另一个 shape 命令。</span><span class="sxs-lookup"><span data-stu-id="11649-134">That is, the *parent-command* or *child-command* may itself be another shape command.</span></span>

<span data-ttu-id="11649-135">即使用户指定了 **adUseServer** 的游标位置，构形提供程序也会始终返回客户端游标。</span><span class="sxs-lookup"><span data-stu-id="11649-135">The shape provider always returns a client cursor, even when the user specifies a cursor location of **adUseServer**.</span></span>

<span data-ttu-id="11649-136">有关在分层 **Recordset** 中导航的信息，请参阅 [访问分层记录集中的行](accessing-rows-in-a-hierarchical-recordset.md)。</span><span class="sxs-lookup"><span data-stu-id="11649-136">For information about navigating a hierarchical **Recordset**, see [Accessing Rows in a Hierarchical Recordset](accessing-rows-in-a-hierarchical-recordset.md).</span></span>

<span data-ttu-id="11649-137">有关语法正确的 Shape 命令的准确信息，请参阅[正式 Shape 语法](formal-shape-grammar.md)。</span><span class="sxs-lookup"><span data-stu-id="11649-137">For precise information about syntactically correct shape commands, see [Formal Shape Grammar](formal-shape-grammar.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="11649-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11649-138">See also</span></span>

- [<span data-ttu-id="11649-139">向基础数据提供程序发出命令</span><span class="sxs-lookup"><span data-stu-id="11649-139">Issuing Commands to the Underlying Data Provider</span></span>](issuing-commands-to-the-underlying-data-provider.md)

