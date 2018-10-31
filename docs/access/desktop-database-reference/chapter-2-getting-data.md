---
title: 第 2 章：获取数据
TOCTitle: 'Chapter 2: Getting Data'
ms:assetid: 72d097e1-9284-cc27-fd48-e6bbb6a2a543
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249465(v=office.15)
ms:contentKeyID: 48545619
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 601d18373f5bcd0a9ed6777fa50c2a3ed631594a
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860887"
---
# <a name="chapter-2-getting-data"></a>第 2 章：获取数据


**适用于**： Access 2013 |Office 2013

前一章介绍了在创建 ADO 应用程序时涉及的四个主要操作：获取数据、检查数据、编辑数据和更新数据。本章将重点介绍与第一个操作（获取数据）相关的概念的详细信息。

若干 ADO 对象可以在此操作中发挥作用。首先，需要使用 ADO **Connection** 对象（有时会隐式创建该对象）连接到数据源。然后，使用 ADO **Command** 对象（也可以隐式创建它）将指令传递给数据源，告诉它您希望做什么。在将命令传递给数据源并接收其响应后，通常将在 ADO **Recordset** 对象中显示相应结果。

若要获取数据，应用程序必须与诸如 DBMS、文件存储或逗号分隔的文本文件这样的数据源进行通信。 此通信代表一个*连接*— 交换数据所必需的环境。

ADO 对象模型用 **Connection** 对象来表示连接的概念 - 这是建立很多 ADO 功能的基础。 **Connection** 对象的用途是：

  - 定义 ADO 在与数据源通信并创建会话时所需的信息。

  - 定义会话的事务性功能。

  - 允许您针对数据源创建和执行命令。

  - 提供有关以架构行集的形式设计基础数据源的信息。有关架构行集的详细信息，请参阅 [OpenSchema 方法](openschema-method-ado.md)。

本章包含以下主题：

  - [创建连接](making-a-connection.md)

  - [Using the Connection Object Reference (ADO)](using-the-connection-object-access.md)

  - [Using the Command Object Reference (ADO)](using-the-command-object-access.md)

  - [Adding Data to a Recordset (ADO)](adding-data-to-a-recordset.md)