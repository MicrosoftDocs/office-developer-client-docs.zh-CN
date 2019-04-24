---
title: CommandTimeout 属性 (ADO)
TOCTitle: CommandTimeout property (ADO)
ms:assetid: a0b6209c-9feb-08ae-002a-15d1d20734a8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249739(v=office.15)
ms:contentKeyID: 48546714
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231124
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 9d44bc8fae0143b183ef54120cdaaf91337f36f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296127"
---
# <a name="commandtimeout-property-ado"></a>CommandTimeout 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示在执行命令时要等待多长时间才终止操作尝试并生成错误。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，该值指示等待命令执行的时间（以秒为单位）。 默认值为 30。

## <a name="remarks"></a>注解

使用 **Connection** 对象或 [Command](connection-object-ado.md) 对象上的 [CommandTimeout](command-object-ado.md) 属性，可以允许在网络通信延迟或服务器负载太大的情况下取消 [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 方法调用。如果在完成执行命令前超过了 **CommandTimeout** 属性中设置的间隔时间，则将发生错误，且 ADO 将取消该命令。如果将该属性设置为零，ADO 将无限期等待，直到完成执行为止。请确保向其中写入代码的提供程序和数据源支持 **CommandTimeout** 功能。

**Connection** 对象上的 **CommandTimeout** 设置对同一个 **Connection** 中的 **Command** 对象的 **CommandTimeout** 设置没有影响；即， **Command** 对象的 **CommandTimeout** 属性并不会继承 **Connection** 对象的 **CommandTimeout** 值。

在 **Connection** 对象上， **CommandTimeout** 属性会在该 **Connection** 打开后保持可读/写状态。

