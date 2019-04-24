---
title: Recordset2 属性 (DAO)
TOCTitle: Filter Property
ms:assetid: 5b3b4e18-8af4-5acd-a129-513ba2d913d1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194529(v=office.15)
ms:contentKeyID: 48545069
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053062
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 19f3c017aa5d4a353f3e832a3678d921565ea822
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307327"
---
# <a name="recordset2filter-property-dao"></a>Recordset2 属性 (DAO)


**适用于**：Access 2013、Office 2013

设置或返回一个值，该值确定在随后打开的 **Recordset** 对象中包括的记录（仅适用于 Microsoft Access 工作区）。 可读写 **String**。

## <a name="syntax"></a>语法

*表达式*。筛选器

*表达式*一个返回**Recordset2**对象的表达式。

## <a name="remarks"></a>注解

设置或返回值是一个 String 数据类型，它包含不带保留字 WHERE 的 SQL 语句的 WHERE 子句。

使用**filter**属性将筛选器应用于动态集类型、快照类型或仅向前类型的**Recordset**对象。

可以使用 **Filter** 属性限制当基于现有 **Recordset** 对象打开新的 **Recordset** 对象时从现有对象返回的记录。

在筛选包含日期的字段时使用美国日期格式 (月-年), 即使您没有使用美国版本的 Microsoft Access 数据库引擎 (在这种情况下, 您必须通过串联字符串来组合任何日期, 例如, strMonth & "-")。aMP_ strDay & "-" & strYear)。 否则，日期数据可能不按您期望的方式进行筛选。

在许多情况下，使用包含 WHERE 子句的 SQL 语句打开新的 **Recordset** 对象会快一些。

如果将该属性设置为与非整数值串联在一起的字符串, 并且系统参数指定的非美国十进制字符 (如逗号) (例如, strFilter = "PRICE \> " & lngPrice 和 lngPrice = 125, 50), 则当您尝试打开下一个**Recordset**。 这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。

