---
title: Shape Compute 子句
TOCTitle: Shape Compute clause
ms:assetid: f4fee4a6-ec9e-c0b6-40e0-258f76c4696f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250245(v=office.15)
ms:contentKeyID: 48548699
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: eadc448d59814f0573a959c6c1038f9c4afdbac9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711523"
---
# <a name="shape-compute-clause"></a>Shape Compute 子句

**适用于**： Access 2013、 Office 2013

shape COMPUTE 子句可以生成父 **Recordset** ，该记录集的列由以下项组成：对子 **Recordset** 的引用；其内容为章节列、新列或计算列的可选列，或者是对子 **Recordset** 或以前定形的 **Recordset** 执行聚合函数的结果；以及在可选的 BY 子句中列出的子 **Recordset** 中的任何列。

## <a name="syntax"></a>语法

```vb 
 
SHAPE child-command [AS] child-alias 
   COMPUTE child-alias [[AS] name], [appended-column-list] 
   [BY grp-field-list] 
```

## <a name="description"></a>说明

此子句的各部分如下所示：

- *child-command*

  - 由下列各项之一组成：
    
    - 返回子 {} 对象的查询命令，放在大括号（"****"）中。该命令向基础数据提供程序发出，其语法取决于该提供程序的要求。这通常是 SQL 语言，但 ADO 不需要任何特定的查询语言。
    
    - 现有已构形 **Recordset** 的名称。
    
    - 另一个 Shape 命令。
    
    - TABLE 关键字，后跟数据提供程序中的表的名称。

- *child-alias*

  - 用于引用**Recordset**的别名返回*子命令。* *子别名*所需的 COMPUTE 子句中的列的列表中，并定义父和子**Recordset**对象之间的关系。

- *appended-column-list*

  - 列表，其中的每个元素定义了所生成的父记录集中的列。每个元素都包含章节列、新列、计算列或对子 **Recordset** 执行聚合函数得到的值。

- *grp-field-list*

  - 父和子 **Recordset** 对象中列的列表，用于指定在子记录集中应当如何对行进行分组。 对于*组字段列表*中的每个列在子和父**Recordset**对象中没有对应的列。 *组字段列表*列的父**Recordset**中的各行，具有唯一值和的子**记录集**由父行引用只包含子行其*组字段列表*列具有相同的值父行。

如果包含 BY 子句，将基于 COMPUTE 子句中的列对子 **Recordset** 的行进行分组。对于子 **Recordset** 中的每一组行，父 **Recordset** 将相应包含一行。

如果省略 BY 子句，则会将整个子 **Recordset** 视为单个组，并且父 **Recordset** 将只包含一行。该行将引用整个子 **Recordset** 。通过省略 BY 子句，可以对整个子 **Recordset** 计算"总计"聚合。

例如：

```vb
    SHAPE {select * from Orders} AS orders
       COMPUTE orders, SUM(orders.OrderAmount) as TotalSales
```

不管采用什么方式形成父 **Recordset** （使用 COMPUTE 或使用 APPEND），它都将包含用来将它与子 **Recordset** 相关的章节列。如果愿意，父 **Recordset** 所包含的列还可能包含针对子行的聚合（SUM、MIN、MAX 等）。父和子 **Recordset** 所包含的列都可能包含针对 **Recordset** 中的行的表达式，以及最初为空的新列。

## <a name="operation"></a>操作

*子命令*颁发给提供程序，返回子**Recordset**。

COMPUTE 子句指定父 **Recordset** 的列，而父记录集则可能是以下项：对子 **Recordset** 的引用、一个或多个聚合、计算表达式或新列。如果有 BY 子句，则它定义的列也将追加到父 **Recordset** 中。BY 子句指定如何对子 **Recordset** 的行进行分组。

