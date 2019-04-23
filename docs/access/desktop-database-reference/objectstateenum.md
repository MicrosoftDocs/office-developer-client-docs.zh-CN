---
title: ObjectStateEnum (Access desktop database reference)
TOCTitle: ObjectStateEnum
ms:assetid: 129d589a-2955-3da9-e60a-7fbfdd6bfbdc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248900(v=office.15)
ms:contentKeyID: 48543347
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b6e346db2fb2dac0695e8c9048a210d8e40e6dc4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288523"
---
# <a name="objectstateenum"></a>ObjectStateEnum

**适用于**：Access 2013、Office 2013

用于指定对象已打开还是已关闭，正在连接数据源，正在执行命令，还是正在检索数据。

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
<td><p><strong>adStateClosed</strong></p></td>
<td><p>0</p></td>
<td><p>指示对象已关闭。</p></td>
</tr>
<tr class="even">
<td><p><strong>adStateOpen</strong></p></td>
<td><p>1</p></td>
<td><p>指示对象已打开。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adStateConnecting</strong></p></td>
<td><p>双面</p></td>
<td><p>指示对象正在连接。</p></td>
</tr>
<tr class="even">
<td><p><strong>adStateExecuting</strong></p></td>
<td><p>4</p></td>
<td><p>指示对象正在执行命令。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adStateFetching</strong></p></td>
<td><p>utf-8</p></td>
<td><p>指示正在检索对象的行。</p></td>
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
<td><p>AdoEnums 对象 state</p></td>
</tr>
<tr class="even">
<td><p>对象 state。打开 AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>对象 state 连接 AdoEnums</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums 对象 state</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums 对象 state</p></td>
</tr>
</tbody>
</table>

