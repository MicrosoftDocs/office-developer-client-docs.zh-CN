---
title: LockTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: LockTypeEnum
ms:assetid: 966b4952-5591-4a99-82d5-99cb9ae3fc72
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249667(v=office.15)
ms:contentKeyID: 48546448
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 57cef1ca3a31665db1db517c22756213abf49042
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860530"
---
# <a name="locktypeenum"></a><span data-ttu-id="f3103-102">LockTypeEnum</span><span class="sxs-lookup"><span data-stu-id="f3103-102">LockTypeEnum</span></span>

<span data-ttu-id="f3103-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f3103-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f3103-104">指定在编辑过程中对记录设置的锁定类型。</span><span class="sxs-lookup"><span data-stu-id="f3103-104">Specifies the type of lock placed on records during editing.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f3103-105">常量</span><span class="sxs-lookup"><span data-stu-id="f3103-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="f3103-106">值</span><span class="sxs-lookup"><span data-stu-id="f3103-106">Value</span></span></p></th>
<th><p><span data-ttu-id="f3103-107">说明</span><span class="sxs-lookup"><span data-stu-id="f3103-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3103-108"><strong>adLockBatchOptimistic</strong></span><span class="sxs-lookup"><span data-stu-id="f3103-108"><strong>adLockBatchOptimistic</strong></span></span></p></td>
<td><p><span data-ttu-id="f3103-109">4</span><span class="sxs-lookup"><span data-stu-id="f3103-109">4</span></span></p></td>
<td><p><span data-ttu-id="f3103-p101">指示开放式批更新。这是批更新模式所必需的。</span><span class="sxs-lookup"><span data-stu-id="f3103-p101">Indicates optimistic batch updates. Required for batch update mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3103-112"><strong>adLockOptimistic</strong></span><span class="sxs-lookup"><span data-stu-id="f3103-112"><strong>adLockOptimistic</strong></span></span></p></td>
<td><p><span data-ttu-id="f3103-113">3</span><span class="sxs-lookup"><span data-stu-id="f3103-113">3</span></span></p></td>
<td><p><span data-ttu-id="f3103-p102">指示逐记录的开放式锁定。提供程序使用开放式锁定，即仅在您调用 <a href="update-method-ado.md">Update</a> 方法时锁定记录。</span><span class="sxs-lookup"><span data-stu-id="f3103-p102">Indicates optimistic locking, record by record. The provider uses optimistic locking, locking records only when you call the <a href="update-method-ado.md">Update</a> method.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3103-116"><strong>adLockPessimistic</strong></span><span class="sxs-lookup"><span data-stu-id="f3103-116"><strong>adLockPessimistic</strong></span></span></p></td>
<td><p><span data-ttu-id="f3103-117">2</span><span class="sxs-lookup"><span data-stu-id="f3103-117">2</span></span></p></td>
<td><p><span data-ttu-id="f3103-p103">指示以保守方式逐个锁定记录。提供程序执行必要的操作（通常通过在编辑之后立即锁定数据源的记录）以确保成功编辑记录。</span><span class="sxs-lookup"><span data-stu-id="f3103-p103">Indicates pessimistic locking, record by record. The provider does what is necessary to ensure successful editing of the records, usually by locking records at the data source immediately after editing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3103-120"><strong>adLockReadOnly</strong></span><span class="sxs-lookup"><span data-stu-id="f3103-120"><strong>adLockReadOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="f3103-121">1</span><span class="sxs-lookup"><span data-stu-id="f3103-121">1</span></span></p></td>
<td><p><span data-ttu-id="f3103-p104">指示只读记录。您不能修改数据。</span><span class="sxs-lookup"><span data-stu-id="f3103-p104">Indicates read-only records. You cannot alter the data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3103-124"><strong>adLockUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="f3103-124"><strong>adLockUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="f3103-125">-1</span><span class="sxs-lookup"><span data-stu-id="f3103-125">-1</span></span></p></td>
<td><p><span data-ttu-id="f3103-p105">不指定锁定类型。对于克隆，使用与原始锁相同的类型来创建克隆。</span><span class="sxs-lookup"><span data-stu-id="f3103-p105">Does not specify a type of lock. For clones, the clone is created with the same lock type as the original.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="f3103-128">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="f3103-128">ADO/WFC equivalent</span></span>

<span data-ttu-id="f3103-129">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="f3103-129">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f3103-130">常量</span><span class="sxs-lookup"><span data-stu-id="f3103-130">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3103-131">AdoEnums.LockType.BATCHOPTIMISTIC</span><span class="sxs-lookup"><span data-stu-id="f3103-131">AdoEnums.LockType.BATCHOPTIMISTIC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3103-132">AdoEnums.LockType.OPTIMISTIC</span><span class="sxs-lookup"><span data-stu-id="f3103-132">AdoEnums.LockType.OPTIMISTIC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3103-133">AdoEnums.LockType.PESSIMISTIC</span><span class="sxs-lookup"><span data-stu-id="f3103-133">AdoEnums.LockType.PESSIMISTIC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3103-134">AdoEnums.LockType.READONLY</span><span class="sxs-lookup"><span data-stu-id="f3103-134">AdoEnums.LockType.READONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3103-135">AdoEnums.LockType.UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="f3103-135">AdoEnums.LockType.UNSPECIFIED</span></span></p></td>
</tr>
</tbody>
</table>

