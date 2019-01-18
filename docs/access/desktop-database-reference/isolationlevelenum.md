---
title: IsolationLevelEnum （访问桌面数据库参考 （英文）
TOCTitle: IsolationLevelEnum
ms:assetid: 438af3f3-65ed-237d-94d8-f3aff6addd3b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249204(v=office.15)
ms:contentKeyID: 48544506
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9f0176772b366b39d368f8bae1e402d420f0136c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707182"
---
# <a name="isolationlevelenum"></a><span data-ttu-id="ec795-102">IsolationLevelEnum</span><span class="sxs-lookup"><span data-stu-id="ec795-102">IsolationLevelEnum</span></span>

<span data-ttu-id="ec795-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ec795-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ec795-104">指定 [Connection](connection-object-ado.md) 对象的事务隔离级别。</span><span class="sxs-lookup"><span data-stu-id="ec795-104">Specifies the level of transaction isolation for a [Connection](connection-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ec795-105">常量</span><span class="sxs-lookup"><span data-stu-id="ec795-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="ec795-106">值</span><span class="sxs-lookup"><span data-stu-id="ec795-106">Value</span></span></p></th>
<th><p><span data-ttu-id="ec795-107">说明</span><span class="sxs-lookup"><span data-stu-id="ec795-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec795-108"><strong>adXactUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="ec795-108"><strong>adXactUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="ec795-109">-1</span><span class="sxs-lookup"><span data-stu-id="ec795-109">-1</span></span></p></td>
<td><p><span data-ttu-id="ec795-110">指示提供程序正在使用与指定的隔离级别不同的隔离级别，但该级别无法确定。</span><span class="sxs-lookup"><span data-stu-id="ec795-110">Indicates that the provider is using a different isolation level than specified, but that the level cannot be determined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec795-111"><strong>adXactChaos</strong></span><span class="sxs-lookup"><span data-stu-id="ec795-111"><strong>adXactChaos</strong></span></span></p></td>
<td><p><span data-ttu-id="ec795-112">16</span><span class="sxs-lookup"><span data-stu-id="ec795-112">16</span></span></p></td>
<td><p><span data-ttu-id="ec795-113">指示无法覆盖来自隔离程度更高的事务的挂起更改。</span><span class="sxs-lookup"><span data-stu-id="ec795-113">Indicates that pending changes from more highly isolated transactions cannot be overwritten.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec795-114"><strong>adXactBrowse</strong></span><span class="sxs-lookup"><span data-stu-id="ec795-114"><strong>adXactBrowse</strong></span></span></p></td>
<td><p><span data-ttu-id="ec795-115">256</span><span class="sxs-lookup"><span data-stu-id="ec795-115">256</span></span></p></td>
<td><p><span data-ttu-id="ec795-116">指示可以从一个事务查看其他事务中未提交的更改。</span><span class="sxs-lookup"><span data-stu-id="ec795-116">Indicates that from one transaction you can view uncommitted changes in other transactions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec795-117"><strong>adXactReadUncommitted</strong></span><span class="sxs-lookup"><span data-stu-id="ec795-117"><strong>adXactReadUncommitted</strong></span></span></p></td>
<td><p><span data-ttu-id="ec795-118">256</span><span class="sxs-lookup"><span data-stu-id="ec795-118">256</span></span></p></td>
<td><p><span data-ttu-id="ec795-119">与 <strong>adXactBrowse</strong> 相同。</span><span class="sxs-lookup"><span data-stu-id="ec795-119">Same as <strong>adXactBrowse</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec795-120"><strong>adXactCursorStability</strong></span><span class="sxs-lookup"><span data-stu-id="ec795-120"><strong>adXactCursorStability</strong></span></span></p></td>
<td><p><span data-ttu-id="ec795-121">4096</span><span class="sxs-lookup"><span data-stu-id="ec795-121">4096</span></span></p></td>
<td><p><span data-ttu-id="ec795-122">指示从一个事务只能查看其他事务中已经提交的更改。</span><span class="sxs-lookup"><span data-stu-id="ec795-122">Indicates that from one transaction you can view changes in other transactions only after they have been committed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec795-123"><strong>adXactReadCommitted</strong></span><span class="sxs-lookup"><span data-stu-id="ec795-123"><strong>adXactReadCommitted</strong></span></span></p></td>
<td><p><span data-ttu-id="ec795-124">4096</span><span class="sxs-lookup"><span data-stu-id="ec795-124">4096</span></span></p></td>
<td><p><span data-ttu-id="ec795-125">与 <strong>adXactCursorStability</strong> 相同。</span><span class="sxs-lookup"><span data-stu-id="ec795-125">Same as <strong>adXactCursorStability</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec795-126"><strong>adXactRepeatableRead</strong></span><span class="sxs-lookup"><span data-stu-id="ec795-126"><strong>adXactRepeatableRead</strong></span></span></p></td>
<td><p><span data-ttu-id="ec795-127">65536</span><span class="sxs-lookup"><span data-stu-id="ec795-127">65536</span></span></p></td>
<td><p><span data-ttu-id="ec795-128">指示从一个事务无法查看其他事务中所做的更改，但重新查询操作可以检索新的 <strong>Recordset</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ec795-128">Indicates that from one transaction you cannot see changes made in other transactions, but that requerying can retrieve new <strong>Recordset</strong> objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec795-129"><strong>adXactIsolated</strong></span><span class="sxs-lookup"><span data-stu-id="ec795-129"><strong>adXactIsolated</strong></span></span></p></td>
<td><p><span data-ttu-id="ec795-130">1048576</span><span class="sxs-lookup"><span data-stu-id="ec795-130">1048576</span></span></p></td>
<td><p><span data-ttu-id="ec795-131">指示事务是在隔离其他事务的状况下执行的。</span><span class="sxs-lookup"><span data-stu-id="ec795-131">Indicates that transactions are conducted in isolation of other transactions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec795-132"><strong>adXactSerializable</strong></span><span class="sxs-lookup"><span data-stu-id="ec795-132"><strong>adXactSerializable</strong></span></span></p></td>
<td><p><span data-ttu-id="ec795-133">1048576</span><span class="sxs-lookup"><span data-stu-id="ec795-133">1048576</span></span></p></td>
<td><p><span data-ttu-id="ec795-134">与 <strong>adXactIsolated</strong> 相同。</span><span class="sxs-lookup"><span data-stu-id="ec795-134">Same as <strong>adXactIsolated</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="ec795-135">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="ec795-135">ADO/WFC equivalent</span></span>

<span data-ttu-id="ec795-136">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="ec795-136">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ec795-137">常量</span><span class="sxs-lookup"><span data-stu-id="ec795-137">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec795-138">AdoEnums.IsolationLevel.UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="ec795-138">AdoEnums.IsolationLevel.UNSPECIFIED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec795-139">AdoEnums.IsolationLevel.CHAOS</span><span class="sxs-lookup"><span data-stu-id="ec795-139">AdoEnums.IsolationLevel.CHAOS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec795-140">AdoEnums.IsolationLevel.BROWSE</span><span class="sxs-lookup"><span data-stu-id="ec795-140">AdoEnums.IsolationLevel.BROWSE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec795-141">AdoEnums.IsolationLevel.READUNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="ec795-141">AdoEnums.IsolationLevel.READUNCOMMITTED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec795-142">AdoEnums.IsolationLevel.CURSORSTABILITY</span><span class="sxs-lookup"><span data-stu-id="ec795-142">AdoEnums.IsolationLevel.CURSORSTABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec795-143">AdoEnums.IsolationLevel.READCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="ec795-143">AdoEnums.IsolationLevel.READCOMMITTED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec795-144">AdoEnums.IsolationLevel.REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="ec795-144">AdoEnums.IsolationLevel.REPEATABLEREAD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec795-145">AdoEnums.IsolationLevel.ISOLATED</span><span class="sxs-lookup"><span data-stu-id="ec795-145">AdoEnums.IsolationLevel.ISOLATED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec795-146">AdoEnums.IsolationLevel.SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="ec795-146">AdoEnums.IsolationLevel.SERIALIZABLE</span></span></p></td>
</tr>
</tbody>
</table>

