---
title: CompareEnum (Access desktop database reference)
TOCTitle: CompareEnum
ms:assetid: 7ac84af6-4f8b-4d1f-7eb3-a015b8b60bc6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249509(v=office.15)
ms:contentKeyID: 48545801
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cd120f726a51c884d063bb03f6d6864ea2d48344
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296064"
---
# <a name="compareenum"></a><span data-ttu-id="7b255-102">CompareEnum</span><span class="sxs-lookup"><span data-stu-id="7b255-102">CompareEnum</span></span>

<span data-ttu-id="7b255-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7b255-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7b255-104">指定通过记录书签表示的两个记录的相对位置。</span><span class="sxs-lookup"><span data-stu-id="7b255-104">Specifies the relative position of two records represented by their bookmarks.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7b255-105">常量</span><span class="sxs-lookup"><span data-stu-id="7b255-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="7b255-106">值</span><span class="sxs-lookup"><span data-stu-id="7b255-106">Value</span></span></p></th>
<th><p><span data-ttu-id="7b255-107">说明</span><span class="sxs-lookup"><span data-stu-id="7b255-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b255-108"><strong>adCompareEqual</strong></span><span class="sxs-lookup"><span data-stu-id="7b255-108"><strong>adCompareEqual</strong></span></span></p></td>
<td><p><span data-ttu-id="7b255-109">1</span><span class="sxs-lookup"><span data-stu-id="7b255-109">1</span></span></p></td>
<td><p><span data-ttu-id="7b255-110">指示书签相同。</span><span class="sxs-lookup"><span data-stu-id="7b255-110">Indicates that the bookmarks are equal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b255-111"><strong>adCompareGreaterThan</strong></span><span class="sxs-lookup"><span data-stu-id="7b255-111"><strong>adCompareGreaterThan</strong></span></span></p></td>
<td><p><span data-ttu-id="7b255-112">双面</span><span class="sxs-lookup"><span data-stu-id="7b255-112">2</span></span></p></td>
<td><p><span data-ttu-id="7b255-113">指示第一个书签在第二个书签之后。</span><span class="sxs-lookup"><span data-stu-id="7b255-113">Indicates that the first bookmark is after the second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b255-114"><strong>adCompareLessThan</strong></span><span class="sxs-lookup"><span data-stu-id="7b255-114"><strong>adCompareLessThan</strong></span></span></p></td>
<td><p><span data-ttu-id="7b255-115">0</span><span class="sxs-lookup"><span data-stu-id="7b255-115">0</span></span></p></td>
<td><p><span data-ttu-id="7b255-116">指示第一个书签在第二个书签之前。</span><span class="sxs-lookup"><span data-stu-id="7b255-116">Indicates that the first bookmark is before the second.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b255-117"><strong>adCompareNotComparable</strong></span><span class="sxs-lookup"><span data-stu-id="7b255-117"><strong>adCompareNotComparable</strong></span></span></p></td>
<td><p><span data-ttu-id="7b255-118">4</span><span class="sxs-lookup"><span data-stu-id="7b255-118">4</span></span></p></td>
<td><p><span data-ttu-id="7b255-119">指示无法比较书签。</span><span class="sxs-lookup"><span data-stu-id="7b255-119">Indicates that the bookmarks cannot be compared.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b255-120"><strong>adCompareNotEqual</strong></span><span class="sxs-lookup"><span data-stu-id="7b255-120"><strong>adCompareNotEqual</strong></span></span></p></td>
<td><p><span data-ttu-id="7b255-121">第三章</span><span class="sxs-lookup"><span data-stu-id="7b255-121">3</span></span></p></td>
<td><p><span data-ttu-id="7b255-122">指示书签不相同或者未排序。</span><span class="sxs-lookup"><span data-stu-id="7b255-122">Indicates that the bookmarks are not equal and not ordered.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="7b255-123">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="7b255-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="7b255-124">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="7b255-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7b255-125">常量</span><span class="sxs-lookup"><span data-stu-id="7b255-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b255-126">AdoEnums (比较) 相等</span><span class="sxs-lookup"><span data-stu-id="7b255-126">AdoEnums.Compare.EQUAL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b255-127">AdoEnums. GREATERTHAN</span><span class="sxs-lookup"><span data-stu-id="7b255-127">AdoEnums.Compare.GREATERTHAN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b255-128">AdoEnums. LESSTHAN</span><span class="sxs-lookup"><span data-stu-id="7b255-128">AdoEnums.Compare.LESSTHAN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b255-129">AdoEnums. NOTCOMPARABLE</span><span class="sxs-lookup"><span data-stu-id="7b255-129">AdoEnums.Compare.NOTCOMPARABLE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b255-130">AdoEnums. NOTEQUAL</span><span class="sxs-lookup"><span data-stu-id="7b255-130">AdoEnums.Compare.NOTEQUAL</span></span></p></td>
</tr>
</tbody>
</table>

