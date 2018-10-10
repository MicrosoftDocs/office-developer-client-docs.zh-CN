---
title: ResyncEnum （访问桌面数据库参考 （英文）
TOCTitle: ResyncEnum
ms:assetid: 3d38b77b-6afe-e6a0-1a05-7c7ffc19edef
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249164(v=office.15)
ms:contentKeyID: 48544337
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3607c0796edb58a6d4227fee09a658220deabfe7
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468767"
---
# <a name="resyncenum"></a><span data-ttu-id="cde7e-102">ResyncEnum</span><span class="sxs-lookup"><span data-stu-id="cde7e-102">ResyncEnum</span></span>


<span data-ttu-id="cde7e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cde7e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cde7e-104">指定是否通过调用 [Resync](resync-method-ado.md) 来覆盖基础值。</span><span class="sxs-lookup"><span data-stu-id="cde7e-104">Specifies whether underlying values are overwritten by a call to [Resync](resync-method-ado.md).</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cde7e-105">常量</span><span class="sxs-lookup"><span data-stu-id="cde7e-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="cde7e-106">值</span><span class="sxs-lookup"><span data-stu-id="cde7e-106">Value</span></span></p></th>
<th><p><span data-ttu-id="cde7e-107">说明</span><span class="sxs-lookup"><span data-stu-id="cde7e-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cde7e-108"><strong>adResyncAllValues</strong></span><span class="sxs-lookup"><span data-stu-id="cde7e-108"><strong>adResyncAllValues</strong></span></span></p></td>
<td><p><span data-ttu-id="cde7e-109">2</span><span class="sxs-lookup"><span data-stu-id="cde7e-109">2</span></span></p></td>
<td><p><span data-ttu-id="cde7e-p101">默认值。覆盖数据，且取消挂起更改。</span><span class="sxs-lookup"><span data-stu-id="cde7e-p101">Default. Overwrites data, and pending updates are canceled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cde7e-112"><strong>adResyncUnderlyingValues</strong></span><span class="sxs-lookup"><span data-stu-id="cde7e-112"><strong>adResyncUnderlyingValues</strong></span></span></p></td>
<td><p><span data-ttu-id="cde7e-113">1</span><span class="sxs-lookup"><span data-stu-id="cde7e-113">1</span></span></p></td>
<td><p><span data-ttu-id="cde7e-114">不覆盖数据，且不取消挂起更改。</span><span class="sxs-lookup"><span data-stu-id="cde7e-114">Does not overwrite data, and pending updates are not canceled.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cde7e-115">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="cde7e-115">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="cde7e-116">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="cde7e-116">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cde7e-117">常量</span><span class="sxs-lookup"><span data-stu-id="cde7e-117">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cde7e-118">AdoEnums.Resync.ALLVALUES</span><span class="sxs-lookup"><span data-stu-id="cde7e-118">AdoEnums.Resync.ALLVALUES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cde7e-119">AdoEnums.Resync.UNDERLYINGVALUES</span><span class="sxs-lookup"><span data-stu-id="cde7e-119">AdoEnums.Resync.UNDERLYINGVALUES</span></span></p></td>
</tr>
</tbody>
</table>

