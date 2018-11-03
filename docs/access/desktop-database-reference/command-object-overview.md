---
title: Command 对象概述
TOCTitle: Command object overview
ms:assetid: 3d6d81c4-4cf0-0c13-adb3-0c2c5934dc21
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249166(v=office.15)
ms:contentKeyID: 48544346
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 65ca58b7a2edc0397207cf7bbf6a001349ffc636
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947390"
---
# <a name="command-object-overview"></a><span data-ttu-id="7f0ef-102">Command 对象概述</span><span class="sxs-lookup"><span data-stu-id="7f0ef-102">Command object overview</span></span>

<span data-ttu-id="7f0ef-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7f0ef-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7f0ef-104">利用 **Command** 对象的集合、方法和属性，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7f0ef-104">With the collections, methods, and properties of a **Command** object, you can do the following:</span></span>

  - <span data-ttu-id="7f0ef-105">使用 **CommandText** 属性定义命令的可执行文本（例如，SQL 语句或存储过程）。</span><span class="sxs-lookup"><span data-stu-id="7f0ef-105">Define the executable text of the command (for example, a SQL statement or a stored procedure) by using the **CommandText** property.</span></span>

  - <span data-ttu-id="7f0ef-106">使用 **Parameter** 对象和 **Parameters** 集合定义参数化的查询和存储过程参数。</span><span class="sxs-lookup"><span data-stu-id="7f0ef-106">Define parameterized queries or stored procedure arguments by using **Parameter** objects and the **Parameters** collection.</span></span>

  - <span data-ttu-id="7f0ef-107">使用 **Execute** 方法执行命令并返回 **Recordset** 对象（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="7f0ef-107">Execute a command and return a **Recordset** object, if appropriate, by using the **Execute** method.</span></span>

  - <span data-ttu-id="7f0ef-108">在执行优化性能前，使用 **CommandType** 属性指定命令的类型。</span><span class="sxs-lookup"><span data-stu-id="7f0ef-108">Specify the type of command by using the **CommandType** property prior to execution to optimize performance.</span></span>

  - <span data-ttu-id="7f0ef-109">使用 **Prepared** 属性控制提供程序在执行命令前是否保存命令的 prepared（或 compiled）版本。</span><span class="sxs-lookup"><span data-stu-id="7f0ef-109">Control whether the provider saves a prepared (or compiled) version of the command prior to execution by using the **Prepared** property.</span></span>

  - <span data-ttu-id="7f0ef-110">使用 **CommandTimeout** 属性设置提供程序将等待命令执行的秒数。</span><span class="sxs-lookup"><span data-stu-id="7f0ef-110">Set the number of seconds that a provider will wait for a command to execute by using the **CommandTimeout** property.</span></span>

  - <span data-ttu-id="7f0ef-111">通过设置 **Command** 对象的 **ActiveConnection** 属性，将打开的连接与该对象关联在一起。</span><span class="sxs-lookup"><span data-stu-id="7f0ef-111">Associate an open connection with a **Command** object by setting its **ActiveConnection** property.</span></span>

  - <span data-ttu-id="7f0ef-112">设置 **Name** 属性将 **Command** 对象标识为相关联的 **Connection** 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="7f0ef-112">Set the **Name** property to identify the **Command** object as a method on the associated **Connection** object.</span></span>

  - <span data-ttu-id="7f0ef-113">将 **Command** 对象传递到 **Recordset** 的 **Source** 属性以获取数据。</span><span class="sxs-lookup"><span data-stu-id="7f0ef-113">Pass a **Command** object to the **Source** property of a **Recordset** in order to obtain data.</span></span>

