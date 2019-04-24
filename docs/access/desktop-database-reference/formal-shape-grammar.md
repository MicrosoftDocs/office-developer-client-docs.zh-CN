---
title: Formal Shape语法
TOCTitle: Formal shape grammar
ms:assetid: a3220569-8804-3dc3-7f9f-b4f8cdab1316
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249752(v=office.15)
ms:contentKeyID: 48546774
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d30ff9146146bb0457a5aa383b2b720a4fdaeb78
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292319"
---
# <a name="formal-shape-grammar"></a>Formal Shape语法

**适用于**：Access 2013、Office 2013

以下是创建任何 Shape 命令的正式语法：

  - 必需的语法术语是以尖括号（"\<\>"）分隔的文本字符串。

  - 可选的术语以方括号 ("\[ \]") 分隔。

  - 替代项以竖线（"|"）指示。

  - 重复替代项以省略号（“...”）指示。

  - *Alpha* 指示字母字符串。

  - *Digit* 指示数字字符串。

  - *Unicode-digit* 指示 unicode 数字的字符串。

所有其他术语是文字。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>术语</p></th>
<th><p>定义</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;shape 命令&gt;</p></td>
<td><p>SHAPE [&lt;表-exp&gt; [[AS] &lt;别名&gt;]] [&lt;形状-操作&gt;]</p></td>
</tr>
<tr class="even">
<td><p>&lt;表-exp&gt;</p></td>
<td><p>{&lt;provider-command-text&gt;} |<br />
(&lt;形状-命令&gt;) |<br />
引用&lt;的表-名称&gt; |<br />
&lt;带引号的名称&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;形状-操作&gt;</p></td>
<td><p>追加&lt;别名字段列表&gt; |</p>
<p>计算&lt;别名字段列表&gt; [按&lt;字段列表]&gt;</p></td>
</tr>
<tr class="even">
<td><p>&lt;别名字段列表&gt;</p></td>
<td><p>&lt;别名字段&gt; [, &lt;别名字段 .。。&gt;]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;别名字段&gt;</p></td>
<td><p>&lt;字段 exp&gt; [[AS] &lt;别名]&gt;</p></td>
</tr>
<tr class="even">
<td><p>&lt;字段-exp&gt;</p></td>
<td><p>(&lt;关系-exp&gt;) |</p>
<p>&lt;计算-exp&gt; |</p>
<p>&lt;聚合-exp&gt; |</p>
<p>&lt;new-exp&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;relation_exp&gt;</p></td>
<td><p>&lt;表-exp&gt; [[AS] &lt;别名&gt;]</p>
<p>&lt;表-exp&gt; [[AS] &lt;别名&gt;]</p></td>
</tr>
<tr class="even">
<td><p>&lt;关系--列表&gt;</p></td>
<td><p>&lt;关系-导线&gt; [, &lt;关系-导线&gt;...]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;关系-导线&gt;</p></td>
<td><p>&lt;field-名称&gt;到&lt;子引用&gt;</p></td>
</tr>
<tr class="even">
<td><p>&lt;子引用&gt;</p></td>
<td><p>&lt;域名称&gt; |</p>
<p>参数&lt;参数-ref&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;param-ref&gt;</p></td>
<td><p>&lt;多种&gt;</p></td>
</tr>
<tr class="even">
<td><p>&lt;字段-列表&gt;</p></td>
<td><p>&lt;field-name&gt; [, &lt;field-name&gt;]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;聚合-exp&gt;</p></td>
<td><p>SUM (&lt;限定字段名称&gt;) |</p>
<p>AVG (&lt;限定字段名称&gt;) |</p>
<p>MIN (&lt;限定字段名称&gt;) |</p>
<p>MAX (&lt;限定字段名称&gt;) |</p>
<p>COUNT (&lt;限定别名&gt; | &lt;限定名称&gt;) |</p>
<p>STDEV (&lt;限定字段名称&gt;) |</p>
<p>ANY (&lt;限定字段名称&gt;)</p></td>
</tr>
<tr class="even">
<td><p>&lt;计算-exp&gt;</p></td>
<td><p>CALC (&lt;表达式&gt;)</p></td>
</tr>
<tr class="odd">
<td><p>&lt;限定字段名称&gt;</p></td>
<td><p>&lt;别名&gt;。[&lt;别名&gt;...]&lt;域名称&gt;</p></td>
</tr>
<tr class="even">
<td><p>&lt;alias&gt;</p></td>
<td><p>&lt;带引号的名称&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;域名称&gt;</p></td>
<td><p>&lt;带引号的&gt;名称 [[AS &lt;]&gt;别名]</p></td>
</tr>
<tr class="even">
<td><p>&lt;带引号的名称&gt;</p></td>
<td><p>&quot;&lt;类似&gt;&quot; |</p>
<p>"&lt;string&gt;" |</p>
<p>[&lt;string&gt;] |</p>
<p>&lt;别名&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;限定名称&gt;</p></td>
<td><p>别名 [. 别名 ...]</p></td>
</tr>
<tr class="even">
<td><p>&lt;别名&gt;</p></td>
<td><p>alpha [alpha | 数字 | _ | # |: | ...]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;多种&gt;</p></td>
<td><p>数字 [数字 ...]</p></td>
</tr>
<tr class="even">
<td><p>&lt;new-exp&gt;</p></td>
<td><p>新&lt;字段-type&gt; [(&lt;number&gt; [, &lt;number&gt;])]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;field 类型&gt;</p></td>
<td><p>OLE DB 或 ADO 数据类型。</p></td>
</tr>
<tr class="even">
<td><p>&lt;类似&gt;</p></td>
<td><p>unicode 字符 [unicode-字符 ...]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;表达式&gt;</p></td>
<td><p>Visual Basic for Applications 表达式，其操作数是在相同行中的其他非 CALC 列。</p></td>
</tr>
</tbody>
</table>