例如，假设有一个表 Demographics（人口统计）是由 State（省/市/自治区）、City（市/县）和 Population（人口）字段组成的（人口数字仅用于举例说明）。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>省/市/自治区</p></th>
<th><p>市/县</p></th>
<th><p>人口</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WA</p></td>
<td><p>Seattle</p></td>
<td><p>700000</p></td>
</tr>
<tr class="even">
<td><p>OR</p></td>
<td><p>Medford</p></td>
<td><p>200000</p></td>
</tr>
<tr class="odd">
<td><p>OR</p></td>
<td><p>Portland</p></td>
<td><p>400,000</p></td>
</tr>
<tr class="even">
<td><p>CA</p></td>
<td><p>Los Angeles</p></td>
<td><p>800000</p></td>
</tr>
<tr class="odd">
<td><p>CA</p></td>
<td><p>San Diego</p></td>
<td><p>600,000</p></td>
</tr>
<tr class="even">
<td><p>WA</p></td>
<td><p>Tacoma</p></td>
<td><p>500,000 个</p></td>
</tr>
<tr class="odd">
<td><p>OR</p></td>
<td><p>Corvallis</p></td>
<td><p>300000</p></td>
</tr>
</tbody>
</table>


现在，发出以下 Shape 命令：

```vb 
 
rst.Open  "SHAPE {select * from demographics} AS rs "  & _ 
          "COMPUTE rs, SUM(rs.population) BY state", _ 
           objConnection 
```

此命令将打开一个具有两个级别的已构形 **Recordset** 。 父级别是与聚合列 (SUM(rs.population))、 引用子**Recordset** (rs) 的列和分组的子**Recordset** （状态） 的列生成的**Recordset** 。 子层是由查询命令 （）、 引用子**Recordset** (rs) 的列和分组的子**Recordset** （状态） 的列返回的**Recordset** 。 子层是由查询命令返回的**Recordset** (选择\*从人口统计)。

子 **Recordset** 明细行将按省/市/自治区进行分组，但在其他情况下并没有特定的顺序。就是说，组将不以字母或数字顺序分组。如果想让父 **Recordset** 排序，可以使用 **Recordset** 的 **Sort** 方法对父 **Recordset** 进行排序。

现在可以在打开的父 **Recordset** 中导航，并访问子明细 **Recordset** 对象。有关详细信息，请参阅 [访问分层记录集中的行](accessing-rows-in-a-hierarchical-recordset.md)。

**结果父和子明细记录集**

**Parent**

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>SUM (rs.Population)</p></th>
<th><p>rs</p></th>
<th><p>省/市/自治区</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,300,000</p></td>
<td><p>引用 child1</p></td>
<td><p>CA</p></td>
</tr>
<tr class="even">
<td><p>总共花费 1200000</p></td>
<td><p>引用 child2</p></td>
<td><p>WA</p></td>
</tr>
<tr class="odd">
<td><p>1,100,000</p></td>
<td><p>引用 child3</p></td>
<td><p>OR</p></td>
</tr>
</tbody>
</table>


**Child1**

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>省/市/自治区</p></th>
<th><p>市/县</p></th>
<th><p>人口</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CA</p></td>
<td><p>Los Angeles</p></td>
<td><p>800000</p></td>
</tr>
<tr class="even">
<td><p>CA</p></td>
<td><p>San Diego</p></td>
<td><p>600,000</p></td>
</tr>
</tbody>
</table>


**Child2**

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>省/市/自治区</p></th>
<th><p>市/县</p></th>
<th><p>人口</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WA</p></td>
<td><p>Seattle</p></td>
<td><p>700000</p></td>
</tr>
<tr class="even">
<td><p>WA</p></td>
<td><p>Tacoma</p></td>
<td><p>500,000 个</p></td>
</tr>
</tbody>
</table>


**Child3**

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>省/市/自治区</p></th>
<th><p>市/县</p></th>
<th><p>人口</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OR</p></td>
<td><p>Medford</p></td>
<td><p>200000</p></td>
</tr>
<tr class="even">
<td><p>OR</p></td>
<td><p>Portland</p></td>
<td><p>400,000</p></td>
</tr>
<tr class="odd">
<td><p>OR</p></td>
<td><p>Corvallis</p></td>
<td><p>300000</p></td>
</tr>
</tbody>
</table>

