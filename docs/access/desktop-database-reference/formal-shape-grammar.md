---
title: 正式 shape 语法
TOCTitle: Formal shape grammar
ms:assetid: a3220569-8804-3dc3-7f9f-b4f8cdab1316
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249752(v=office.15)
ms:contentKeyID: 48546774
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0de4f2eca0b5dd607cb9d93cc7e90f4af0ba8d89
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945535"
---
# <a name="formal-shape-grammar"></a>正式 shape 语法

**适用于**： Access 2013、 Office 2013

以下是创建任何 Shape 命令的正式语法：

  - 必需的语法术语是以尖括号（"\<\>"）分隔的文本字符串。

  - 可选的术语分隔方括号 ("\[ \]")。

  - 替代项以竖线（"|"）指示。

  - 重复替代项以省略号（"..."）指示。

  - *Alpha*指示字母字符串。

  - *Digit*指示数字字符串。

  - *Unicode-digit*指示 unicode 数字的字符串。

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
<td><p>形状 [&lt;表 exp&gt; [[AS]&lt;别名&gt;]] [&lt;形状动作&gt;]</p></td>
</tr>
<tr class="even">
<td><p>&lt;表 exp&gt;</p></td>
<td><p>{&lt;提供程序命令文本&gt;} |<br />
(&lt;shape 命令&gt;) |<br />
表&lt;带引号的名称&gt; |<br />
&lt;带引号的名称&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;形状操作&gt;</p></td>
<td><p>APPEND&lt;失真字段列表&gt; |</p>
<p>计算&lt;失真字段列表&gt;[BY&lt;字段列表&gt;]</p></td>
</tr>
<tr class="even">
<td><p>&lt;失真字段列表&gt;</p></td>
<td><p>&lt;失真字段&gt;[， &lt;...失真字段&gt;]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;失真字段&gt;</p></td>
<td><p>&lt;字段 exp&gt; [[AS]&lt;别名&gt;]</p></td>
</tr>
<tr class="even">
<td><p>&lt;字段 exp&gt;</p></td>
<td><p>(&lt;关系 exp&gt;) |</p>
<p>&lt;计算 exp&gt; |</p>
<p>&lt;聚合 exp&gt; |</p>
<p>&lt;新 exp&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;relation_exp&gt;</p></td>
<td><p>&lt;表 exp&gt; [[AS]&lt;别名&gt;]</p>
<p>&lt;表 exp&gt; [[AS]&lt;别名&gt;]</p></td>
</tr>
<tr class="even">
<td><p>&lt;关系黑列表&gt;</p></td>
<td><p>&lt;关系黑&gt;[，&lt;关系黑&gt;...]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;关系黑&gt;</p></td>
<td><p>&lt;字段名称&gt;收件人&lt;子 ref&gt;</p></td>
</tr>
<tr class="even">
<td><p>&lt;子 ref&gt;</p></td>
<td><p>&lt;字段名称&gt; |</p>
<p>参数&lt;param ref&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;param ref&gt;</p></td>
<td><p>&lt;号码&gt;</p></td>
</tr>
<tr class="even">
<td><p>&lt;字段列表&gt;</p></td>
<td><p>&lt;字段名称&gt;[，&lt;字段名称&gt;]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;聚合 exp&gt;</p></td>
<td><p>SUM (&lt;限定-字段-name&gt;) |</p>
<p>平均 (&lt;限定-字段-name&gt;) |</p>
<p>MIN (&lt;限定-字段-name&gt;) |</p>
<p>最大值 (&lt;限定-字段-name&gt;) |</p>
<p>计数 (&lt;限定别名&gt; | &lt;限定名称&gt;) |</p>
<p>STDEV (&lt;限定-字段-name&gt;) |</p>
<p>任何 (&lt;限定-字段-name&gt;)</p></td>
</tr>
<tr class="even">
<td><p>&lt;计算 exp&gt;</p></td>
<td><p>CALC(&lt;expression&gt;)</p></td>
</tr>
<tr class="odd">
<td><p>&lt;限定字段名称&gt;</p></td>
<td><p>&lt;别名&gt;。[&lt;别名&gt;...]&lt;字段名称&gt;</p></td>
</tr>
<tr class="even">
<td><p>&lt;别名&gt;</p></td>
<td><p>&lt;带引号的名称&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;字段名称&gt;</p></td>
<td><p>&lt;用引号括起来-name&gt; [[AS]&lt;别名&gt;]</p></td>
</tr>
<tr class="even">
<td><p>&lt;带引号的名称&gt;</p></td>
<td><p>&quot;&lt;字符串&gt;&quot; |</p>
<p>&lt;字符串&gt;|</p>
<p>[&lt;字符串&gt;] |</p>
<p>&lt;名称&gt;</p></td>
</tr>
<tr class="odd">
<td><p>&lt;限定名称&gt;</p></td>
<td><p>别名 [.alias...]</p></td>
</tr>
<tr class="even">
<td><p>&lt;名称&gt;</p></td>
<td><p>alpha [alpha | 数字 | _ | # |: |...]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;号码&gt;</p></td>
<td><p>位数 [...数字]</p></td>
</tr>
<tr class="even">
<td><p>&lt;新 exp&gt;</p></td>
<td><p>新&lt;字段类型&gt;[(&lt;号码&gt;[，&lt;号码&gt;])]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;字段类型&gt;</p></td>
<td><p>OLE DB 或 ADO 数据类型。</p></td>
</tr>
<tr class="even">
<td><p>&lt;字符串&gt;</p></td>
<td><p>unicode 字符 [unicode char。..]</p></td>
</tr>
<tr class="odd">
<td><p>&lt;表达式&gt;</p></td>
<td><p>Visual Basic for Applications 表达式，其操作数是在相同行中的其他非 CALC 列。</p></td>
</tr>
</tbody>
</table>

