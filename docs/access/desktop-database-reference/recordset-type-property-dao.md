---
title: Recordset.Type Property (DAO)
TOCTitle: Type Property
ms:assetid: d841b088-50bf-16d9-33e0-2140050e1ac6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835080(v=office.15)
ms:contentKeyID: 48548030
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f56af1af04ea2cbd603a2f4a0c71bc8e67e5be51
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465508"
---
# <a name="recordsettype-property-dao"></a>Recordset.Type Property (DAO)


**适用于**： Access 2013 |Office 2013

设置或返回一个值，该值指示对象的操作类型或数据类型。只读 **Integer**。

## <a name="syntax"></a>语法

*表达式*。类型

*表达式*一个表示**Recordset**对象的变量。

## <a name="remarks"></a>注解

对于 **Recordset** 对象，可能的设置和返回值如下。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>记录集类型</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbOpenTable</strong></p></td>
<td><p>表（仅适用于 Microsoft Access 工作区）</p></td>
</tr>
<tr class="even">
<td><p><strong>dbOpenDynamic</strong></p></td>
<td><p>动态（仅适用于 ODBCDirect 工作区）</p>

> [!NOTE]
> <P>Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</P>


<p></p></td>
</tr>
<tr class="odd">
<td><p><strong>dbOpenDynaset</strong></p></td>
<td><p>动态集</p></td>
</tr>
<tr class="even">
<td><p><strong>dbOpenSnapshot</strong></p></td>
<td><p>快照</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbOpenForwardOnly</strong></p></td>
<td><p>仅向前</p></td>
</tr>
</tbody>
</table>

