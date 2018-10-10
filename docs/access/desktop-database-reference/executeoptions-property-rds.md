---
title: ExecuteOptions 属性 (RDS)
TOCTitle: ExecuteOptions Property (RDS)
ms:assetid: fb244cbd-9a03-9128-1373-694c9061c9da
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250285(v=office.15)
ms:contentKeyID: 48548864
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 641e7942f5336f230d396db7e06b9d0601645cb6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465995"
---
# <a name="executeoptions-property-rds"></a>ExecuteOptions 属性 (RDS)


**适用于**： Access 2013 |Office 2013

指示是否启用异步执行。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回下列值之一。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adcExecSync</strong></p></td>
<td><p>同步执行 <a href="recordset-object-ado.md">Recordset</a> 的下一个刷新操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adcExecAsync</strong></p></td>
<td><p>该值为默认值。异步执行 <strong>Recordset</strong> 的下一个刷新操作。</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>[!注释] 使用这些常量的每个客户端可执行文件必须提供其声明。可从位于 C:\Program Files\Common Files\System\MSADC 文件夹中的 Adcvbs.inc 文件剪切并粘贴所需的常量声明。</P>



## <a name="remarks"></a>备注

如果 **ExecuteOptions** 设置为 **adcExecAsync** ，则将对 **RDS.DataControl** 对象的 [Recordset](datacontrol-object-rds.md) 异步执行下一个 **Refresh** 调用。

当正在执行另一个可能更改 [RDS.DataControl](reset-method-rds.md) 对象的 [Recordset](refresh-method-rds.md) 的异步操作时，如果尝试调用 [Reset](submitchanges-method-rds.md)、[Refresh](cancelupdate-method-ado.md)、[SubmitChanges](recordset-sourcerecordset-properties-rds.md)、[CancelUpdate](datacontrol-object-rds.md) 或 **Recordset**，则将发生错误。

如果在异步操作期间发生错误，则 **RDS.DataControl** 对象的 [ReadyState](readystate-property-rds.md) 值将从 **adcReadyStateLoaded** 更改为 **adcReadyStateComplete**，而 **Recordset** 属性值仍为 *Nothing*。

