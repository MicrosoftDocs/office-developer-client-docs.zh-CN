---
title: ADCPROP_UPDATECRITERIA_ENUM
TOCTitle: ADCPROP_UPDATECRITERIA_ENUM
ms:assetid: 70da63fa-fa75-9bb4-683d-0fcb4c4a2934
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249450(v=office.15)
ms:contentKeyID: 48545571
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8be93b0b7e4b32e3c040e871ff7d97a95f1e247e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282850"
---
# <a name="adcpropupdatecriteriaenum"></a>ADCPROP\_UPDATECRITERIA\_枚举

**适用于**：Access 2013、Office 2013

指定在使用 [Recordset](recordset-object-ado.md) 对象来对数据源中的行进行开放式更新期间可以用哪些字段来检测冲突。

这些常量用于 **Recordset** 的“**Update Criteria**”动态属性，该动态属性在 [ADO 动态属性索引](ado-dynamic-property-index.md)中被引用，并在 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 文档中进行了介绍。

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
<td><p><strong>adCriteriaAllCols</strong></p></td>
<td><p>1</p></td>
<td><p>如果数据源行中的任何列已发生更改，则检测冲突。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCriteriaKey</strong></p></td>
<td><p>0</p></td>
<td><p>如果数据源行中的键列已发生更改（这意味着该行已被删除），则检测冲突。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adCriteriaTimeStamp</strong></p></td>
<td><p>第三章</p></td>
<td><p>如果数据源行中的时间戳已发生更改（这意味着在获取 <strong>Recordset</strong> 之后，该行已被访问过），则检测冲突。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCriteriaUpdCols</strong></p></td>
<td><p>双面</p></td>
<td><p>如果数据源行中与 <strong>Recordset</strong> 的更新字段相对应的任何列已发生更改，则检测冲突。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

包：**com.ms.wfc.data**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdoEnums AdcPropUpdateCriteria</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums AdcPropUpdateCriteria</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums AdcPropUpdateCriteria</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums AdcPropUpdateCriteria</p></td>
</tr>
</tbody>
</table>

