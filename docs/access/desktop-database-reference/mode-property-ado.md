---
title: Mode 属性 (ADO)
TOCTitle: Mode property (ADO)
ms:assetid: 62086f4f-8624-16c4-dae1-a17475d1864d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249365(v=office.15)
ms:contentKeyID: 48545227
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 74b0a401c5fbd7e34cbd002020d81b9b0858e4f7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25874277"
---
# <a name="mode-property-ado"></a>Mode 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示在 [Connection](connection-object-ado.md)、[Record](record-object-ado.md) 或 [Stream](stream-object-ado.md) 对象中修改数据的可用权限。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 [ConnectModeEnum](connectmodeenum.md) 值。**Connection** 的默认值为 **adModeUnknown**。**Record** 对象的默认值为 **adModeRead**。与基础源关联的 **Stream**（通过作为源的 URL 打开，或作为 **Record** 的默认 **Stream** 打开）的默认值为 **adModeRead**。不与基础源关联的 **Stream**（在内存中实例化）的默认值为 **adModeUnknown**。

## <a name="remarks"></a>备注

使用 **Mode** 属性可设置或返回提供程序在当前连接上使用的访问权限。只有 **Connection** 对象关闭时才可以设置 **Mode** 属性。

对于 **Stream** 对象，如果未指定访问模式，则从用于打开该 **Stream** 对象的源继承。例如，如果从 **Record** 对象打开 **Stream** ，则默认情况下，其打开模式与 **Record** 相同。

对象关闭时此属性为可读/写属性，对象打开时为只读属性。

**远程数据服务用法**当客户端 Connection 对象上使用时， **Mode**属性可以仅可设为**adModeUnknown**。

