---
title: 数据提供程序 （Access 桌面数据库参考 （英文）
TOCTitle: Data Providers
ms:assetid: c1e36245-4ece-4986-db30-dc4be3daa794
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249946(v=office.15)
ms:contentKeyID: 48547540
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4eab9679b09b31b01250372df294af55729e9dd9
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25604538"
---
# <a name="data-providers"></a><span data-ttu-id="7b37c-102">数据提供程序</span><span class="sxs-lookup"><span data-stu-id="7b37c-102">Data Providers</span></span>


<span data-ttu-id="7b37c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7b37c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7b37c-p101">数据提供程序代表各种不同的数据源，例如 SQL 数据库、索引化序列文件、电子表格、文档存储和邮件文件。提供程序使用称为行集的公用抽象来统一公开数据。</span><span class="sxs-lookup"><span data-stu-id="7b37c-p101">Data providers represent diverse sources of data such as SQL databases, indexed-sequential files, spreadsheets, document stores, and mail files. Providers expose data uniformly using a common abstraction called the rowset.</span></span>

<span data-ttu-id="7b37c-p102">ADO 功能强大并且灵活易用，因为 ADO 可以连接到几种不同的数据提供程序，并且仍然公开相同的编程模型，无论任何给定的提供程序具有何种具体功能。但是，由于每种数据提供程序都是唯一的，因此应用程序与 ADO 交互的方式将因数据提供程序而异。</span><span class="sxs-lookup"><span data-stu-id="7b37c-p102">ADO is powerful and flexible because it can connect to any of several different data providers and still expose the same programming model, regardless of the specific features of any given provider. However, because each data provider is unique, how your application interacts with ADO will vary by data provider.</span></span>

<span data-ttu-id="7b37c-108"><<<<<<< 标头的示例的功能和特性的 OLE DB Provider for SQL Server，用来访问 Microsoft SQL Server 数据库，有很大差异的 Microsoft OLE DB Provider for Internet发布，用于访问文件存储在 Web 服务器上。</span><span class="sxs-lookup"><span data-stu-id="7b37c-108"><<<<<<< HEAD For example, the capabilities and features of the OLE DB Provider for SQL Server, which is used to access Microsoft SQL Server databases, are considerably different from those of the Microsoft OLE DB Provider for Internet Publishing, which is used to access file stores on a Web server.</span></span>
<span data-ttu-id="7b37c-109">=== 如的功能和特性的 OLE DB Provider for SQL Server，用来访问 Microsoft SQL Server 数据库，有很大差异的 Microsoft OLE DB Provider for Internet Publishing，用于访问web 服务器上的文件存储。</span><span class="sxs-lookup"><span data-stu-id="7b37c-109">======= For example, the capabilities and features of the OLE DB Provider for SQL Server, which is used to access Microsoft SQL Server databases, are considerably different from those of the Microsoft OLE DB Provider for Internet Publishing, which is used to access file stores on a web server.</span></span>
>>>>>>> <span data-ttu-id="7b37c-110">master</span><span class="sxs-lookup"><span data-stu-id="7b37c-110">master</span></span>

