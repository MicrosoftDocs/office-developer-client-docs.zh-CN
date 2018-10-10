---
title: Using the Connection Object (Access)
TOCTitle: Using the Connection Object
ms:assetid: e8786411-2be4-8d75-9df7-e345d5a6a7e8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250177(v=office.15)
ms:contentKeyID: 48548423
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cd3e691258fe5950f40c36a1efcaed8e79810c7a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466723"
---
# <a name="using-the-connection-object-access"></a><span data-ttu-id="65465-102">Using the Connection Object (Access)</span><span class="sxs-lookup"><span data-stu-id="65465-102">Using the Connection Object (Access)</span></span>


<span data-ttu-id="65465-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="65465-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="65465-p101">**Connection** 对象表示与数据源的唯一会话。对于客户端/服务器数据库系统，该对象等效于与服务器的实际网络连接。根据提供程序所支持的功能， **Connection** 对象的某些集合、方法或属性可能不可用。</span><span class="sxs-lookup"><span data-stu-id="65465-p101">A **Connection** object represents a unique session with a data source. In the case of a client/server database system, it can be equivalent to an actual network connection to the server. Depending on the functionality supported by the provider, some collections, methods, or properties of a **Connection** object might not be available.</span></span>

<span data-ttu-id="65465-107">在打开 **Connection** 对象之前，必须定义有关数据源和连接类型的某些信息。</span><span class="sxs-lookup"><span data-stu-id="65465-107">Before opening a **Connection** object, you must define certain information about the data source and type of connection.</span></span> <span data-ttu-id="65465-108">**Connection**对象的**Open**方法的*ConnectionString*参数 — 或**Connection**对象的**ConnectionString**属性 — 通常包含大部分此信息。</span><span class="sxs-lookup"><span data-stu-id="65465-108">The *ConnectionString* parameter of the **Connection** object **Open** method — or the **ConnectionString** property on the **Connection** object — usually contains most of this information.</span></span> <span data-ttu-id="65465-109">连接字符串是用来定义参数的可变数量的字符串。</span><span class="sxs-lookup"><span data-stu-id="65465-109">A connection string is a string of characters that defines a variable number of arguments.</span></span> <span data-ttu-id="65465-110">参数中包含 **Connection** 对象执行其工作所必需的信息，一些参数是 ADO 必需的，而另一些参数是特定于提供程序的。</span><span class="sxs-lookup"><span data-stu-id="65465-110">The arguments — some required by ADO, but others provider-specific — contain information that the **Connection** object must have to carry out its work.</span></span> <span data-ttu-id="65465-111">用分号 （;） 分隔组成的*ConnectionString*参数的参数。</span><span class="sxs-lookup"><span data-stu-id="65465-111">The arguments that make up the *ConnectionString* parameter are separated with semicolons (;).</span></span>


> [!NOTE]
> <P><span data-ttu-id="65465-p103">还可以在连接字符串中指定 ODBC 数据源名称 (DSN) 或数据链接 (UDL) 文件。有关 DSN 的详细信息，请参阅<EM>《ODBC 程序员参考》</EM>第 1 部分中的“数据源”。有关 UDL 的详细信息，请参阅<EM>《OLE DB 程序员参考》</EM>中的“数据链接 API 概述”。</span><span class="sxs-lookup"><span data-stu-id="65465-p103">You can also specify an ODBC Data Source Name (DSN) or a Data Link (UDL) file in a connection string. For more information about DSNs, see Data Sources in Part 1 of the <EM>ODBC Programmer's Reference</EM>. For more information about UDLs, see Data Link API Overview in the <EM>OLE DB Programmer's Reference</EM>.</span></span></P>


