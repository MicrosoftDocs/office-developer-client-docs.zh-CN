---
title: QueryDef.Type Property (DAO)
TOCTitle: Type Property
ms:assetid: 03db891d-b958-7cf9-56c1-524d9ff2b9b5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844814(v=office.15)
ms:contentKeyID: 48542993
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5129f4a50f056259c5b556c8e8ea408358718d3c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466814"
---
# <a name="querydeftype-property-dao"></a>QueryDef.Type Property (DAO)


**适用于**： Access 2013 |Office 2013

设置或返回一个值，该值指示对象的操作类型或数据类型。只读 **Integer**。

## <a name="syntax"></a>语法

*表达式*。类型

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

对于 **QueryDef** 对象，可能的设置和返回值如下表所示。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>查询类型</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbQAction</strong></p></td>
<td><p>操作</p></td>
</tr>
<tr class="even">
<td><p><strong>dbQAppend</strong></p></td>
<td><p>追加</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbQCompound</strong></p></td>
<td><p>复合</p></td>
</tr>
<tr class="even">
<td><p><strong>dbQCrosstab</strong></p></td>
<td><p>交叉表</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbQDDL</strong></p></td>
<td><p>数据定义</p></td>
</tr>
<tr class="even">
<td><p><strong>dbQDelete</strong></p></td>
<td><p>Delete</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbQMakeTable</strong></p></td>
<td><p>生成表查询</p></td>
</tr>
<tr class="even">
<td><p><strong>dbQProcedure</strong></p></td>
<td><p>过程（仅适用于 ODBCDirect 工作区）</p>

> [!NOTE]
> <P>Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</P>


<p></p></td>
</tr>
<tr class="odd">
<td><p><strong>dbQSelect</strong></p></td>
<td><p>选择</p></td>
</tr>
<tr class="even">
<td><p><strong>dbQSetOperation</strong></p></td>
<td><p>联合</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbQSPTBulk</strong></p></td>
<td><p>与 <strong>dbQSQLPassThrough</strong> 一起用于指定不返回记录的查询（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbQSQLPassThrough</strong></p></td>
<td><p>传递（仅适用于 Microsoft Access 工作区）</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbQUpdate</strong></p></td>
<td><p>Update</p></td>
</tr>
</tbody>
</table>


将新的 **[Field](field-object-dao.md)** 、 **[Parameter](parameter-object-dao.md)** 或 **[Property](property-object-dao.md)** 对象追加到 **[Index](index-object-dao.md)** 、 **QueryDef**、 **[Recordset](recordset-object-dao.md)** 或 **[TableDef](tabledef-object-dao.md)** 对象集合中时，如果基础数据库不支持为新对象指定的数据类型，则会发生错误。

