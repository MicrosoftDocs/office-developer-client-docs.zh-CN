---
title: Command 对象概述
TOCTitle: Command object overview
ms:assetid: 3d6d81c4-4cf0-0c13-adb3-0c2c5934dc21
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249166(v=office.15)
ms:contentKeyID: 48544346
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f2c7697d4ae8b830afb53eee10e7dd59a7dc8db4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712083"
---
# <a name="command-object-overview"></a>Command 对象概述

**适用于**： Access 2013、 Office 2013

利用 **Command** 对象的集合、方法和属性，可以执行以下操作：

  - 使用 **CommandText** 属性定义命令的可执行文本（例如，SQL 语句或存储过程）。

  - 使用 **Parameter** 对象和 **Parameters** 集合定义参数化的查询和存储过程参数。

  - 使用 **Execute** 方法执行命令并返回 **Recordset** 对象（如果适用）。

  - 在执行优化性能前，使用 **CommandType** 属性指定命令的类型。

  - 使用 **Prepared** 属性控制提供程序在执行命令前是否保存命令的 prepared（或 compiled）版本。

  - 使用 **CommandTimeout** 属性设置提供程序将等待命令执行的秒数。

  - 通过设置 **Command** 对象的 **ActiveConnection** 属性，将打开的连接与该对象关联在一起。

  - 设置 **Name** 属性将 **Command** 对象标识为相关联的 **Connection** 对象的方法。

  - 将 **Command** 对象传递到 **Recordset** 的 **Source** 属性以获取数据。

