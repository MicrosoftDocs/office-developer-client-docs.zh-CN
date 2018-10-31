---
title: Command 对象 (ADO)
TOCTitle: Command Object (ADO)
ms:assetid: 64f4ef03-f858-c004-b891-0c96d13a5e6e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249389(v=office.15)
ms:contentKeyID: 48545303
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231106
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 153f59ebbcfae89f6358fe0d707791aab8a8cdd7
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25864072"
---
# <a name="command-object-ado"></a>Command 对象 (ADO)


**适用于**： Access 2013 |Office 2013

定义要对数据源执行的特定命令。

## <a name="remarks"></a>说明

使用 **Command** 对象可查询数据库并通过 [Recordset](recordset-object-ado.md) 对象返回记录，执行批量操作或处理数据库的结构。根据提供程序功能的不同，引用某些 **Command** 集合、方法或属性时，可能生成错误。

使用 **Command** 对象的集合、方法和属性，可以执行以下操作：

  - 使用 [CommandText](commandtext-property-ado.md) 属性可定义命令的可执行文本（如一条 SQL 语句）。

  - 使用 [Parameter](parameter-object-ado.md) 对象和 [Parameters](parameters-collection-ado.md) 集合可定义参数化查询或存储过程参数。

<<<<<<< 头
  - 使用 **Execute** 方法可执行命令并返回 [Recordset](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 对象（如果适用）。
=======
  - 使用 **Execute** 方法可执行命令并返回 [Recordset](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 对象（如果适用）。
>>>>>>> 母版

  - 在执行命令之前，使用 [CommandType](commandtype-property-ado.md) 属性指定命令的类型可优化性能。

  - 使用 [Prepared](prepared-property-ado.md) 属性可控制提供程序是否在执行命令之前保存命令的预备（或已编译）版本。

  - 使用 [CommandTimeout](commandtimeout-property-ado.md) 属性可设置提供程序等待命令执行的秒数。

  - 通过设置 **Command** 对象的 [ActiveConnection](activeconnection-property-ado.md) 属性，可将打开的连接与该对象关联。

  - 设置 [Name](name-property-ado.md) 属性将 **Command** 对象标识为相关联的 [Connection](connection-object-ado.md) 对象的方法。

  - 将 **Command** 对象传递给 [Recordset](source-property-ado-recordset.md) 对象的 **Source** 属性可获取数据。

  - 使用 [Properties](properties-collection-ado.md) 集合可访问特定于提供程序的属性。

> [!NOTE]
> [!注释] 若要在不使用 **Command** 对象的情况下执行查询，可将查询字符串传递给 [Connection](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection) 对象的 **Execute** 方法或 [Recordset](open-method-ado-recordset.md) 对象的 **Open** 方法。但是，如果要持久保留命令文本并重新执行它，或使用查询参数，则需要 **Command** 对象。

若要独立于以前定义的 **Connection** 对象创建 **Command** 对象，请将 Command 对象的 **ActiveConnection** 属性设置为有效的连接字符串。ADO 仍然创建 **Connection** 对象，但不将该对象分配给对象变量。但是，如果将多个 **Command** 对象与同一连接关联，则应显式创建和打开 **Connection** 对象；这样就会将 **Connection** 对象分配给对象变量。如果不将 **Command** 对象的 **ActiveConnection** 属性设置为该对象变量，ADO 就会为每个 **Command** 对象创建一个新的 **Connection** 对象，即便使用相同的连接字符串也是如此。

若要执行 **Command** ，只需通过其关联的 [Connection](name-property-ado.md) 对象的 **Name** 属性调用它即可。 **Command** 的 **ActiveConnection** 属性必须设置为 **Connection** 对象。如果 **Command** 具有参数，请将它们的值作为参数传递给方法。

在同一连接上执行两个或多个 **Command** 对象时，如果任一 **Command** 对象是具有输出参数的存储过程，将产生错误。若要执行每个 **Command** 对象，可使用单独的连接或将其他所有 **Command** 对象与该连接断开。

**Parameters** 集合是 **Command** 对象的默认成员。因此，以下两个代码语句是等效的。

