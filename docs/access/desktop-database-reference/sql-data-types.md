---
title: SQL 数据类型 （访问桌面数据库参考 （英文）
TOCTitle: SQL Data Types
ms:assetid: 4fc2dc8c-7825-8fbb-ff91-a0f39ef90115
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193793(v=office.15)
ms:contentKeyID: 48544783
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277590
f1_categories:
- Office.Version=v15
ms.openlocfilehash: fd49861af896ae1c2d55a80665f119662c0baf53
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25880395"
---
# <a name="sql-data-types"></a>SQL 数据类型


**适用于**： Access 2013、 Office 2013

Microsoft Access 数据库引擎 SQL 数据类型包含由 Microsoft® Jet 数据库引擎定义的 13 种主要数据类型，以及若干可识别为这些数据类型的有效同义词。

下表列出了主要数据类型。同义词是在 [Microsoft Access 数据库引擎 SQL 保留字](sql-reserved-words.md)中标识的。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>数据类型</p></th>
<th><p>存储空间大小</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BINARY</p></td>
<td><p>每个字符占 1 个字节</p></td>
<td><p>任何类型的数据都可以存储在这种类型的字段中。不进行数据转换（例如，转换成文本）。数据怎样输入到二进制字段就怎样作为输出显示，</p></td>
</tr>
<tr class="even">
<td><p>BIT</p></td>
<td><p>1 个字节</p></td>
<td><p>值为 Yes 和 No，并且该字段只能取这两个值中的一个。</p></td>
</tr>
<tr class="odd">
<td><p>TINYINT</p></td>
<td><p>1 个字节</p></td>
<td><p>在 0 和 255 之间的整数值。</p></td>
</tr>
<tr class="even">
<td><p>MONEY</p></td>
<td><p>8 个字节</p></td>
<td><p>在 – 922,337,203,685,477.5808 和 922,337,203,685,477.5807 之间的依比例调整整数。</p></td>
</tr>
<tr class="odd">
<td><p>DATETIME （请参阅 DOUBLE）</p></td>
<td><p>8 个字节</p></td>
<td><p>在 100 年和 9999 年之间的日期或时间值。</p></td>
</tr>
<tr class="even">
<td><p>UNIQUEIDENTIFIER</p></td>
<td><p>128 个字节</p></td>
<td><p>用于远程过程调用的唯一标识数字。</p></td>
</tr>
<tr class="odd">
<td><p>REAL</p></td>
<td><p>4 个字节</p></td>
<td><p>单精度浮点值，负数值从 – 3.402823E38 到 – 1.401298E-45，正数值从 1.401298E-45 到 3.402823E38，包括零。</p></td>
</tr>
<tr class="even">
<td><p>FLOAT</p></td>
<td><p>8 个字节</p></td>
<td><p>双精度浮点值，负数值从 – 1.79769313486232E308 到 – 4.94065645841247E-324，正数值从 4.94065645841247E-324 到 1.79769313486232E308，包括零。</p></td>
</tr>
<tr class="odd">
<td><p>SMALLINT</p></td>
<td><p>2 个字节</p></td>
<td><p>介于 – 32,768 和 32,767 之间的短整型。（请参阅“注释”）</p></td>
</tr>
<tr class="even">
<td><p>INTEGER</p></td>
<td><p>4 个字节</p></td>
<td><p>介于 – 2,147,483,648 和 2,147,483,647 之间的长整型。（请参阅“注释”）</p></td>
</tr>
<tr class="odd">
<td><p>DECIMAL</p></td>
<td><p>17 个字节</p></td>
<td><p>精确的数字数据类型，取值范围从 1028 - 1 到 - 1028 - 1. 可以定义精度 (1 - 28) 和大小（0 -- 定义精度）。默认的精度和大小分别为 18 和 0。</p></td>
</tr>
<tr class="even">
<td><p>TEXT</p></td>
<td><p>每个字符占 2 个字节（请参阅“注释”）</p></td>
<td><p>从零到最大值 2.14 吉字节。</p></td>
</tr>
<tr class="odd">
<td><p>IMAGE</p></td>
<td><p>根据需要</p></td>
<td><p>从零到最大值 2.14 吉字节。用于 OLE 对象。</p></td>
</tr>
<tr class="even">
<td><p>CHARACTER</p></td>
<td><p>每个字符占 2 个字节（请参阅“注释”）</p></td>
<td><p>从零到 255 个字符。</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <UL>
> <LI>
> <P>种子和增量都能够通过 <A href="alter-table-statement-microsoft-access-sql.md">ALTER TABLE 语句</A>进行修改。根据自动为列生成的新种子和增量值，插入表中的新行会具有值。如果新种子和增量产生的值与根据先前的种子和增量所产生的值相匹配，将产生重复值。如果该列是一个主键，那么生成重复值时插入新行就会产生错误。</P>
> <LI>
> <P>若要查找用于自动增量列的最后一个值，可以使用以下语句：SELECT @@IDENTITY。不能指定表名。返回的值来自更新的最后一个表（其中包含一个自动增加列）。</P></LI></UL>


