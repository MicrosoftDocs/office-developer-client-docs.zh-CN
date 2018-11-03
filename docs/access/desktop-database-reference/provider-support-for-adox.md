---
title: 对 ADOX 的提供程序支持
TOCTitle: Provider support for ADOX
ms:assetid: 32ea3236-d69f-df94-1685-d8791aeb9e0f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249100(v=office.15)
ms:contentKeyID: 48544091
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bdd9ca9a2274f03f1592f73c3da5a6837101fda2
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947824"
---
# <a name="provider-support-for-adox"></a><span data-ttu-id="7c706-102">对 ADOX 的提供程序支持</span><span class="sxs-lookup"><span data-stu-id="7c706-102">Provider support for ADOX</span></span>


<span data-ttu-id="7c706-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7c706-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7c706-p101">ADOX 的某些功能不受支持，这取决于您的 OLE DB 数据提供程序。[OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md) 全面支持 ADOX。 [Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md)、[Microsoft OLE DB Provider for ODBC](microsoft-ole-db-provider-for-odbc.md) 或 [Microsoft OLE DB Provider for Oracle](microsoft-ole-db-provider-for-oracle.md) 不支持的功能在下面列出。任何其他 Microsoft OLE DB 提供程序不支持 ADOX。</span><span class="sxs-lookup"><span data-stu-id="7c706-p101">Certain features of ADOX are unsupported, depending upon your OLE DB data provider. ADOX is fully supported with the [OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md). The unsupported features with the [Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md), the [Microsoft OLE DB Provider for ODBC](microsoft-ole-db-provider-for-odbc.md), or the [Microsoft OLE DB Provider for Oracle](microsoft-ole-db-provider-for-oracle.md) are listed below. ADOX is not supported by any other Microsoft OLE DB providers.</span></span>

## <a name="microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="7c706-108">Microsoft OLE DB Provider for SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c706-108">Microsoft OLE DB Provider for SQL Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7c706-109">对象或集合</span><span class="sxs-lookup"><span data-stu-id="7c706-109">Object or Collection</span></span></p></th>
<th><p><span data-ttu-id="7c706-110">使用限制</span><span class="sxs-lookup"><span data-stu-id="7c706-110">Usage Restriction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c706-111"><strong>Catalog</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="7c706-111"><strong>Catalog</strong> object</span></span></p></td>
<td><p><span data-ttu-id="7c706-112"><strong>Create</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-112">The <strong>Create</strong> method is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-113"><strong>Tables</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="7c706-113"><strong>Tables</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-114">属性在对象创建之前可读写，而在引用现有对象时只读。</span><span class="sxs-lookup"><span data-stu-id="7c706-114">Properties are read/write prior to object creation, and read-only when referencing an existing object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-115"><strong>Views</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="7c706-115"><strong>Views</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-116"><strong>Views</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-116"><strong>Views</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-117"><strong>Procedures</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-117"><strong>Procedures</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-118"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-118">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-119"><strong>Procedure</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="7c706-119"><strong>Procedure</strong> object</span></span></p></td>
<td><p><span data-ttu-id="7c706-120"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-120">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-121"><strong>Keys</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-121"><strong>Keys</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-122"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-122">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-123"><strong>Users</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-123"><strong>Users</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-124"><strong>Users</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-124"><strong>Users</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-125"><strong>Groups</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-125"><strong>Groups</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-126"><strong>Groups</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-126"><strong>Groups</strong> is not supported.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="microsoft-ole-db-provider-for-odbc"></a><span data-ttu-id="7c706-127">Microsoft OLE DB Provider for ODBC</span><span class="sxs-lookup"><span data-stu-id="7c706-127">Microsoft OLE DB Provider for ODBC</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7c706-128">对象或集合</span><span class="sxs-lookup"><span data-stu-id="7c706-128">Object or Collection</span></span></p></th>
<th><p><span data-ttu-id="7c706-129">使用限制</span><span class="sxs-lookup"><span data-stu-id="7c706-129">Usage Restriction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c706-130"><strong>Catalog</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="7c706-130"><strong>Catalog</strong> object</span></span></p></td>
<td><p><span data-ttu-id="7c706-131"><strong>Create</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-131">The <strong>Create</strong> method is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-132"><strong>Tables</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-132"><strong>Tables</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-133"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。
</span><span class="sxs-lookup"><span data-stu-id="7c706-133">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span> <span data-ttu-id="7c706-134">属性在对象创建之前可读写，而在引用现有对象时只读。</span><span class="sxs-lookup"><span data-stu-id="7c706-134">Properties are read/write prior to object creation, and read-only when referencing an existing object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-135"><strong>Procedures</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="7c706-135"><strong>Procedures</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-136"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-136">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-137"><strong>Procedure</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="7c706-137"><strong>Procedure</strong> object</span></span></p></td>
<td><p><span data-ttu-id="7c706-138"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-138">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-139"><strong>Indexes</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-139"><strong>Indexes</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-140"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-140">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-141"><strong>Keys</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-141"><strong>Keys</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-142"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-142">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-143"><strong>Users</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-143"><strong>Users</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-144"><strong>Users</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-144"><strong>Users</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-145"><strong>Groups</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-145"><strong>Groups</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-146"><strong>Groups</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-146"><strong>Groups</strong> is not supported.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="microsoft-ole-db-provider-for-oracle"></a><span data-ttu-id="7c706-147">Microsoft OLE DB Provider for Oracle</span><span class="sxs-lookup"><span data-stu-id="7c706-147">Microsoft OLE DB Provider for Oracle</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7c706-148">对象或集合</span><span class="sxs-lookup"><span data-stu-id="7c706-148">Object or Collection</span></span></p></th>
<th><p><span data-ttu-id="7c706-149">使用限制</span><span class="sxs-lookup"><span data-stu-id="7c706-149">Usage Restriction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c706-150"><strong>Catalog</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="7c706-150"><strong>Catalog</strong> object</span></span></p></td>
<td><p><span data-ttu-id="7c706-151"><strong>Create</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-151">The <strong>Create</strong> method is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-152"><strong>Tables</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-152"><strong>Tables</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-153"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。
</span><span class="sxs-lookup"><span data-stu-id="7c706-153">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span> <span data-ttu-id="7c706-154">属性在对象创建之前可读写，而在引用现有对象时只读。</span><span class="sxs-lookup"><span data-stu-id="7c706-154">Properties are read/write prior to object creation, and read-only when referencing an existing object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-155"><strong>Views</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="7c706-155"><strong>Views</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-156"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-156">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-157"><strong>View</strong>对象</span><span class="sxs-lookup"><span data-stu-id="7c706-157"><strong>View</strong> object</span></span></p></td>
<td><p><span data-ttu-id="7c706-158"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-158">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-159"><strong>Procedures</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="7c706-159"><strong>Procedures</strong> object</span></span></p></td>
<td><p><span data-ttu-id="7c706-160"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-160">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-161"><strong>Procedure</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="7c706-161"><strong>Procedure</strong> object</span></span></p></td>
<td><p><span data-ttu-id="7c706-162"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-162">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-163"><strong>Indexes</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-163"><strong>Indexes</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-164"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-164">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-165"><strong>Keys</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-165"><strong>Keys</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-166"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-166">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c706-167"><strong>Users</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-167"><strong>Users</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-168"><strong>Users</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-168"><strong>Users</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c706-169"><strong>Groups</strong>集合</span><span class="sxs-lookup"><span data-stu-id="7c706-169"><strong>Groups</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="7c706-170"><strong>Groups</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="7c706-170"><strong>Groups</strong> is not supported.</span></span></p></td>
</tr>
</tbody>
</table>

