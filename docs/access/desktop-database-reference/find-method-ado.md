---
title: 查找方法-ActiveX 数据对象 (ADO)
TOCTitle: Find method (ADO)
ms:assetid: a7cc9ceb-fdb9-73e2-8328-70b174f93cda
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249776(v=office.15)
ms:contentKeyID: 48546887
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 32f14e4aeed669e68d976559932306c3cb76c696
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292410"
---
# <a name="find-method-ado"></a>Find 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于在 [Recordset](recordset-object-ado.md) 中搜索满足指定条件的行。可以选择性地指定搜索方向、起始行和与起始行的偏移量。如果满足条件，当前行位置将设置为找到的记录位置；否则，该位置设置为 **Recordset** 的末尾（或开头）。

## <a name="syntax"></a>语法

Find (*Criteria*、 *SkipRows*、 *SearchDirection*、 *Start*)

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Criteria* |**字符串型** 值，包含用于指定在搜索中使用的列名、比较运算符和值的语句。|
|*SkipRows* |可选。 **长整型**值，默认值为零，用于指定与当前行的行偏移量或*开始*书签，以开始搜索。 默认情况下，搜索将从当前行开始。|
|*SearchDirection* |可选。 [SearchDirectionEnum](searchdirectionenum.md) 值，指定搜索应从当前行开始还是从搜索方向上的下一个可用行开始。 如果该值为 **adSearchForward** ，则不成功的搜索在 **Recordset** 的末尾停止。 如果该值为 **adSearchBackward** ，则不成功的搜索在 **Recordset** 的开头停止。|
|*Start* |可选。 **变量型** 书签，充当搜索的开始位置。|

## <a name="remarks"></a>注解

*Criteria* 中只能指定一个列名称。该方法不支持多列搜索。

*Criteria*中的比较运算符可以是 "**\>**" (大于)、**\<**\>"(小于)、" = "(等于)、" = "(大于或等于)、"\<= "(小于或等于)、" = "(小于或\<\>等于)、" "(不等于) 或" like "(模式匹配)。

*Criteria* 中的值可以是字符串、浮点数或日期。 字符串值用单引号或 "\#" (数字符号) 标记分隔 (例如, "state = ' WA '" 或 "state = \#WA\#")。 日期值用\#"" (数字符号) 标记 (例如, "开始\_日期\> \#7/22/97\#") 来分隔, 并且可以包含小时数、分钟数和秒数以指示时间戳, 但不应包含毫秒或错误将发生.

如果比较运算符是"like"，则字符串值中可以包含星号 (\*)，以查找一次或多次出现的任何字符或子字符串。例如，"state like 'M\*'"与 Maine 和 Massachusetts 相匹配。还可以使用前导和尾随星号来查找包含在值中的子字符串。例如，"state like '\*as\*'"与 Alaska、Arkansas 和 Massachusetts 相匹配。

星号只能在条件字符串的末尾使用，或者同时在条件字符串的开头和末尾使用，如上所述。不能将星号用作前导通配符 ("\*str") 或嵌入式通配符 ("s\*r")。否则将导致错误。

> [!NOTE]
> [!注释] 如果当前行位置不是在调用 **Find** 之前设置的，将发生错误。设置行位置的任何方法（如 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)）都应该在调用 **Find** 之前调用。

> [!NOTE]
> [!注释] 如果对记录集调用 **Find** 方法，且记录集中的当前位置位于最后一个记录或文件末尾 (EOF)，您将找不到任何内容。您需要调用 **MoveFirst** 方法将当前位置/游标设置在记录集的开头。


