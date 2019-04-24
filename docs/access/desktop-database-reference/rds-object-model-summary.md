---
title: RDS 对象模型摘要
TOCTitle: RDS object model summary
ms:assetid: 0355d62a-dabb-8643-5c43-1e98ccf7f3b0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248800(v=office.15)
ms:contentKeyID: 48542981
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 33cbdc6de644592d87b7d49e65a5c5674ad94d5b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300873"
---
# <a name="rds-object-model-summary"></a>RDS 对象模型摘要


**适用于**：Access 2013、Office 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Object</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="dataspace-object-rds.md">RDS.DataSpace</a></p></td>
<td><p>此对象包含一个用于获取服务器代理的方法。代理可以是默认的服务器程序或自定义服务器程序（业务对象）。该服务器程序可以在 Internet、Intranet、局域网或本地动态链接库上调用。</p></td>
</tr>
<tr class="even">
<td><p><a href="datafactory-object-rdsserver.md">rdsserver.datafactory。 DataFactory</a></p></td>
<td><p>此对象表示默认的服务器程序。 用于执行默认的 RDS 数据检索和更新行为。</p></td>
</tr>
<tr class="odd">
<td><p><a href="datacontrol-object-rds.md">RDS.rds.datacontrol</a></p></td>
<td><p>此对象可以自动调用 <strong>RDS.DataSpace</strong> 和 <strong>RDSServer.DataFactory</strong> 对象。 此对象可用于调用默认的 RDS 数据检索或更新行为。 此对象还提供了多种方法，以供可视控件访问返回的 <strong>Recordset</strong> 对象。</p></td>
</tr>
</tbody>
</table>

