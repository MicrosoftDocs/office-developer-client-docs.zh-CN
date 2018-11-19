---
title: 在字符串比较中使用通配符
TOCTitle: Using wildcard characters in string comparisons
ms:assetid: 37dda2b8-c710-4f73-bb2a-76a1348c42fe
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192499(v=office.15)
ms:contentKeyID: 48544205
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9fb6c63d5d2db1db54d52a03fef41e44a29f42c9
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026161"
---
# <a name="using-wildcard-characters-in-string-comparisons"></a>在字符串比较中使用通配符

**适用于**： Access 2013、 Office 2013

内置的模式匹配方法提供了一个用于字符串比较的通用工具。下表中展示了可以用于 **Like** 运算符的通配符，以及与它们匹配的数字和字符串。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Pattern<em>中</em>的字符</p></th>
<th><p><em>expression</em> 中的匹配项</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>? 或  _（下划线）</p></td>
<td><p>任意单个字符</p></td>
</tr>
<tr class="even">
<td><p>*或 %</p></td>
<td><p>零个或多个字符</p></td>
</tr>
<tr class="odd">
<td><p>#</p></td>
<td><p>任何单个数字 (0 - 9)</p></td>
</tr>
<tr class="even">
<td><p>[<em>charlist</em>]</p></td>
<td><p><em>charlist</em> 中的任何单个字符</p></td>
</tr>
<tr class="odd">
<td><p>[!<em>charlist</em>]</p></td>
<td><p>不在 <em>charlist</em> 中的任何单个字符</p></td>
</tr>
</tbody>
</table>


您可以使用一组一个或多个字符 (*charlist*) 括在方括号 (\[ \]) 以匹配*表达式*和*charlist*中的任意单个字符可以包括几乎任何中字符的 ANSI 字符集字符设置，包括数字。 您可以使用特殊字符打开括号 (\[ )、 问号 (?)、 数字记号 (\#)，和星号 (\*) 自身进行匹配直接才括在方括号内。 不能使用右括号 ( \]) 在某个组将匹配本身，但您可以使用它在组外作为单个字符。

括在方括号中的字符的简单列表，除了*charlist*可以通过使用连字符 （-） 分隔上限和下限范围的指定范围的字符。 例如，使用\[A-Z\] *模式*如果*表达式*中的相应字符位置包含任何范围 A 到 Z 中大写字母匹配的结果中。没有分隔的范围可以包含在方括号中的多个区域。 例如， \[a-zA-Z0-9\]匹配任何字母数字字符。

请注意，务必 ANSI SQL 通配符 （%） 和 (\_) 才可用与 Microsoft jet 4.X 和 Microsoft OLE DB Provider for Jet。 如果用于 Microsoft Access 或 DAO，则被视为文本。

用于模式匹配的其他重要规则如下所示：

- 感叹号 (\!) *charlist*意味着除了*charlist 外*的那些*表达式*中发现的任何字符进行匹配的开头。 感叹号用在方括号外面时，将与自身匹配。

- 您可以使用连字符 （-） 开头 （感叹号之后如果使用了） 或末尾的*字符列表*匹配本身。 如果用于任何其他位置，则标识 ANSI 字符的范围。

- 指定一系列字符时，这些字符必须以升序排序次序显示（A-Z 或 0-100）。 \[A 到 Z\]是有效的模式，但\[Z 到 A\]不是。

- 字符序列\[\]将被忽略;它被视为一个零长度字符串 ("")。

