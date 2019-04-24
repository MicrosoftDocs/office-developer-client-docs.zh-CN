---
title: RecordStatusEnum (Access desktop database reference)
TOCTitle: RecordStatusEnum
ms:assetid: 302915b8-494d-0be2-6dce-eaf91a0ea8ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249080(v=office.15)
ms:contentKeyID: 48544022
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a83de7730224c5ecd5080c795d38cf2e9a3305a9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309378"
---
# <a name="recordstatusenum"></a><span data-ttu-id="16f6f-102">RecordStatusEnum</span><span class="sxs-lookup"><span data-stu-id="16f6f-102">RecordStatusEnum</span></span>

<span data-ttu-id="16f6f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="16f6f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="16f6f-104">指定记录的批更新和其他批量操作的状态。</span><span class="sxs-lookup"><span data-stu-id="16f6f-104">Specifies the status of a record with regard to batch updates and other bulk operations.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="16f6f-105">常量</span><span class="sxs-lookup"><span data-stu-id="16f6f-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="16f6f-106">值</span><span class="sxs-lookup"><span data-stu-id="16f6f-106">Value</span></span></p></th>
<th><p><span data-ttu-id="16f6f-107">说明</span><span class="sxs-lookup"><span data-stu-id="16f6f-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-108"><strong>adRecCanceled</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-108"><strong>adRecCanceled</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-109">0x100</span><span class="sxs-lookup"><span data-stu-id="16f6f-109">0x100</span></span></p></td>
<td><p><span data-ttu-id="16f6f-110">指示由于操作被取消而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-110">Indicates that the record was not saved because the operation was canceled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-111"><strong>adRecCantRelease</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-111"><strong>adRecCantRelease</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-112">0x400</span><span class="sxs-lookup"><span data-stu-id="16f6f-112">0x400</span></span></p></td>
<td><p><span data-ttu-id="16f6f-113">指示由于现有记录被锁定而未保存新记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-113">Indicates that the new record was not saved because the existing record was locked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-114"><strong>adRecConcurrencyViolation</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-114"><strong>adRecConcurrencyViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-115">0x800</span><span class="sxs-lookup"><span data-stu-id="16f6f-115">0x800</span></span></p></td>
<td><p><span data-ttu-id="16f6f-116">指示由于开放式并发正在使用中而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-116">Indicates that the record was not saved because optimistic concurrency was in use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-117"><strong>adRecDBDeleted</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-117"><strong>adRecDBDeleted</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-118">0x40000</span><span class="sxs-lookup"><span data-stu-id="16f6f-118">0x40000</span></span></p></td>
<td><p><span data-ttu-id="16f6f-119">指示已经从数据源删除记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-119">Indicates that the record has already been deleted from the data source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-120"><strong>adRecDeleted</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-120"><strong>adRecDeleted</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-121">0x4</span><span class="sxs-lookup"><span data-stu-id="16f6f-121">0x4</span></span></p></td>
<td><p><span data-ttu-id="16f6f-122">指示已删除记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-122">Indicates that the record was deleted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-123"><strong>adRecIntegrityViolation</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-123"><strong>adRecIntegrityViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-124">0x1000</span><span class="sxs-lookup"><span data-stu-id="16f6f-124">0x1000</span></span></p></td>
<td><p><span data-ttu-id="16f6f-125">指示由于用户违反了完整性约束而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-125">Indicates that the record was not saved because the user violated integrity constraints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-126"><strong>adRecInvalid</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-126"><strong>adRecInvalid</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-127">0x10</span><span class="sxs-lookup"><span data-stu-id="16f6f-127">0x10</span></span></p></td>
<td><p><span data-ttu-id="16f6f-128">指示由于记录的书签无效而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-128">Indicates that the record was not saved because its bookmark is invalid.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-129"><strong>adRecMaxChangesExceeded</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-129"><strong>adRecMaxChangesExceeded</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-130">0x2000</span><span class="sxs-lookup"><span data-stu-id="16f6f-130">0x2000</span></span></p></td>
<td><p><span data-ttu-id="16f6f-131">指示由于挂起更改过多而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-131">Indicates that the record was not saved because there were too many pending changes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-132"><strong>adRecModified</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-132"><strong>adRecModified</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-133">0x2</span><span class="sxs-lookup"><span data-stu-id="16f6f-133">0x2</span></span></p></td>
<td><p><span data-ttu-id="16f6f-134">指示已修改记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-134">Indicates that the record was modified.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-135"><strong>adRecMultipleChanges</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-135"><strong>adRecMultipleChanges</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-136">0x40</span><span class="sxs-lookup"><span data-stu-id="16f6f-136">0x40</span></span></p></td>
<td><p><span data-ttu-id="16f6f-137">指示由于该记录会影响多个记录而未保存该记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-137">Indicates that the record was not saved because it would have affected multiple records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-138"><strong>adRecNew</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-138"><strong>adRecNew</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-139">0x1</span><span class="sxs-lookup"><span data-stu-id="16f6f-139">0x1</span></span></p></td>
<td><p><span data-ttu-id="16f6f-140">指示该记录是新的。</span><span class="sxs-lookup"><span data-stu-id="16f6f-140">Indicates that the record is new.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-141"><strong>adRecObjectOpen</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-141"><strong>adRecObjectOpen</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-142">0x4000</span><span class="sxs-lookup"><span data-stu-id="16f6f-142">0x4000</span></span></p></td>
<td><p><span data-ttu-id="16f6f-143">指示由于与某个打开的存储对象发生冲突而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-143">Indicates that the record was not saved because of a conflict with an open storage object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-144"><strong>adRecOK</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-144"><strong>adRecOK</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-145">0</span><span class="sxs-lookup"><span data-stu-id="16f6f-145">0</span></span></p></td>
<td><p><span data-ttu-id="16f6f-146">指示已成功更新记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-146">Indicates that the record was successfully updated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-147"><strong>adRecOutOfMemory</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-147"><strong>adRecOutOfMemory</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-148">0x8000</span><span class="sxs-lookup"><span data-stu-id="16f6f-148">0x8000</span></span></p></td>
<td><p><span data-ttu-id="16f6f-149">指示由于计算机耗尽内存而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-149">Indicates that the record was not saved because the computer has run out of memory.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-150"><strong>adRecPendingChanges</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-150"><strong>adRecPendingChanges</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-151">0x80</span><span class="sxs-lookup"><span data-stu-id="16f6f-151">0x80</span></span></p></td>
<td><p><span data-ttu-id="16f6f-152">指示记录由于引用了某个待定插入而未保存。</span><span class="sxs-lookup"><span data-stu-id="16f6f-152">Indicates that the record was not saved because it refers to a pending insert.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-153"><strong>adRecPermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-153"><strong>adRecPermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-154">0x10000</span><span class="sxs-lookup"><span data-stu-id="16f6f-154">0x10000</span></span></p></td>
<td><p><span data-ttu-id="16f6f-155">指示由于用户权限不足而未保存记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-155">Indicates that the record was not saved because the user has insufficient permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-156"><strong>adRecSchemaViolation</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-156"><strong>adRecSchemaViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-157">0x20000</span><span class="sxs-lookup"><span data-stu-id="16f6f-157">0x20000</span></span></p></td>
<td><p><span data-ttu-id="16f6f-158">指示记录由于违反了基础数据库的结构而未保存。</span><span class="sxs-lookup"><span data-stu-id="16f6f-158">Indicates that the record was not saved because it violates the structure of the underlying database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-159"><strong>adRecUnmodified</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-159"><strong>adRecUnmodified</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-160">0x8</span><span class="sxs-lookup"><span data-stu-id="16f6f-160">0x8</span></span></p></td>
<td><p><span data-ttu-id="16f6f-161">指示未修改记录。</span><span class="sxs-lookup"><span data-stu-id="16f6f-161">Indicates that the record was not modified.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="16f6f-162">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="16f6f-162">ADO/WFC equivalent</span></span>

