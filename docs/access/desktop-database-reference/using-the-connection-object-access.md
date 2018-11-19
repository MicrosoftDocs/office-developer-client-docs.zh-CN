---
title: Using the Connection Object (Access)
TOCTitle: Using the Connection Object
ms:assetid: e8786411-2be4-8d75-9df7-e345d5a6a7e8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250177(v=office.15)
ms:contentKeyID: 48548423
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c2f14be526100b1ffcbe34af89c1f72d0a64ff99
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025495"
---
# <a name="using-the-connection-object-access"></a>使用 Connection 对象 (Access)


**适用于**： Access 2013、 Office 2013

**Connection** 对象表示与数据源的唯一会话。对于客户端/服务器数据库系统，该对象等效于与服务器的实际网络连接。根据提供程序所支持的功能， **Connection** 对象的某些集合、方法或属性可能不可用。

在打开 **Connection** 对象之前，必须定义有关数据源和连接类型的某些信息。 **Connection**对象的**Open**方法的*ConnectionString*参数 — 或**Connection**对象的**ConnectionString**属性 — 通常包含大部分此信息。 连接字符串是用来定义参数的可变数量的字符串。 参数中包含 **Connection** 对象执行其工作所必需的信息，一些参数是 ADO 必需的，而另一些参数是特定于提供程序的。 用分号 （;） 分隔组成的*ConnectionString*参数的参数。

> [!NOTE]
> 还可以在连接字符串中指定 ODBC 数据源名称 (DSN) 或数据链接 (UDL) 文件。有关 DSN 的详细信息，请参阅 *《ODBC 程序员参考》* 第 1 部分中的“数据源”。有关 UDL 的详细信息，请参阅 *《OLE DB 程序员参考》* 中的“数据链接 API 概述”。

本节包括下列主题：

- [创建连接字符串](creating-the-connection-string.md)
- [控制事务](controlling-transactions.md)
