---
title: MarshalOptions 属性 (ADO)
TOCTitle: MarshalOptions Property (ADO)
ms:assetid: dc9c4e94-0725-210d-8251-079054541142
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250118(v=office.15)
ms:contentKeyID: 48548143
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f290f2f4fb4820fb01d3a63aef7bcfbfa7c1f035
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468075"
---
# <a name="marshaloptions-property-ado"></a>MarshalOptions 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示哪些记录要封送回服务器。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 [MarshalOptionsEnum](marshaloptionsenum.md) 值。默认值是 **adMarshalAll** 。

## <a name="remarks"></a>备注

使用客户端 [Recordset](recordset-object-ado.md) 时，已在客户端上修改的记录通过名为封送的技术写回中间层或 Web 服务器，封送是指跨线程或进程边界打包和发送接口方法参数的过程。当已修改的远程数据通过封送更新回中间层或 Web 服务器时，设置 **MarshalOptions** 属性可提高性能。

**远程数据服务用法**此属性只能在客户端**Recordset**上使用。

