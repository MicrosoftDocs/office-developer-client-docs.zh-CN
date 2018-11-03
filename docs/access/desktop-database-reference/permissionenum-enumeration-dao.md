---
title: PermissionEnum 枚举 (DAO)
TOCTitle: PermissionEnum Enumeration
ms:assetid: dcce9940-f8a7-e915-1b69-05c341bea8cd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835373(v=office.15)
ms:contentKeyID: 48548147
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ed3abb0e3ff76ae19c6c19a3e2040b338e2b5ff3
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945864"
---
# <a name="permissionenum-enumeration-dao"></a><span data-ttu-id="c63cf-102">PermissionEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c63cf-102">PermissionEnum enumeration (DAO)</span></span>


<span data-ttu-id="c63cf-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c63cf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c63cf-104">与 **Permissions** 属性一起用来指定权限的类型。</span><span class="sxs-lookup"><span data-stu-id="c63cf-104">Used with the **Permissions** property to specify the type of permissions.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c63cf-105">名称</span><span class="sxs-lookup"><span data-stu-id="c63cf-105">Name</span></span></p></th>
<th><p><span data-ttu-id="c63cf-106">值</span><span class="sxs-lookup"><span data-stu-id="c63cf-106">Value</span></span></p></th>
<th><p><span data-ttu-id="c63cf-107">说明</span><span class="sxs-lookup"><span data-stu-id="c63cf-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c63cf-108">dbSecCreate</span><span class="sxs-lookup"><span data-stu-id="c63cf-108">dbSecCreate</span></span></p></td>
<td><p><span data-ttu-id="c63cf-109">1</span><span class="sxs-lookup"><span data-stu-id="c63cf-109">1</span></span></p></td>
<td><p><span data-ttu-id="c63cf-110">用户可以创建新文档（对于 Document 对象无效）。</span><span class="sxs-lookup"><span data-stu-id="c63cf-110">The user can create new documents (not valid for Document objects).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cf-111">dbSecDBAdmin</span><span class="sxs-lookup"><span data-stu-id="c63cf-111">dbSecDBAdmin</span></span></p></td>
<td><p><span data-ttu-id="c63cf-112">8</span><span class="sxs-lookup"><span data-stu-id="c63cf-112">8</span></span></p></td>
<td><p><span data-ttu-id="c63cf-113">用户可以复制数据库并更改数据库密码（对于 Document 对象无效）。</span><span class="sxs-lookup"><span data-stu-id="c63cf-113">The user can replicate a database and change the database password (not valid for Document objects).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cf-114">dbSecDBCreate</span><span class="sxs-lookup"><span data-stu-id="c63cf-114">dbSecDBCreate</span></span></p></td>
<td><p><span data-ttu-id="c63cf-115">1</span><span class="sxs-lookup"><span data-stu-id="c63cf-115">1</span></span></p></td>
<td><p><span data-ttu-id="c63cf-p101">用户可以创建新数据库。此选项仅对于工作组信息文件 (Systen.mdw) 中的 Databases 容器有效。此常量对于 Document 对象无效。</span><span class="sxs-lookup"><span data-stu-id="c63cf-p101">The user can create new databases. This option is valid only on the Databases container in the workgroup information file (Systen.mdw). This constant is not valid for Document objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cf-119">dbSecDBExclusive</span><span class="sxs-lookup"><span data-stu-id="c63cf-119">dbSecDBExclusive</span></span></p></td>
<td><p><span data-ttu-id="c63cf-120">4</span><span class="sxs-lookup"><span data-stu-id="c63cf-120">4</span></span></p></td>
<td><p><span data-ttu-id="c63cf-121">用户对数据库具有独占访问权限。</span><span class="sxs-lookup"><span data-stu-id="c63cf-121">The user has exclusive access to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cf-122">dbSecDBOpen</span><span class="sxs-lookup"><span data-stu-id="c63cf-122">dbSecDBOpen</span></span></p></td>
<td><p><span data-ttu-id="c63cf-123">2</span><span class="sxs-lookup"><span data-stu-id="c63cf-123">2</span></span></p></td>
<td><p><span data-ttu-id="c63cf-124">用户可以打开数据库。</span><span class="sxs-lookup"><span data-stu-id="c63cf-124">The user can open the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cf-125">dbSecDelete</span><span class="sxs-lookup"><span data-stu-id="c63cf-125">dbSecDelete</span></span></p></td>
<td><p><span data-ttu-id="c63cf-126">65536</span><span class="sxs-lookup"><span data-stu-id="c63cf-126">65536</span></span></p></td>
<td><p><span data-ttu-id="c63cf-127">用户可以删除对象。</span><span class="sxs-lookup"><span data-stu-id="c63cf-127">The user can delete the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cf-128">dbSecDeleteData</span><span class="sxs-lookup"><span data-stu-id="c63cf-128">dbSecDeleteData</span></span></p></td>
<td><p><span data-ttu-id="c63cf-129">128</span><span class="sxs-lookup"><span data-stu-id="c63cf-129">128</span></span></p></td>
<td><p><span data-ttu-id="c63cf-130">用户可以删除记录。</span><span class="sxs-lookup"><span data-stu-id="c63cf-130">The user can delete records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cf-131">dbSecFullAccess</span><span class="sxs-lookup"><span data-stu-id="c63cf-131">dbSecFullAccess</span></span></p></td>
<td><p><span data-ttu-id="c63cf-132">1048575</span><span class="sxs-lookup"><span data-stu-id="c63cf-132">1048575</span></span></p></td>
<td><p><span data-ttu-id="c63cf-133">用户对对象具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="c63cf-133">The user has full access to the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cf-134">dbSecInsertData</span><span class="sxs-lookup"><span data-stu-id="c63cf-134">dbSecInsertData</span></span></p></td>
<td><p><span data-ttu-id="c63cf-135">32</span><span class="sxs-lookup"><span data-stu-id="c63cf-135">32</span></span></p></td>
<td><p><span data-ttu-id="c63cf-136">用户可以添加记录。</span><span class="sxs-lookup"><span data-stu-id="c63cf-136">The user can add records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cf-137">dbSecNoAccess</span><span class="sxs-lookup"><span data-stu-id="c63cf-137">dbSecNoAccess</span></span></p></td>
<td><p><span data-ttu-id="c63cf-138">0</span><span class="sxs-lookup"><span data-stu-id="c63cf-138">0</span></span></p></td>
<td><p><span data-ttu-id="c63cf-139">用户无权访问对象（对于 Document 对象无效）。</span><span class="sxs-lookup"><span data-stu-id="c63cf-139">The user does not have access to the object (not valid for Document objects).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cf-140">dbSecReadDef</span><span class="sxs-lookup"><span data-stu-id="c63cf-140">dbSecReadDef</span></span></p></td>
<td><p><span data-ttu-id="c63cf-141">4</span><span class="sxs-lookup"><span data-stu-id="c63cf-141">4</span></span></p></td>
<td><p><span data-ttu-id="c63cf-142">用户可以读取表定义（包括列和索引信息）。</span><span class="sxs-lookup"><span data-stu-id="c63cf-142">The user can read the table definition, including column and index information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cf-143">dbSecReadSec</span><span class="sxs-lookup"><span data-stu-id="c63cf-143">dbSecReadSec</span></span></p></td>
<td><p><span data-ttu-id="c63cf-144">131072</span><span class="sxs-lookup"><span data-stu-id="c63cf-144">131072</span></span></p></td>
<td><p><span data-ttu-id="c63cf-145">用户可以读取对象的与安全有关的信息。</span><span class="sxs-lookup"><span data-stu-id="c63cf-145">The user can read the object's security-related information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cf-146">dbSecReplaceData</span><span class="sxs-lookup"><span data-stu-id="c63cf-146">dbSecReplaceData</span></span></p></td>
<td><p><span data-ttu-id="c63cf-147">64</span><span class="sxs-lookup"><span data-stu-id="c63cf-147">64</span></span></p></td>
<td><p><span data-ttu-id="c63cf-148">用户可以修改记录。</span><span class="sxs-lookup"><span data-stu-id="c63cf-148">The user can modify records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cf-149">dbSecRetrieveData</span><span class="sxs-lookup"><span data-stu-id="c63cf-149">dbSecRetrieveData</span></span></p></td>
<td><p><span data-ttu-id="c63cf-150">20</span><span class="sxs-lookup"><span data-stu-id="c63cf-150">20</span></span></p></td>
<td><p><span data-ttu-id="c63cf-151">用户可以从 Document 对象中检索数据。</span><span class="sxs-lookup"><span data-stu-id="c63cf-151">The user can retrieve data from the Document object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cf-152">dbSecWriteDef</span><span class="sxs-lookup"><span data-stu-id="c63cf-152">dbSecWriteDef</span></span></p></td>
<td><p><span data-ttu-id="c63cf-153">65548</span><span class="sxs-lookup"><span data-stu-id="c63cf-153">65548</span></span></p></td>
<td><p><span data-ttu-id="c63cf-154">用户可以修改或删除表定义（包括列和索引信息）。</span><span class="sxs-lookup"><span data-stu-id="c63cf-154">The user can modify or delete the table definition, including column and index information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cf-155">dbSecWriteOwner</span><span class="sxs-lookup"><span data-stu-id="c63cf-155">dbSecWriteOwner</span></span></p></td>
<td><p><span data-ttu-id="c63cf-156">524288</span><span class="sxs-lookup"><span data-stu-id="c63cf-156">524288</span></span></p></td>
<td><p><span data-ttu-id="c63cf-157">用户可以更改 Owner 属性设置。</span><span class="sxs-lookup"><span data-stu-id="c63cf-157">The user can change the Owner property setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cf-158">dbSecWriteSec</span><span class="sxs-lookup"><span data-stu-id="c63cf-158">dbSecWriteSec</span></span></p></td>
<td><p><span data-ttu-id="c63cf-159">262144</span><span class="sxs-lookup"><span data-stu-id="c63cf-159">262144</span></span></p></td>
<td><p><span data-ttu-id="c63cf-160">用户可以修改访问权限。</span><span class="sxs-lookup"><span data-stu-id="c63cf-160">The user can alter access permissions.</span></span></p></td>
</tr>
</tbody>
</table>

