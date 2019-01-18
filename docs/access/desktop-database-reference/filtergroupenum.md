---
title: FilterGroupEnum （访问桌面数据库参考 （英文）
TOCTitle: FilterGroupEnum
ms:assetid: 141f8f9a-c188-5937-91cc-3155eaebebd2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248912(v=office.15)
ms:contentKeyID: 48543381
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: be2ce54fe743c46468850abc5dc16520e208ec9e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704062"
---
# <a name="filtergroupenum"></a><span data-ttu-id="e4646-102">FilterGroupEnum</span><span class="sxs-lookup"><span data-stu-id="e4646-102">FilterGroupEnum</span></span>

<span data-ttu-id="e4646-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e4646-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e4646-104">指定要从 [Recordset](recordset-object-ado.md) 中筛选的记录组。</span><span class="sxs-lookup"><span data-stu-id="e4646-104">Specifies the group of records to be filtered from a [Recordset](recordset-object-ado.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e4646-105">常量</span><span class="sxs-lookup"><span data-stu-id="e4646-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="e4646-106">值</span><span class="sxs-lookup"><span data-stu-id="e4646-106">Value</span></span></p></th>
<th><p><span data-ttu-id="e4646-107">说明</span><span class="sxs-lookup"><span data-stu-id="e4646-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4646-108"><strong>adFilterAffectedRecords</strong></span><span class="sxs-lookup"><span data-stu-id="e4646-108"><strong>adFilterAffectedRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="e4646-109">2</span><span class="sxs-lookup"><span data-stu-id="e4646-109">2</span></span></p></td>
<td><p><span data-ttu-id="e4646-110">用于仅查看受上一次 <a href="delete-method-ado-recordset.md">Delete</a>、<a href="resync-method-ado.md">Resync</a>、<a href="updatebatch-method-ado.md">UpdateBatch</a> 或 <a href="cancelbatch-method-ado.md">CancelBatch</a> 调用影响的记录的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e4646-110">Filters for viewing only records affected by the last <a href="delete-method-ado-recordset.md">Delete</a>, <a href="resync-method-ado.md">Resync</a>, <a href="updatebatch-method-ado.md">UpdateBatch</a>, or <a href="cancelbatch-method-ado.md">CancelBatch</a> call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4646-111"><strong>adFilterConflictingRecords</strong></span><span class="sxs-lookup"><span data-stu-id="e4646-111"><strong>adFilterConflictingRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="e4646-112">5</span><span class="sxs-lookup"><span data-stu-id="e4646-112">5</span></span></p></td>
<td><p><span data-ttu-id="e4646-113">用于查看使上一次批更新失败的记录的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e4646-113">Filters for viewing the records that failed the last batch update.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4646-114"><strong>adFilterFetchedRecords</strong></span><span class="sxs-lookup"><span data-stu-id="e4646-114"><strong>adFilterFetchedRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="e4646-115">3</span><span class="sxs-lookup"><span data-stu-id="e4646-115">3</span></span></p></td>
<td><p><span data-ttu-id="e4646-116">用于查看当前缓存中的记录（即，上一次从数据库检索记录的调用的结果）的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e4646-116">Filters for viewing the records in the current cache — that is, the results of the last call to retrieve records from the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4646-117"><strong>adFilterNone</strong></span><span class="sxs-lookup"><span data-stu-id="e4646-117"><strong>adFilterNone</strong></span></span></p></td>
<td><p><span data-ttu-id="e4646-118">0</span><span class="sxs-lookup"><span data-stu-id="e4646-118">0</span></span></p></td>
<td><p><span data-ttu-id="e4646-119">删除当前的筛选并还原所有的记录以进行查看。</span><span class="sxs-lookup"><span data-stu-id="e4646-119">Removes the current filter and restores all records for viewing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4646-120"><strong>adFilterPendingRecords</strong></span><span class="sxs-lookup"><span data-stu-id="e4646-120"><strong>adFilterPendingRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="e4646-121">1</span><span class="sxs-lookup"><span data-stu-id="e4646-121">1</span></span></p></td>
<td><p><span data-ttu-id="e4646-p101">用于仅查看已更改但尚未发送到服务器的记录的筛选器。仅适用于批更新模式。</span><span class="sxs-lookup"><span data-stu-id="e4646-p101">Filters for viewing only records that have changed but have not yet been sent to the server. Applicable only for batch update mode.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="e4646-124">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="e4646-124">ADO/WFC equivalent</span></span>

<span data-ttu-id="e4646-125">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="e4646-125">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e4646-126">常量</span><span class="sxs-lookup"><span data-stu-id="e4646-126">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4646-127">AdoEnums.FilterGroup.AFFECTEDRECORDS</span><span class="sxs-lookup"><span data-stu-id="e4646-127">AdoEnums.FilterGroup.AFFECTEDRECORDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4646-128">AdoEnums.FilterGroup.CONFLICTINGRECORDS</span><span class="sxs-lookup"><span data-stu-id="e4646-128">AdoEnums.FilterGroup.CONFLICTINGRECORDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4646-129">AdoEnums.FilterGroup.FETCHEDRECORDS</span><span class="sxs-lookup"><span data-stu-id="e4646-129">AdoEnums.FilterGroup.FETCHEDRECORDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4646-130">AdoEnums.FilterGroup.NONE</span><span class="sxs-lookup"><span data-stu-id="e4646-130">AdoEnums.FilterGroup.NONE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4646-131">AdoEnums.FilterGroup.PENDINGRECORDS</span><span class="sxs-lookup"><span data-stu-id="e4646-131">AdoEnums.FilterGroup.PENDINGRECORDS</span></span></p></td>
</tr>
</tbody>
</table>

