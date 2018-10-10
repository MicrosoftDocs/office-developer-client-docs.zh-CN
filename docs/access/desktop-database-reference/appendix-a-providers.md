---
title: 附录 A：提供程序
TOCTitle: 'Appendix A: Providers'
ms:assetid: b3f92279-8d66-ad59-71c4-c0448168125a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249857(v=office.15)
ms:contentKeyID: 48547207
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: dbd9536edd15f923af85f2fadad8b696077af4a4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468050"
---
# <a name="appendix-a-providers"></a><span data-ttu-id="c1f9d-102">附录 A：提供程序</span><span class="sxs-lookup"><span data-stu-id="c1f9d-102">Appendix A: Providers</span></span>


<span data-ttu-id="c1f9d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c1f9d-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="c1f9d-p101">本节论述三种提供程序：数据提供程序、服务提供程序和服务组件。提供程序分为两类：提供数据的提供程序和提供服务的提供程序。*数据提供程序*拥有自己的数据并以表格形式向应用程序公开这些数据。*服务提供程序*生成并使用数据，增加 ADO 应用程序中的功能，从而对服务进行封装。可以将服务提供程序进一步定义为*服务组件*，服务组件必须与其他服务提供程序或组件结合使用。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-p101">This section addresses three kinds of providers: data providers, service providers, and service components. Providers fall into two categories: those providing data and those providing services. A *data provider* owns its own data and exposes it in tabular form to your application. A *service provider* encapsulates a service by producing and consuming data, augmenting features in your ADO applications. A service provider may also be further defined as a *service component*, which must work in conjunction with other service providers or components.</span></span>

## <a name="data-providers"></a><span data-ttu-id="c1f9d-109">数据提供程序</span><span class="sxs-lookup"><span data-stu-id="c1f9d-109">Data Providers</span></span>

<span data-ttu-id="c1f9d-110">ADO 功能强大而又灵活，因为它可以连接到若干个不同数据提供程序中的任何一个，并且仍然可以公开同一个编程模型，而不考虑给定提供程序的特定功能。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-110">ADO is powerful and flexible because it can connect to any of several different data providers and still expose the same programming model, regardless of the specific features of any given provider.</span></span>

<span data-ttu-id="c1f9d-p102">但是，由于每个数据提供程序都是唯一的，因此，应用程序与 ADO 之间的交互方式可能会根据数据提供程序的不同而略有差异。这种差异分为三类：</span><span class="sxs-lookup"><span data-stu-id="c1f9d-p102">However, because each data provider is unique, how your application interacts with ADO will vary slightly by data provider. The differences usually fall into one of three categories:</span></span>

  - <span data-ttu-id="c1f9d-113">[ConnectionString](connectionstring-property-ado.md) 属性中的连接参数。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-113">Connection parameters in the [ConnectionString](connectionstring-property-ado.md) property.</span></span>

  - <span data-ttu-id="c1f9d-114">[Command](command-object-ado.md) 对象用法。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-114">[Command](command-object-ado.md) object usage.</span></span>

  - <span data-ttu-id="c1f9d-115">提供程序特定的 [Recordset](recordset-object-ado.md) 行为。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-115">Provider-specific [Recordset](recordset-object-ado.md) behavior.</span></span>

