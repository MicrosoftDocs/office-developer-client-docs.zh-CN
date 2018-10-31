---
title: SeekEnum （访问桌面数据库参考 （英文）
TOCTitle: SeekEnum
ms:assetid: a0574809-db2d-8759-18cc-fb1cf776e8fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249737(v=office.15)
ms:contentKeyID: 48546706
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 5025706d64927482b632a17a5f71839cd4186619
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861412"
---
# <a name="seekenum"></a><span data-ttu-id="0955f-102">SeekEnum</span><span class="sxs-lookup"><span data-stu-id="0955f-102">SeekEnum</span></span>

<span data-ttu-id="0955f-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0955f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="0955f-104">用于指定要执行的 [Seek 方法 (ADO)](seek-method-ado.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="0955f-104">Specifies the type of [Seek](seek-method-ado.md) to execute.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0955f-105">常量</span><span class="sxs-lookup"><span data-stu-id="0955f-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="0955f-106">值</span><span class="sxs-lookup"><span data-stu-id="0955f-106">Value</span></span></p></th>
<th><p><span data-ttu-id="0955f-107">说明</span><span class="sxs-lookup"><span data-stu-id="0955f-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0955f-108">adSeekFirstEQ</span><span class="sxs-lookup"><span data-stu-id="0955f-108">adSeekFirstEQ</span></span></p></td>
<td><p><span data-ttu-id="0955f-109">1</span><span class="sxs-lookup"><span data-stu-id="0955f-109">1</span></span></p></td>
<td><p><span data-ttu-id="0955f-110">搜寻第一个等于 <em>KeyValues</em> 的键。</span><span class="sxs-lookup"><span data-stu-id="0955f-110">Seeks the first key equal to <em>KeyValues</em>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0955f-111">adSeekLastEQ</span><span class="sxs-lookup"><span data-stu-id="0955f-111">adSeekLastEQ</span></span></p></td>
<td><p><span data-ttu-id="0955f-112">2</span><span class="sxs-lookup"><span data-stu-id="0955f-112">2</span></span></p></td>
<td><p><span data-ttu-id="0955f-113">搜寻最后一个等于 <em>KeyValues</em> 的键。</span><span class="sxs-lookup"><span data-stu-id="0955f-113">Seeks the last key equal to <em>KeyValues</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0955f-114">adSeekAfterEQ</span><span class="sxs-lookup"><span data-stu-id="0955f-114">adSeekAfterEQ</span></span></p></td>
<td><p><span data-ttu-id="0955f-115">4</span><span class="sxs-lookup"><span data-stu-id="0955f-115">4</span></span></p></td>
<td><p><span data-ttu-id="0955f-116">搜寻等于 <em>KeyValues</em> 的键或正好在应出现匹配项的位置之后的键。</span><span class="sxs-lookup"><span data-stu-id="0955f-116">Seeks either a key equal to <em>KeyValues</em> or just after where that match would have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0955f-117">adSeekAfter</span><span class="sxs-lookup"><span data-stu-id="0955f-117">adSeekAfter</span></span></p></td>
<td><p><span data-ttu-id="0955f-118">8</span><span class="sxs-lookup"><span data-stu-id="0955f-118">8</span></span></p></td>
<td><p><span data-ttu-id="0955f-119">搜索正好在应出现匹配 <em>KeyValues</em> 的项的位置之后的键。</span><span class="sxs-lookup"><span data-stu-id="0955f-119">Seeks a key just after where a match with <em>KeyValues</em> would have occurred.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0955f-120">adSeekBeforeEQ</span><span class="sxs-lookup"><span data-stu-id="0955f-120">adSeekBeforeEQ</span></span></p></td>
<td><p><span data-ttu-id="0955f-121">16</span><span class="sxs-lookup"><span data-stu-id="0955f-121">16</span></span></p></td>
<td><p><span data-ttu-id="0955f-122">搜寻等于 <em>KeyValues</em> 的键或正好在应出现匹配项的位置之前的键。</span><span class="sxs-lookup"><span data-stu-id="0955f-122">Seeks either a key equal to <em>KeyValues</em> or just before where that match would have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0955f-123">adSeekBefore</span><span class="sxs-lookup"><span data-stu-id="0955f-123">adSeekBefore</span></span></p></td>
<td><p><span data-ttu-id="0955f-124">32</span><span class="sxs-lookup"><span data-stu-id="0955f-124">32</span></span></p></td>
<td><p><span data-ttu-id="0955f-125">搜寻正好在应出现匹配 <em>KeyValues</em> 的项的位置之前的键。</span><span class="sxs-lookup"><span data-stu-id="0955f-125">Seeks a key just before where a match with <em>KeyValues</em> would have occurred.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="0955f-126">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="0955f-126">ADO/WFC equivalent</span></span>

<span data-ttu-id="0955f-127">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="0955f-127">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0955f-128">常量</span><span class="sxs-lookup"><span data-stu-id="0955f-128">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0955f-129">AdoEnums.Seek.FIRSTEQ</span><span class="sxs-lookup"><span data-stu-id="0955f-129">AdoEnums.Seek.FIRSTEQ</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0955f-130">AdoEnums.Seek.LASTEQ</span><span class="sxs-lookup"><span data-stu-id="0955f-130">AdoEnums.Seek.LASTEQ</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0955f-131">AdoEnums.Seek.AFTEREQ</span><span class="sxs-lookup"><span data-stu-id="0955f-131">AdoEnums.Seek.AFTEREQ</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0955f-132">AdoEnums.Seek.AFTER</span><span class="sxs-lookup"><span data-stu-id="0955f-132">AdoEnums.Seek.AFTER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0955f-133">AdoEnums.Seek.BEFOREEQ</span><span class="sxs-lookup"><span data-stu-id="0955f-133">AdoEnums.Seek.BEFOREEQ</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0955f-134">AdoEnums.Seek.BEFORE</span><span class="sxs-lookup"><span data-stu-id="0955f-134">AdoEnums.Seek.BEFORE</span></span></p></td>
</tr>
</tbody>
</table>

