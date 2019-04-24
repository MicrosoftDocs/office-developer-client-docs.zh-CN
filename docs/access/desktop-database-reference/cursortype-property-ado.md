---
title: CursorType 属性 (ADO)
TOCTitle: CursorType property (ADO)
ms:assetid: f42ded8f-9f92-ef03-a198-ffb892324611
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250239(v=office.15)
ms:contentKeyID: 48548682
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7cdb32bb8ff9bb6e0556a87de0efe82cd919dbe2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295182"
---
# <a name="cursortype-property-ado"></a>CursorType 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示在 [Recordset](recordset-object-ado.md) 对象中使用的游标类型。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回 [CursorTypeEnum](cursortypeenum.md) 值。 默认值为 **adOpenForwardOnly**。

## <a name="remarks"></a>注解

使用 **CursorType** 属性可以指定打开 **Recordset** 对象时应使用的游标类型。

如果 **CursorLocation** 属性设置为 [adUseClient](cursorlocation-property-ado.md) ，则仅支持 **adOpenStatic** 设置。如果设置了不受支持的值，则不会导致出错；因此应改用最接近的受支持的 **CursorType** 。

如果提供程序不支持所请求的游标类型，它可能会返回另一个游标类型。打开 **Recordset** 对象时， [CursorType](recordset-object-ado.md) 属性将更改为与实际使用的游标类型相匹配的值。若要验证返回的游标的特定功能，请使用 [Supports](supports-method-ado.md) 方法。关闭 **Recordset** 后， **CursorType** 属性将恢复为其原始设置。

下面的图表显示了每种游标类型所需要的提供程序功能（由 **Supports** 方法常量进行标识）。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>对于使用此 CursorType 的 Recordset</p></th>
<th><p>Supports 方法必须为以下所有常量返回 True</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adOpenForwardOnly</strong></p></td>
<td><p>无</p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenKeyset</strong></p></td>
<td><p><strong>adBookmark</strong>、 <strong>adHoldRecords</strong>、<strong>带有 admoveprevious</strong>、 <strong>adResync</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>adOpenDynamic</strong></p></td>
<td><p><strong>带有 admoveprevious</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenStatic</strong></p></td>
<td><p><strong>adBookmark</strong>、 <strong>adHoldRecords</strong>、<strong>带有 admoveprevious</strong>、 <strong>adResync</strong></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 虽然 **Supports**(**adUpdateBatch**) 对于动态游标和只进游标为 true，但对于批更新，应使用键集游标或静态游标。请将 [LockType](locktype-property-ado.md) 属性设置为 **adLockBatchOptimistic**，并将 **CursorLocation** 属性设置为 **adUseClient**，以启用批更新所必需的 Cursor Service for OLE DB。

当 **Recordset** 关闭时， **CursorType** 属性为可读/写属性，而当其打开时为只读属性。

**远程数据服务使用情况**在客户端 Recordset 对象上使用时, **CursorType**属性只能设置为**adOpenStatic**。

