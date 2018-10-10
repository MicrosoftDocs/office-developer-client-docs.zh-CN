---
title: 对 ADOX 的提供程序支持
TOCTitle: Provider Support for ADOX
ms:assetid: 32ea3236-d69f-df94-1685-d8791aeb9e0f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249100(v=office.15)
ms:contentKeyID: 48544091
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3d55ae14d124bfad7f8abbfcf3d94398ea92d792
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468688"
---
# <a name="provider-support-for-adox"></a><span data-ttu-id="9314b-102">对 ADOX 的提供程序支持</span><span class="sxs-lookup"><span data-stu-id="9314b-102">Provider Support for ADOX</span></span>


<span data-ttu-id="9314b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9314b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9314b-p101">ADOX 的某些功能不受支持，这取决于您的 OLE DB 数据提供程序。[OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md) 全面支持 ADOX。 [Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md)、[Microsoft OLE DB Provider for ODBC](microsoft-ole-db-provider-for-odbc.md) 或 [Microsoft OLE DB Provider for Oracle](microsoft-ole-db-provider-for-oracle.md) 不支持的功能在下面列出。任何其他 Microsoft OLE DB 提供程序不支持 ADOX。</span><span class="sxs-lookup"><span data-stu-id="9314b-p101">Certain features of ADOX are unsupported, depending upon your OLE DB data provider. ADOX is fully supported with the [OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md). The unsupported features with the [Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md), the [Microsoft OLE DB Provider for ODBC](microsoft-ole-db-provider-for-odbc.md), or the [Microsoft OLE DB Provider for Oracle](microsoft-ole-db-provider-for-oracle.md) are listed below. ADOX is not supported by any other Microsoft OLE DB providers.</span></span>

## <a name="microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="9314b-108">Microsoft OLE DB Provider for SQL Server</span><span class="sxs-lookup"><span data-stu-id="9314b-108">Microsoft OLE DB Provider for SQL Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9314b-109">对象或集合</span><span class="sxs-lookup"><span data-stu-id="9314b-109">Object or Collection</span></span></p></th>
<th><p><span data-ttu-id="9314b-110">使用限制</span><span class="sxs-lookup"><span data-stu-id="9314b-110">Usage Restriction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9314b-111"><strong>Catalog</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="9314b-111"><strong>Catalog</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9314b-112"><strong>Create</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-112">The <strong>Create</strong> method is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-113"><strong>Tables</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="9314b-113"><strong>Tables</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-114">属性在对象创建之前可读写，而在引用现有对象时只读。</span><span class="sxs-lookup"><span data-stu-id="9314b-114">Properties are read/write prior to object creation, and read-only when referencing an existing object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-115"><strong>Views</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="9314b-115"><strong>Views</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-116"><strong>Views</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-116"><strong>Views</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-117"><strong>Procedures</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-117"><strong>Procedures</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-118"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-118">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-119"><strong>Procedure</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="9314b-119"><strong>Procedure</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9314b-120"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-120">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-121"><strong>Keys</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-121"><strong>Keys</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-122"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-122">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-123"><strong>Users</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-123"><strong>Users</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-124"><strong>Users</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-124"><strong>Users</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-125"><strong>Groups</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-125"><strong>Groups</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-126"><strong>Groups</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-126"><strong>Groups</strong> is not supported.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="microsoft-ole-db-provider-for-odbc"></a><span data-ttu-id="9314b-127">Microsoft OLE DB Provider for ODBC</span><span class="sxs-lookup"><span data-stu-id="9314b-127">Microsoft OLE DB Provider for ODBC</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9314b-128">对象或集合</span><span class="sxs-lookup"><span data-stu-id="9314b-128">Object or Collection</span></span></p></th>
<th><p><span data-ttu-id="9314b-129">使用限制</span><span class="sxs-lookup"><span data-stu-id="9314b-129">Usage Restriction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9314b-130"><strong>Catalog</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="9314b-130"><strong>Catalog</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9314b-131"><strong>Create</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-131">The <strong>Create</strong> method is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-132"><strong>Tables</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-132"><strong>Tables</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-133"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。
</span><span class="sxs-lookup"><span data-stu-id="9314b-133">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span> <span data-ttu-id="9314b-134">属性在对象创建之前可读写，而在引用现有对象时只读。</span><span class="sxs-lookup"><span data-stu-id="9314b-134">Properties are read/write prior to object creation, and read-only when referencing an existing object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-135"><strong>Procedures</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="9314b-135"><strong>Procedures</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-136"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-136">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-137"><strong>Procedure</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="9314b-137"><strong>Procedure</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9314b-138"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-138">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-139"><strong>Indexes</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-139"><strong>Indexes</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-140"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-140">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-141"><strong>Keys</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-141"><strong>Keys</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-142"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-142">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-143"><strong>Users</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-143"><strong>Users</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-144"><strong>Users</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-144"><strong>Users</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-145"><strong>Groups</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-145"><strong>Groups</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-146"><strong>Groups</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-146"><strong>Groups</strong> is not supported.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="microsoft-ole-db-provider-for-oracle"></a><span data-ttu-id="9314b-147">Microsoft OLE DB Provider for Oracle</span><span class="sxs-lookup"><span data-stu-id="9314b-147">Microsoft OLE DB Provider for Oracle</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9314b-148">对象或集合</span><span class="sxs-lookup"><span data-stu-id="9314b-148">Object or Collection</span></span></p></th>
<th><p><span data-ttu-id="9314b-149">使用限制</span><span class="sxs-lookup"><span data-stu-id="9314b-149">Usage Restriction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9314b-150"><strong>Catalog</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="9314b-150"><strong>Catalog</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9314b-151"><strong>Create</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-151">The <strong>Create</strong> method is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-152"><strong>Tables</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-152"><strong>Tables</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-153"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。
</span><span class="sxs-lookup"><span data-stu-id="9314b-153">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span> <span data-ttu-id="9314b-154">属性在对象创建之前可读写，而在引用现有对象时只读。</span><span class="sxs-lookup"><span data-stu-id="9314b-154">Properties are read/write prior to object creation, and read-only when referencing an existing object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-155"><strong>Views</strong> 集合</span><span class="sxs-lookup"><span data-stu-id="9314b-155"><strong>Views</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-156"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-156">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-157"><strong>View</strong>对象</span><span class="sxs-lookup"><span data-stu-id="9314b-157"><strong>View</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9314b-158"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-158">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-159"><strong>Procedures</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="9314b-159"><strong>Procedures</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9314b-160"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-160">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-161"><strong>Procedure</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="9314b-161"><strong>Procedure</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9314b-162"><strong>Command</strong> 属性不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-162">The <strong>Command</strong> property is not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-163"><strong>Indexes</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-163"><strong>Indexes</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-164"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-164">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-165"><strong>Keys</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-165"><strong>Keys</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-166"><strong>Append</strong> 和 <strong>Delete</strong> 方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-166">The <strong>Append</strong> and <strong>Delete</strong> methods are not supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9314b-167"><strong>Users</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-167"><strong>Users</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-168"><strong>Users</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-168"><strong>Users</strong> is not supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9314b-169"><strong>Groups</strong>集合</span><span class="sxs-lookup"><span data-stu-id="9314b-169"><strong>Groups</strong> collection</span></span></p></td>
<td><p><span data-ttu-id="9314b-170"><strong>Groups</strong> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="9314b-170"><strong>Groups</strong> is not supported.</span></span></p></td>
</tr>
</tbody>
</table>

