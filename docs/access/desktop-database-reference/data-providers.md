---
title: 数据提供程序 （Access 桌面数据库参考 （英文）
TOCTitle: Data Providers
ms:assetid: c1e36245-4ece-4986-db30-dc4be3daa794
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249946(v=office.15)
ms:contentKeyID: 48547540
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd2f17bcc490031625cc8f6cd0ea6d369133fa06
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466386"
---
# <a name="data-providers"></a><span data-ttu-id="fa55c-102">数据提供程序</span><span class="sxs-lookup"><span data-stu-id="fa55c-102">Data Providers</span></span>


<span data-ttu-id="fa55c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="fa55c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="fa55c-p101">数据提供程序代表各种不同的数据源，例如 SQL 数据库、索引化序列文件、电子表格、文档存储和邮件文件。提供程序使用称为行集的公用抽象来统一公开数据。</span><span class="sxs-lookup"><span data-stu-id="fa55c-p101">Data providers represent diverse sources of data such as SQL databases, indexed-sequential files, spreadsheets, document stores, and mail files. Providers expose data uniformly using a common abstraction called the rowset.</span></span>

<span data-ttu-id="fa55c-p102">ADO 功能强大并且灵活易用，因为 ADO 可以连接到几种不同的数据提供程序，并且仍然公开相同的编程模型，无论任何给定的提供程序具有何种具体功能。但是，由于每种数据提供程序都是唯一的，因此应用程序与 ADO 交互的方式将因数据提供程序而异。</span><span class="sxs-lookup"><span data-stu-id="fa55c-p102">ADO is powerful and flexible because it can connect to any of several different data providers and still expose the same programming model, regardless of the specific features of any given provider. However, because each data provider is unique, how your application interacts with ADO will vary by data provider.</span></span>

<span data-ttu-id="fa55c-108">例如，用来访问 Microsoft SQL Server 数据库的 OLE DB Provider for SQL Server 与用来访问 Web 服务器上文件存储的 Microsoft OLE DB Provider for Internet Publishing 相比，二者的能力和功能存在很大差异。</span><span class="sxs-lookup"><span data-stu-id="fa55c-108">For example, the capabilities and features of the OLE DB Provider for SQL Server, which is used to access Microsoft SQL Server databases, are considerably different from those of the Microsoft OLE DB Provider for Internet Publishing, which is used to access file stores on a Web server.</span></span>
