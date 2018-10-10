---
title: RightsEnum （访问桌面数据库参考 （英文）
TOCTitle: RightsEnum
ms:assetid: 7647b9d5-5271-fdcf-489d-5a8beb931ca5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249485(v=office.15)
ms:contentKeyID: 48545693
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ffc964be66649536b89e7f95ace1325eddee6169
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466995"
---
# <a name="rightsenum"></a><span data-ttu-id="19f5a-102">RightsEnum</span><span class="sxs-lookup"><span data-stu-id="19f5a-102">RightsEnum</span></span>


<span data-ttu-id="19f5a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="19f5a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="19f5a-104">指定组或用户对某个对象的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-104">Specifies the rights or permissions for a group or user on an object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="19f5a-105">常量</span><span class="sxs-lookup"><span data-stu-id="19f5a-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="19f5a-106">值</span><span class="sxs-lookup"><span data-stu-id="19f5a-106">Value</span></span></p></th>
<th><p><span data-ttu-id="19f5a-107">说明</span><span class="sxs-lookup"><span data-stu-id="19f5a-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19f5a-108"><strong>adRightCreate</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-108"><strong>adRightCreate</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-109">16384</span><span class="sxs-lookup"><span data-stu-id="19f5a-109">16384</span></span><br />
<span data-ttu-id="19f5a-110">(&amp;H4000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-110">(&amp;H4000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-111">用户或组拥有创建此类型的新对象的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-111">The user or group has permission to create new objects of this type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f5a-112"><strong>adRightDelete</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-112"><strong>adRightDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-113">65536</span><span class="sxs-lookup"><span data-stu-id="19f5a-113">65536</span></span><br />
<span data-ttu-id="19f5a-114">(&amp;H10000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-114">(&amp;H10000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-p101">用户或组拥有从对象删除数据的权限。对于 <strong>Tables</strong> 之类的对象，用户拥有从记录中删除数据值的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-p101">The user or group has permission to delete data from an object. For objects such as <strong>Tables</strong>, the user has permission to delete data values from records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19f5a-117"><strong>adRightDrop</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-117"><strong>adRightDrop</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-118">256</span><span class="sxs-lookup"><span data-stu-id="19f5a-118">256</span></span><br />
<span data-ttu-id="19f5a-119">(&amp;H100)</span><span class="sxs-lookup"><span data-stu-id="19f5a-119">(&amp;H100)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-p102">用户或组拥有从目录移除对象的权限。例如，<strong>Tables</strong> 可通过 DROP TABLE SQL 命令删除。</span><span class="sxs-lookup"><span data-stu-id="19f5a-p102">The user or group has permission to remove objects from the catalog. For example, <strong>Tables</strong> can be deleted by a DROP TABLE SQL command.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f5a-122"><strong>adRightExclusive</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-122"><strong>adRightExclusive</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-123">512</span><span class="sxs-lookup"><span data-stu-id="19f5a-123">512</span></span><br />
<span data-ttu-id="19f5a-124">(&amp;H200)</span><span class="sxs-lookup"><span data-stu-id="19f5a-124">(&amp;H200)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-125">用户或组拥有独占访问该对象的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-125">The user or group has permission to access the object exclusively.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19f5a-126"><strong>adRightExecute</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-126"><strong>adRightExecute</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-127">536870912</span><span class="sxs-lookup"><span data-stu-id="19f5a-127">536870912</span></span><br />
<span data-ttu-id="19f5a-128">(&amp;H20000000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-128">(&amp;H20000000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-129">用户或组拥有执行该对象的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-129">The user or group has permission to execute the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f5a-130"><strong>adRightFull</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-130"><strong>adRightFull</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-131">268435456</span><span class="sxs-lookup"><span data-stu-id="19f5a-131">268435456</span></span><br />
<span data-ttu-id="19f5a-132">(&amp;H10000000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-132">(&amp;H10000000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-133">用户或组拥有对该对象的全部权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-133">The user or group has all permissions on the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19f5a-134"><strong>adRightInsert</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-134"><strong>adRightInsert</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-135">32768</span><span class="sxs-lookup"><span data-stu-id="19f5a-135">32768</span></span><br />
<span data-ttu-id="19f5a-136">(&amp;H8000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-136">(&amp;H8000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-p103">用户或组拥有插入该对象的权限。对于 <strong>Table</strong> 之类的对象，用户拥有将数据插入表中的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-p103">The user or group has permission to insert the object. For objects such as <strong>Tables</strong>, the user has permission to insert data into the table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f5a-139"><strong>adRightMaximumAllowed</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-139"><strong>adRightMaximumAllowed</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-140">33554432 (&amp;h 2000000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-140">33554432 (&amp;H2000000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-p104">用户或组拥有提供程序所允许的最大数量的权限。特定权限与提供程序有关。</span><span class="sxs-lookup"><span data-stu-id="19f5a-p104">The user or group has the maximum number of permissions allowed by the provider. Specific permissions are provider-dependent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19f5a-143"><strong>adRightNone</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-143"><strong>adRightNone</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-144">0</span><span class="sxs-lookup"><span data-stu-id="19f5a-144">0</span></span></p></td>
<td><p><span data-ttu-id="19f5a-145">用户或组对该对象没有权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-145">The user or group has no permissions for the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f5a-146"><strong>adRightRead</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-146"><strong>adRightRead</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-147">-2147483648</span><span class="sxs-lookup"><span data-stu-id="19f5a-147">-2147483648</span></span><br />
<span data-ttu-id="19f5a-148">(&amp;H 80000000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-148">(&amp;H80000000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-p105">用户或组拥有读取该对象的权限。对于 <a href="table-object-adox.md">Table</a> 之类的对象，用户拥有读取表中数据的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-p105">The user or group has permission to read the object. For objects such as <a href="table-object-adox.md">Tables</a>, the user has permission to read the data in the table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19f5a-151"><strong>adRightReadDesign</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-151"><strong>adRightReadDesign</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-152">1024</span><span class="sxs-lookup"><span data-stu-id="19f5a-152">1024</span></span><br />
<span data-ttu-id="19f5a-153">(&amp;H400)</span><span class="sxs-lookup"><span data-stu-id="19f5a-153">(&amp;H400)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-154">用户或组拥有读取该对象的设计的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-154">The user or group has permission to read the design for the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f5a-155"><strong>adRightReadPermissions</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-155"><strong>adRightReadPermissions</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-156">131072</span><span class="sxs-lookup"><span data-stu-id="19f5a-156">131072</span></span><br />
<span data-ttu-id="19f5a-157">(&amp;H20000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-157">(&amp;H20000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-158">用户或组可查看目录中某个对象的特定权限，但是不能更改。</span><span class="sxs-lookup"><span data-stu-id="19f5a-158">The user or group can view, but not change, the specific permissions for an object in the catalog.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19f5a-159"><strong>adRightReference</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-159"><strong>adRightReference</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-160">8192</span><span class="sxs-lookup"><span data-stu-id="19f5a-160">8192</span></span><br />
<span data-ttu-id="19f5a-161">(&amp;H2000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-161">(&amp;H2000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-162">用户或组拥有引用该对象的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-162">The user or group has permission to reference the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f5a-163"><strong>adRightUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-163"><strong>adRightUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-164">1073741824</span><span class="sxs-lookup"><span data-stu-id="19f5a-164">1073741824</span></span><br />
<span data-ttu-id="19f5a-165">(&amp;H40000000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-165">(&amp;H40000000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-p106">用户或组拥有更新该对象的权限。对于 <strong>Table</strong> 之类的对象，用户拥有更新表中数据的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-p106">The user or group has permission to update the object. For objects such as <strong>Tables</strong>, the user has permission to update the data in the table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19f5a-168"><strong>adRightWithGrant</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-168"><strong>adRightWithGrant</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-169">4096</span><span class="sxs-lookup"><span data-stu-id="19f5a-169">4096</span></span><br />
<span data-ttu-id="19f5a-170">(&amp;H1000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-170">(&amp;H1000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-171">用户或组有权将对该对象的权限授予他人。</span><span class="sxs-lookup"><span data-stu-id="19f5a-171">The user or group has permission to grant permissions on the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f5a-172"><strong>adRightWriteDesign</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-172"><strong>adRightWriteDesign</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-173">2048</span><span class="sxs-lookup"><span data-stu-id="19f5a-173">2048</span></span><br />
<span data-ttu-id="19f5a-174">(&amp;H800)</span><span class="sxs-lookup"><span data-stu-id="19f5a-174">(&amp;H800)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-175">用户或组拥有更新该对象的设计的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-175">The user or group has permission to modify the design for the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19f5a-176"><strong>adRightWriteOwner</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-176"><strong>adRightWriteOwner</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-177">524288</span><span class="sxs-lookup"><span data-stu-id="19f5a-177">524288</span></span><br />
<span data-ttu-id="19f5a-178">(&amp;H80000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-178">(&amp;H80000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-179">用户或组拥有修改该对象的所有者的权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-179">The user or group has permission to modify the owner of the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f5a-180"><strong>adRightWritePermissions</strong></span><span class="sxs-lookup"><span data-stu-id="19f5a-180"><strong>adRightWritePermissions</strong></span></span></p></td>
<td><p><span data-ttu-id="19f5a-181">262144</span><span class="sxs-lookup"><span data-stu-id="19f5a-181">262144</span></span><br />
<span data-ttu-id="19f5a-182">(&amp;H40000)</span><span class="sxs-lookup"><span data-stu-id="19f5a-182">(&amp;H40000)</span></span></p></td>
<td><p><span data-ttu-id="19f5a-183">用户或组可修改目录中某个对象的特定权限。</span><span class="sxs-lookup"><span data-stu-id="19f5a-183">The user or group can modify the specific permissions for an object in the catalog.</span></span></p></td>
</tr>
</tbody>
</table>

