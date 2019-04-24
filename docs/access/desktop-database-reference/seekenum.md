---
title: SeekEnum (Access desktop database reference)
TOCTitle: SeekEnum
ms:assetid: a0574809-db2d-8759-18cc-fb1cf776e8fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249737(v=office.15)
ms:contentKeyID: 48546706
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2f8334cbfc8e0f6a362a36e03984739d1d52b6f6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314656"
---
# <a name="seekenum"></a><span data-ttu-id="38956-102">SeekEnum</span><span class="sxs-lookup"><span data-stu-id="38956-102">SeekEnum</span></span>

<span data-ttu-id="38956-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="38956-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="38956-104">用于指定要执行的 [Seek 方法 (ADO)](seek-method-ado.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="38956-104">Specifies the type of [Seek](seek-method-ado.md) to execute.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="38956-105">常量</span><span class="sxs-lookup"><span data-stu-id="38956-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="38956-106">值</span><span class="sxs-lookup"><span data-stu-id="38956-106">Value</span></span></p></th>
<th><p><span data-ttu-id="38956-107">说明</span><span class="sxs-lookup"><span data-stu-id="38956-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38956-108">adSeekFirstEQ</span><span class="sxs-lookup"><span data-stu-id="38956-108">adSeekFirstEQ</span></span></p></td>
<td><p><span data-ttu-id="38956-109">1</span><span class="sxs-lookup"><span data-stu-id="38956-109">1</span></span></p></td>
<td><p><span data-ttu-id="38956-110">搜寻第一个等于 <em>KeyValues</em> 的键。</span><span class="sxs-lookup"><span data-stu-id="38956-110">Seeks the first key equal to <em>KeyValues</em>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38956-111">adSeekLastEQ</span><span class="sxs-lookup"><span data-stu-id="38956-111">adSeekLastEQ</span></span></p></td>
<td><p><span data-ttu-id="38956-112">双面</span><span class="sxs-lookup"><span data-stu-id="38956-112">2</span></span></p></td>
<td><p><span data-ttu-id="38956-113">搜寻最后一个等于 <em>KeyValues</em> 的键。</span><span class="sxs-lookup"><span data-stu-id="38956-113">Seeks the last key equal to <em>KeyValues</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38956-114">adSeekAfterEQ</span><span class="sxs-lookup"><span data-stu-id="38956-114">adSeekAfterEQ</span></span></p></td>
<td><p><span data-ttu-id="38956-115">4</span><span class="sxs-lookup"><span data-stu-id="38956-115">4</span></span></p></td>
<td><p><span data-ttu-id="38956-116">搜寻等于 <em>KeyValues</em> 的键或正好在应出现匹配项的位置之后的键。</span><span class="sxs-lookup"><span data-stu-id="38956-116">Seeks either a key equal to <em>KeyValues</em> or just after where that match would have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38956-117">adSeekAfter</span><span class="sxs-lookup"><span data-stu-id="38956-117">adSeekAfter</span></span></p></td>
<td><p><span data-ttu-id="38956-118">utf-8</span><span class="sxs-lookup"><span data-stu-id="38956-118">8</span></span></p></td>
<td><p><span data-ttu-id="38956-119">搜索正好在应出现匹配 <em>KeyValues</em> 的项的位置之后的键。</span><span class="sxs-lookup"><span data-stu-id="38956-119">Seeks a key just after where a match with <em>KeyValues</em> would have occurred.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38956-120">adSeekBeforeEQ</span><span class="sxs-lookup"><span data-stu-id="38956-120">adSeekBeforeEQ</span></span></p></td>
<td><p><span data-ttu-id="38956-121">位</span><span class="sxs-lookup"><span data-stu-id="38956-121">16</span></span></p></td>
<td><p><span data-ttu-id="38956-122">搜寻等于 <em>KeyValues</em> 的键或正好在应出现匹配项的位置之前的键。</span><span class="sxs-lookup"><span data-stu-id="38956-122">Seeks either a key equal to <em>KeyValues</em> or just before where that match would have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38956-123">adSeekBefore</span><span class="sxs-lookup"><span data-stu-id="38956-123">adSeekBefore</span></span></p></td>
<td><p><span data-ttu-id="38956-124">32</span><span class="sxs-lookup"><span data-stu-id="38956-124">32</span></span></p></td>
<td><p><span data-ttu-id="38956-125">搜寻正好在应出现匹配 <em>KeyValues</em> 的项的位置之前的键。</span><span class="sxs-lookup"><span data-stu-id="38956-125">Seeks a key just before where a match with <em>KeyValues</em> would have occurred.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="38956-126">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="38956-126">ADO/WFC equivalent</span></span>

<span data-ttu-id="38956-127">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="38956-127">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="38956-128">常量</span><span class="sxs-lookup"><span data-stu-id="38956-128">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38956-129">AdoEnums。 FIRSTEQ</span><span class="sxs-lookup"><span data-stu-id="38956-129">AdoEnums.Seek.FIRSTEQ</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38956-130">AdoEnums。 LASTEQ</span><span class="sxs-lookup"><span data-stu-id="38956-130">AdoEnums.Seek.LASTEQ</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38956-131">AdoEnums。 AFTEREQ</span><span class="sxs-lookup"><span data-stu-id="38956-131">AdoEnums.Seek.AFTEREQ</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38956-132">AdoEnums。</span><span class="sxs-lookup"><span data-stu-id="38956-132">AdoEnums.Seek.AFTER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38956-133">AdoEnums。 BEFOREEQ</span><span class="sxs-lookup"><span data-stu-id="38956-133">AdoEnums.Seek.BEFOREEQ</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38956-134">AdoEnums。</span><span class="sxs-lookup"><span data-stu-id="38956-134">AdoEnums.Seek.BEFORE</span></span></p></td>
</tr>
</tbody>
</table>