<span data-ttu-id="c1f9d-116">下面列出了 Microsoft 当前提供的每个数据提供程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-116">Details for each of the data providers currently available from Microsoft are listed as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c1f9d-117">区域</span><span class="sxs-lookup"><span data-stu-id="c1f9d-117">Area</span></span></p></th>
<th><p><span data-ttu-id="c1f9d-118">主题</span><span class="sxs-lookup"><span data-stu-id="c1f9d-118">Topic</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1f9d-119">ODBC 数据库</span><span class="sxs-lookup"><span data-stu-id="c1f9d-119">ODBC databases</span></span></p></td>
<td><p><span data-ttu-id="c1f9d-120"><a href="microsoft-ole-db-provider-for-odbc.md">Microsoft OLE DB Provider for ODBC</a></span><span class="sxs-lookup"><span data-stu-id="c1f9d-120"><a href="microsoft-ole-db-provider-for-odbc.md">Microsoft OLE DB Provider for ODBC</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1f9d-121">Microsoft 索引服务</span><span class="sxs-lookup"><span data-stu-id="c1f9d-121">Microsoft Indexing Service</span></span></p></td>
<td><p><span data-ttu-id="c1f9d-122"><a href="microsoft-ole-db-provider-for-microsoft-indexing-service.md">Microsoft OLE DB Provider for Microsoft Indexing Service</a></span><span class="sxs-lookup"><span data-stu-id="c1f9d-122"><a href="microsoft-ole-db-provider-for-microsoft-indexing-service.md">Microsoft OLE DB Provider for Microsoft Indexing Service</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1f9d-123">Microsoft Active Directory Service</span><span class="sxs-lookup"><span data-stu-id="c1f9d-123">Microsoft Active Directory Service</span></span></p></td>
<td><p><span data-ttu-id="c1f9d-124"><a href="microsoft-ole-db-provider-for-microsoft-active-directory-service.md">Microsoft OLE DB Provider for Microsoft Active Directory Service</a></span><span class="sxs-lookup"><span data-stu-id="c1f9d-124"><a href="microsoft-ole-db-provider-for-microsoft-active-directory-service.md">Microsoft OLE DB Provider for Microsoft Active Directory Service</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1f9d-125">Microsoft Jet 数据库</span><span class="sxs-lookup"><span data-stu-id="c1f9d-125">Microsoft Jet databases</span></span></p></td>
<td><p><span data-ttu-id="c1f9d-126"><a href="microsoft-ole-db-provider-for-microsoft-jet.md">OLE DB Provider for Microsoft Jet</a></span><span class="sxs-lookup"><span data-stu-id="c1f9d-126"><a href="microsoft-ole-db-provider-for-microsoft-jet.md">OLE DB Provider for Microsoft Jet</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1f9d-127">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="c1f9d-127">Microsoft SQL Server</span></span></p></td>
<td><p><span data-ttu-id="c1f9d-128"><a href="microsoft-ole-db-provider-for-sql-server.md">Microsoft OLE DB Provider for SQL Server</a></span><span class="sxs-lookup"><span data-stu-id="c1f9d-128"><a href="microsoft-ole-db-provider-for-sql-server.md">Microsoft OLE DB Provider for SQL Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1f9d-129">Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="c1f9d-129">Oracle databases</span></span></p></td>
<td><p><span data-ttu-id="c1f9d-130"><a href="microsoft-ole-db-provider-for-oracle.md">Microsoft OLE DB Provider for Oracle</a></span><span class="sxs-lookup"><span data-stu-id="c1f9d-130"><a href="microsoft-ole-db-provider-for-oracle.md">Microsoft OLE DB Provider for Oracle</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1f9d-131">Internet 发布</span><span class="sxs-lookup"><span data-stu-id="c1f9d-131">Internet Publishing</span></span></p></td>
<td><p><span data-ttu-id="c1f9d-132"><a href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</a></span><span class="sxs-lookup"><span data-stu-id="c1f9d-132"><a href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</a></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-dynamic-properties"></a><span data-ttu-id="c1f9d-133">提供程序特定的动态属性</span><span class="sxs-lookup"><span data-stu-id="c1f9d-133">Provider-Specific Dynamic Properties</span></span>

<span data-ttu-id="c1f9d-p103">[Connection](properties-collection-ado.md)、[Command](connection-object-ado.md) 和 [Recordset](command-object-ado.md) 对象的 [Properties](recordset-object-ado.md) 集合包含提供程序特定的动态属性。这些属性提供有关 ADO 支持的内置属性以外的提供程序特定功能的信息。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-p103">The [Properties](properties-collection-ado.md) collections of the [Connection](connection-object-ado.md), [Command](command-object-ado.md), and [Recordset](recordset-object-ado.md) objects include dynamic properties specific to the provider. These properties provide information about functionality specific to the provider beyond the built-in properties that ADO supports.</span></span>

