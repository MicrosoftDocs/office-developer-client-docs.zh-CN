---
title: OLE DB 提供程序 （Access 桌面数据库参考 （英文）
TOCTitle: OLE DB providers
ms:assetid: ef412198-eac5-bf86-73fd-574e67276408
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250215(v=office.15)
ms:contentKeyID: 48548576
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e80df3dad65edb23e7fcd4e6828f2435df405e70
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947775"
---
# <a name="ole-db-providers"></a><span data-ttu-id="984e6-102">OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="984e6-102">OLE DB providers</span></span>


<span data-ttu-id="984e6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="984e6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="984e6-104">ADO 程序员指南 》[介绍](introduction-to-ado-programming.md)讨论 ADO 和 Microsoft 数据访问体系结构的其余部分之间的关系。</span><span class="sxs-lookup"><span data-stu-id="984e6-104">The ADO programmer's guide [Introduction](introduction-to-ado-programming.md) discusses the relationship between ADO and the rest of the Microsoft Data Access architecture.</span></span> <span data-ttu-id="984e6-105">OLE DB 定义了一组 COM 接口，用于向应用程序提供对存储在各种信息源中的数据的统一访问。</span><span class="sxs-lookup"><span data-stu-id="984e6-105">OLE DB defines a set of COM interfaces to provide applications with uniform access to data that is stored in diverse information sources.</span></span> <span data-ttu-id="984e6-106">此方法允许数据源通过一些接口来共享其数据，这些接口支持适用于数据源的众多 DBMS 功能。</span><span class="sxs-lookup"><span data-stu-id="984e6-106">This approach allows a data source to share its data through the interfaces that support the amount of DBMS functionality appropriate to the data source.</span></span> <span data-ttu-id="984e6-107">在设计上，OLE DB 的高性能结构基于它所使用的基于组件且非常灵活的服务模型。</span><span class="sxs-lookup"><span data-stu-id="984e6-107">By design, the high-performance architecture of OLE DB is based on its use of a flexible, component-based services model.</span></span> <span data-ttu-id="984e6-108">OLE DB 只需要完成特定任务所必需的组件，而不是在应用程序和数据之间建立规定数量的中间层。</span><span class="sxs-lookup"><span data-stu-id="984e6-108">Rather than having a prescribed number of intermediary layers between the application and the data, OLE DB requires only as many components as are needed to accomplish a particular task.</span></span>

<span data-ttu-id="984e6-p102">例如，假设用户要运行查询，请考虑下面的方案：</span><span class="sxs-lookup"><span data-stu-id="984e6-p102">For example, suppose a user wants to run a query. Consider the following scenarios:</span></span>

  - <span data-ttu-id="984e6-p103">数据驻留在关系数据库中，当前具有 ODBC 驱动程序，但是没有本机 OLE DB 提供程序：应用程序使用 ADO 与 OLE DB Provider for ODBC 联系，OLE DB Provider for ODBC 随后会加载相应的 ODBC 驱动程序。该驱动程序会向 DBMS 传递 SQL 语句，DBMS 随后会对数据进行检索。</span><span class="sxs-lookup"><span data-stu-id="984e6-p103">The data resides in a relational database for which there currently exists an ODBC driver but no native OLE DB provider: The application uses ADO to talk to the OLE DB Provider for ODBC, which then loads the appropriate ODBC driver. The driver passes the SQL statement to the DBMS, which retrieves the data.</span></span>

  - <span data-ttu-id="984e6-p104">数据驻留 Microsoft SQL Server 中，具有本机 OLE DB 提供程序：应用程序使用 ADO 直接与 OLE DB Provider for Microsoft SQL Server 联系，而不需要媒介。</span><span class="sxs-lookup"><span data-stu-id="984e6-p104">The data resides in Microsoft SQL Server for which there is a native OLE DB provider: The application uses ADO to talk directly to the OLE DB Provider for Microsoft SQL Server. No intermediaries are required.</span></span>

  - <span data-ttu-id="984e6-115">数据驻留在 Microsoft Exchange Server 中，具有 OLE DB 提供程序，但是 OLE DB 提供程序不公开用于处理 SQL 查询的引擎：应用程序使用 ADO 与 OLE DB Provider for Microsoft Exchange 联系并调用 OLE DB 查询处理器组件来处理查询。</span><span class="sxs-lookup"><span data-stu-id="984e6-115">The data resides in Microsoft Exchange Server, for which there is an OLE DB provider but which does not expose an engine to process SQL queries: The application uses ADO to talk to the OLE DB Provider for Microsoft Exchange and calls upon an OLE DB query processor component to handle the querying.</span></span>

  - <span data-ttu-id="984e6-116">数据以文档的形式驻留在 Microsoft NTFS 文件系统中：通过 Microsoft 索引服务使用本机 OLE DB 提供程序来访问数据，Microsoft 索引服务对文件系统中文档的内容和属性编制索引，从而提高内容搜索的效率。</span><span class="sxs-lookup"><span data-stu-id="984e6-116">The data resides in the Microsoft NTFS file system in the form of documents: Data is accessed by using a native OLE DB provider over Microsoft Indexing Service, which indexes the content and properties of documents in the file system to enable efficient content searches.</span></span>

<span data-ttu-id="984e6-p105">在前面的所有示例中，应用程序都可以查询数据，用最少的组件来满足用户的要求。在每种情况下，都是在需要时才使用额外的组件，而且仅调用必需的组件。在使用 OLE DB 时，这种按需加载可重复使用、可共享的组件会大大提高性能。</span><span class="sxs-lookup"><span data-stu-id="984e6-p105">In all of the preceding examples, the application can query the data. The user's needs are met with a minimum number of components. In each case, additional components are used only if needed, and only the required components are invoked. This demand-loading of reusable and shareable components greatly contributes to high performance when OLE DB is used.</span></span>

<span data-ttu-id="984e6-p106">提供程序可分两类：提供数据的提供程序和提供服务的提供程序。[数据提供程序](data-providers.md)拥有自己的数据，并将数据以表格形式向您的应用程序公开。[服务提供程序](service-providers-and-components.md)通过生成和使用数据并在 ADO 应用程序中增加功能来封装服务。还可以将服务提供程序进一步定义为[服务组件](service-providers-and-components.md)，服务组件必须与其他服务提供程序或组件协同工作。</span><span class="sxs-lookup"><span data-stu-id="984e6-p106">Providers fall into two categories: those providing data and those providing services. A [data provider](data-providers.md) owns its own data and exposes it in tabular form to your application. A [service provider](service-providers-and-components.md) encapsulates a service by producing and consuming data, augmenting features in your ADO applications. A service provider may also be further defined as a [service component](service-providers-and-components.md), which must work in conjunction with other service providers or components.</span></span>

<span data-ttu-id="984e6-125">ADO 为各种 OLE DB 提供程序提供一致的更高级别的接口。</span><span class="sxs-lookup"><span data-stu-id="984e6-125">ADO provides a consistent, higher level interface to the various OLE DB providers.</span></span>

<span data-ttu-id="984e6-126">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="984e6-126">This section includes the following topics:</span></span>

- [<span data-ttu-id="984e6-127">数据提供程序</span><span class="sxs-lookup"><span data-stu-id="984e6-127">Data Providers</span></span>](data-providers.md)

- [<span data-ttu-id="984e6-128">服务提供程序和组件</span><span class="sxs-lookup"><span data-stu-id="984e6-128">Service Providers and Components</span></span>](service-providers-and-components.md)