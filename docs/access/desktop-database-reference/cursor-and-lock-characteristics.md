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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704614"
---
# <a name="cursor-and-lock-characteristics"></a><span data-ttu-id="61edd-102">游标和锁定特征</span><span class="sxs-lookup"><span data-stu-id="61edd-102">Cursor and lock characteristics</span></span>

<span data-ttu-id="61edd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="61edd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="61edd-104">尽管游标的特征依赖于提供程序的功能，但以下优点和缺点通常适用于各种游标和锁定。</span><span class="sxs-lookup"><span data-stu-id="61edd-104">While the characteristics of a cursor depend upon capabilities of the provider, the following advantages and disadvantages generally apply to the various types of cursors and locks.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="61edd-105">游标或锁定类型</span><span class="sxs-lookup"><span data-stu-id="61edd-105">Cursor or lock type</span></span></p></th>
<th><p><span data-ttu-id="61edd-106">优点</span><span class="sxs-lookup"><span data-stu-id="61edd-106">Advantages</span></span></p></th>
<th><p><span data-ttu-id="61edd-107">缺点</span><span class="sxs-lookup"><span data-stu-id="61edd-107">Disadvantages</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61edd-108"><strong>adOpenForwardOnly</strong></span><span class="sxs-lookup"><span data-stu-id="61edd-108"><strong>adOpenForwardOnly</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-109">资源要求低</span><span class="sxs-lookup"><span data-stu-id="61edd-109">Low resource requirements</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-110">不能向后滚动</span><span class="sxs-lookup"><span data-stu-id="61edd-110">Cannot scroll backward</span></span></p></li>
<li><p><span data-ttu-id="61edd-111">没有数据并发</span><span class="sxs-lookup"><span data-stu-id="61edd-111">No data concurrency</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61edd-112"><strong>为 adOpenStatic</strong></span><span class="sxs-lookup"><span data-stu-id="61edd-112"><strong>adOpenStatic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-113">可滚动</span><span class="sxs-lookup"><span data-stu-id="61edd-113">Scrollable</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-114">没有数据并发</span><span class="sxs-lookup"><span data-stu-id="61edd-114">No data concurrency</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61edd-115"><strong>adOpenKeyset</strong></span><span class="sxs-lookup"><span data-stu-id="61edd-115"><strong>adOpenKeyset</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-116">有数据并发</span><span class="sxs-lookup"><span data-stu-id="61edd-116">Some data concurrency</span></span></p></li>
<li><p><span data-ttu-id="61edd-117">可滚动</span><span class="sxs-lookup"><span data-stu-id="61edd-117">Scrollable</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-118">资源要求高</span><span class="sxs-lookup"><span data-stu-id="61edd-118">Higher resource requirements</span></span></p></li>
<li><p><span data-ttu-id="61edd-119">在连接中断的方案中不可用</span><span class="sxs-lookup"><span data-stu-id="61edd-119">Not available in disconnected scenario</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61edd-120"><strong>adOpenDynamic</strong></span><span class="sxs-lookup"><span data-stu-id="61edd-120"><strong>adOpenDynamic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-121">高数据并发</span><span class="sxs-lookup"><span data-stu-id="61edd-121">High data concurrency</span></span></p></li>
<li><p><span data-ttu-id="61edd-122">可滚动</span><span class="sxs-lookup"><span data-stu-id="61edd-122">Scrollable</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-123">资源要求最高</span><span class="sxs-lookup"><span data-stu-id="61edd-123">Highest resource requirements</span></span></p></li>
<li><p><span data-ttu-id="61edd-124">在连接中断的方案中不可用</span><span class="sxs-lookup"><span data-stu-id="61edd-124">Not available in disconnected scenario</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61edd-125"><strong>adLockReadOnly</strong></span><span class="sxs-lookup"><span data-stu-id="61edd-125"><strong>adLockReadOnly</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-126">资源要求低</span><span class="sxs-lookup"><span data-stu-id="61edd-126">Low resource requirements</span></span></p></li>
<li><p><span data-ttu-id="61edd-127">可伸缩性高</span><span class="sxs-lookup"><span data-stu-id="61edd-127">Highly scalable</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-128">无法通过游标更新数据</span><span class="sxs-lookup"><span data-stu-id="61edd-128">Data not updatable through cursor</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61edd-129"><strong>adLockBatchOptimistic</strong></span><span class="sxs-lookup"><span data-stu-id="61edd-129"><strong>adLockBatchOptimistic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-130">批更新</span><span class="sxs-lookup"><span data-stu-id="61edd-130">Batch updates</span></span></p></li>
<li><p><span data-ttu-id="61edd-131">允许连接中断的方案</span><span class="sxs-lookup"><span data-stu-id="61edd-131">Allows disconnected scenarios</span></span></p></li>
<li><p><span data-ttu-id="61edd-132">其他用户可以访问数据</span><span class="sxs-lookup"><span data-stu-id="61edd-132">Other users able to access data</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-133">多个用户可以同时更改数据</span><span class="sxs-lookup"><span data-stu-id="61edd-133">Data can be changed by multiple users at once</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61edd-134"><strong>adLockPessimistic</strong></span><span class="sxs-lookup"><span data-stu-id="61edd-134"><strong>adLockPessimistic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-135">锁定时其他用户不能更改数据</span><span class="sxs-lookup"><span data-stu-id="61edd-135">Data cannot be changed by other users while locked</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-136">锁定时防止其他用户访问数据</span><span class="sxs-lookup"><span data-stu-id="61edd-136">Prevents other users from accessing data while locked</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61edd-137"><strong>adLockOptimistic</strong></span><span class="sxs-lookup"><span data-stu-id="61edd-137"><strong>adLockOptimistic</strong></span></span></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-138">其他用户可以访问数据</span><span class="sxs-lookup"><span data-stu-id="61edd-138">Other users able to access data</span></span></p></li>
</ul>
<p></p></td>
<td><p></p>
<ul>
<li><p><span data-ttu-id="61edd-139">多个用户可以同时更改数据</span><span class="sxs-lookup"><span data-stu-id="61edd-139">Data can be changed by multiple users at once</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

