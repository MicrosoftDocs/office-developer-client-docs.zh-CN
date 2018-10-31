---
title: AffectEnum （访问桌面数据库参考 （英文）
TOCTitle: AffectEnum
ms:assetid: 15393398-d7eb-a685-1bfa-d6712d8e5015
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248916(v=office.15)
ms:contentKeyID: 48543404
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 9e1bd4d86e6e269c9363daca0ffa7b8df6303326
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25863666"
---
# <a name="affectenum"></a><span data-ttu-id="9967a-102">AffectEnum</span><span class="sxs-lookup"><span data-stu-id="9967a-102">AffectEnum</span></span>

<span data-ttu-id="9967a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9967a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9967a-104">指定操作会影响哪些记录。</span><span class="sxs-lookup"><span data-stu-id="9967a-104">Specifies which records are affected by an operation.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9967a-105">常量</span><span class="sxs-lookup"><span data-stu-id="9967a-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="9967a-106">值</span><span class="sxs-lookup"><span data-stu-id="9967a-106">Value</span></span></p></th>
<th><p><span data-ttu-id="9967a-107">说明</span><span class="sxs-lookup"><span data-stu-id="9967a-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9967a-108"><strong>adAffectAll</strong></span><span class="sxs-lookup"><span data-stu-id="9967a-108"><strong>adAffectAll</strong></span></span></p></td>
<td><p><span data-ttu-id="9967a-109">3</span><span class="sxs-lookup"><span data-stu-id="9967a-109">3</span></span></p></td>
<td><p><span data-ttu-id="9967a-110">如果未对 <strong>Recordset</strong> 应用任何 <a href="filter-property-ado.md">Filter</a>，则所有记录都受影响。
</span><span class="sxs-lookup"><span data-stu-id="9967a-110">If there is not a <a href="filter-property-ado.md">Filter</a> applied to the <strong>Recordset</strong>, affects all records.</span></span> <span data-ttu-id="9967a-111">如果将<strong>Filter</strong>属性设置为字符串条件 (如&quot;作者 = 'Smith'&quot;)，该操作将影响当前章节中的可见记录。</span><span class="sxs-lookup"><span data-stu-id="9967a-111">If the <strong>Filter</strong> property is set to a string criteria (such as &quot;Author='Smith'&quot;), the operation affects visible records in the current chapter.</span></span> <span data-ttu-id="9967a-112">如果将<strong>Filter</strong>属性设置为<a href="filtergroupenum.md">FilterGroupEnum</a>的成员或书签数组，该操作将影响<strong>Recordset</strong>的所有行。</span><span class="sxs-lookup"><span data-stu-id="9967a-112">If the <strong>Filter</strong> property is set to a member of the <a href="filtergroupenum.md">FilterGroupEnum</a> or an array of Bookmarks, the operation will affect all rows of the <strong>Recordset</strong>.</span></span></p>
<p><span data-ttu-id="9967a-113"><strong>注意</strong>： adAffectAll 在 Visual Basic 对象浏览器中处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="9967a-113"><strong>NOTE</strong>: adAffectAll is hidden in the Visual Basic Object Browser.</span></span></p>
</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9967a-114"><strong>adAffectAllChapters</strong></span><span class="sxs-lookup"><span data-stu-id="9967a-114"><strong>adAffectAllChapters</strong></span></span></p></td>
<td><p><span data-ttu-id="9967a-115">4</span><span class="sxs-lookup"><span data-stu-id="9967a-115">4</span></span></p></td>
<td><p><span data-ttu-id="9967a-116">影响 <strong>Recordset</strong> 的所有同级章节中的全部记录，包括通过当前所应用的任何 <strong>Filter</strong> 都看不到的记录。</span><span class="sxs-lookup"><span data-stu-id="9967a-116">Affects all records in all sibling chapters of the <strong>Recordset</strong>, including those not visible via any <strong>Filter</strong> that is currently applied.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9967a-117"><strong>adaffectcurrent:</strong></span><span class="sxs-lookup"><span data-stu-id="9967a-117"><strong>adAffectCurrent</strong></span></span></p></td>
<td><p><span data-ttu-id="9967a-118">1</span><span class="sxs-lookup"><span data-stu-id="9967a-118">1</span></span></p></td>
<td><p><span data-ttu-id="9967a-119">只影响当前的记录。</span><span class="sxs-lookup"><span data-stu-id="9967a-119">Affects only the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9967a-120"><strong>adAffectGroup</strong></span><span class="sxs-lookup"><span data-stu-id="9967a-120"><strong>adAffectGroup</strong></span></span></p></td>
<td><p><span data-ttu-id="9967a-121">2</span><span class="sxs-lookup"><span data-stu-id="9967a-121">2</span></span></p></td>
<td><p><span data-ttu-id="9967a-p102">只影响满足当前 <a href="filter-property-ado.md">Filter</a> 属性设置的记录。必须将 <strong>Filter</strong> 属性设置为 <strong>FilterGroupEnum</strong> 值或 <strong>Bookmarks</strong> 数组，才能使用此选项。</span><span class="sxs-lookup"><span data-stu-id="9967a-p102">Affects only records that satisfy the current <a href="filter-property-ado.md">Filter</a> property setting. You must set the <strong>Filter</strong> property to a <strong>FilterGroupEnum</strong> value or an array of <strong>Bookmarks</strong> to use this option.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="9967a-124">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="9967a-124">ADO/WFC equivalent</span></span>

<span data-ttu-id="9967a-125">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="9967a-125">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9967a-126">常量</span><span class="sxs-lookup"><span data-stu-id="9967a-126">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9967a-127">AdoEnums.Affect.ALL</span><span class="sxs-lookup"><span data-stu-id="9967a-127">AdoEnums.Affect.ALL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9967a-128">AdoEnums.Affect.ALLCHAPTERS</span><span class="sxs-lookup"><span data-stu-id="9967a-128">AdoEnums.Affect.ALLCHAPTERS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9967a-129">AdoEnums.Affect.CURRENT</span><span class="sxs-lookup"><span data-stu-id="9967a-129">AdoEnums.Affect.CURRENT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9967a-130">AdoEnums.Affect.GROUP</span><span class="sxs-lookup"><span data-stu-id="9967a-130">AdoEnums.Affect.GROUP</span></span></p></td>
</tr>
</tbody>
</table>

