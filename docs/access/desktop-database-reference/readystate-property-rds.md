---
title: ReadyState 属性 (RDS)
TOCTitle: ReadyState Property (RDS)
ms:assetid: e7b62205-a604-ef43-2f5d-9b51b46d2b5a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250175(v=office.15)
ms:contentKeyID: 48548412
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 804a98a6fa7c93617a5b6e165a2a012969c66913
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467616"
---
# <a name="readystate-property-rds"></a>ReadyState 属性 (RDS)


**适用于**： Access 2013 |Office 2013

指示 [DataControl](datacontrol-object-rds.md) 对象将数据检索进其 [Recordset](recordset-object-ado.md) 对象的进度。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回下列值之一。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adcReadyStateLoaded</strong></p></td>
<td><p>仍在执行当前查询，尚未获取任何行。<strong>DataControl</strong> 对象的 <strong>Recordset</strong> 不可用。</p></td>
</tr>
<tr class="even">
<td><p><strong>adcReadyStateInteractive</strong></p></td>
<td><p>当前查询检索到的初始行集已存储在 <strong>DataControl</strong> 对象的 <strong>Recordset</strong> 中，可以使用。仍在获取其余行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adcReadyStateComplete</strong></p></td>
<td><p>当前查询检索到的所有行已存储在 <strong>DataControl</strong> 对象的 <strong>Recordset</strong> 中，可以使用。
 如果由于错误或由于未初始化 <strong>Recordset</strong> 对象而中止操作，也会存在此状态。</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>[!注释] 使用这些常量的每个客户端可执行文件必须提供其声明。可从位于 C:\Program Files\Common Files\System\MSADC 文件夹中的 Adcvbs.inc 文件剪切并粘贴所需的常量声明。</P>



## <a name="remarks"></a>备注

使用 [onReadyStateChange](onreadystatechange-event-rds.md) 事件可在异步查询操作期间监视 **ReadyState** 属性的变化。这比定时检查属性值的效率更高。

如果出现错误时发生异步操作， **ReadyState**属性更改为**adcReadyStateComplete**， [State](state-property-ado.md)属性从**adStateExecuting**更改为**adStateClosed**和**记录集**对象的[Value](value-property-ado.md)属性会保持为*Nothing*。

