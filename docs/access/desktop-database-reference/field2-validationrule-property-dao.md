---
title: Field2.ValidationRule 属性 (DAO)
TOCTitle: ValidationRule Property
ms:assetid: 5464d2de-f3d7-5d6b-4fc5-66df6a5540cb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194105(v=office.15)
ms:contentKeyID: 48544896
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cf640597405205987040d95033b2eb1ceee13867
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922711"
---
# <a name="field2validationrule-property-dao"></a>Field2.ValidationRule 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回一个值，当字段中的数据发生更改或被添加到表中时，该值将会验证该数据（仅适用于 Microsoft Access 工作区）。可读写 **String**。

## <a name="syntax"></a>语法

*表达式*。ValidationRule

*表达式*一个返回**Field2**对象的表达式。

## <a name="remarks"></a>注解

设置或返回值是一个 String，用于描述以不含 WHERE 保留字的 SQL WHERE 子句形式进行的比较。对于尚未追加到 **[Fields](fields-collection-dao.md)** 集合中的对象，该属性是可读写的。

**ValidationRule** 属性确定字段是否包含有效数据。如果数据无效，则会发生可捕获的运行时错误。返回的错误消息是 **ValidationText** 属性的文本，或者是 **ValidationRule** 指定的表达式的文本（如果已指定）。

对于 **Field2** 对象， **ValidationRule** 属性的用法取决于包含 **Field2** 对象所追加到的 **Fields** 集合的对象。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>对象追加到</p></th>
<th><p>用法</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Index</strong></p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p><strong>QueryDef</strong></p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recordset</strong></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation</strong></p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableDef</strong></p></td>
<td><p>可读写</p></td>
</tr>
</tbody>
</table>


只对使用 Microsoft Access 数据库引擎的数据库支持验证。

**Field2** 对象的 **ValidationRule** 属性所指定的字符串表达式只能引用该 **Field2**。该表达式不能引用用户定义的函数、SQL 聚合函数或查询。若要在 **Field2** 对象的 **ValidateOnSet** 属性设置为 **True** 时设置其 **ValidationRule** 属性，表达式必须成功分析（将字段名称作为隐含的操作数）且计算结果为 **True**。如果其 **ValidateOnSet** 属性设置为 **False**，则忽略 **ValidationRule** 属性设置。


> [!NOTE]
> <P>如果属性设置为非整数值时，连接字符串和系统参数指定非美国十进制字符，例如逗号分隔 (例如，strRule ="价格&gt;" &amp; lngPrice，和 lngPrice = 125,50)，将导致错误时您的代码，尝试进行验证的任何数据。 这是因为在连接过程中，将使用系统的默认小数字符，将数字转换为字符串，并且 Microsoft Access 数据库引擎 SQL 只接受美国格式小数字符。</P>


