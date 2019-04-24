---
title: 为 cursorlocationenum (Access desktop database reference)
TOCTitle: CursorLocationEnum
ms:assetid: 520cc738-998b-ce80-6362-0df310c40c39
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249268(v=office.15)
ms:contentKeyID: 48544836
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 95e5744d5e19e7c3d40de19e240bbe338b2d5d55
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295210"
---
# <a name="cursorlocationenum"></a><span data-ttu-id="f327c-102">CursorLocationEnum</span><span class="sxs-lookup"><span data-stu-id="f327c-102">CursorLocationEnum</span></span>

<span data-ttu-id="f327c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f327c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f327c-104">用于指定游标服务的位置。</span><span class="sxs-lookup"><span data-stu-id="f327c-104">Specifies the location of the cursor service.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f327c-105">常量</span><span class="sxs-lookup"><span data-stu-id="f327c-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="f327c-106">值</span><span class="sxs-lookup"><span data-stu-id="f327c-106">Value</span></span></p></th>
<th><p><span data-ttu-id="f327c-107">说明</span><span class="sxs-lookup"><span data-stu-id="f327c-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f327c-108"><strong>adUseClient</strong></span><span class="sxs-lookup"><span data-stu-id="f327c-108"><strong>adUseClient</strong></span></span></p></td>
<td><p><span data-ttu-id="f327c-109">第三章</span><span class="sxs-lookup"><span data-stu-id="f327c-109">3</span></span></p></td>
<td><p><span data-ttu-id="f327c-110">使用由本地游标库提供的客户端游标。</span><span class="sxs-lookup"><span data-stu-id="f327c-110">Uses client-side cursors supplied by a local cursor library.</span></span> <span data-ttu-id="f327c-111">本地游标服务通常能够允许驱动程序提供的游标所不允许的许多功能，因此，对于将要启用的功能来说，使用此设置可以提供便利。</span><span class="sxs-lookup"><span data-stu-id="f327c-111">Local cursor services often will allow many features that driver-supplied cursors may not, so using this setting may provide an advantage with respect to features that will be enabled.</span></span> <span data-ttu-id="f327c-112">为了向后兼容，还支持同义词 <strong>adUseClientBatch</strong>。</span><span class="sxs-lookup"><span data-stu-id="f327c-112">For backward compatibility, the synonym <strong>adUseClientBatch</strong> is also supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f327c-113"><strong>adUseNone</strong></span><span class="sxs-lookup"><span data-stu-id="f327c-113"><strong>adUseNone</strong></span></span></p></td>
<td><p><span data-ttu-id="f327c-114">1</span><span class="sxs-lookup"><span data-stu-id="f327c-114">1</span></span></p></td>
<td><p><span data-ttu-id="f327c-p102">不使用游标服务。（此常量已过时，仅仅为了向后兼容而出现。）</span><span class="sxs-lookup"><span data-stu-id="f327c-p102">Does not use cursor services. (This constant is obsolete and appears solely for the sake of backward compatibility.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f327c-117"><strong>adUseServer</strong></span><span class="sxs-lookup"><span data-stu-id="f327c-117"><strong>adUseServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f327c-118">双面</span><span class="sxs-lookup"><span data-stu-id="f327c-118">2</span></span></p></td>
<td><p><span data-ttu-id="f327c-119">默认值。</span><span class="sxs-lookup"><span data-stu-id="f327c-119">Default.</span></span> <span data-ttu-id="f327c-120">使用数据提供程序或驱动程序提供的游标。</span><span class="sxs-lookup"><span data-stu-id="f327c-120">Uses data-provider or driver-supplied cursors.</span></span> <span data-ttu-id="f327c-121">这些游标有时候非常灵活，允许对他人对数据源所做的更改具有额外的敏感度。</span><span class="sxs-lookup"><span data-stu-id="f327c-121">These cursors are sometimes very flexible and allow for additional sensitivity to changes others make to the data source.</span></span> <span data-ttu-id="f327c-122">但是, <a href="microsoft-cursor-service-for-ole-db-ado-service-component.md">Microsoft Cursor Service for OLE DB</a> (如未关联的<a href="recordset-object-ado.md">Recordset</a>对象) 的某些功能无法使用服务器端游标进行模拟, 并且这些功能将在此设置中不可用。</span><span class="sxs-lookup"><span data-stu-id="f327c-122">However, some features of the <a href="microsoft-cursor-service-for-ole-db-ado-service-component.md">Microsoft Cursor Service for OLE DB</a> (such as disassociated <a href="recordset-object-ado.md">Recordset</a> objects) cannot be simulated with server-side cursors, and these features will be unavailable with this setting.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="f327c-123">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="f327c-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="f327c-124">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="f327c-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f327c-125">常量</span><span class="sxs-lookup"><span data-stu-id="f327c-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f327c-126">AdoEnums CursorLocation</span><span class="sxs-lookup"><span data-stu-id="f327c-126">AdoEnums.CursorLocation.CLIENT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f327c-127">AdoEnums CursorLocation</span><span class="sxs-lookup"><span data-stu-id="f327c-127">AdoEnums.CursorLocation.NONE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f327c-128">AdoEnums CursorLocation</span><span class="sxs-lookup"><span data-stu-id="f327c-128">AdoEnums.CursorLocation.SERVER</span></span></p></td>
</tr>
</tbody>
</table>

