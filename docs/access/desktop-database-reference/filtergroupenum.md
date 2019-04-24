---
title: FilterGroupEnum (Access desktop database reference)
TOCTitle: FilterGroupEnum
ms:assetid: 141f8f9a-c188-5937-91cc-3155eaebebd2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248912(v=office.15)
ms:contentKeyID: 48543381
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: be2ce54fe743c46468850abc5dc16520e208ec9e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292417"
---
# <a name="filtergroupenum"></a><span data-ttu-id="3ed10-102">FilterGroupEnum</span><span class="sxs-lookup"><span data-stu-id="3ed10-102">FilterGroupEnum</span></span>

<span data-ttu-id="3ed10-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="3ed10-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3ed10-104">指定要从 [Recordset](recordset-object-ado.md) 中筛选的记录组。</span><span class="sxs-lookup"><span data-stu-id="3ed10-104">Specifies the group of records to be filtered from a [Recordset](recordset-object-ado.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3ed10-105">常量</span><span class="sxs-lookup"><span data-stu-id="3ed10-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="3ed10-106">值</span><span class="sxs-lookup"><span data-stu-id="3ed10-106">Value</span></span></p></th>
<th><p><span data-ttu-id="3ed10-107">说明</span><span class="sxs-lookup"><span data-stu-id="3ed10-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ed10-108"><strong>adFilterAffectedRecords</strong></span><span class="sxs-lookup"><span data-stu-id="3ed10-108"><strong>adFilterAffectedRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="3ed10-109">双面</span><span class="sxs-lookup"><span data-stu-id="3ed10-109">2</span></span></p></td>
<td><p><span data-ttu-id="3ed10-110">用于仅查看受上一次 <a href="delete-method-ado-recordset.md">Delete</a>、<a href="resync-method-ado.md">Resync</a>、<a href="updatebatch-method-ado.md">UpdateBatch</a> 或 <a href="cancelbatch-method-ado.md">CancelBatch</a> 调用影响的记录的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3ed10-110">Filters for viewing only records affected by the last <a href="delete-method-ado-recordset.md">Delete</a>, <a href="resync-method-ado.md">Resync</a>, <a href="updatebatch-method-ado.md">UpdateBatch</a>, or <a href="cancelbatch-method-ado.md">CancelBatch</a> call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ed10-111"><strong>adFilterConflictingRecords</strong></span><span class="sxs-lookup"><span data-stu-id="3ed10-111"><strong>adFilterConflictingRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="3ed10-112">5</span><span class="sxs-lookup"><span data-stu-id="3ed10-112">5</span></span></p></td>
<td><p><span data-ttu-id="3ed10-113">用于查看使上一次批更新失败的记录的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3ed10-113">Filters for viewing the records that failed the last batch update.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ed10-114"><strong>adFilterFetchedRecords</strong></span><span class="sxs-lookup"><span data-stu-id="3ed10-114"><strong>adFilterFetchedRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="3ed10-115">第三章</span><span class="sxs-lookup"><span data-stu-id="3ed10-115">3</span></span></p></td>
<td><p><span data-ttu-id="3ed10-116">用于查看当前缓存中的记录（即，上一次从数据库检索记录的调用的结果）的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3ed10-116">Filters for viewing the records in the current cache — that is, the results of the last call to retrieve records from the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ed10-117"><strong>adFilterNone</strong></span><span class="sxs-lookup"><span data-stu-id="3ed10-117"><strong>adFilterNone</strong></span></span></p></td>
<td><p><span data-ttu-id="3ed10-118">0</span><span class="sxs-lookup"><span data-stu-id="3ed10-118">0</span></span></p></td>
<td><p><span data-ttu-id="3ed10-119">删除当前的筛选并还原所有的记录以进行查看。</span><span class="sxs-lookup"><span data-stu-id="3ed10-119">Removes the current filter and restores all records for viewing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ed10-120"><strong>adFilterPendingRecords</strong></span><span class="sxs-lookup"><span data-stu-id="3ed10-120"><strong>adFilterPendingRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="3ed10-121">1</span><span class="sxs-lookup"><span data-stu-id="3ed10-121">1</span></span></p></td>
<td><p><span data-ttu-id="3ed10-p101">用于仅查看已更改但尚未发送到服务器的记录的筛选器。仅适用于批更新模式。</span><span class="sxs-lookup"><span data-stu-id="3ed10-p101">Filters for viewing only records that have changed but have not yet been sent to the server. Applicable only for batch update mode.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="3ed10-124">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="3ed10-124">ADO/WFC equivalent</span></span>

<span data-ttu-id="3ed10-125">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="3ed10-125">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3ed10-126">常量</span><span class="sxs-lookup"><span data-stu-id="3ed10-126">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ed10-127">AdoEnums FilterGroup</span><span class="sxs-lookup"><span data-stu-id="3ed10-127">AdoEnums.FilterGroup.AFFECTEDRECORDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ed10-128">AdoEnums FilterGroup</span><span class="sxs-lookup"><span data-stu-id="3ed10-128">AdoEnums.FilterGroup.CONFLICTINGRECORDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ed10-129">AdoEnums FilterGroup</span><span class="sxs-lookup"><span data-stu-id="3ed10-129">AdoEnums.FilterGroup.FETCHEDRECORDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ed10-130">AdoEnums FilterGroup</span><span class="sxs-lookup"><span data-stu-id="3ed10-130">AdoEnums.FilterGroup.NONE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ed10-131">AdoEnums FilterGroup</span><span class="sxs-lookup"><span data-stu-id="3ed10-131">AdoEnums.FilterGroup.PENDINGRECORDS</span></span></p></td>
</tr>
</tbody>
</table>

