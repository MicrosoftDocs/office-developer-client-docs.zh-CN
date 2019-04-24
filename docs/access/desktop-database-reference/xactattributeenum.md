---
title: XactAttributeEnum (Access desktop database reference)
TOCTitle: XactAttributeEnum
ms:assetid: 9206698b-7cfa-1229-2701-f2b6949e54fc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249643(v=office.15)
ms:contentKeyID: 48546366
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e79a6143c65637660b2d59b7c7efb6a21e8935bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302567"
---
# <a name="xactattributeenum"></a>XactAttributeEnum

**适用于**：Access 2013、Office 2013

指定 [Connection](connection-object-ado.md) 对象的事务属性。

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
<td><p><strong>adXactAbortRetaining</strong></p></td>
<td><p>262144</p></td>
<td><p>执行保留中止;即, 调用<a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">RollbackTrans</a>将自动启动一个新的事务。 并非所有提供程序都支持此行为。</p></td>
</tr>
<tr class="even">
<td><p><strong>adXactCommitRetaining</strong></p></td>
<td><p>131072</p></td>
<td><p>执行保留提交;即, 调用<a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">CommitTrans</a>将自动启动一个新的事务。 并非所有提供程序都支持此行为。</p></td>
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
<td><p>AdoEnums XactAttribute</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums XactAttribute</p></td>
</tr>
</tbody>
</table>

