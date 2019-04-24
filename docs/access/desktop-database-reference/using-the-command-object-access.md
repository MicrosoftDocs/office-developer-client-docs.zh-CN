---
title: 使用 Command 对象 (Access)
TOCTitle: Using the Command Object
ms:assetid: dab6f0dd-1efa-3a5c-b192-c6d6afcaabfb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250102(v=office.15)
ms:contentKeyID: 48548088
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9b89d292d86035e565ad18413062274dfbfc74db
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312024"
---
# <a name="using-the-command-object-access"></a>使用 Command 对象 (Access)


**适用于**：Access 2013、Office 2013

在连接到数据源之后，需要针对它执行请求以获取结果集。ADO 将此类命令功能封装在 **Command** 对象中。

使用 **Command** 对象，可以从提供程序请求任何类型的操作，前提是提供程序可以正确地解释命令字符串。数据提供程序一个常见的操作是查询数据库并在 **Recordset** 对象中返回记录。**Recordset** 随后将在本章和其他各章中讨论；现在，让我们将记录集视为用来存放和查看结果集的工具。与许多 ADO 对象一样，根据提供程序的功能，某些 **Command** 对象的集合、方法或属性可能会在被引用时产生错误。

若要针对数据源执行命令，不必总是创建 **Command** 对象。可以针对 **Connection** 对象使用 **Execute** 方法或针对 **Recordset** 对象使用 **Open** 方法。但是，如果您需要在代码中重复使用某个命令，或者如果您需要在命令中传递详细的参数信息，则应当使用 **Command** 对象。本章稍后将更详细地介绍这些方案。

> [!NOTE]
> 某些 Command 可以返回二进制流或单个 Record（而非 Recordset）形式的结果集，但前提是提供程序支持此功能。 同样，某些 Command（例如，SQL 更新查询）根本不会返回任何结果集。 本章将介绍最典型的方案，但是，本章执行的是可将结果返回到 Recordset 对象中的 Command。 有关将结果返回到 Record 或 Stream 的详细信息，请参阅[第 10 章：记录和流](chapter-10-records-and-streams.md)。

本节包括下列主题：

- [Command 对象概述](command-object-overview.md)
- [创建和执行简单的命令](creating-and-executing-a-simple-command.md)
- [Command 对象参数](command-object-parameters.md)
- [使用 command 调用存储过程](calling-a-stored-procedure-with-a-command.md)
- [Named 命令](named-commands.md)
