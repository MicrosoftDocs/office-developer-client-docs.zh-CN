---
title: 服务提供程序和组件
TOCTitle: Service Providers and Components
ms:assetid: e42d9c84-525a-4aca-01b2-88e3f2b0717f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250163(v=office.15)
ms:contentKeyID: 48548333
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bd75314cc3f1fbdb110b6c5647894887e400ca1e
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947628"
---
# <a name="service-providers-and-components"></a><span data-ttu-id="81e99-102">服务提供程序和组件</span><span class="sxs-lookup"><span data-stu-id="81e99-102">Service providers and components</span></span>


<span data-ttu-id="81e99-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="81e99-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="81e99-104">服务提供程序是一些组件，它们可以通过实现数据存储区在本地不支持的扩展接口来扩展数据提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="81e99-104">Service providers are components that extend the functionality of data providers by implementing extended interfaces that are not natively supported by the data store.</span></span>

<span data-ttu-id="81e99-105">Microsoft 数据访问提供允许单个专门的组件来实现离散*组件体系结构*功能较少的存储区上设置的数据库功能或"服务"。</span><span class="sxs-lookup"><span data-stu-id="81e99-105">Microsoft Data Access provides a *component architecture* that allows individual, specialized components to implement discrete sets of database functionality, or "services," on top of less capable stores.</span></span> <span data-ttu-id="81e99-106">因此，服务组件提供了一个可供任何应用程序在访问任意数据存储区时使用的公共实现，而不是强制每个数据存储区提供扩展功能的各自实现，也不强制通用应用程序在内部实现数据库功能。</span><span class="sxs-lookup"><span data-stu-id="81e99-106">Thus, rather than forcing each data store to provide its own implementation of extended functionality or forcing generic applications to implement database functionality internally, service components provide a common implementation that any application can use when accessing any data store.</span></span> <span data-ttu-id="81e99-107">某些功能可以由数据存储区在本地实现，某些功能可以通过普通组件来实现，这一情况对于应用程序是透明的。</span><span class="sxs-lookup"><span data-stu-id="81e99-107">The fact that some functionality is implemented natively by the data store and some through generic components is transparent to the application.</span></span>

<span data-ttu-id="81e99-p102">例如，游标引擎（如 Microsoft Cursor Service for OLE DB）就是一种服务组件，可以使用仅向前型的顺序存储区中的数据生成可滚动数据。ADO 常用的其他服务提供程序包括 Microsoft OLE DB Persistence Provider（用于将数据保存到文件）、Microsoft Data Shaping Service for OLE DB（用于分层 **Recordset**）和 Microsoft OLE DB Remoting Provider（用于调用远程计算机上的数据提供程序）。</span><span class="sxs-lookup"><span data-stu-id="81e99-p102">For example, a cursor engine, such as the Microsoft Cursor Service for OLE DB, is a service component that can consume data from a sequential, forward-only data store to produce scrollable data. Other service providers commonly used by ADO include the Microsoft OLE DB Persistence Provider (for saving data to a file), the Microsoft Data Shaping Service for OLE DB (for hierarchical **Recordsets**), and the Microsoft OLE DB Remoting Provider (for invoking data providers on a remote computer).</span></span>

<span data-ttu-id="81e99-110">有关服务提供程序和数据提供程序的详细信息，请参阅[附录 A：提供程序](appendix-a-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="81e99-110">For more information about service and data providers, see [Appendix A: Providers](appendix-a-providers.md).</span></span>

