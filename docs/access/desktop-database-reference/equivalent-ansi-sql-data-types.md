---
title: 等效的 ANSI SQL 数据类型
TOCTitle: Equivalent ANSI SQL data types
ms:assetid: 720abf59-f9ef-4e14-4223-c873f604ad58
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195814(v=office.15)
ms:contentKeyID: 48545599
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277587
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 3ea0641c7325bfcb4339572bc8b50724115af8d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293509"
---
# <a name="equivalent-ansi-sql-data-types"></a>等效的 ANSI SQL 数据类型


**适用于**：Access 2013、Office 2013

下表列出了 ANSI SQL 数据类型、它们的等效 Microsoft Access 数据库引擎 SQL 数据类型以及它们的有效同义词。 表中还列出了等效的 Microsoft SQL Server™ 数据类型。

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>ANSI SQL 数据类型</p></th>
<th><p>Microsoft Access SQL 数据类型</p></th>
<th><p>同义词</p></th>
<th><p>Microsoft SQL Server 数据类型</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BIT 和 BIT VARYING</p></td>
<td><p>BINARY（请参阅“注释”）</p></td>
<td><p>VARBINARY、BINARY VARYING 和 BIT VARYING</p></td>
<td><p>BINARY 和 VARBINARY</p></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>BIT（请参阅“注释”）</p></td>
<td><p>BOOLEAN、LOGICAL、LOGICAL1 和 YESNO</p></td>
<td><p>BIT</p></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>TINYINT</p></td>
<td><p>INTEGER1 和 BYTE</p></td>
<td><p>TINYINT</p></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>COUNTER（请参阅“注释”）</p></td>
<td><p>AUTOINCREMENT</p></td>
<td><p>（参见注释）</p></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>MONEY</p></td>
<td><p>CURRENCY</p></td>
<td><p>MONEY</p></td>
</tr>
<tr class="even">
<td><p>DATE、TIME 和 TIMESTAMP</p></td>
<td><p>DATETIME</p></td>
<td><p>DATE 和 TIME（请参阅“注释”）</p></td>
<td><p>DATETIME</p></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>UNIQUEIDENTIFIER</p></td>
<td><p>GUID</p></td>
<td><p>UNIQUEIDENTIFIER</p></td>
</tr>
<tr class="even">
<td><p>DECIMAL</p></td>
<td><p>DECIMAL</p></td>
<td><p>NUMERIC 和 DEC</p></td>
<td><p>DECIMAL</p></td>
</tr>
<tr class="odd">
<td><p>REAL</p></td>
<td><p>REAL</p></td>
<td><p>SINGLE、FLOAT4 和 IEEESINGLE</p></td>
<td><p>REAL</p></td>
</tr>
<tr class="even">
<td><p>DOUBLE PRECISION 和 FLOAT</p></td>
<td><p>FLOAT</p></td>
<td><p>DOUBLE、FLOAT8、IEEEDOUBLE 和 NUMBER（请参阅“注释”）</p></td>
<td><p>FLOAT</p></td>
</tr>
<tr class="odd">
<td><p>SMALLINT</p></td>
<td><p>SMALLINT</p></td>
<td><p>SHORT 和 INTEGER2</p></td>
<td><p>SMALLINT</p></td>
</tr>
<tr class="even">
<td><p>INTEGER</p></td>
<td><p>INTEGER</p></td>
<td><p>LONG、INT 和 INTEGER4</p></td>
<td><p>INTEGER</p></td>
</tr>
<tr class="odd">
<td><p>INTERVAL</p></td>
<td><p>不支持</p></td>
<td><p></p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>IMAGE</p></td>
<td><p>LONGBINARY、GENERAL 和 OLEOBJECT</p></td>
<td><p>IMAGE</p></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>TEXT（请参阅“注释”）</p></td>
<td><p>LONGTEXT、LONGCHAR、MEMO、NOTE 和 NTEXT（请参阅“注释”）</p></td>
<td><p>TEXT</p></td>
</tr>
<tr class="even">
<td><p>CHARACTER、CHARACTER VARYING、NATIONAL CHARACTER 和 NATIONAL CHARACTER VARYING</p></td>
<td><p>CHAR（请参阅“注释”）</p></td>
<td><p>TEXT(n)、ALPHANUMERIC、CHARACTER、STRING、VARCHAR、CHARACTER VARYING、NCHAR、NATIONAL CHARACTER、NATIONAL CHAR、NATIONAL CHARACTER VARYING 和 NATIONAL CHAR VARYING（请参阅“注释”）</p></td>
<td><p>CHAR、VARCHAR、NCHAR 和 NVARCHAR</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> - ANSI SQL BIT 数据类型不对应于 Microsoft Access SQL BIT 数据类型。但它对应于 BINARY 数据类型。不存在等价于 Microsoft Access SQL BIT 数据类型的 ANSI SQL 数据类型。
> - 不再支持 TIMESTAMP 作为 DATETIME 的同义词。
> - 不再支持 NUMERIC 作为 FLOAT 或 DOUBLE 的同义词。现在，NUMERIC 可作为 DECIMAL 的同义词使用。
> - LONGTEXT 字段总是存储为 Unicode 表示格式。
> - 如果使用数据类型名称 TEXT，但未指定可选长度，例如 TEXT(25)，将创建一个 LONGTEXT 字段。这样使要编写的 [CREATE TABLE 语句](create-table-statement-microsoft-access-sql.md)生成的数据类型与 Microsoft SQL Server 一致。
> - CHAR 字段总是存储为 Unicode 表示格式，它等价于 ANSI SQL NATIONAL CHAR 数据类型。
> - 如果使用数据类型名称 TEXT，但未指定可选长度，例如 TEXT(25)，那么该字段的数据类型等价于 CHAR 数据类型。这样，可保持大多数 Microsoft Jet 应用程序的后向兼容性，同时使 TEXT 数据类型（没有长度限制）符合 Microsoft SQL Server 规范。


