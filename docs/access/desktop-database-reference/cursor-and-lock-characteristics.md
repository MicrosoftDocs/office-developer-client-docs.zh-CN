---
title: 游标和锁定特征
TOCTitle: Cursor and lock characteristics
ms:assetid: 5f8b6700-14f6-d342-42f6-cc8e89c71a1a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249347(v=office.15)
ms:contentKeyID: 48545164
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 41a42aa3b0c49a5d871fa7b079a26c7d8076116a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295287"
---
# <a name="cursor-and-lock-characteristics"></a><span data-ttu-id="6851d-102">游标和锁定特征</span><span class="sxs-lookup"><span data-stu-id="6851d-102">Cursor and lock characteristics</span></span>

<span data-ttu-id="6851d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6851d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6851d-104">尽管游标的特征依赖于提供程序的功能，但以下优点和缺点通常适用于各种游标和锁定。</span><span class="sxs-lookup"><span data-stu-id="6851d-104">While the characteristics of a cursor depend upon capabilities of the provider, the following advantages and disadvantages generally apply to the various types of cursors and locks.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6851d-105">游标或锁定类型</span><span class="sxs-lookup"><span data-stu-id="6851d-105">Cursor or lock type</span></span></p></th>
<th><p><span data-ttu-id="6851d-106">优点</span><span class="sxs-lookup"><span data-stu-id="6851d-106">Advantages</span></span></p></th>
<th><p><span data-ttu-id="6851d-107">缺点</span><span class="sxs-lookup"><span data-stu-id="6851d-107">Disadvantages</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6851d-108"><strong>adOpenForwardOnly</strong></span><span class="sxs-lookup"><span data-stu-id="6851d-108"><strong>adOpenForwardOnly</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-109">资源要求低</span><span class="sxs-lookup"><span data-stu-id="6851d-109">Low resource requirements</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-110">不能向后滚动</span><span class="sxs-lookup"><span data-stu-id="6851d-110">Cannot scroll backward</span></span></p></li>
<li><p><span data-ttu-id="6851d-111">没有数据并发</span><span class="sxs-lookup"><span data-stu-id="6851d-111">No data concurrency</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6851d-112"><strong>adOpenStatic</strong></span><span class="sxs-lookup"><span data-stu-id="6851d-112"><strong>adOpenStatic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-113">可</span><span class="sxs-lookup"><span data-stu-id="6851d-113">Scrollable</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-114">没有数据并发</span><span class="sxs-lookup"><span data-stu-id="6851d-114">No data concurrency</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6851d-115"><strong>adOpenKeyset</strong></span><span class="sxs-lookup"><span data-stu-id="6851d-115"><strong>adOpenKeyset</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-116">有数据并发</span><span class="sxs-lookup"><span data-stu-id="6851d-116">Some data concurrency</span></span></p></li>
<li><p><span data-ttu-id="6851d-117">可</span><span class="sxs-lookup"><span data-stu-id="6851d-117">Scrollable</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-118">资源要求高</span><span class="sxs-lookup"><span data-stu-id="6851d-118">Higher resource requirements</span></span></p></li>
<li><p><span data-ttu-id="6851d-119">在连接中断的方案中不可用</span><span class="sxs-lookup"><span data-stu-id="6851d-119">Not available in disconnected scenario</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6851d-120"><strong>adOpenDynamic</strong></span><span class="sxs-lookup"><span data-stu-id="6851d-120"><strong>adOpenDynamic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-121">高数据并发</span><span class="sxs-lookup"><span data-stu-id="6851d-121">High data concurrency</span></span></p></li>
<li><p><span data-ttu-id="6851d-122">可</span><span class="sxs-lookup"><span data-stu-id="6851d-122">Scrollable</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-123">资源要求最高</span><span class="sxs-lookup"><span data-stu-id="6851d-123">Highest resource requirements</span></span></p></li>
<li><p><span data-ttu-id="6851d-124">在连接中断的方案中不可用</span><span class="sxs-lookup"><span data-stu-id="6851d-124">Not available in disconnected scenario</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6851d-125"><strong>adLockReadOnly</strong></span><span class="sxs-lookup"><span data-stu-id="6851d-125"><strong>adLockReadOnly</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-126">资源要求低</span><span class="sxs-lookup"><span data-stu-id="6851d-126">Low resource requirements</span></span></p></li>
<li><p><span data-ttu-id="6851d-127">可伸缩性高</span><span class="sxs-lookup"><span data-stu-id="6851d-127">Highly scalable</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-128">无法通过游标更新数据</span><span class="sxs-lookup"><span data-stu-id="6851d-128">Data not updatable through cursor</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6851d-129"><strong>adLockBatchOptimistic</strong></span><span class="sxs-lookup"><span data-stu-id="6851d-129"><strong>adLockBatchOptimistic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-130">批更新</span><span class="sxs-lookup"><span data-stu-id="6851d-130">Batch updates</span></span></p></li>
<li><p><span data-ttu-id="6851d-131">允许连接中断的方案</span><span class="sxs-lookup"><span data-stu-id="6851d-131">Allows disconnected scenarios</span></span></p></li>
<li><p><span data-ttu-id="6851d-132">其他用户可以访问数据</span><span class="sxs-lookup"><span data-stu-id="6851d-132">Other users able to access data</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-133">多个用户可以同时更改数据</span><span class="sxs-lookup"><span data-stu-id="6851d-133">Data can be changed by multiple users at once</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6851d-134"><strong>adLockPessimistic</strong></span><span class="sxs-lookup"><span data-stu-id="6851d-134"><strong>adLockPessimistic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-135">锁定时其他用户不能更改数据</span><span class="sxs-lookup"><span data-stu-id="6851d-135">Data cannot be changed by other users while locked</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-136">锁定时防止其他用户访问数据</span><span class="sxs-lookup"><span data-stu-id="6851d-136">Prevents other users from accessing data while locked</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6851d-137"><strong>adLockOptimistic</strong></span><span class="sxs-lookup"><span data-stu-id="6851d-137"><strong>adLockOptimistic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-138">其他用户可以访问数据</span><span class="sxs-lookup"><span data-stu-id="6851d-138">Other users able to access data</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="6851d-139">多个用户可以同时更改数据</span><span class="sxs-lookup"><span data-stu-id="6851d-139">Data can be changed by multiple users at once</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

