---
title: 建立连接
TOCTitle: Making a connection
ms:assetid: 188f6794-f4ec-8e8d-5adc-bdee36f4c9ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248932(v=office.15)
ms:contentKeyID: 48543472
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 487212acd8847928e1fab405593edb172d0172d0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289782"
---
# <a name="making-a-connection"></a>建立连接

**适用于**：Access 2013、Office 2013

若要连接到数据源，必须指定 *connection string*，连接字符串的参数可能因每个提供程序和数据源而异。有关详细信息，请参阅[创建连接字符串](creating-the-connection-string.md)。

ADO 通常使用 **Connection** 对象的 **Open** 方法来打开连接。 **Open** 方法的语法如下：

```vb
Dim connection as New ADODB.Connection 
connection.Open ConnectionString, UserID, Password, OpenOptions
```

或者，也可以调用快捷技术 **Recordset.Open** 在一次操作中完成打开隐式连接并通过该连接发出命令的操作。要这样做，需要将有效的连接字符串作为 *ActiveConnection* 参数传递给 **Open** 方法。下面是在 Visual Basic 中每个方法的语法：

```vb
Dim recordset as ADODB.Recordset 
Set recordset = New ADODB.Recordset 
recordset.Open Source, ActiveConnection, CursorType, LockType, Options
```

> [!NOTE]
> [!注释] 什么时候应当使用 **Connection** 对象，什么时候应当使用 **Recordset.Open** 快捷技术？如果计划打开多个 **Recordset** ，或者要执行多个命令，请使用 **Connection** 对象。使用 **Recordset.Open** 快捷技术时，ADO 仍然会隐式创建连接。


