---
title: 常用 Shape 命令
TOCTitle: Shape Commands in General
ms:assetid: ad555aa7-bc64-b495-a98d-e927061a5809
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249814(v=office.15)
ms:contentKeyID: 48547039
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 34e691edd429b5d7f00da0c8eb994ffd999c6305
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603950"
---
# <a name="shape-commands-in-general"></a>常用 Shape 命令


**适用于**： Access 2013 |Office 2013

数据定形用于定义已构形 **Recordset** 的列、列所表示的实体之间的关系以及用数据填充 **Recordset** 的方式。

已构形的 **Recordset** 可能由以下类型的列组成。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>列类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>数据</p></td>
<td><p>由查询命令返回给数据提供程序、表或以前定形的 <strong>Recordset</strong> 的 <strong>Recordset</strong> 中的字段。</p></td>
</tr>
<tr class="even">
<td><p>章节</p></td>
<td><p>对另一个称为<em>章节</em>的 <strong>Recordset</strong> 的引用。章节列使您可以定义<em>父子</em>关系，其中<em>父</em>是包含章节列的 <strong>Recordset</strong>，而<em>子</em>是章节所表示的 <strong>Recordset</strong>。</p></td>
</tr>
<tr class="odd">
<td><p>聚合</p></td>
<td><p>列的值是通过对子 <strong>Recordset</strong> 的所有行或所有行的某列执行<em>聚合函数</em>而产生的。（请参阅以下主题中的“聚合函数”：<a href="aggregate-functions-the-calc-function-and-the-new-keyword.md">聚合函数、CALC 函数和 NEW 关键字</a>。）</p></td>
</tr>
<tr class="even">
<td><p>计算表达式</p></td>
<td><p>列的值是通过对 <strong>Recordset</strong> 的同一行中的列计算 Visual Basic for Applications 表达式而产生的。表达式是 CALC 函数的参数。（请参阅以下主题中的“计算表达式”：<a href="aggregate-functions-the-calc-function-and-the-new-keyword.md">聚合函数、CALC 函数和 NEW 关键字</a>以及 <a href="visual-basic-for-applications-functions.md">Visual Basic for Applications 函数</a>）。</p></td>
</tr>
<tr class="odd">
<td><p>新建</p></td>
<td><p>构造的空字段，可以随后用数据填充这些字段。列用是用 NEW 关键字进行定义的。（请参阅以下主题中的“NEW 关键字”：<a href="aggregate-functions-the-calc-function-and-the-new-keyword.md">聚合函数、CALC 函数和 NEW 关键字</a>）。</p></td>
</tr>
</tbody>
</table>


shape 命令可能包含子句，用于指定针对基础数据提供程序的、将返回 **Recordset** 对象的查询命令。查询的语法取决于基础数据提供程序的要求。通常，这是结构化查询语言 (SQL)，尽管 ADO 不需要使用任何特定的查询语言。

可以使用 SQL JOIN 子句来使两个表相关；但是，分层 **Recordset** 可能会更有效地表示信息。由 JOIN 创建的 **Recordset** 的每个行会冗余地重复一个表中的信息。对于每个多子 **Recordset** 对象，分层 **Recordset** 只有一个父 **Recordset** 。

<<<<<<< 标头 Shape 命令可以由**Recordset**对象或通过设置[Command](command-object-ado.md)对象的[CommandText](commandtext-property-ado.md)属性，然后调用[Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\))方法颁发。
=== 由**Recordset**对象或通过设置[Command](command-object-ado.md)对象的[CommandText](commandtext-property-ado.md)属性，然后调用[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command)方法，可以发出 shape 命令。
>>>>>>> master

Shape 命令可以嵌套。 即*父命令*或*子命令*本身可能是另一个 shape 命令。

即使用户指定了 **adUseServer** 的游标位置，构形提供程序也会始终返回客户端游标。

有关在分层 **Recordset** 中导航的信息，请参阅 [访问分层记录集中的行](accessing-rows-in-a-hierarchical-recordset.md)。

有关语法正确的 Shape 命令的准确信息，请参阅[正式 Shape 语法](formal-shape-grammar.md)。

