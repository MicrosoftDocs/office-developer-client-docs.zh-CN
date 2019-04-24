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
# <a name="provider-support-for-adox"></a><span data-ttu-id="f3c59-102">ADOX 的提供程序支持</span><span class="sxs-lookup"><span data-stu-id="f3c59-102">Provider support for ADOX</span></span>


<span data-ttu-id="f3c59-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f3c59-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f3c59-p101">ADOX 的某些功能不受支持，这取决于您的 OLE DB 数据提供程序。[OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md) 全面支持 ADOX。[Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md)、[Microsoft OLE DB Provider for ODBC](microsoft-ole-db-provider-for-odbc.md) 或 [Microsoft OLE DB Provider for Oracle](microsoft-ole-db-provider-for-oracle.md) 不支持的功能在下面列出。任何其他 Microsoft OLE DB 提供程序不支持 ADOX。</span><span class="sxs-lookup"><span data-stu-id="f3c59-p101">Certain features of ADOX are unsupported, depending upon your OLE DB data provider. ADOX is fully supported with the [OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md). The unsupported features with the [Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md), the [Microsoft OLE DB Provider for ODBC](microsoft-ole-db-provider-for-odbc.md), or the [Microsoft OLE DB Provider for Oracle](microsoft-ole-db-provider-for-oracle.md) are listed below. ADOX is not supported by any other Microsoft OLE DB providers.</span></span>

## <a name="microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="f3c59-108">Microsoft OLE DB Provider for SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3c59-108">Microsoft OLE DB Provider for SQL Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f3c59-109">对象或集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-109">Object or Collection</span></span></p></th>
<th><p><span data-ttu-id="f3c59-110">使用限制</span><span class="sxs-lookup"><span data-stu-id="f3c59-110">Usage Restriction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-111"><strong>Catalog</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f3c59-111"><strong>Catalog</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f3c59-112"><strong>Create</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-112">The <strong>Create</strong> method is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-113"><strong>Tables</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-113"><strong>Tables</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-114">属性在对象创建之前可读写，而在引用现有对象时只读。</span><span class="sxs-lookup"><span data-stu-id="f3c59-114">Properties are read/write prior to object creation, and read-only when referencing an existing object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-115"><strong>Views</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-115"><strong>Views</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-116"><strong>Views</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-116"><strong>Views</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-117"><strong>Procedures</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-117"><strong>Procedures</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-118"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-118">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-119"><strong>Procedure</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f3c59-119"><strong>Procedure</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f3c59-120"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-120">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-121"><strong>Keys</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-121"><strong>Keys</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-122"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-122">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-123"><strong>Users</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-123"><strong>Users</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-124"><strong>Users</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-124"><strong>Users</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-125"><strong>Groups</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-125"><strong>Groups</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-126"><strong>Groups</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-126"><strong>Groups</strong> is not supported.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="microsoft-ole-db-provider-for-odbc"></a><span data-ttu-id="f3c59-127">Microsoft OLE DB Provider for ODBC</span><span class="sxs-lookup"><span data-stu-id="f3c59-127">Microsoft OLE DB Provider for ODBC</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f3c59-128">对象或集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-128">Object or Collection</span></span></p></th>
<th><p><span data-ttu-id="f3c59-129">使用限制</span><span class="sxs-lookup"><span data-stu-id="f3c59-129">Usage Restriction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-130"><strong>Catalog</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f3c59-130"><strong>Catalog</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f3c59-131"><strong>Create</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-131">The <strong>Create</strong> method is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-132"><strong>Tables</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-132"><strong>Tables</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-133"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-133">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span> <span data-ttu-id="f3c59-134">属性在对象创建之前可读写，而在引用现有对象时只读。</span><span class="sxs-lookup"><span data-stu-id="f3c59-134">Properties are read/write prior to object creation, and read-only when referencing an existing object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-135"><strong>Procedures</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-135"><strong>Procedures</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-136"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-136">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-137"><strong>Procedure</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f3c59-137"><strong>Procedure</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f3c59-138"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-138">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-139"><strong>Indexes</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-139"><strong>Indexes</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-140"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-140">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-141"><strong>Keys</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-141"><strong>Keys</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-142"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-142">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-143"><strong>Users</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-143"><strong>Users</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-144"><strong>Users</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-144"><strong>Users</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-145"><strong>Groups</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-145"><strong>Groups</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-146"><strong>Groups</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-146"><strong>Groups</strong> is not supported.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="microsoft-ole-db-provider-for-oracle"></a><span data-ttu-id="f3c59-147">Microsoft OLE DB Provider for Oracle</span><span class="sxs-lookup"><span data-stu-id="f3c59-147">Microsoft OLE DB Provider for Oracle</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f3c59-148">对象或集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-148">Object or Collection</span></span></p></th>
<th><p><span data-ttu-id="f3c59-149">使用限制</span><span class="sxs-lookup"><span data-stu-id="f3c59-149">Usage Restriction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-150"><strong>Catalog</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f3c59-150"><strong>Catalog</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f3c59-151"><strong>Create</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-151">The <strong>Create</strong> method is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-152"><strong>Tables</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-152"><strong>Tables</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-153"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-153">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span> <span data-ttu-id="f3c59-154">属性在对象创建之前可读写，而在引用现有对象时只读。</span><span class="sxs-lookup"><span data-stu-id="f3c59-154">Properties are read/write prior to object creation, and read-only when referencing an existing object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-155"><strong>Views</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-155"><strong>Views</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-156"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-156">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-157"><strong>View</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f3c59-157"><strong>View</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f3c59-158"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-158">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-159"><strong>Procedures</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f3c59-159"><strong>Procedures</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f3c59-160"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-160">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-161"><strong>Procedure</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f3c59-161"><strong>Procedure</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f3c59-162"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-162">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-163"><strong>Indexes</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-163"><strong>Indexes</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-164"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-164">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-165"><strong>Keys</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-165"><strong>Keys</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-166"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-166">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c59-167"><strong>Users</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-167"><strong>Users</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-168"><strong>Users</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-168"><strong>Users</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c59-169"><strong>Groups</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="f3c59-169"><strong>Groups</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="f3c59-170"><strong>Groups</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3c59-170"><strong>Groups</strong> is not supported.</span></span></p></td>
</tr>
</tbody>
</table>

