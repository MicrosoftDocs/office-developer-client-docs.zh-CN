---
title: Using the Command Object (Access)
TOCTitle: Using the Command Object
ms:assetid: dab6f0dd-1efa-3a5c-b192-c6d6afcaabfb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250102(v=office.15)
ms:contentKeyID: 48548088
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 36d7bf1b39186eca841e417473e31e2bfd3a2dfc
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465988"
---
# <a name="using-the-command-object-access"></a><span data-ttu-id="2a439-102">Using the Command Object (Access)</span><span class="sxs-lookup"><span data-stu-id="2a439-102">Using the Command Object (Access)</span></span>


<span data-ttu-id="2a439-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2a439-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2a439-p101">在连接到数据源之后，需要针对它执行请求以获取结果集。ADO 将此类命令功能封装在 **Command** 对象中。</span><span class="sxs-lookup"><span data-stu-id="2a439-p101">After connecting to a data source, you need to execute requests against it to obtain result sets. ADO encapsulates this type of command functionality in the **Command** object.</span></span>

<span data-ttu-id="2a439-p102">使用 **Command** 对象，可以从提供程序请求任何类型的操作，前提是提供程序可以正确地解释命令字符串。数据提供程序一个常见的操作是查询数据库并在 **Recordset** 对象中返回记录。**Recordset** 随后将在本章和其他各章中讨论；现在，让我们将记录集视为用来存放和查看结果集的工具。与许多 ADO 对象一样，根据提供程序的功能，某些 **Command** 对象的集合、方法或属性可能会在被引用时产生错误。</span><span class="sxs-lookup"><span data-stu-id="2a439-p102">You can use the **Command** object to request any type of operation from the provider, assuming that the provider can interpret the command string properly. A common operation for data providers is to query a database and return records in a **Recordset** object. **Recordset**s will be discussed later in this and other chapters; for now, think of them as tools to hold and view result sets. As with many ADO objects, depending on the functionality of the provider, some **Command** object collections, methods, or properties might generate errors when referenced.</span></span>

<span data-ttu-id="2a439-p103">若要针对数据源执行命令，不必总是创建 **Command** 对象。可以针对 **Connection** 对象使用 **Execute** 方法或针对 **Recordset** 对象使用 **Open** 方法。但是，如果您需要在代码中重复使用某个命令，或者如果您需要在命令中传递详细的参数信息，则应当使用 **Command** 对象。本章稍后将更详细地介绍这些方案。</span><span class="sxs-lookup"><span data-stu-id="2a439-p103">It is not always necessary to create a **Command** object to execute a command against a data source. You can use the **Execute** method on the **Connection** object or the **Open** method on the **Recordset** object. However, you should use a **Command** object if you need to reuse a command in your code or if you need to pass detailed parameter information with your command. These scenarios are covered in more detail later in this chapter.</span></span>


> [!NOTE]
> <P><span data-ttu-id="2a439-p104">某些 <STRONG>Command</STRONG> 可以返回二进制流或单个 <STRONG>Record</STRONG>（而非 <STRONG>Recordset</STRONG>）形式的结果集，但前提是提供程序支持此功能。同样，某些 <STRONG>Command</STRONG>（例如，SQL 更新查询）根本不会返回任何结果集。本章将介绍最典型的方案，但是，本章执行的是可将结果返回到 <STRONG>Recordset</STRONG> 对象中的 <STRONG>Command</STRONG>。有关将结果返回到 <STRONG>Record</STRONG> 或 <STRONG>Stream</STRONG> 的详细信息，请参阅<A href="chapter-10-records-and-streams.md">第 10 章：记录和流</A>。</span><span class="sxs-lookup"><span data-stu-id="2a439-p104">Certain <STRONG>Command</STRONG>s can return a result set as a binary stream or as a single <STRONG>Record</STRONG> rather than as a <STRONG>Recordset</STRONG>, if this is supported by the provider. Also, some <STRONG>Command</STRONG>s are not intended to return any result set at all (for example, a SQL Update query). This chapter will cover the most typical scenario, however: executing <STRONG>Command</STRONG>s that return results into a <STRONG>Recordset</STRONG> object. For more information about returning results into <STRONG>Record</STRONG>s or <STRONG>Stream</STRONG>s, see <A href="chapter-10-records-and-streams.md">Chapter 10: Records and Streams</A>.</span></span></P>


