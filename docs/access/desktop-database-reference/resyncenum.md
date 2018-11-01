---
title: ResyncEnum （访问桌面数据库参考 （英文）
TOCTitle: ResyncEnum
ms:assetid: 3d38b77b-6afe-e6a0-1a05-7c7ffc19edef
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249164(v=office.15)
ms:contentKeyID: 48544337
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: d75ae42d5d3b63e1eea56153ef8e2dd2fb366a30
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870063"
---
# <a name="resyncenum"></a><span data-ttu-id="1fef5-102">ResyncEnum</span><span class="sxs-lookup"><span data-stu-id="1fef5-102">ResyncEnum</span></span>

<span data-ttu-id="1fef5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1fef5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1fef5-104">指定是否通过调用 [Resync](resync-method-ado.md) 来覆盖基础值。</span><span class="sxs-lookup"><span data-stu-id="1fef5-104">Specifies whether underlying values are overwritten by a call to [Resync](resync-method-ado.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1fef5-105">常量</span><span class="sxs-lookup"><span data-stu-id="1fef5-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="1fef5-106">值</span><span class="sxs-lookup"><span data-stu-id="1fef5-106">Value</span></span></p></th>
<th><p><span data-ttu-id="1fef5-107">说明</span><span class="sxs-lookup"><span data-stu-id="1fef5-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fef5-108"><strong>adResyncAllValues</strong></span><span class="sxs-lookup"><span data-stu-id="1fef5-108"><strong>adResyncAllValues</strong></span></span></p></td>
<td><p><span data-ttu-id="1fef5-109">2</span><span class="sxs-lookup"><span data-stu-id="1fef5-109">2</span></span></p></td>
<td><p><span data-ttu-id="1fef5-p101">默认值。覆盖数据，且取消挂起更改。</span><span class="sxs-lookup"><span data-stu-id="1fef5-p101">Default. Overwrites data, and pending updates are canceled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fef5-112"><strong>adResyncUnderlyingValues</strong></span><span class="sxs-lookup"><span data-stu-id="1fef5-112"><strong>adResyncUnderlyingValues</strong></span></span></p></td>
<td><p><span data-ttu-id="1fef5-113">1</span><span class="sxs-lookup"><span data-stu-id="1fef5-113">1</span></span></p></td>
<td><p><span data-ttu-id="1fef5-114">不覆盖数据，且不取消挂起更改。</span><span class="sxs-lookup"><span data-stu-id="1fef5-114">Does not overwrite data, and pending updates are not canceled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="1fef5-115">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="1fef5-115">ADO/WFC equivalent</span></span>

<span data-ttu-id="1fef5-116">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="1fef5-116">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1fef5-117">常量</span><span class="sxs-lookup"><span data-stu-id="1fef5-117">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fef5-118">AdoEnums.Resync.ALLVALUES</span><span class="sxs-lookup"><span data-stu-id="1fef5-118">AdoEnums.Resync.ALLVALUES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fef5-119">AdoEnums.Resync.UNDERLYINGVALUES</span><span class="sxs-lookup"><span data-stu-id="1fef5-119">AdoEnums.Resync.UNDERLYINGVALUES</span></span></p></td>
</tr>
</tbody>
</table>

