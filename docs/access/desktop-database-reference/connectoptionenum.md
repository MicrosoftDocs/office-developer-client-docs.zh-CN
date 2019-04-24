---
title: ConnectOptionEnum (Access desktop database reference)
TOCTitle: ConnectOptionEnum
ms:assetid: 803d3fd6-93cf-85ea-eeb0-ca1bc965577d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249544(v=office.15)
ms:contentKeyID: 48545921
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 95b622d2216b085ffd0f76c8a26533187c17bd7b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295679"
---
# <a name="connectoptionenum"></a>ConnectOptionEnum

**适用于**：Access 2013、Office 2013

指定在建立连接之后（同步）或之前（异步）是否应返回 [Connection](open-method-ado-connection.md) 对象的 [Open](connection-object-ado.md) 方法。

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
<td><p><strong>即用 adasyncconnect</strong></p></td>
<td><p>位</p></td>
<td><p>异步打开连接。可以使用 <a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete</a> 事件来确定连接何时可用。</p></td>
</tr>
<tr class="even">
<td><p><strong>adConnectUnspecified</strong></p></td>
<td><p>-1</p></td>
<td><p>默认值。同步打开连接。</p></td>
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
<td><p>AdoEnums ConnectOption</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums ConnectOption</p></td>
</tr>
</tbody>
</table>

