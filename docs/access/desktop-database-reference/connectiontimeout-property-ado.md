---
title: ConnectionTimeout 属性 (ADO)
TOCTitle: ConnectionTimeout property (ADO)
ms:assetid: efc39fd8-afce-5ac0-2fff-cbb55c1a444d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250218(v=office.15)
ms:contentKeyID: 48548589
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0526ee6a0d6cf9aa8f9263e8f3d31e66fad7da82
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700932"
---
# <a name="connectiontimeout-property-ado"></a>ConnectionTimeout 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示在建立连接时要等待多长时间才终止连接尝试并生成错误。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，该值指示等待连接打开的时间（以秒为单位）。默认值为 15。

## <a name="remarks"></a>备注

如果由于网络通信延迟或服务器负载太大而有必要放弃连接尝试，请使用 **Connection** 对象上的 [ConnectionTimeout](connection-object-ado.md) 属性。如果在打开连接前超过了 **ConnectionTimeout** 属性设置的时间，将发生错误，且 ADO 将取消连接尝试。如果将该属性设置为零，ADO 将无限期等待，直到连接打开为止。请确保您向其中写入代码的提供程序支持 **ConnectionTimeout** 功能。

**ConnectionTimeout** 属性在连接关闭时为可读/写属性，而在连接打开时为只读属性。

