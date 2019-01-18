---
title: CursorTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: CursorTypeEnum
ms:assetid: 7c5fa8b2-85ea-a0a7-41f1-a78650aced3e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249519(v=office.15)
ms:contentKeyID: 48545835
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0bcaaa1298f12d72c5e836dcfe1e74cdcda68d19
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710788"
---
# <a name="cursortypeenum"></a><span data-ttu-id="8b5f3-102">CursorTypeEnum</span><span class="sxs-lookup"><span data-stu-id="8b5f3-102">CursorTypeEnum</span></span>

<span data-ttu-id="8b5f3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8b5f3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8b5f3-104">指定在 [Recordset](recordset-object-ado.md) 对象中使用的游标的类型。</span><span class="sxs-lookup"><span data-stu-id="8b5f3-104">Specifies the type of cursor used in a [Recordset](recordset-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8b5f3-105">常量</span><span class="sxs-lookup"><span data-stu-id="8b5f3-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="8b5f3-106">值</span><span class="sxs-lookup"><span data-stu-id="8b5f3-106">Value</span></span></p></th>
<th><p><span data-ttu-id="8b5f3-107">说明</span><span class="sxs-lookup"><span data-stu-id="8b5f3-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b5f3-108"><strong>adOpenDynamic</strong></span><span class="sxs-lookup"><span data-stu-id="8b5f3-108"><strong>adOpenDynamic</strong></span></span></p></td>
<td><p><span data-ttu-id="8b5f3-109">2</span><span class="sxs-lookup"><span data-stu-id="8b5f3-109">2</span></span></p></td>
<td><p><span data-ttu-id="8b5f3-p101">使用动态游标。其他用户所做的添加、更改和删除均可见，且允许在 <strong>Recordset</strong> 中移动所有类型，但提供程序不支持的书签除外。</span><span class="sxs-lookup"><span data-stu-id="8b5f3-p101">Uses a dynamic cursor. Additions, changes, and deletions by other users are visible, and all types of movement through the <strong>Recordset</strong> are allowed, except for bookmarks, if the provider doesn't support them.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b5f3-112"><strong>adOpenForwardOnly</strong></span><span class="sxs-lookup"><span data-stu-id="8b5f3-112"><strong>adOpenForwardOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="8b5f3-113">0</span><span class="sxs-lookup"><span data-stu-id="8b5f3-113">0</span></span></p></td>
<td><p><span data-ttu-id="8b5f3-p102">默认值。使用仅向前型游标。与静态游标相似，但您只能在记录中向前滚动。这样可以在您仅需要在 <strong>Recordset</strong> 中通过一次时提高性能。</span><span class="sxs-lookup"><span data-stu-id="8b5f3-p102">Default. Uses a forward-only cursor. Identical to a static cursor, except that you can only scroll forward through records. This improves performance when you need to make only one pass through a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b5f3-118"><strong>adOpenKeyset</strong></span><span class="sxs-lookup"><span data-stu-id="8b5f3-118"><strong>adOpenKeyset</strong></span></span></p></td>
<td><p><span data-ttu-id="8b5f3-119">1</span><span class="sxs-lookup"><span data-stu-id="8b5f3-119">1</span></span></p></td>
<td><p><span data-ttu-id="8b5f3-p103">使用键集游标。与动态游标相似，不同的是：尽管其他用户删除的记录从您的 <strong>Recordset</strong> 不可访问，但您无法看到其他用户添加的记录。由其他用户所作的数据更改仍然可见。</span><span class="sxs-lookup"><span data-stu-id="8b5f3-p103">Uses a keyset cursor. Like a dynamic cursor, except that you can't see records that other users add, although records that other users delete are inaccessible from your <strong>Recordset</strong>. Data changes by other users are still visible.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b5f3-123"><strong>为 adOpenStatic</strong></span><span class="sxs-lookup"><span data-stu-id="8b5f3-123"><strong>adOpenStatic</strong></span></span></p></td>
<td><p><span data-ttu-id="8b5f3-124">3</span><span class="sxs-lookup"><span data-stu-id="8b5f3-124">3</span></span></p></td>
<td><p><span data-ttu-id="8b5f3-p104">使用静态游标。您可用于查找数据或生成报表的记录集的静态副本。其他用户所做的添加、更改或删除不可见。</span><span class="sxs-lookup"><span data-stu-id="8b5f3-p104">Uses a static cursor. A static copy of a set of records that you can use to find data or generate reports. Additions, changes, or deletions by other users are not visible.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b5f3-128"><strong>adOpenUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="8b5f3-128"><strong>adOpenUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="8b5f3-129">-1</span><span class="sxs-lookup"><span data-stu-id="8b5f3-129">-1</span></span></p></td>
<td><p><span data-ttu-id="8b5f3-130">不指定游标类型。</span><span class="sxs-lookup"><span data-stu-id="8b5f3-130">Does not specify the type of cursor.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="8b5f3-131">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="8b5f3-131">ADO/WFC equivalent</span></span>

<span data-ttu-id="8b5f3-132">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="8b5f3-132">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8b5f3-133">常量</span><span class="sxs-lookup"><span data-stu-id="8b5f3-133">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b5f3-134">AdoEnums.CursorType.DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="8b5f3-134">AdoEnums.CursorType.DYNAMIC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b5f3-135">AdoEnums.CursorType.FORWARDONLY</span><span class="sxs-lookup"><span data-stu-id="8b5f3-135">AdoEnums.CursorType.FORWARDONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b5f3-136">AdoEnums.CursorType.KEYSET</span><span class="sxs-lookup"><span data-stu-id="8b5f3-136">AdoEnums.CursorType.KEYSET</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b5f3-137">AdoEnums.CursorType.STATIC</span><span class="sxs-lookup"><span data-stu-id="8b5f3-137">AdoEnums.CursorType.STATIC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b5f3-138">AdoEnums.CursorType.UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="8b5f3-138">AdoEnums.CursorType.UNSPECIFIED</span></span></p></td>
</tr>
</tbody>
</table>

