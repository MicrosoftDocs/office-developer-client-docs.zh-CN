---
title: ADCPROP_AUTORECALC_ENUM
TOCTitle: ADCPROP_AUTORECALC_ENUM
ms:assetid: 79ed16c1-964d-bf88-22c9-aa0a51303da6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249502(v=office.15)
ms:contentKeyID: 48545779
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e385df5029238106b51aa62949d5e4e94f065657
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280520"
---
# <a name="adcpropautorecalcenum"></a>ADCPROP\_AUTORECALC\_枚举

**适用于**：Access 2013、Office 2013

指定 [MSDataShape](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供程序何时重新计算分层记录集中的聚合和计算列。

这些常量仅用于**MSDataShape**提供程序和**Recordset** "**自动**重新计算" 动态属性, 该动态属性在[ADO 动态属性索引](ado-dynamic-property-index.md)中引用, 并在[Microsoft Cursor Service for OLE 中进行了记录。](microsoft-cursor-service-for-ole-db-ado-service-component.md) [OLE db 文档的 DB 或 Microsoft 数据定形服务](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)。

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adRecalcAlways</strong></p></td>
<td><p>1</p></td>
<td><p>默认值。每当 <strong>MSDataShape</strong> 提供程序确定计算列所依赖的值已发生更改时，都会重新计算该值。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecalcUpFront</strong></p></td>
<td><p>0</p></td>
<td><p>只在最初构建分层 <strong>Recordset</strong> 时计算。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

这些常量没有 ADO/WFC 等效值。

