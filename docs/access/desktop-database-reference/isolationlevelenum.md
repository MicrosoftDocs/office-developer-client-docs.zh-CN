---
title: IsolationLevelEnum （访问桌面数据库参考 （英文）
TOCTitle: IsolationLevelEnum
ms:assetid: 438af3f3-65ed-237d-94d8-f3aff6addd3b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249204(v=office.15)
ms:contentKeyID: 48544506
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 80e7d22a5152b24894bf746b939f705739d4220d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468868"
---
# <a name="isolationlevelenum"></a><span data-ttu-id="82c5a-102">IsolationLevelEnum</span><span class="sxs-lookup"><span data-stu-id="82c5a-102">IsolationLevelEnum</span></span>


<span data-ttu-id="82c5a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="82c5a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="82c5a-104">指定 [Connection](connection-object-ado.md) 对象的事务隔离级别。</span><span class="sxs-lookup"><span data-stu-id="82c5a-104">Specifies the level of transaction isolation for a [Connection](connection-object-ado.md) object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="82c5a-105">常量</span><span class="sxs-lookup"><span data-stu-id="82c5a-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="82c5a-106">值</span><span class="sxs-lookup"><span data-stu-id="82c5a-106">Value</span></span></p></th>
<th><p><span data-ttu-id="82c5a-107">说明</span><span class="sxs-lookup"><span data-stu-id="82c5a-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-108"><strong>adXactUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="82c5a-108"><strong>adXactUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="82c5a-109">-1</span><span class="sxs-lookup"><span data-stu-id="82c5a-109">-1</span></span></p></td>
<td><p><span data-ttu-id="82c5a-110">指示提供程序正在使用与指定的隔离级别不同的隔离级别，但该级别无法确定。</span><span class="sxs-lookup"><span data-stu-id="82c5a-110">Indicates that the provider is using a different isolation level than specified, but that the level cannot be determined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5a-111"><strong>adXactChaos</strong></span><span class="sxs-lookup"><span data-stu-id="82c5a-111"><strong>adXactChaos</strong></span></span></p></td>
<td><p><span data-ttu-id="82c5a-112">16</span><span class="sxs-lookup"><span data-stu-id="82c5a-112">16</span></span></p></td>
<td><p><span data-ttu-id="82c5a-113">指示无法覆盖来自隔离程度更高的事务的挂起更改。</span><span class="sxs-lookup"><span data-stu-id="82c5a-113">Indicates that pending changes from more highly isolated transactions cannot be overwritten.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-114"><strong>adXactBrowse</strong></span><span class="sxs-lookup"><span data-stu-id="82c5a-114"><strong>adXactBrowse</strong></span></span></p></td>
<td><p><span data-ttu-id="82c5a-115">256</span><span class="sxs-lookup"><span data-stu-id="82c5a-115">256</span></span></p></td>
<td><p><span data-ttu-id="82c5a-116">指示可以从一个事务查看其他事务中未提交的更改。</span><span class="sxs-lookup"><span data-stu-id="82c5a-116">Indicates that from one transaction you can view uncommitted changes in other transactions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5a-117"><strong>adXactReadUncommitted</strong></span><span class="sxs-lookup"><span data-stu-id="82c5a-117"><strong>adXactReadUncommitted</strong></span></span></p></td>
<td><p><span data-ttu-id="82c5a-118">256</span><span class="sxs-lookup"><span data-stu-id="82c5a-118">256</span></span></p></td>
<td><p><span data-ttu-id="82c5a-119">与 <strong>adXactBrowse</strong> 相同。</span><span class="sxs-lookup"><span data-stu-id="82c5a-119">Same as <strong>adXactBrowse</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-120"><strong>adXactCursorStability</strong></span><span class="sxs-lookup"><span data-stu-id="82c5a-120"><strong>adXactCursorStability</strong></span></span></p></td>
<td><p><span data-ttu-id="82c5a-121">4096</span><span class="sxs-lookup"><span data-stu-id="82c5a-121">4096</span></span></p></td>
<td><p><span data-ttu-id="82c5a-122">指示从一个事务只能查看其他事务中已经提交的更改。</span><span class="sxs-lookup"><span data-stu-id="82c5a-122">Indicates that from one transaction you can view changes in other transactions only after they have been committed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5a-123"><strong>adXactReadCommitted</strong></span><span class="sxs-lookup"><span data-stu-id="82c5a-123"><strong>adXactReadCommitted</strong></span></span></p></td>
<td><p><span data-ttu-id="82c5a-124">4096</span><span class="sxs-lookup"><span data-stu-id="82c5a-124">4096</span></span></p></td>
<td><p><span data-ttu-id="82c5a-125">与 <strong>adXactCursorStability</strong> 相同。</span><span class="sxs-lookup"><span data-stu-id="82c5a-125">Same as <strong>adXactCursorStability</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-126"><strong>adXactRepeatableRead</strong></span><span class="sxs-lookup"><span data-stu-id="82c5a-126"><strong>adXactRepeatableRead</strong></span></span></p></td>
<td><p><span data-ttu-id="82c5a-127">65536</span><span class="sxs-lookup"><span data-stu-id="82c5a-127">65536</span></span></p></td>
<td><p><span data-ttu-id="82c5a-128">指示从一个事务无法查看其他事务中所做的更改，但重新查询操作可以检索新的 <strong>Recordset</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="82c5a-128">Indicates that from one transaction you cannot see changes made in other transactions, but that requerying can retrieve new <strong>Recordset</strong> objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5a-129"><strong>adXactIsolated</strong></span><span class="sxs-lookup"><span data-stu-id="82c5a-129"><strong>adXactIsolated</strong></span></span></p></td>
<td><p><span data-ttu-id="82c5a-130">1048576</span><span class="sxs-lookup"><span data-stu-id="82c5a-130">1048576</span></span></p></td>
<td><p><span data-ttu-id="82c5a-131">指示事务是在隔离其他事务的状况下执行的。</span><span class="sxs-lookup"><span data-stu-id="82c5a-131">Indicates that transactions are conducted in isolation of other transactions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-132"><strong>adXactSerializable</strong></span><span class="sxs-lookup"><span data-stu-id="82c5a-132"><strong>adXactSerializable</strong></span></span></p></td>
<td><p><span data-ttu-id="82c5a-133">1048576</span><span class="sxs-lookup"><span data-stu-id="82c5a-133">1048576</span></span></p></td>
<td><p><span data-ttu-id="82c5a-134">与 <strong>adXactIsolated</strong> 相同。</span><span class="sxs-lookup"><span data-stu-id="82c5a-134">Same as <strong>adXactIsolated</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82c5a-135">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="82c5a-135">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="82c5a-136">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="82c5a-136">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="82c5a-137">常量</span><span class="sxs-lookup"><span data-stu-id="82c5a-137">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-138">AdoEnums.IsolationLevel.UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="82c5a-138">AdoEnums.IsolationLevel.UNSPECIFIED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5a-139">AdoEnums.IsolationLevel.CHAOS</span><span class="sxs-lookup"><span data-stu-id="82c5a-139">AdoEnums.IsolationLevel.CHAOS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-140">AdoEnums.IsolationLevel.BROWSE</span><span class="sxs-lookup"><span data-stu-id="82c5a-140">AdoEnums.IsolationLevel.BROWSE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5a-141">AdoEnums.IsolationLevel.READUNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="82c5a-141">AdoEnums.IsolationLevel.READUNCOMMITTED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-142">AdoEnums.IsolationLevel.CURSORSTABILITY</span><span class="sxs-lookup"><span data-stu-id="82c5a-142">AdoEnums.IsolationLevel.CURSORSTABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5a-143">AdoEnums.IsolationLevel.READCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="82c5a-143">AdoEnums.IsolationLevel.READCOMMITTED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-144">AdoEnums.IsolationLevel.REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="82c5a-144">AdoEnums.IsolationLevel.REPEATABLEREAD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5a-145">AdoEnums.IsolationLevel.ISOLATED</span><span class="sxs-lookup"><span data-stu-id="82c5a-145">AdoEnums.IsolationLevel.ISOLATED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5a-146">AdoEnums.IsolationLevel.SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="82c5a-146">AdoEnums.IsolationLevel.SERIALIZABLE</span></span></p></td>
</tr>
</tbody>
</table>

