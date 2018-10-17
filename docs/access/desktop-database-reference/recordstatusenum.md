---
title: RecordStatusEnum （访问桌面数据库参考 （英文）
TOCTitle: RecordStatusEnum
ms:assetid: 302915b8-494d-0be2-6dce-eaf91a0ea8ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249080(v=office.15)
ms:contentKeyID: 48544022
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 88929ced56583316c42f2d5195054e51e98a1d5b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466925"
---
# <a name="recordstatusenum"></a><span data-ttu-id="8e0b1-102">RecordStatusEnum</span><span class="sxs-lookup"><span data-stu-id="8e0b1-102">RecordStatusEnum</span></span>


<span data-ttu-id="8e0b1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8e0b1-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8e0b1-104">指定记录的批更新和其他批量操作的状态。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-104">Specifies the status of a record with regard to batch updates and other bulk operations.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8e0b1-105">常量</span><span class="sxs-lookup"><span data-stu-id="8e0b1-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="8e0b1-106">值</span><span class="sxs-lookup"><span data-stu-id="8e0b1-106">Value</span></span></p></th>
<th><p><span data-ttu-id="8e0b1-107">说明</span><span class="sxs-lookup"><span data-stu-id="8e0b1-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-108"><strong>adRecCanceled</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-108"><strong>adRecCanceled</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-109">0x100</span><span class="sxs-lookup"><span data-stu-id="8e0b1-109">0x100</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-110">指示由于操作被取消而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-110">Indicates that the record was not saved because the operation was canceled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-111"><strong>adRecCantRelease</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-111"><strong>adRecCantRelease</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-112">0x400</span><span class="sxs-lookup"><span data-stu-id="8e0b1-112">0x400</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-113">指示由于现有记录被锁定而未保存新记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-113">Indicates that the new record was not saved because the existing record was locked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-114"><strong>adRecConcurrencyViolation</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-114"><strong>adRecConcurrencyViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-115">0x800</span><span class="sxs-lookup"><span data-stu-id="8e0b1-115">0x800</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-116">指示由于开放式并发正在使用中而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-116">Indicates that the record was not saved because optimistic concurrency was in use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-117"><strong>adRecDBDeleted</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-117"><strong>adRecDBDeleted</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-118">而 0x40000 可</span><span class="sxs-lookup"><span data-stu-id="8e0b1-118">0x40000</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-119">指示已经从数据源删除记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-119">Indicates that the record has already been deleted from the data source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-120"><strong>adRecDeleted</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-120"><strong>adRecDeleted</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-121">0x4</span><span class="sxs-lookup"><span data-stu-id="8e0b1-121">0x4</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-122">指示已删除记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-122">Indicates that the record was deleted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-123"><strong>adRecIntegrityViolation</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-123"><strong>adRecIntegrityViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-124">0x1000</span><span class="sxs-lookup"><span data-stu-id="8e0b1-124">0x1000</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-125">指示由于用户违反了完整性约束而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-125">Indicates that the record was not saved because the user violated integrity constraints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-126"><strong>adRecInvalid</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-126"><strong>adRecInvalid</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-127">0x10</span><span class="sxs-lookup"><span data-stu-id="8e0b1-127">0x10</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-128">指示由于记录的书签无效而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-128">Indicates that the record was not saved because its bookmark is invalid.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-129"><strong>adRecMaxChangesExceeded</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-129"><strong>adRecMaxChangesExceeded</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-130">0x2000</span><span class="sxs-lookup"><span data-stu-id="8e0b1-130">0x2000</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-131">指示由于挂起更改过多而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-131">Indicates that the record was not saved because there were too many pending changes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-132"><strong>adRecModified</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-132"><strong>adRecModified</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-133">0x2</span><span class="sxs-lookup"><span data-stu-id="8e0b1-133">0x2</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-134">指示已修改记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-134">Indicates that the record was modified.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-135"><strong>adRecMultipleChanges</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-135"><strong>adRecMultipleChanges</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-136">0x40</span><span class="sxs-lookup"><span data-stu-id="8e0b1-136">0x40</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-137">指示由于该记录会影响多个记录而未保存该记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-137">Indicates that the record was not saved because it would have affected multiple records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-138"><strong>adRecNew</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-138"><strong>adRecNew</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-139">0x1</span><span class="sxs-lookup"><span data-stu-id="8e0b1-139">0x1</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-140">指示该记录是新的。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-140">Indicates that the record is new.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-141"><strong>adRecObjectOpen</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-141"><strong>adRecObjectOpen</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-142">0x4000</span><span class="sxs-lookup"><span data-stu-id="8e0b1-142">0x4000</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-143">指示由于与某个打开的存储对象发生冲突而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-143">Indicates that the record was not saved because of a conflict with an open storage object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-144"><strong>adRecOK</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-144"><strong>adRecOK</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-145">0</span><span class="sxs-lookup"><span data-stu-id="8e0b1-145">0</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-146">指示已成功更新记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-146">Indicates that the record was successfully updated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-147"><strong>adRecOutOfMemory</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-147"><strong>adRecOutOfMemory</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-148">0x8000</span><span class="sxs-lookup"><span data-stu-id="8e0b1-148">0x8000</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-149">指示由于计算机耗尽内存而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-149">Indicates that the record was not saved because the computer has run out of memory.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-150"><strong>adRecPendingChanges</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-150"><strong>adRecPendingChanges</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-151">0x80</span><span class="sxs-lookup"><span data-stu-id="8e0b1-151">0x80</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-152">指示记录由于引用了某个待定插入而未保存。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-152">Indicates that the record was not saved because it refers to a pending insert.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-153"><strong>adRecPermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-153"><strong>adRecPermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-154">0x10000</span><span class="sxs-lookup"><span data-stu-id="8e0b1-154">0x10000</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-155">指示由于用户权限不足而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-155">Indicates that the record was not saved because the user has insufficient permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-156"><strong>adRecSchemaViolation</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-156"><strong>adRecSchemaViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-157">0x20000</span><span class="sxs-lookup"><span data-stu-id="8e0b1-157">0x20000</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-158">指示记录由于违反了基础数据库的结构而未保存。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-158">Indicates that the record was not saved because it violates the structure of the underlying database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-159"><strong>adRecUnmodified</strong></span><span class="sxs-lookup"><span data-stu-id="8e0b1-159"><strong>adRecUnmodified</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0b1-160">0x8</span><span class="sxs-lookup"><span data-stu-id="8e0b1-160">0x8</span></span></p></td>
<td><p><span data-ttu-id="8e0b1-161">指示未修改记录。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-161">Indicates that the record was not modified.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8e0b1-162">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="8e0b1-162">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="8e0b1-163">AdoEnums.RecordStatus。</span><span class="sxs-lookup"><span data-stu-id="8e0b1-163">AdoEnums.RecordStatus.</span></span>

