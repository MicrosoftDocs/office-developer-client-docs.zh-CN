---
title: MarshalOptions 属性 (ADO)
TOCTitle: MarshalOptions property (ADO)
ms:assetid: dc9c4e94-0725-210d-8251-079054541142
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250118(v=office.15)
ms:contentKeyID: 48548143
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 22a3662d3d14dd639069fa7aa48eda6f032fd2d1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704593"
---
# <a name="marshaloptions-property-ado"></a>MarshalOptions 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示哪些记录要封送回服务器。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 [MarshalOptionsEnum](marshaloptionsenum.md) 值。默认值是 **adMarshalAll** 。

## <a name="remarks"></a>备注

在使用客户端[Recordset](recordset-object-ado.md)时，客户端已修改的记录写回中间层或通过称为封送，打包和跨线程发送接口方法参数的过程的技术的 web 服务器或进程边界。 已修改的远程数据封送回中间层或 web 服务器更新时，设置**MarshalOptions**属性可以提高性能。

**远程数据服务用法**此属性只能在客户端**Recordset**上使用。

