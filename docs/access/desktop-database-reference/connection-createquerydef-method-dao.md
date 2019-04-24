---
title: CreateQueryDef 方法 (DAO)
TOCTitle: CreateQueryDef Method
ms:assetid: 254fe81a-9b45-e8e7-108d-503c1c1c0fcc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191860(v=office.15)
ms:contentKeyID: 48543781
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053067
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: b6600d4508a33a31098d6a2e7c92f5904beb0e95
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295931"
---
# <a name="connectioncreatequerydef-method-dao"></a>CreateQueryDef 方法 (DAO)

**适用于**：Access 2013、Office 2013

创建新的 **[QueryDef](querydef-object-dao.md)** 对象。

## <a name="syntax"></a>语法

*表达式*。CreateQueryDef (***Name***, ***SQLText***)

*表达式*一个代表**Connection**对象的变量。

## <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>对新的 <strong>QueryDef</strong> 进行唯一命名的 <strong>Variant</strong>（<strong>String</strong> 子类型）。</p></td>
</tr>
<tr class="even">
<td><p><em>SQLText</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 <strong>Variant</strong>（<strong>String</strong> 子类型）类型的值，它是一个定义 <strong>QueryDef</strong> 的 SQL 语句。 如果省略此参数，则可以通过在将 <strong>QueryDef</strong> 追加到集合之前或之后设置它的 <strong><a href="querydef-sql-property-dao.md">SQL</a></strong> 属性对其进行定义。</p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

QueryDef

## <a name="remarks"></a>注解

在 Microsoft Access 工作区中，如果在创建 **QueryDef** 时为名称提供了除零长度字符串之外的信息，产生的 **QueryDef** 对象将自动追加到 **[QueryDefs](querydefs-collection-dao.md)** 集合。

如果 name 指定的对象已经是 **QueryDefs** 集合的成员，则会发生运行时错误。 可通过在执行 **CreateQueryDef** 方法时为 name 参数使用零长度字符串创建临时的 **QueryDef**。 您也可以通过将新创建的**QueryDef**的**[Name](connection-name-property-dao.md)** 属性设置为零长度字符串 ("") 来实现此目的。 如果您希望反复使用动态 SQL 语句，且不必在 **QueryDefs** 集合中创建任何新的永久对象，则使用临时的 **QueryDef** 对象十分有帮助。 不能将临时的 **QueryDef** 追加到任何集合，因为零长度字符串对永久的 **QueryDef** 对象来说是无效名称。 始终可以设置新建 **QueryDef** 的 **Name** 和 **SQL** 属性，然后将 **QueryDef** 追加到 **QueryDefs** 集合。

若要在 **QueryDef** 对象中运行 SQL 语句，请使用 **[Execute](connection-execute-method-dao.md)** 或 **[OpenRecordset](connection-openrecordset-method-dao.md)** 方法。

使用 **QueryDef** 对象是对 ODBC 数据库执行 SQL 传递查询的首选方法。

若要从 Microsoft Access 数据库引擎数据库中的 **QueryDefs** 集合中删除一个 **QueryDef** 对象，请对该集合使用 **[Delete](fields-delete-method-dao.md)** 方法。

