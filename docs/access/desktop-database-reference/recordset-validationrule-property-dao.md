---
title: Recordset 属性 (DAO)
TOCTitle: ValidationRule Property
ms:assetid: c9250c13-18fe-1ff7-7846-7872c49a1e3b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823208(v=office.15)
ms:contentKeyID: 48547671
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e73d81cd890930952835ca6529cc3bfb455e6c21
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307502"
---
# <a name="recordsetvalidationrule-property-dao"></a>Recordset 属性 (DAO)

**适用于**：Access 2013、Office 2013

设置或返回一个值，当字段中的数据更改或添加到表中时，该值对这些数据进行验证（仅适用于 Microsoft Access 工作区）。可读写 **String**。

## <a name="syntax"></a>语法

*表达式*。规则

*表达式*一个代表**Recordset**对象的变量。

## <a name="remarks"></a>注解

设置或返回值是一个 **String**，用于描述以不含 WHERE 保留字的 SQL WHERE 子句形式进行的比较。对于尚未追加到 **Fields** 集合中的对象，该属性是可读写的。

**ValidationRule** 属性确定字段是否包含有效数据。如果数据无效，则会发生可捕获的运行时错误。返回的错误消息是 **ValidationText** 属性的文本，或者是 **ValidationRule** 指定的表达式的文本（如果指定了该表达式）。

对于 **Recordset** 对象， **ValidationRule** 属性的用法是只读的。对于 **TableDef** 对象， **ValidationRule** 属性的用法取决于 **TableDef** 对象的状态，如下表所示。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>TableDef</p></th>
<th><p>用法</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>基表</p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p>链接表</p></td>
<td><p>只读</p></td>
</tr>
</tbody>
</table>


只对使用 Microsoft Access 数据库引擎的数据库支持验证。

**Field** 对象的 **ValidationRule** 属性所指定的字符串表达式只能引用该 **Field**。该表达式不能引用用户定义的函数、SQL 聚合函数或查询。若要在 **Field** 对象的 **ValidateOnSet** 属性设置为 **True** 时设置其 **ValidationRule** 属性，表达式必须成功分析（将字段名称作为隐含的操作数）且计算结果为 **True**。如果其 **ValidateOnSet** 属性设置为 **False**，则忽略 **ValidationRule** 属性设置。

**Recordset** 或 **TableDef** 对象的 **ValidationRule** 属性可以引用该对象中的多个字段。本主题前面所述的对 **Field** 对象的限制在此适用。

对于表类型的 **Recordset** 对象， **ValidationRule** 属性继承您用于创建该表类型 **Recordset** 对象的 **TableDef** 对象的 **ValidationRule** 属性设置。

> [!NOTE]
> 如果将该属性设置为与非整数值串联在一起的字符串, 并且系统参数指定的非美国十进制字符 (如逗号) (例如, strRule = "PRICE &gt; " &amp; lngPrice 和 lngPrice = 125, 50), 则会导致错误您的代码尝试验证任何数据。 这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。