<span data-ttu-id="c1f9d-p104">建立连接并创建这些对象后，请对对象的 [Properties](refresh-method-ado.md) 集合使用 **Refresh** 方法以获取提供程序特定的属性。有关这些动态属性的详细信息，请参阅提供程序文档和《OLE DB 程序员参考》。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-p104">After establishing the connection and creating these objects, use the [Refresh](refresh-method-ado.md) method on the object's **Properties** collection to obtain the provider-specific properties. Refer to the provider documentation and the OLE DB Programmer's Reference for detailed information about these dynamic properties.</span></span>

## <a name="service-providers"></a><span data-ttu-id="c1f9d-138">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="c1f9d-138">Service Providers</span></span>

<span data-ttu-id="c1f9d-p105">若要使用服务提供程序，必须提供关键字。此外，还应该注意与每个服务提供程序关联的提供程序特定的动态属性。下面列出了与 Microsoft 当前提供的每个服务提供程序对应的提供程序特定的详细信息：</span><span class="sxs-lookup"><span data-stu-id="c1f9d-p105">To use a service provider, you must supply a keyword. You should also be aware of the provider-specific dynamic properties associated with each service provider. Provider-specific details are listed for each of the service providers currently available from Microsoft:</span></span>

  - [<span data-ttu-id="c1f9d-142">Microsoft Data Shaping Service for OLE DB</span><span class="sxs-lookup"><span data-stu-id="c1f9d-142">Microsoft Data Shaping Service for OLE DB</span></span>](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)

  - [<span data-ttu-id="c1f9d-143">Microsoft OLE DB Persistence Provider</span><span class="sxs-lookup"><span data-stu-id="c1f9d-143">Microsoft OLE DB Persistence Provider</span></span>](microsoft-ole-db-persistence-provider-ado-service-provider.md)

  - [<span data-ttu-id="c1f9d-144">Microsoft OLE DB Remoting Provider</span><span class="sxs-lookup"><span data-stu-id="c1f9d-144">Microsoft OLE DB Remoting Provider</span></span>](microsoft-ole-db-remoting-provider-ado-service-provider.md)

## <a name="service-components"></a><span data-ttu-id="c1f9d-145">服务组件</span><span class="sxs-lookup"><span data-stu-id="c1f9d-145">Service Components</span></span>

<span data-ttu-id="c1f9d-p106">[Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 服务组件补充了数据提供程序的游标支持功能。此外，该服务组件还需要使用一个关键字，且有动态属性。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-p106">The [Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) service component supplements the cursor support functions of data providers. It also requires a keyword and has dynamic properties.</span></span>

<span data-ttu-id="c1f9d-148">有关提供程序的详细信息，请参阅 Microsoft Data Access Components SDK 中的 Microsoft OLE DB 文档，或者访问[数据平台开发人员中心（英文）](https://msdn.microsoft.com/data/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-148">For more information about providers, see the documentation for Microsoft OLE DB in the Microsoft Data Access Components SDK or visit the [Data Platform Developer Center](https://msdn.microsoft.com/data/default.aspx).</span></span>

## <a name="provider-commands"></a><span data-ttu-id="c1f9d-149">提供程序命令</span><span class="sxs-lookup"><span data-stu-id="c1f9d-149">Provider Commands</span></span>

<span data-ttu-id="c1f9d-150">每个提供程序列出在这里，如果您的应用程序允许用户为提供程序命令输入的 SQL 语句，您必须始终验证用户输入并要小心使用有潜在危险的 SQL 语句，如，作为的一部分的可能的黑客攻击的用户输入。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-150">For each provider listed here, if your applications allow users to enter SQL statements as the provider commands, you must always validate the user input and be vigilant of possible hacker attacks using potentially dangerous SQL statement, such as, , as part of the user input.</span></span>

