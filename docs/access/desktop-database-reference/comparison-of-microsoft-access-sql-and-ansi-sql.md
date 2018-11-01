---
title: Microsoft Access SQL 和 ANSI SQL 的比较
TOCTitle: Comparison of Microsoft Access SQL and ANSI SQL
ms:assetid: 0686f98f-10fe-0e02-e9d1-84ff3e755b57
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844937(v=office.15)
ms:contentKeyID: 48543052
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1d941e93fba9e5152bb2f1c973245fa9a7647dab
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25874403"
---
# <a name="comparison-of-microsoft-access-sql-and-ansi-sql"></a>Microsoft Access SQL 和 ANSI SQL 的比较


**适用于**： Access 2013、 Office 2013

Microsoft Access 数据库引擎 SQL 通常与 ANSI-89 Level 1 兼容。但某些 ANSI SQL 功能无法在 Microsoft® Access SQL 中实现，而 Microsoft Access SQL 则包含 ANSI SQL 不支持的一些保留字和功能。

## <a name="major-differences"></a>主要区别

  - Microsoft Access SQL 和 ANSI SQL 各自拥有不同的保留字和数据类型。有关详细信息，请参阅 [Microsoft Access 数据库引擎 SQL 保留字](sql-reserved-words.md)和[等价的 ANSI SQL 数据类型](equivalent-ansi-sql-data-types.md)。使用 Microsoft Access 数据库引擎 OLE DB 提供程序时，还提供其他保留字。

  - **[Between...And](https://msdn.microsoft.com/library/ff192436\(v=office.15\))**
    
    *expr1*\[不\]**之间** *value1* **和** *value2*
    
    在 Microsoft Access SQL 中，*value1* 可以大于 *value2*；在 ANSI SQL 中，*value1* 必须小于或等于 *value2*。

  - Microsoft Access SQL 既支持 ANSI SQL 通配符，也支持特定于 Microsoft Access 数据库引擎的[通配符](using-wildcard-characters-in-string-comparisons.md)以便与 **[Like](https://msdn.microsoft.com/library/ff195752\(v=office.15\))** 运算符配合使用。ANSI 和 Microsoft Access 数据库引擎通配符的使用是相互排斥的。必须使用其中一种而不能混合使用。ANSI SQL 通配符仅在使用 Microsoft Access 数据库引擎和 Microsoft Access 数据库引擎 OLE DB 提供程序时可用。如果试图通过 Microsoft Access 或者 DAO 来使用 ANSI SQL 通配符，则这些通配符将被解释为文本。相反，使用 Microsoft Access 数据库引擎 OLE DB 提供程序才能使用 ANSI SQL 通配符。
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>匹配字符</p></th>
    <th><p>Microsoft Access SQL</p></th>
    <th><p>ANSI SQL</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>任意单个字符</p></td>
    <td><p>?</p></td>
    <td><p>_（下划线）</p></td>
    </tr>
    <tr class="even">
    <td><p>零个或多个字符</p></td>
    <td><p>*</p></td>
    <td><p>%</p></td>
    </tr>
    </tbody>
    </table>


  - Microsoft Access SQL 通常限制性很少。例如，它允许对表达式进行分组和排序。

  - Microsoft Access SQL 支持更加强大的表达式。

## <a name="enhanced-features-of-microsoft-access-sql"></a>Microsoft Access SQL 的增强功能

Microsoft Access SQL 提供了以下增强功能：

  - [TRANSFORM](transform-statement-microsoft-access-sql.md) 语句，它支持交叉表查询。

  - 其他[聚合函数](sql-aggregate-functions-sql.md)，例如 **StDev** 和 **VarP** 。

  - [PARAMETERS](parameters-declaration-microsoft-access-sql.md) 声明，用于定义参数查询。

## <a name="ansi-sql-features-not-supported-in-microsoft-access-sql"></a>Microsoft Access SQL 不支持的 ANSI SQL 功能

Microsoft Access SQL 不支持以下 ANSI SQL 功能：

  - DISTINCT 聚合函数引用。例如，Microsoft Access SQL 不允许 SUM(DISTINCT *columnname*)。

  - 限制为*nn*行子句用于限制的查询所返回的行数。 只能使用 [WHERE 子句](https://msdn.microsoft.com/library/ff195245\(v=office.15\))来限制查询的范围。

