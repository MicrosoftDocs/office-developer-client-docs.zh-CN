---
title: PermissionEnum 枚举 (DAO)
TOCTitle: PermissionEnum Enumeration
ms:assetid: dcce9940-f8a7-e915-1b69-05c341bea8cd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835373(v=office.15)
ms:contentKeyID: 48548147
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8d4f6741bd6203dbdeffb364650b5e3550ea8b1c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287708"
---
# <a name="permissionenum-enumeration-dao"></a><span data-ttu-id="b3cfd-102">PermissionEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="b3cfd-102">PermissionEnum enumeration (DAO)</span></span>


<span data-ttu-id="b3cfd-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b3cfd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b3cfd-104">与 **Permissions** 属性一起用来指定权限的类型。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-104">Used with the **Permissions** property to specify the type of permissions.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b3cfd-105">名称</span><span class="sxs-lookup"><span data-stu-id="b3cfd-105">Name</span></span></p></th>
<th><p><span data-ttu-id="b3cfd-106">值</span><span class="sxs-lookup"><span data-stu-id="b3cfd-106">Value</span></span></p></th>
<th><p><span data-ttu-id="b3cfd-107">说明</span><span class="sxs-lookup"><span data-stu-id="b3cfd-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3cfd-108">dbSecCreate</span><span class="sxs-lookup"><span data-stu-id="b3cfd-108">dbSecCreate</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-109">1</span><span class="sxs-lookup"><span data-stu-id="b3cfd-109">1</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-110">用户可以创建新文档（对于 Document 对象无效）。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-110">The user can create new documents (not valid for Document objects).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3cfd-111">dbSecDBAdmin</span><span class="sxs-lookup"><span data-stu-id="b3cfd-111">dbSecDBAdmin</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-112">utf-8</span><span class="sxs-lookup"><span data-stu-id="b3cfd-112">8</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-113">用户可以复制数据库并更改数据库密码（对于 Document 对象无效）。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-113">The user can replicate a database and change the database password (not valid for Document objects).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3cfd-114">dbSecDBCreate</span><span class="sxs-lookup"><span data-stu-id="b3cfd-114">dbSecDBCreate</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-115">1</span><span class="sxs-lookup"><span data-stu-id="b3cfd-115">1</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-p101">用户可以创建新数据库。此选项仅对于工作组信息文件 (Systen.mdw) 中的 Databases 容器有效。此常量对于 Document 对象无效。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-p101">The user can create new databases. This option is valid only on the Databases container in the workgroup information file (Systen.mdw). This constant is not valid for Document objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3cfd-119">dbSecDBExclusive</span><span class="sxs-lookup"><span data-stu-id="b3cfd-119">dbSecDBExclusive</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-120">4</span><span class="sxs-lookup"><span data-stu-id="b3cfd-120">4</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-121">用户对数据库具有独占访问权限。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-121">The user has exclusive access to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3cfd-122">dbSecDBOpen</span><span class="sxs-lookup"><span data-stu-id="b3cfd-122">dbSecDBOpen</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-123">双面</span><span class="sxs-lookup"><span data-stu-id="b3cfd-123">2</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-124">用户可以打开数据库。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-124">The user can open the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3cfd-125">dbSecDelete</span><span class="sxs-lookup"><span data-stu-id="b3cfd-125">dbSecDelete</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-126">65536</span><span class="sxs-lookup"><span data-stu-id="b3cfd-126">65536</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-127">用户可以删除对象。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-127">The user can delete the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3cfd-128">dbSecDeleteData</span><span class="sxs-lookup"><span data-stu-id="b3cfd-128">dbSecDeleteData</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-129">128</span><span class="sxs-lookup"><span data-stu-id="b3cfd-129">128</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-130">用户可以删除记录。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-130">The user can delete records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3cfd-131">dbSecFullAccess</span><span class="sxs-lookup"><span data-stu-id="b3cfd-131">dbSecFullAccess</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-132">1048575</span><span class="sxs-lookup"><span data-stu-id="b3cfd-132">1048575</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-133">用户对对象具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-133">The user has full access to the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3cfd-134">dbSecInsertData</span><span class="sxs-lookup"><span data-stu-id="b3cfd-134">dbSecInsertData</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-135">32</span><span class="sxs-lookup"><span data-stu-id="b3cfd-135">32</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-136">用户可以添加记录。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-136">The user can add records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3cfd-137">dbSecNoAccess</span><span class="sxs-lookup"><span data-stu-id="b3cfd-137">dbSecNoAccess</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-138">0</span><span class="sxs-lookup"><span data-stu-id="b3cfd-138">0</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-139">用户无权访问对象（对于 Document 对象无效）。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-139">The user does not have access to the object (not valid for Document objects).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3cfd-140">dbSecReadDef</span><span class="sxs-lookup"><span data-stu-id="b3cfd-140">dbSecReadDef</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-141">4</span><span class="sxs-lookup"><span data-stu-id="b3cfd-141">4</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-142">用户可以读取表定义（包括列和索引信息）。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-142">The user can read the table definition, including column and index information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3cfd-143">dbSecReadSec</span><span class="sxs-lookup"><span data-stu-id="b3cfd-143">dbSecReadSec</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-144">131072</span><span class="sxs-lookup"><span data-stu-id="b3cfd-144">131072</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-145">用户可以读取对象的与安全有关的信息。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-145">The user can read the object's security-related information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3cfd-146">dbSecReplaceData</span><span class="sxs-lookup"><span data-stu-id="b3cfd-146">dbSecReplaceData</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-147">64</span><span class="sxs-lookup"><span data-stu-id="b3cfd-147">64</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-148">用户可以修改记录。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-148">The user can modify records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3cfd-149">dbSecRetrieveData</span><span class="sxs-lookup"><span data-stu-id="b3cfd-149">dbSecRetrieveData</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-150">20</span><span class="sxs-lookup"><span data-stu-id="b3cfd-150">20</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-151">用户可以从 Document 对象中检索数据。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-151">The user can retrieve data from the Document object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3cfd-152">dbSecWriteDef</span><span class="sxs-lookup"><span data-stu-id="b3cfd-152">dbSecWriteDef</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-153">65548</span><span class="sxs-lookup"><span data-stu-id="b3cfd-153">65548</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-154">用户可以修改或删除表定义（包括列和索引信息）。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-154">The user can modify or delete the table definition, including column and index information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3cfd-155">dbSecWriteOwner</span><span class="sxs-lookup"><span data-stu-id="b3cfd-155">dbSecWriteOwner</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-156">524288</span><span class="sxs-lookup"><span data-stu-id="b3cfd-156">524288</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-157">用户可以更改 Owner 属性设置。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-157">The user can change the Owner property setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3cfd-158">dbSecWriteSec</span><span class="sxs-lookup"><span data-stu-id="b3cfd-158">dbSecWriteSec</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-159">262144</span><span class="sxs-lookup"><span data-stu-id="b3cfd-159">262144</span></span></p></td>
<td><p><span data-ttu-id="b3cfd-160">用户可以修改访问权限。</span><span class="sxs-lookup"><span data-stu-id="b3cfd-160">The user can alter access permissions.</span></span></p></td>
</tr>
</tbody>
</table>

