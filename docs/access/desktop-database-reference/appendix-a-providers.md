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
# <a name="appendix-a-providers"></a>附录 A：提供程序


**适用于**： Access 2013 |Office 2013


本节论述三种提供程序：数据提供程序、服务提供程序和服务组件。提供程序分为两类：提供数据的提供程序和提供服务的提供程序。*数据提供程序*拥有自己的数据并以表格形式向应用程序公开这些数据。*服务提供程序*生成并使用数据，增加 ADO 应用程序中的功能，从而对服务进行封装。可以将服务提供程序进一步定义为*服务组件*，服务组件必须与其他服务提供程序或组件结合使用。

## <a name="data-providers"></a>数据提供程序

ADO 功能强大而又灵活，因为它可以连接到若干个不同数据提供程序中的任何一个，并且仍然可以公开同一个编程模型，而不考虑给定提供程序的特定功能。

但是，由于每个数据提供程序都是唯一的，因此，应用程序与 ADO 之间的交互方式可能会根据数据提供程序的不同而略有差异。这种差异分为三类：

  - [ConnectionString](connectionstring-property-ado.md) 属性中的连接参数。

  - [Command](command-object-ado.md) 对象用法。

  - 提供程序特定的 [Recordset](recordset-object-ado.md) 行为。

下面列出了 Microsoft 当前提供的每个数据提供程序的详细信息。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>区域</p></th>
<th><p>主题</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ODBC 数据库</p></td>
<td><p><a href="microsoft-ole-db-provider-for-odbc.md">Microsoft OLE DB Provider for ODBC</a></p></td>
</tr>
<tr class="even">
<td><p>Microsoft 索引服务</p></td>
<td><p><a href="microsoft-ole-db-provider-for-microsoft-indexing-service.md">Microsoft OLE DB Provider for Microsoft Indexing Service</a></p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Active Directory Service</p></td>
<td><p><a href="microsoft-ole-db-provider-for-microsoft-active-directory-service.md">Microsoft OLE DB Provider for Microsoft Active Directory Service</a></p></td>
</tr>
<tr class="even">
<td><p>Microsoft Jet 数据库</p></td>
<td><p><a href="microsoft-ole-db-provider-for-microsoft-jet.md">OLE DB Provider for Microsoft Jet</a></p></td>
</tr>
<tr class="odd">
<td><p>Microsoft SQL Server</p></td>
<td><p><a href="microsoft-ole-db-provider-for-sql-server.md">Microsoft OLE DB Provider for SQL Server</a></p></td>
</tr>
<tr class="even">
<td><p>Oracle 数据库</p></td>
<td><p><a href="microsoft-ole-db-provider-for-oracle.md">Microsoft OLE DB Provider for Oracle</a></p></td>
</tr>
<tr class="odd">
<td><p>Internet 发布</p></td>
<td><p><a href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</a></p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-dynamic-properties"></a>提供程序特定的动态属性

[Connection](properties-collection-ado.md)、[Command](connection-object-ado.md) 和 [Recordset](command-object-ado.md) 对象的 [Properties](recordset-object-ado.md) 集合包含提供程序特定的动态属性。这些属性提供有关 ADO 支持的内置属性以外的提供程序特定功能的信息。

建立连接并创建这些对象后，请对对象的 [Properties](refresh-method-ado.md) 集合使用 **Refresh** 方法以获取提供程序特定的属性。有关这些动态属性的详细信息，请参阅提供程序文档和《OLE DB 程序员参考》。

## <a name="service-providers"></a>服务提供程序

若要使用服务提供程序，必须提供关键字。此外，还应该注意与每个服务提供程序关联的提供程序特定的动态属性。下面列出了与 Microsoft 当前提供的每个服务提供程序对应的提供程序特定的详细信息：

  - [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)

  - [Microsoft OLE DB Persistence Provider](microsoft-ole-db-persistence-provider-ado-service-provider.md)

  - [Microsoft OLE DB Remoting Provider](microsoft-ole-db-remoting-provider-ado-service-provider.md)

## <a name="service-components"></a>服务组件

[Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 服务组件补充了数据提供程序的游标支持功能。此外，该服务组件还需要使用一个关键字，且有动态属性。

有关提供程序的详细信息，请参阅 Microsoft Data Access Components SDK 中的 Microsoft OLE DB 文档，或者访问[数据平台开发人员中心（英文）](https://msdn.microsoft.com/data/default.aspx)。

## <a name="provider-commands"></a>提供程序命令

每个提供程序列出在这里，如果您的应用程序允许用户为提供程序命令输入的 SQL 语句，您必须始终验证用户输入并要小心使用有潜在危险的 SQL 语句，如，作为的一部分的可能的黑客攻击的用户输入。

