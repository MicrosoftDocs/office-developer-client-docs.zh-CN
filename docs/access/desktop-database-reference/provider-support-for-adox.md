---
title: ADOX 的提供程序支持
TOCTitle: Provider support for ADOX
ms:assetid: 32ea3236-d69f-df94-1685-d8791aeb9e0f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249100(v=office.15)
ms:contentKeyID: 48544091
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a92ffe9b4b713518330d9dbfd9979d904a5abe8e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301097"
---
# <a name="provider-support-for-adox"></a>ADOX 的提供程序支持


**适用于**：Access 2013、Office 2013

ADOX 的某些功能不受支持，这取决于您的 OLE DB 数据提供程序。[OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md) 全面支持 ADOX。[Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md)、[Microsoft OLE DB Provider for ODBC](microsoft-ole-db-provider-for-odbc.md) 或 [Microsoft OLE DB Provider for Oracle](microsoft-ole-db-provider-for-oracle.md) 不支持的功能在下面列出。任何其他 Microsoft OLE DB 提供程序不支持 ADOX。

## <a name="microsoft-ole-db-provider-for-sql-server"></a>Microsoft OLE DB Provider for SQL Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>对象或集合</p></th>
<th><p>使用限制</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Catalog</strong> 对象</p></td>
<td><p><strong>Create</strong> 方法不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Tables</strong> 集合</p></td>
<td><p>属性在对象创建之前可读写，而在引用现有对象时只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Views</strong> 集合</p></td>
<td><p><strong>Views</strong> 不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Procedures</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Procedure</strong> 对象</p></td>
<td><p><strong>Command</strong> 属性不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Keys</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Users</strong> 集合</p></td>
<td><p><strong>Users</strong> 不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Groups</strong> 集合</p></td>
<td><p><strong>Groups</strong> 不受支持。</p></td>
</tr>
</tbody>
</table>


## <a name="microsoft-ole-db-provider-for-odbc"></a>Microsoft OLE DB Provider for ODBC

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>对象或集合</p></th>
<th><p>使用限制</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Catalog</strong> 对象</p></td>
<td><p><strong>Create</strong> 方法不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Tables</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。 属性在对象创建之前可读写，而在引用现有对象时只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Procedures</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Procedure</strong> 对象</p></td>
<td><p><strong>Command</strong> 属性不受支持。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Indexes</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Keys</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Users</strong> 集合</p></td>
<td><p><strong>Users</strong> 不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Groups</strong> 集合</p></td>
<td><p><strong>Groups</strong> 不受支持。</p></td>
</tr>
</tbody>
</table>


## <a name="microsoft-ole-db-provider-for-oracle"></a>Microsoft OLE DB Provider for Oracle

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>对象或集合</p></th>
<th><p>使用限制</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Catalog</strong> 对象</p></td>
<td><p><strong>Create</strong> 方法不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Tables</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。 属性在对象创建之前可读写，而在引用现有对象时只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Views</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>View</strong> 对象</p></td>
<td><p><strong>Command</strong> 属性不受支持。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Procedures</strong> 对象</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Procedure</strong> 对象</p></td>
<td><p><strong>Command</strong> 属性不受支持。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Indexes</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Keys</strong> 集合</p></td>
<td><p><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Users</strong> 集合</p></td>
<td><p><strong>Users</strong> 不受支持。</p></td>
</tr>
<tr class="even">
<td><p><strong>Groups</strong> 集合</p></td>
<td><p><strong>Groups</strong> 不受支持。</p></td>
</tr>
</tbody>
</table>

