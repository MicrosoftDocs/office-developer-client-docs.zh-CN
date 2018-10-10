---
title: CursorLocationEnum （访问桌面数据库参考 （英文）
TOCTitle: CursorLocationEnum
ms:assetid: 520cc738-998b-ce80-6362-0df310c40c39
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249268(v=office.15)
ms:contentKeyID: 48544836
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 90226413579a8fac7586cbd5ef08510a36a42959
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466890"
---
# <a name="cursorlocationenum"></a><span data-ttu-id="b2b73-102">CursorLocationEnum</span><span class="sxs-lookup"><span data-stu-id="b2b73-102">CursorLocationEnum</span></span>


<span data-ttu-id="b2b73-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b2b73-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b2b73-104">用于指定游标服务的位置。</span><span class="sxs-lookup"><span data-stu-id="b2b73-104">Specifies the location of the cursor service.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b2b73-105">常量</span><span class="sxs-lookup"><span data-stu-id="b2b73-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="b2b73-106">值</span><span class="sxs-lookup"><span data-stu-id="b2b73-106">Value</span></span></p></th>
<th><p><span data-ttu-id="b2b73-107">说明</span><span class="sxs-lookup"><span data-stu-id="b2b73-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2b73-108"><strong>adUseClient</strong></span><span class="sxs-lookup"><span data-stu-id="b2b73-108"><strong>adUseClient</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b73-109">3</span><span class="sxs-lookup"><span data-stu-id="b2b73-109">3</span></span></p></td>
<td><p><span data-ttu-id="b2b73-110">使用由本地游标库提供的客户端游标。</span><span class="sxs-lookup"><span data-stu-id="b2b73-110">Uses client-side cursors supplied by a local cursor library.</span></span> <span data-ttu-id="b2b73-111">本地游标服务通常将允许驱动程序提供的游标可能不会的许多功能，以便使用此设置可能会提供一个优点相对于将启用的功能。</span><span class="sxs-lookup"><span data-stu-id="b2b73-111">Local cursor services often will allow many features that driver-supplied cursors may not, so using this setting may provide an advantage with respect to features that will be enabled.</span></span> <span data-ttu-id="b2b73-112">向后兼容性，还支持同义词<strong>adUseClientBatch</strong> 。</span><span class="sxs-lookup"><span data-stu-id="b2b73-112">For backward compatibility, the synonym <strong>adUseClientBatch</strong> is also supported.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b73-113"><strong>adUseNone</strong></span><span class="sxs-lookup"><span data-stu-id="b2b73-113"><strong>adUseNone</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b73-114">1</span><span class="sxs-lookup"><span data-stu-id="b2b73-114">1</span></span></p></td>
<td><p><span data-ttu-id="b2b73-p102">不使用游标服务。（此常量已过时，仅仅为了向后兼容而出现。）</span><span class="sxs-lookup"><span data-stu-id="b2b73-p102">Does not use cursor services. (This constant is obsolete and appears solely for the sake of backward compatibility.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b73-117"><strong>为 adUseServer</strong></span><span class="sxs-lookup"><span data-stu-id="b2b73-117"><strong>adUseServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b73-118">2</span><span class="sxs-lookup"><span data-stu-id="b2b73-118">2</span></span></p></td>
<td><p><span data-ttu-id="b2b73-p103">默认值。使用数据提供程序或驱动程序提供的游标。这些游标有时候非常灵活，允许对他人对数据源所做的更改具有额外的敏感度。但是，<a href="microsoft-cursor-service-for-ole-db-ado-service-component.md">Microsoft Cursor Service for OLE DB</a> 的某些功能（例如未关联的 <a href="recordset-object-ado.md">Recordset</a> 对象）无法使用服务器端游标进行模拟，因此，使用此设置时这些功能将不可用。</span><span class="sxs-lookup"><span data-stu-id="b2b73-p103">Default. Uses data-provider or driver-supplied cursors. These cursors are sometimes very flexible and allow for additional sensitivity to changes others make to the data source. However, some features of the <a href="microsoft-cursor-service-for-ole-db-ado-service-component.md">Microsoft Cursor Service for OLE DB</a> (such as disassociated <a href="recordset-object-ado.md">Recordset</a> objects) cannot be simulated with server-side cursors and these features will be unavailable with this setting.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b2b73-123">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="b2b73-123">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="b2b73-124">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="b2b73-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b2b73-125">常量</span><span class="sxs-lookup"><span data-stu-id="b2b73-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2b73-126">AdoEnums.CursorLocation.CLIENT</span><span class="sxs-lookup"><span data-stu-id="b2b73-126">AdoEnums.CursorLocation.CLIENT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b73-127">AdoEnums.CursorLocation.NONE</span><span class="sxs-lookup"><span data-stu-id="b2b73-127">AdoEnums.CursorLocation.NONE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b73-128">AdoEnums.CursorLocation.SERVER</span><span class="sxs-lookup"><span data-stu-id="b2b73-128">AdoEnums.CursorLocation.SERVER</span></span></p></td>
</tr>
</tbody>
</table>

