---
title: ForEachRecord 数据块
TOCTitle: ForEachRecord data block
ms:assetid: be369196-230e-1f92-e36b-667048eef2be
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822743(v=office.15)
ms:contentKeyID: 48547455
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd16b91bb3d6ca0d206be0a63bb73e6f9176da8e
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921024"
---
# <a name="foreachrecord-data-block"></a>ForEachRecord 数据块


**适用于**： Access 2013、 Office 2013

**ForEachRecord**数据块的域中的每个记录都重复一组语句。


> [!NOTE]
> <P>[!注释] <STRONG>ForEachRecord</STRONG> 数据块仅适用于数据宏。</P>



## <a name="setting"></a>设置

**ForEachRecord** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>是否必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>In</strong></p></td>
<td><p>是</p></td>
<td><p>一个字符串，标识的记录执行操作的域。 <em>在</em>参数可以包含表、 选择查询或 SQL 语句的名称。</p>

> [!NOTE]
> <P>指定域不能包括链接表或 ODBC 数据源中存储的数据。</P>


<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Where Condition</strong></p></td>
<td><p>否</p></td>
<td><p>执行字符串表达式，用来限制在其上的数据区域<strong>ForEachRecord</strong>数据块。 例如，criteria通常是相当于 SQL 表达式中的 WHERE 子句位置，但是不使用 WHERE一词。 如果省略条件，则<strong>ForEachRecord</strong>数据块运行上指定<em>中</em>参数的整个域。 条件中包括的任何字段必须同时是<em>中</em>的字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Alias</strong></p></td>
<td><p>否</p></td>
<td><p>提供<em>在</em>参数指定的域的替代名称的字符串。 通常用于缩短后续参考，以防止可能出现的不明确引用的表名称。如果未指定<em>别名</em>，则表或查询名称将用作别名。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

使用 **[ExitForEachRecord](exitforeachrecord-macro-action.md)** 操作可立即退出 **ForEachRecord** 数据块。

