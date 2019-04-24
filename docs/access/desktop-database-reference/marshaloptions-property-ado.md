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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289768"
---
# <a name="marshaloptions-property-ado"></a>MarshalOptions 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示哪些记录要封送回服务器。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 [MarshalOptionsEnum](marshaloptionsenum.md) 值。默认值是 **adMarshalAll**。

## <a name="remarks"></a>注解

使用客户端[Recordset](recordset-object-ado.md)时, 已在客户端上修改的记录将通过一种称为封送的技术写回到中间层或 web 服务器, 这是在各个线程之间打包和发送接口方法参数的过程进程边界。 当修改的远程数据被封送回中间层或 web 服务器时, 设置**MarshalOptions**属性可以提高性能。

**远程数据服务使用情况**此属性仅在客户端**Recordset**上使用。