<span data-ttu-id="8e0b1-164">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="8e0b1-164">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8e0b1-165">常量</span><span class="sxs-lookup"><span data-stu-id="8e0b1-165">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-166">AdoEnums.RecordStatus.CANCELED</span><span class="sxs-lookup"><span data-stu-id="8e0b1-166">AdoEnums.RecordStatus.CANCELED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-167">AdoEnums.RecordStatus.CANTRELEASE</span><span class="sxs-lookup"><span data-stu-id="8e0b1-167">AdoEnums.RecordStatus.CANTRELEASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-168">AdoEnums.RecordStatus.CONCURRENCYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="8e0b1-168">AdoEnums.RecordStatus.CONCURRENCYVIOLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-169">AdoEnums.RecordStatus.DBDELETED</span><span class="sxs-lookup"><span data-stu-id="8e0b1-169">AdoEnums.RecordStatus.DBDELETED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-170">AdoEnums.RecordStatus.DELETED</span><span class="sxs-lookup"><span data-stu-id="8e0b1-170">AdoEnums.RecordStatus.DELETED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-171">AdoEnums.RecordStatus.INTEGRITYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="8e0b1-171">AdoEnums.RecordStatus.INTEGRITYVIOLATION</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-172">AdoEnums.RecordStatus.INVALID</span><span class="sxs-lookup"><span data-stu-id="8e0b1-172">AdoEnums.RecordStatus.INVALID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-173">AdoEnums.RecordStatus.MAXCHANGESEXCEEDED</span><span class="sxs-lookup"><span data-stu-id="8e0b1-173">AdoEnums.RecordStatus.MAXCHANGESEXCEEDED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-174">AdoEnums.RecordStatus.MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8e0b1-174">AdoEnums.RecordStatus.MODIFIED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-175">AdoEnums.RecordStatus.MULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="8e0b1-175">AdoEnums.RecordStatus.MULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-176">AdoEnums.RecordStatus.NEW</span><span class="sxs-lookup"><span data-stu-id="8e0b1-176">AdoEnums.RecordStatus.NEW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-177">AdoEnums.RecordStatus.OBJECTOPEN</span><span class="sxs-lookup"><span data-stu-id="8e0b1-177">AdoEnums.RecordStatus.OBJECTOPEN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-178">AdoEnums.RecordStatus.OK</span><span class="sxs-lookup"><span data-stu-id="8e0b1-178">AdoEnums.RecordStatus.OK</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-179">AdoEnums.RecordStatus.OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8e0b1-179">AdoEnums.RecordStatus.OUTOFMEMORY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-180">AdoEnums.RecordStatus.PENDINGCHANGES</span><span class="sxs-lookup"><span data-stu-id="8e0b1-180">AdoEnums.RecordStatus.PENDINGCHANGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-181">AdoEnums.RecordStatus.PERMISSIONDENIED</span><span class="sxs-lookup"><span data-stu-id="8e0b1-181">AdoEnums.RecordStatus.PERMISSIONDENIED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e0b1-182">AdoEnums.RecordStatus.SCHEMAVIOLATION</span><span class="sxs-lookup"><span data-stu-id="8e0b1-182">AdoEnums.RecordStatus.SCHEMAVIOLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0b1-183">AdoEnums.RecordStatus.UNMODIFIED</span><span class="sxs-lookup"><span data-stu-id="8e0b1-183">AdoEnums.RecordStatus.UNMODIFIED</span></span></p></td>
</tr>
</tbody>
</table>
