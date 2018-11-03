---
title: 第 2 章： 获取数据
TOCTitle: 'Chapter 2: Getting data'
ms:assetid: 72d097e1-9284-cc27-fd48-e6bbb6a2a543
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249465(v=office.15)
ms:contentKeyID: 48545619
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 729d7a74c8e1ead84810e82d608e4e9b37268a6b
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936999"
---
# <a name="chapter-2-getting-data"></a><span data-ttu-id="5a521-102">第 2 章： 获取数据</span><span class="sxs-lookup"><span data-stu-id="5a521-102">Chapter 2: Getting data</span></span>

<span data-ttu-id="5a521-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5a521-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5a521-p101">前一章介绍了在创建 ADO 应用程序时涉及的四个主要操作：获取数据、检查数据、编辑数据和更新数据。本章将重点介绍与第一个操作（获取数据）相关的概念的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5a521-p101">The preceding chapter introduced four primary operations involved in creating an ADO application: getting data, examining data, editing data, and updating data. This chapter will focus on the details of the concepts relevant to the first operation: getting data.</span></span>

<span data-ttu-id="5a521-p102">若干 ADO 对象可以在此操作中发挥作用。首先，需要使用 ADO **Connection** 对象（有时会隐式创建该对象）连接到数据源。然后，使用 ADO **Command** 对象（也可以隐式创建它）将指令传递给数据源，告诉它您希望做什么。在将命令传递给数据源并接收其响应后，通常将在 ADO **Recordset** 对象中显示相应结果。</span><span class="sxs-lookup"><span data-stu-id="5a521-p102">Several ADO objects can play a role in this operation. First you connect to the data source using an ADO **Connection** object (which at times will be created implicitly). Then you pass instructions to the data source about what you want to do using an ADO **Command** object (which also can be created implicitly). The result of passing a command to a data source and receiving its response usually will be represented in an ADO **Recordset** object.</span></span>

<span data-ttu-id="5a521-110">若要获取数据，应用程序必须与诸如 DBMS、文件存储或逗号分隔的文本文件这样的数据源进行通信。</span><span class="sxs-lookup"><span data-stu-id="5a521-110">To get data, your application must be in communication with a data source, such as a DBMS, a file store, or a comma-delimited text file.</span></span> <span data-ttu-id="5a521-111">此通信代表一个*连接*— 交换数据所必需的环境。</span><span class="sxs-lookup"><span data-stu-id="5a521-111">This communication represents a *connection* — the environment necessary for exchanging data.</span></span>

<span data-ttu-id="5a521-p104">ADO 对象模型用 **Connection** 对象来表示连接的概念 - 这是建立很多 ADO 功能的基础。 **Connection** 对象的用途是：</span><span class="sxs-lookup"><span data-stu-id="5a521-p104">The ADO object model represents the concept of a connection with the **Connection** object — the foundation upon which much ADO functionality is built. The purpose of a **Connection** object is to:</span></span>

- <span data-ttu-id="5a521-114">定义 ADO 在与数据源通信并创建会话时所需的信息。</span><span class="sxs-lookup"><span data-stu-id="5a521-114">Define the information ADO needs to communicate with data sources and create sessions.</span></span>

- <span data-ttu-id="5a521-115">定义会话的事务性功能。</span><span class="sxs-lookup"><span data-stu-id="5a521-115">Define the transactional capabilities of the session.</span></span>

- <span data-ttu-id="5a521-116">允许您针对数据源创建和执行命令。</span><span class="sxs-lookup"><span data-stu-id="5a521-116">Allow you to create and execute commands against the data source.</span></span>

- <span data-ttu-id="5a521-p105">提供有关以架构行集的形式设计基础数据源的信息。有关架构行集的详细信息，请参阅 [OpenSchema 方法](openschema-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="5a521-p105">Provide information about the design of the underlying data source in the form of schema rowsets. For more information about schema rowsets, see [OpenSchema Method](openschema-method-ado.md).</span></span>

<span data-ttu-id="5a521-119">本章包含以下主题：</span><span class="sxs-lookup"><span data-stu-id="5a521-119">This chapter covers the following topics:</span></span>

- [<span data-ttu-id="5a521-120">建立连接</span><span class="sxs-lookup"><span data-stu-id="5a521-120">Making a connection</span></span>](making-a-connection.md)
- [<span data-ttu-id="5a521-121">使用 connection 对象引用 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5a521-121">Using the connection object reference (ADO)</span></span>](using-the-connection-object-access.md)
- [<span data-ttu-id="5a521-122">使用 command 对象引用 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5a521-122">Using the command object reference (ADO)</span></span>](using-the-command-object-access.md)
- [<span data-ttu-id="5a521-123">将数据添加到 Recordset (ADO)</span><span class="sxs-lookup"><span data-stu-id="5a521-123">Adding data to a Recordset (ADO)</span></span>](adding-data-to-a-recordset.md)