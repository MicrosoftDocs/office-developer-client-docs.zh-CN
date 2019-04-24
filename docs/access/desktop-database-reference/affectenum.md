---
title: AffectEnum (Access desktop database reference)
TOCTitle: AffectEnum
ms:assetid: 15393398-d7eb-a685-1bfa-d6712d8e5015
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248916(v=office.15)
ms:contentKeyID: 48543404
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0183cde0862e947f686bed9821e447abc117d205
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297198"
---
# <a name="affectenum"></a><span data-ttu-id="7e398-102">AffectEnum</span><span class="sxs-lookup"><span data-stu-id="7e398-102">AffectEnum</span></span>

<span data-ttu-id="7e398-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7e398-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7e398-104">指定操作会影响哪些记录。</span><span class="sxs-lookup"><span data-stu-id="7e398-104">Specifies which records are affected by an operation.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7e398-105">常量</span><span class="sxs-lookup"><span data-stu-id="7e398-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="7e398-106">值</span><span class="sxs-lookup"><span data-stu-id="7e398-106">Value</span></span></p></th>
<th><p><span data-ttu-id="7e398-107">说明</span><span class="sxs-lookup"><span data-stu-id="7e398-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e398-108"><strong>adAffectAll</strong></span><span class="sxs-lookup"><span data-stu-id="7e398-108"><strong>adAffectAll</strong></span></span></p></td>
<td><p><span data-ttu-id="7e398-109">第三章</span><span class="sxs-lookup"><span data-stu-id="7e398-109">3</span></span></p></td>
<td><p><span data-ttu-id="7e398-110">如果未对 <strong>Recordset</strong> 应用任何 <a href="filter-property-ado.md">Filter</a>，则所有记录都受影响。</span><span class="sxs-lookup"><span data-stu-id="7e398-110">If there is not a <a href="filter-property-ado.md">Filter</a> applied to the <strong>Recordset</strong>, affects all records.</span></span> <span data-ttu-id="7e398-111">如果<strong>Filter</strong>属性设置为字符串条件 (例如&quot;Author = ' Smith '&quot;), 则该操作将影响当前章节中的可见记录。</span><span class="sxs-lookup"><span data-stu-id="7e398-111">If the <strong>Filter</strong> property is set to a string criteria (such as &quot;Author='Smith'&quot;), the operation affects visible records in the current chapter.</span></span> <span data-ttu-id="7e398-112">如果<strong>Filter</strong>属性设置为<a href="filtergroupenum.md">FilterGroupEnum</a>或书签数组的成员, 则该操作将影响<strong>Recordset</strong>的所有行。</span><span class="sxs-lookup"><span data-stu-id="7e398-112">If the <strong>Filter</strong> property is set to a member of the <a href="filtergroupenum.md">FilterGroupEnum</a> or an array of Bookmarks, the operation will affect all rows of the <strong>Recordset</strong>.</span></span></p><p><span data-ttu-id="7e398-113"><strong>注意</strong>: adAffectAll 在 Visual Basic 对象浏览器中处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="7e398-113"><strong>NOTE</strong>: adAffectAll is hidden in the Visual Basic Object Browser.</span></span></p>
</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e398-114"><strong>adAffectAllChapters</strong></span><span class="sxs-lookup"><span data-stu-id="7e398-114"><strong>adAffectAllChapters</strong></span></span></p></td>
<td><p><span data-ttu-id="7e398-115">4</span><span class="sxs-lookup"><span data-stu-id="7e398-115">4</span></span></p></td>
<td><p><span data-ttu-id="7e398-116">影响 <strong>Recordset</strong> 的所有同级章节中的全部记录，包括通过当前所应用的任何 <strong>Filter</strong> 都看不到的记录。</span><span class="sxs-lookup"><span data-stu-id="7e398-116">Affects all records in all sibling chapters of the <strong>Recordset</strong>, including those not visible via any <strong>Filter</strong> that is currently applied.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e398-117"><strong>adAffectCurrent</strong></span><span class="sxs-lookup"><span data-stu-id="7e398-117"><strong>adAffectCurrent</strong></span></span></p></td>
<td><p><span data-ttu-id="7e398-118">1</span><span class="sxs-lookup"><span data-stu-id="7e398-118">1</span></span></p></td>
<td><p><span data-ttu-id="7e398-119">只影响当前的记录。</span><span class="sxs-lookup"><span data-stu-id="7e398-119">Affects only the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e398-120"><strong>adAffectGroup</strong></span><span class="sxs-lookup"><span data-stu-id="7e398-120"><strong>adAffectGroup</strong></span></span></p></td>
<td><p><span data-ttu-id="7e398-121">双面</span><span class="sxs-lookup"><span data-stu-id="7e398-121">2</span></span></p></td>
<td><p><span data-ttu-id="7e398-p102">只影响满足当前 <a href="filter-property-ado.md">Filter</a> 属性设置的记录。必须将 <strong>Filter</strong> 属性设置为 <strong>FilterGroupEnum</strong> 值或 <strong>Bookmarks</strong> 数组，才能使用此选项。</span><span class="sxs-lookup"><span data-stu-id="7e398-p102">Affects only records that satisfy the current <a href="filter-property-ado.md">Filter</a> property setting. You must set the <strong>Filter</strong> property to a <strong>FilterGroupEnum</strong> value or an array of <strong>Bookmarks</strong> to use this option.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="7e398-124">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="7e398-124">ADO/WFC equivalent</span></span>

<span data-ttu-id="7e398-125">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="7e398-125">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7e398-126">常量</span><span class="sxs-lookup"><span data-stu-id="7e398-126">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e398-127">AdoEnums 影响。所有</span><span class="sxs-lookup"><span data-stu-id="7e398-127">AdoEnums.Affect.ALL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e398-128">AdoEnums 影响 ALLCHAPTERS</span><span class="sxs-lookup"><span data-stu-id="7e398-128">AdoEnums.Affect.ALLCHAPTERS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e398-129">AdoEnums 影响。当前</span><span class="sxs-lookup"><span data-stu-id="7e398-129">AdoEnums.Affect.CURRENT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e398-130">AdoEnums 影响。组</span><span class="sxs-lookup"><span data-stu-id="7e398-130">AdoEnums.Affect.GROUP</span></span></p></td>
</tr>
</tbody>
</table>

