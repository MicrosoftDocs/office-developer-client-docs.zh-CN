---
title: 建立连接
TOCTitle: Making a connection
ms:assetid: 188f6794-f4ec-8e8d-5adc-bdee36f4c9ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248932(v=office.15)
ms:contentKeyID: 48543472
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0335c4bbc0d1240d6d4ca53ceacf47bf44fce67d
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945885"
---
# <a name="making-a-connection"></a><span data-ttu-id="2c203-102">建立连接</span><span class="sxs-lookup"><span data-stu-id="2c203-102">Making a connection</span></span>

<span data-ttu-id="2c203-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2c203-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2c203-p101">若要连接到数据源，必须指定 *connection string*，连接字符串的参数可能因每个提供程序和数据源而异。有关详细信息，请参阅[创建连接字符串](creating-the-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="2c203-p101">To connect to a data source, you must specify a *connection string*, the parameters of which might differ for each provider and data source. For more information, see [Creating the Connection String](creating-the-connection-string.md).</span></span>

<span data-ttu-id="2c203-p102">ADO 通常使用 **Connection** 对象的 **Open** 方法来打开连接。 **Open** 方法的语法如下：</span><span class="sxs-lookup"><span data-stu-id="2c203-p102">ADO most commonly opens a connection by using the **Connection** object **Open** method. The syntax for the **Open** method is shown here:</span></span>

```vb
Dim connection as New ADODB.Connection 
connection.Open ConnectionString, UserID, Password, OpenOptions
```

<span data-ttu-id="2c203-108">或者，也可以调用快捷技术 **Recordset.Open** 在一次操作中完成打开隐式连接并通过该连接发出命令的操作。</span><span class="sxs-lookup"><span data-stu-id="2c203-108">Alternatively, you can invoke a shortcut technique, **Recordset.Open**, to open an implicit connection and issue a command over that connection in one operation.</span></span> <span data-ttu-id="2c203-109">执行此操作有效连接字符串中将作为*ActiveConnection*参数传递给**Open**方法。</span><span class="sxs-lookup"><span data-stu-id="2c203-109">Do this by passing in a valid connection string as the *ActiveConnection* argument to the **Open** method.</span></span> <span data-ttu-id="2c203-110">下面是在 Visual Basic 中每个方法的语法：</span><span class="sxs-lookup"><span data-stu-id="2c203-110">Here is the syntax for each method in Visual Basic:</span></span>

```vb
Dim recordset as ADODB.Recordset 
Set recordset = New ADODB.Recordset 
recordset.Open Source, ActiveConnection, CursorType, LockType, Options
```

> [!NOTE]
> <span data-ttu-id="2c203-p104">[!注释] 什么时候应当使用 **Connection** 对象，什么时候应当使用 **Recordset.Open** 快捷技术？如果计划打开多个 **Recordset** ，或者要执行多个命令，请使用 **Connection** 对象。使用 **Recordset.Open** 快捷技术时，ADO 仍然会隐式创建连接。</span><span class="sxs-lookup"><span data-stu-id="2c203-p104">When should you use a **Connection** object vs. the **Recordset.Open** shortcut? Use the **Connection** object if you plan to open more than one **Recordset**, or when executing multiple commands. A connection is still created by ADO implicitly when you use the **Recordset.Open** shortcut.</span></span>


