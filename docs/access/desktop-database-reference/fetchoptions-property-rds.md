---
title: FetchOptions 属性 (RDS)
TOCTitle: FetchOptions Property (RDS)
ms:assetid: 0d86c5e4-9abc-5c0e-dc04-4183f4c278cc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248856(v=office.15)
ms:contentKeyID: 48543221
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b3e7251ba50b003b37cdeb0dd70fe4a98821d4c9
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861930"
---
# <a name="fetchoptions-property-rds"></a>FetchOptions 属性 (RDS)


**适用于**： Access 2013 |Office 2013

指示异步获取类型。

## <a name="setting-and-return-values"></a>设置和返回值

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
<td><p><strong>adcFetchUpFront</strong></p></td>
<td><p>在控制返回到应用程序之前获取 <a href="recordset-object-ado.md">Recordset</a> 的所有记录。在获取完整的 <strong>Recordset</strong> 之后才允许应用程序对其执行操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adcFetchBackground</strong></p></td>
<td><p>只要获取了首批记录，控制即可返回到应用程序。对试图访问未在首批获取的记录进行的后续读取，<strong>Recordset</strong> 将延迟到实际获取待查的记录之后，届时控制将返回到应用程序。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adcFetchAsync</strong></p></td>
<td><p>该值为默认值。在后台获取记录时控制将立刻返回至应用程序。如果应用程序试图读取尚未获取的记录，则将读取最接近所发现的记录的记录，且控制将立刻返回，指示已到达 <strong>Recordset</strong> 的当前末尾处。例如，尽管会有更多记录继续填充 <strong>Recordset</strong>，调用 <a href="movefirst-movelast-movenext-and-moveprevious-methods-rds.md">MoveLast</a> 会始终将当前记录位置移动到实际获取的最后一条记录。</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> [!注释] 使用这些常量的每个客户端可执行文件必须提供其声明。可从位于 C:\Program Files\Common Files\System\MSADC 文件夹中的 Adcvbs.inc 文件剪切并粘贴所需的常量声明。



## <a name="remarks"></a>备注

<<<<<<< 标头中 Web 应用程序中，将通常想要使用**adcFetchAsync** （默认值），因为它提供了更好的性能。 而在已编译的客户端应用程序中，通常会使用 **adcFetchBackground** 。
=== 在 web 应用程序，您通常需要使用**adcFetchAsync** （默认值），因为它提供了更好的性能。 而在已编译的客户端应用程序中，通常会使用 **adcFetchBackground** 。
>>>>>>> 母版