<span data-ttu-id="16f6f-163">AdoEnums. RecordStatus。</span><span class="sxs-lookup"><span data-stu-id="16f6f-163">AdoEnums.RecordStatus.</span></span>

<span data-ttu-id="16f6f-164">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="16f6f-164">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="16f6f-165">常量</span><span class="sxs-lookup"><span data-stu-id="16f6f-165">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-166">AdoEnums。已取消 RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-166">AdoEnums.RecordStatus.CANCELED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-167">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-167">AdoEnums.RecordStatus.CANTRELEASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-168">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-168">AdoEnums.RecordStatus.CONCURRENCYVIOLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-169">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-169">AdoEnums.RecordStatus.DBDELETED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-170">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-170">AdoEnums.RecordStatus.DELETED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-171">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-171">AdoEnums.RecordStatus.INTEGRITYVIOLATION</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-172">AdoEnums RecordStatus 无效</span><span class="sxs-lookup"><span data-stu-id="16f6f-172">AdoEnums.RecordStatus.INVALID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-173">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-173">AdoEnums.RecordStatus.MAXCHANGESEXCEEDED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-174">AdoEnums 修改的 RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-174">AdoEnums.RecordStatus.MODIFIED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-175">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-175">AdoEnums.RecordStatus.MULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-176">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-176">AdoEnums.RecordStatus.NEW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-177">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-177">AdoEnums.RecordStatus.OBJECTOPEN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-178">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-178">AdoEnums.RecordStatus.OK</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-179">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-179">AdoEnums.RecordStatus.OUTOFMEMORY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-180">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-180">AdoEnums.RecordStatus.PENDINGCHANGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-181">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-181">AdoEnums.RecordStatus.PERMISSIONDENIED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-182">AdoEnums RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-182">AdoEnums.RecordStatus.SCHEMAVIOLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-183">AdoEnums 不修改的 RecordStatus</span><span class="sxs-lookup"><span data-stu-id="16f6f-183">AdoEnums.RecordStatus.UNMODIFIED</span></span></p></td>
</tr>
</tbody>
</table>

