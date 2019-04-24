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
# <a name="using-the-command-object-access"></a><span data-ttu-id="8eb64-102">使用 Command 对象 (Access)</span><span class="sxs-lookup"><span data-stu-id="8eb64-102">Using the Command object (Access)</span></span>


<span data-ttu-id="8eb64-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="8eb64-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8eb64-p101">在连接到数据源之后，需要针对它执行请求以获取结果集。ADO 将此类命令功能封装在 **Command** 对象中。</span><span class="sxs-lookup"><span data-stu-id="8eb64-p101">After connecting to a data source, you need to execute requests against it to obtain result sets. ADO encapsulates this type of command functionality in the **Command** object.</span></span>

<span data-ttu-id="8eb64-p102">使用 **Command** 对象，可以从提供程序请求任何类型的操作，前提是提供程序可以正确地解释命令字符串。数据提供程序一个常见的操作是查询数据库并在 **Recordset** 对象中返回记录。**Recordset** 随后将在本章和其他各章中讨论；现在，让我们将记录集视为用来存放和查看结果集的工具。与许多 ADO 对象一样，根据提供程序的功能，某些 **Command** 对象的集合、方法或属性可能会在被引用时产生错误。</span><span class="sxs-lookup"><span data-stu-id="8eb64-p102">You can use the **Command** object to request any type of operation from the provider, assuming that the provider can interpret the command string properly. A common operation for data providers is to query a database and return records in a **Recordset** object. **Recordset**s will be discussed later in this and other chapters; for now, think of them as tools to hold and view result sets. As with many ADO objects, depending on the functionality of the provider, some **Command** object collections, methods, or properties might generate errors when referenced.</span></span>

<span data-ttu-id="8eb64-p103">若要针对数据源执行命令，不必总是创建 **Command** 对象。可以针对 **Connection** 对象使用 **Execute** 方法或针对 **Recordset** 对象使用 **Open** 方法。但是，如果您需要在代码中重复使用某个命令，或者如果您需要在命令中传递详细的参数信息，则应当使用 **Command** 对象。本章稍后将更详细地介绍这些方案。</span><span class="sxs-lookup"><span data-stu-id="8eb64-p103">It is not always necessary to create a **Command** object to execute a command against a data source. You can use the **Execute** method on the **Connection** object or the **Open** method on the **Recordset** object. However, you should use a **Command** object if you need to reuse a command in your code or if you need to pass detailed parameter information with your command. These scenarios are covered in more detail later in this chapter.</span></span>

> [!NOTE]
> <span data-ttu-id="8eb64-114">某些 Command 可以返回二进制流或单个 Record（而非 Recordset）形式的结果集，但前提是提供程序支持此功能。</span><span class="sxs-lookup"><span data-stu-id="8eb64-114">Certain Commands can return a result set as a binary stream or as a single Record rather than as a Recordset, if this is supported by the provider.</span></span> <span data-ttu-id="8eb64-115">同样，某些 Command（例如，SQL 更新查询）根本不会返回任何结果集。</span><span class="sxs-lookup"><span data-stu-id="8eb64-115">Also, some Commands are not intended to return any result set at all (for example, a SQL Update query).</span></span> <span data-ttu-id="8eb64-116">本章将介绍最典型的方案，但是，本章执行的是可将结果返回到 Recordset 对象中的 Command。</span><span class="sxs-lookup"><span data-stu-id="8eb64-116">This chapter will cover the most typical scenario, however: executing Commands that return results into a Recordset object.</span></span> <span data-ttu-id="8eb64-117">有关将结果返回到 Record 或 Stream 的详细信息，请参阅[第 10 章：记录和流](chapter-10-records-and-streams.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb64-117">For more information about returning results into Records or Streams, see [Chapter 10: Records and Streams](chapter-10-records-and-streams.md).</span></span>

<span data-ttu-id="8eb64-118">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="8eb64-118">This section includes the following topics:</span></span>

- [<span data-ttu-id="8eb64-119">Command 对象概述</span><span class="sxs-lookup"><span data-stu-id="8eb64-119">Command object overview</span></span>](command-object-overview.md)
- [<span data-ttu-id="8eb64-120">创建和执行简单的命令</span><span class="sxs-lookup"><span data-stu-id="8eb64-120">Creating and executing a simple command</span></span>](creating-and-executing-a-simple-command.md)
- [<span data-ttu-id="8eb64-121">Command 对象参数</span><span class="sxs-lookup"><span data-stu-id="8eb64-121">Command object parameters</span></span>](command-object-parameters.md)
- [<span data-ttu-id="8eb64-122">使用 command 调用存储过程</span><span class="sxs-lookup"><span data-stu-id="8eb64-122">Calling a stored procedure with a command</span></span>](calling-a-stored-procedure-with-a-command.md)
- [<span data-ttu-id="8eb64-123">Named 命令</span><span class="sxs-lookup"><span data-stu-id="8eb64-123">Named commands</span></span>](named-commands.md)
