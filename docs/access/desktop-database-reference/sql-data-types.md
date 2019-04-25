---
title: SQL 数据类型（Access 桌面数据库参考）
TOCTitle: SQL data types
ms:assetid: 4fc2dc8c-7825-8fbb-ff91-a0f39ef90115
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193793(v=office.15)
ms:contentKeyID: 48544783
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277590
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: fb72a0090550692e7cf5028a6a58a078fc5d9d32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308579"
---
# <a name="sql-data-types"></a>SQL 数据类型

**适用于**：Access 2013、Office 2013

Microsoft Access 数据库引擎 SQL 数据类型包含由 Microsoft Jet 数据库引擎定义的 13 种主要数据类型，以及若干可识别为这些数据类型的有效同义词。

下表列出了主要的数据类型。 同义词是在 [Microsoft Access 数据库引擎 SQL 保留字](sql-reserved-words.md)中标识的。

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
<td><p>每个字符 1 个字节</p></td>
<td><p>任何类型的数据都可能存储在此类型的字段中。没有进行数据转换（如转换为文本）。数据在二进制字段中的输入方式决定其作为输出的显示方式。</p></td>
</tr>
<tr class="even">
<td><p>BIT</p></td>
<td><p>1 个字节</p></td>
<td><p>Yes 和 No 值，以及只包含这两值之一的字段。</p></td>
</tr>
<tr class="odd">
<td><p>TINYINT</p></td>
<td><p>1 个字节</p></td>
<td><p>0 和 255 之间的一个整数值。</p></td>
</tr>
<tr class="even">
<td><p>MONEY</p></td>
<td><p>8 个字节</p></td>
<td><p>在 – 922,337,203,685,477.5808 和 922,337,203,685,477.5807 之间的依比例调整整数。</p></td>
</tr>
<tr class="odd">
<td><p>DATETIME（请参阅 DOUBLE）</p></td>
<td><p>8 个字节</p></td>
<td><p>100 年和 9999 年之间的日期或时间值。</p></td>
</tr>
<tr class="even">
<td><p>UNIQUEIDENTIFIER</p></td>
<td><p>128 个字节</p></td>
<td><p>用于远程过程调用的唯一识别号。</p></td>
</tr>
<tr class="odd">
<td><p>REAL</p></td>
<td><p>4 个字节</p></td>
<td><p>单精度浮点值，可以是任何从 -3.402823E38 到 -1.401298E-45 的负数、从 1.401298E-45 到 3.402823E38 的正数，还可以是 0。</p></td>
</tr>
<tr class="even">
<td><p>FLOAT</p></td>
<td><p>8 个字节</p></td>
<td><p>双精度浮点值，可以是任何从 -1.79769313486232E308 到 -4.94065645841247E-324 的负数、从 4.94065645841247E-324 到 1.79769313486232E308 的正数，还可以是 0。</p></td>
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
<td><p>包含从 1028 - 1 直到 -1028 - 1 范围内的值的准确数字数据类型。可以定义精度 (1 - 28) 和小数位数（0 - 指定精度）。默认精度和小数位数分别为 18 和 0。</p></td>
</tr>
<tr class="even">
<td><p>TEXT</p></td>
<td><p>每个字符占 2 个字节（请参阅“注释”）</p></td>
<td><p>0 至 2.14 GB（至多）。</p></td>
</tr>
<tr class="odd">
<td><p>IMAGE</p></td>
<td><p>根据需要确定</p></td>
<td><p>0 至 2.14 GB（至多）。用于 OLE 对象。</p></td>
</tr>
<tr class="even">
<td><p>CHARACTER</p></td>
<td><p>每个字符占 2 个字节（请参阅“注释”）</p></td>
<td><p>0 至 255 个字符。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> - 种子和增量都能够通过 [ALTER TABLE 语句](alter-table-statement-microsoft-access-sql.md)进行修改。根据自动为列生成的新种子和增量值，插入表中的新行会具有值。如果新种子和增量产生的值与根据先前的种子和增量所产生的值相匹配，将产生重复值。如果该列是一个主键，那么生成重复值时插入新行就会产生错误。
> - 若要查找用于自动增量列的最后一个值，可以使用以下语句：SELECT @@IDENTITY。不能指定表名。返回的值来自更新的最后一个表（其中包含一个自动增加列）。
