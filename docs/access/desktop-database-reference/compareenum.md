---
title: CompareEnum （访问桌面数据库参考 （英文）
TOCTitle: CompareEnum
ms:assetid: 7ac84af6-4f8b-4d1f-7eb3-a015b8b60bc6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249509(v=office.15)
ms:contentKeyID: 48545801
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9cef64707cb2797c6ad4f1090749779f147c87f3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466795"
---
# <a name="compareenum"></a><span data-ttu-id="2b6d3-102">CompareEnum</span><span class="sxs-lookup"><span data-stu-id="2b6d3-102">CompareEnum</span></span>


<span data-ttu-id="2b6d3-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2b6d3-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2b6d3-104">指定通过记录书签表示的两个记录的相对位置。</span><span class="sxs-lookup"><span data-stu-id="2b6d3-104">Specifies the relative position of two records represented by their bookmarks.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2b6d3-105">常量</span><span class="sxs-lookup"><span data-stu-id="2b6d3-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="2b6d3-106">值</span><span class="sxs-lookup"><span data-stu-id="2b6d3-106">Value</span></span></p></th>
<th><p><span data-ttu-id="2b6d3-107">说明</span><span class="sxs-lookup"><span data-stu-id="2b6d3-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b6d3-108"><strong>adCompareEqual</strong></span><span class="sxs-lookup"><span data-stu-id="2b6d3-108"><strong>adCompareEqual</strong></span></span></p></td>
<td><p><span data-ttu-id="2b6d3-109">1</span><span class="sxs-lookup"><span data-stu-id="2b6d3-109">1</span></span></p></td>
<td><p><span data-ttu-id="2b6d3-110">指示书签相同。</span><span class="sxs-lookup"><span data-stu-id="2b6d3-110">Indicates that the bookmarks are equal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b6d3-111"><strong>adCompareGreaterThan</strong></span><span class="sxs-lookup"><span data-stu-id="2b6d3-111"><strong>adCompareGreaterThan</strong></span></span></p></td>
<td><p><span data-ttu-id="2b6d3-112">2</span><span class="sxs-lookup"><span data-stu-id="2b6d3-112">2</span></span></p></td>
<td><p><span data-ttu-id="2b6d3-113">指示第一个书签在第二个书签之后。</span><span class="sxs-lookup"><span data-stu-id="2b6d3-113">Indicates that the first bookmark is after the second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b6d3-114"><strong>adCompareLessThan</strong></span><span class="sxs-lookup"><span data-stu-id="2b6d3-114"><strong>adCompareLessThan</strong></span></span></p></td>
<td><p><span data-ttu-id="2b6d3-115">0</span><span class="sxs-lookup"><span data-stu-id="2b6d3-115">0</span></span></p></td>
<td><p><span data-ttu-id="2b6d3-116">指示第一个书签在第二个书签之前。</span><span class="sxs-lookup"><span data-stu-id="2b6d3-116">Indicates that the first bookmark is before the second.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b6d3-117"><strong>adCompareNotComparable</strong></span><span class="sxs-lookup"><span data-stu-id="2b6d3-117"><strong>adCompareNotComparable</strong></span></span></p></td>
<td><p><span data-ttu-id="2b6d3-118">4</span><span class="sxs-lookup"><span data-stu-id="2b6d3-118">4</span></span></p></td>
<td><p><span data-ttu-id="2b6d3-119">指示无法比较书签。</span><span class="sxs-lookup"><span data-stu-id="2b6d3-119">Indicates that the bookmarks cannot be compared.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b6d3-120"><strong>adCompareNotEqual</strong></span><span class="sxs-lookup"><span data-stu-id="2b6d3-120"><strong>adCompareNotEqual</strong></span></span></p></td>
<td><p><span data-ttu-id="2b6d3-121">3</span><span class="sxs-lookup"><span data-stu-id="2b6d3-121">3</span></span></p></td>
<td><p><span data-ttu-id="2b6d3-122">指示书签不相同或者未排序。</span><span class="sxs-lookup"><span data-stu-id="2b6d3-122">Indicates that the bookmarks are not equal and not ordered.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2b6d3-123">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="2b6d3-123">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="2b6d3-124">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="2b6d3-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2b6d3-125">常量</span><span class="sxs-lookup"><span data-stu-id="2b6d3-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b6d3-126">AdoEnums.Compare.EQUAL</span><span class="sxs-lookup"><span data-stu-id="2b6d3-126">AdoEnums.Compare.EQUAL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b6d3-127">AdoEnums.Compare.GREATERTHAN</span><span class="sxs-lookup"><span data-stu-id="2b6d3-127">AdoEnums.Compare.GREATERTHAN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b6d3-128">AdoEnums.Compare.LESSTHAN</span><span class="sxs-lookup"><span data-stu-id="2b6d3-128">AdoEnums.Compare.LESSTHAN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b6d3-129">AdoEnums.Compare.NOTCOMPARABLE</span><span class="sxs-lookup"><span data-stu-id="2b6d3-129">AdoEnums.Compare.NOTCOMPARABLE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b6d3-130">AdoEnums.Compare.NOTEQUAL</span><span class="sxs-lookup"><span data-stu-id="2b6d3-130">AdoEnums.Compare.NOTEQUAL</span></span></p></td>
</tr>
</tbody>
</table>
