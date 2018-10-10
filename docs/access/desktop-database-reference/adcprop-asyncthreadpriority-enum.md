---
title: ADCPROP_ASYNCTHREADPRIORITY_ENUM
TOCTitle: ADCPROP_ASYNCTHREADPRIORITY_ENUM
ms:assetid: b15006dd-22d5-fcf3-8196-9e24ea9d55a7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249844(v=office.15)
ms:contentKeyID: 48547143
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ae89c81b903930eb114cf050688598bc2802a25e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468032"
---
# <a name="adcpropasyncthreadpriorityenum"></a>ADCPROP\_ASYNCTHREADPRIORITY\_枚举

**适用于**： Access 2013 |Office 2013

对于 RDS [Recordset](recordset-object-ado.md) 对象，指定用于检索数据的异步线程的执行优先级。

这些常量适用于 **Recordset** 的“**Background Thread Priority**”动态属性，该动态属性在 ADO 动态属性索引中被引用，并在 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 文档中进行了介绍。

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
<td><p><strong>adPriorityAboveNormal</strong></p></td>
<td><p>4</p></td>
<td><p>设置普通和最高之间的优先级。</p></td>
</tr>
<tr class="even">
<td><p><strong>adPriorityBelowNormal</strong></p></td>
<td><p>2</p></td>
<td><p>设置最低和普通之间的优先级。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adPriorityHighest</strong></p></td>
<td><p>5</p></td>
<td><p>设置尽可能高的优先级。</p></td>
</tr>
<tr class="even">
<td><p><strong>AdPriorityLowest</strong></p></td>
<td><p>1</p></td>
<td><p>设置尽可能低的优先级。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adPriorityNormal</strong></p></td>
<td><p>3</p></td>
<td><p>将优先级设置为普通。</p></td>
</tr>
</tbody>
</table>


**ADO/WFC 等效值**

包： **com.ms.wfc.data**

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
<td><p>AdoEnums.AdcPropAsyncThreadPriority.ABOVENORMAL</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.AdcPropAsyncThreadPriority.BELOWNORMAL</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.AdcPropAsyncThreadPriority.HIGHEST</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.AdcPropAsyncThreadPriority.LOWEST</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.AdcPropAsyncThreadPriority.NORMAL</p></td>
</tr>
</tbody>
</table>

