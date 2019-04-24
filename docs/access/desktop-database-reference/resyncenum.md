---
title: ResyncEnum (Access desktop database reference)
TOCTitle: ResyncEnum
ms:assetid: 3d38b77b-6afe-e6a0-1a05-7c7ffc19edef
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249164(v=office.15)
ms:contentKeyID: 48544337
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ff09d69a9cf36246b3367202531a011c4e1aba12
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306543"
---
# <a name="resyncenum"></a><span data-ttu-id="daa09-102">ResyncEnum</span><span class="sxs-lookup"><span data-stu-id="daa09-102">ResyncEnum</span></span>

<span data-ttu-id="daa09-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="daa09-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="daa09-104">指定是否通过调用 [Resync](resync-method-ado.md) 来覆盖基础值。</span><span class="sxs-lookup"><span data-stu-id="daa09-104">Specifies whether underlying values are overwritten by a call to [Resync](resync-method-ado.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="daa09-105">常量</span><span class="sxs-lookup"><span data-stu-id="daa09-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="daa09-106">值</span><span class="sxs-lookup"><span data-stu-id="daa09-106">Value</span></span></p></th>
<th><p><span data-ttu-id="daa09-107">说明</span><span class="sxs-lookup"><span data-stu-id="daa09-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa09-108"><strong>adResyncAllValues</strong></span><span class="sxs-lookup"><span data-stu-id="daa09-108"><strong>adResyncAllValues</strong></span></span></p></td>
<td><p><span data-ttu-id="daa09-109">双面</span><span class="sxs-lookup"><span data-stu-id="daa09-109">2</span></span></p></td>
<td><p><span data-ttu-id="daa09-p101">默认值。覆盖数据，且取消挂起更改。</span><span class="sxs-lookup"><span data-stu-id="daa09-p101">Default. Overwrites data, and pending updates are canceled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa09-112"><strong>adResyncUnderlyingValues</strong></span><span class="sxs-lookup"><span data-stu-id="daa09-112"><strong>adResyncUnderlyingValues</strong></span></span></p></td>
<td><p><span data-ttu-id="daa09-113">1</span><span class="sxs-lookup"><span data-stu-id="daa09-113">1</span></span></p></td>
<td><p><span data-ttu-id="daa09-114">不覆盖数据，且不取消挂起更改。</span><span class="sxs-lookup"><span data-stu-id="daa09-114">Does not overwrite data, and pending updates are not canceled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="daa09-115">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="daa09-115">ADO/WFC equivalent</span></span>

<span data-ttu-id="daa09-116">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="daa09-116">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="daa09-117">常量</span><span class="sxs-lookup"><span data-stu-id="daa09-117">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa09-118">AdoEnums ALLVALUES</span><span class="sxs-lookup"><span data-stu-id="daa09-118">AdoEnums.Resync.ALLVALUES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa09-119">AdoEnums UNDERLYINGVALUES</span><span class="sxs-lookup"><span data-stu-id="daa09-119">AdoEnums.Resync.UNDERLYINGVALUES</span></span></p></td>
</tr>
</tbody>
</table>

