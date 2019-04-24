---
title: 在字符串比较中使用通配符
TOCTitle: Using wildcard characters in string comparisons
ms:assetid: 37dda2b8-c710-4f73-bb2a-76a1348c42fe
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192499(v=office.15)
ms:contentKeyID: 48544205
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e6a013865b9615701b1d99678fc2392e0a896c54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32305934"
---
# <a name="using-wildcard-characters-in-string-comparisons"></a>在字符串比较中使用通配符

**适用于**：Access 2013、Office 2013

内置的模式匹配方法提供了一个用于字符串比较的通用工具。下表中展示了可以用于 **Like** 运算符的通配符，以及与它们匹配的数字和字符串。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><em>pattern</em> 中的字符</p></th>
<th><p><em>expression</em> 中的匹配项</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>? 或  _（下划线）</p></td>
<td><p>任意单个字符</p></td>
</tr>
<tr class="even">
<td><p>*和</p></td>
<td><p>零个或多个字符</p></td>
</tr>
<tr class="odd">
<td><p>#</p></td>
<td><p>任何单个数字 (0 - 9)</p></td>
</tr>
<tr class="even">
<td><p>[<em>charlist</em>]</p></td>
<td><p>在 <em>charlist</em> 中的任何单个字符。</p></td>
</tr>
<tr class="odd">
<td><p>[!<em>charlist</em>]</p></td>
<td><p>不在 <em>charlist</em> 中的任何单个字符。</p></td>
</tr>
</tbody>
</table>


可以使用括在方括号 (\[ \]) 中的一个或多个字符 (*charlist*) 组成的组, 以匹配表达式中的任何单个字符 *,* 并且*charlist*可以包含 ANSI 字符集中的几乎所有字符, 包括进制. 您可以使用左括号 (\[ )、问号 (?)、数字符号 (\#) 和星号 (\*) 等特殊字符仅当括在方括号中时才直接与自身匹配。 不能在组中使用右\]括号 () 来匹配自身, 但可以将其作为单个字符用于组之外。

除了括在方括号中的简单字符列表之外, *charlist*可以通过使用连字符 (-) 分隔范围的上限和下限来指定字符的范围。 例如, 如果*表达式*中的对应\]字符位置包含从 A 到 Z 范围内的任何大写字母, 则在*模式*中使用\[a-z 将导致匹配。可以在括号中包含多个区域, 而无需界定区域。 例如, \[Z0-9\]匹配任何字母数字字符。

需要注意的重要一点是, ANSI SQL 通配符 (%)和 (\_) 仅适用于 microsoft jet 版本 4. X 和 microsoft OLE DB Provider for Jet。 如果用于 Microsoft Access 或 DAO，则被视为文本。

用于模式匹配的其他重要规则如下所示：

- *charlist*开头的感叹号\!() 表示在*expression*中发现除*charlist*中的字符之外的任何字符时进行匹配。 感叹号用在方括号外面时，将与自身匹配。

- 可以将连字符 (-) 用于 *charlist* 的开头（如果用了感叹号，则放在感叹号之后）或末尾以便与其自身匹配。如果用于任何其他位置，则标识 ANSI 字符的范围。

- 指定一系列字符时，这些字符必须以升序排序次序显示（A-Z 或 0-100）。 \[a-z\]是有效的模式, 但\[Z-a\]不是。

- 忽略该字符\[ \]序列;它被视为零长度字符串 ("")。

