---
title: CollatingOrder 属性 (DAO)
TOCTitle: CollatingOrder Property
ms:assetid: a2607ace-a660-899b-eae8-4612ce2f87f8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff820980(v=office.15)
ms:contentKeyID: 48546758
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052897
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 3d016d779472ec9809d3ac5c77158c2c1d994f3c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293124"
---
# <a name="fieldcollatingorder-property-dao"></a><span data-ttu-id="6c539-102">CollatingOrder 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="6c539-102">Field.CollatingOrder property (DAO)</span></span>


<span data-ttu-id="6c539-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6c539-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6c539-p101">返回一个值，该值指定用于字符串比较或排序的文本中排序次序的序列（仅适用于 Microsoft Access 工作区）。只读 **Long**。</span><span class="sxs-lookup"><span data-stu-id="6c539-p101">Returns a value that specifies the sequence of the sort order in text for string comparison or sorting (Microsoft Access workspaces only). Read-only **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c539-106">语法</span><span class="sxs-lookup"><span data-stu-id="6c539-106">Syntax</span></span>

<span data-ttu-id="6c539-107">*表达式*。CollatingOrder</span><span class="sxs-lookup"><span data-stu-id="6c539-107">*expression* .CollatingOrder</span></span>

<span data-ttu-id="6c539-108">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6c539-108">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c539-109">注解</span><span class="sxs-lookup"><span data-stu-id="6c539-109">Remarks</span></span>

<span data-ttu-id="6c539-110">返回值为 **Long** 类型值，或者为下列值之一的常量。</span><span class="sxs-lookup"><span data-stu-id="6c539-110">The return value is a **Long** value or constant that can be one of the following values.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6c539-111">常量</span><span class="sxs-lookup"><span data-stu-id="6c539-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="6c539-112">排序次序</span><span class="sxs-lookup"><span data-stu-id="6c539-112">Sort order</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c539-113"><strong>dbSortGeneral</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-113"><strong>dbSortGeneral</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-114">常规（英语、法语、德语、葡萄牙语、意大利语和现代西班牙语）</span><span class="sxs-lookup"><span data-stu-id="6c539-114">General (English, French, German, Portuguese, Italian, and Modern Spanish)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-115"><strong>dbSortArabic</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-115"><strong>dbSortArabic</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-116">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="6c539-116">Arabic</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-117"><strong>dbSortChineseSimplified</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-117"><strong>dbSortChineseSimplified</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-118">简体中文</span><span class="sxs-lookup"><span data-stu-id="6c539-118">Simplified Chinese</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-119"><strong>dbSortChineseTraditional</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-119"><strong>dbSortChineseTraditional</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-120">繁体中文</span><span class="sxs-lookup"><span data-stu-id="6c539-120">Traditional Chinese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-121"><strong>dbSortCyrillic</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-121"><strong>dbSortCyrillic</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-122">俄语</span><span class="sxs-lookup"><span data-stu-id="6c539-122">Russian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-123"><strong>dbSortCzech</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-123"><strong>dbSortCzech</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-124">捷克语</span><span class="sxs-lookup"><span data-stu-id="6c539-124">Czech</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-125"><strong>dbSortDutch</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-125"><strong>dbSortDutch</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-126">荷兰语</span><span class="sxs-lookup"><span data-stu-id="6c539-126">Dutch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-127"><strong>dbSortGreek</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-127"><strong>dbSortGreek</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-128">希腊语</span><span class="sxs-lookup"><span data-stu-id="6c539-128">Greek</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-129"><strong>dbSortHebrew</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-129"><strong>dbSortHebrew</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-130">希伯来语</span><span class="sxs-lookup"><span data-stu-id="6c539-130">Hebrew</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-131"><strong>dbSortHungarian</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-131"><strong>dbSortHungarian</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-132">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="6c539-132">Hungarian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-133"><strong>dbSortIcelandic</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-133"><strong>dbSortIcelandic</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-134">冰岛语</span><span class="sxs-lookup"><span data-stu-id="6c539-134">Icelandic</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-135"><strong>dbSortJapanese</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-135"><strong>dbSortJapanese</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-136">日语</span><span class="sxs-lookup"><span data-stu-id="6c539-136">Japanese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-137"><strong>dbSortKorean</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-137"><strong>dbSortKorean</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-138">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="6c539-138">Korean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-139"><strong>dbSortNeutral</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-139"><strong>dbSortNeutral</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-140">适中</span><span class="sxs-lookup"><span data-stu-id="6c539-140">Neutral</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-141"><strong>dbSortNorwDan</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-141"><strong>dbSortNorwDan</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-142">挪威语或丹麦语</span><span class="sxs-lookup"><span data-stu-id="6c539-142">Norwegian or Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-143"><strong>dbSortPDXIntl</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-143"><strong>dbSortPDXIntl</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-144">Paradox 国际型</span><span class="sxs-lookup"><span data-stu-id="6c539-144">Paradox International</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-145"><strong>dbSortPDXNor</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-145"><strong>dbSortPDXNor</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-146">Paradox 挪威语或丹麦语</span><span class="sxs-lookup"><span data-stu-id="6c539-146">Paradox Norwegian or Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-147"><strong>dbSortPDXSwe</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-147"><strong>dbSortPDXSwe</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-148">Paradox 瑞典语或芬兰语</span><span class="sxs-lookup"><span data-stu-id="6c539-148">Paradox Swedish or Finnish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-149"><strong>dbSortPolish</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-149"><strong>dbSortPolish</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-150">波兰语</span><span class="sxs-lookup"><span data-stu-id="6c539-150">Polish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-151"><strong>dbSortSlovenian</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-151"><strong>dbSortSlovenian</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-152">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="6c539-152">Slovenian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-153"><strong>dbSortSpanish</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-153"><strong>dbSortSpanish</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-154">西班牙语</span><span class="sxs-lookup"><span data-stu-id="6c539-154">Spanish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-155"><strong>dbSortSwedFin</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-155"><strong>dbSortSwedFin</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-156">瑞典语或芬兰语</span><span class="sxs-lookup"><span data-stu-id="6c539-156">Swedish or Finnish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-157"><strong>dbSortThai</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-157"><strong>dbSortThai</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-158">泰语</span><span class="sxs-lookup"><span data-stu-id="6c539-158">Thai</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-159"><strong>dbSortTurkish</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-159"><strong>dbSortTurkish</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-160">土耳其语</span><span class="sxs-lookup"><span data-stu-id="6c539-160">Turkish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-161"><strong>dbSortUndefined</strong></span><span class="sxs-lookup"><span data-stu-id="6c539-161"><strong>dbSortUndefined</strong></span></span></p></td>
<td><p><span data-ttu-id="6c539-162">不确定或未知</span><span class="sxs-lookup"><span data-stu-id="6c539-162">Undefined or unknown</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c539-163">**CollatingOrder** 属性的可用性取决于包含 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="6c539-163">The availability of the **CollatingOrder** property depends on the object that contains the **Fields** collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6c539-164">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="6c539-164">If the Fields collection belongs to an</span></span></p></th>
<th><p><span data-ttu-id="6c539-165">则 CollatingOrder</span><span class="sxs-lookup"><span data-stu-id="6c539-165">Then CollatingOrder is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c539-166"><strong>Index</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="6c539-166"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="6c539-167">不支持</span><span class="sxs-lookup"><span data-stu-id="6c539-167">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-168"><strong>QueryDef</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="6c539-168"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="6c539-169">只读</span><span class="sxs-lookup"><span data-stu-id="6c539-169">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-170"><strong>Recordset</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="6c539-170"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="6c539-171">只读</span><span class="sxs-lookup"><span data-stu-id="6c539-171">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c539-172"><strong>Relation</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="6c539-172"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="6c539-173">不受支持</span><span class="sxs-lookup"><span data-stu-id="6c539-173">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c539-174"><strong>TableDef</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="6c539-174"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="6c539-175">只读</span><span class="sxs-lookup"><span data-stu-id="6c539-175">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c539-176">创建数据库时, **CollatingOrder**属性设置对应于**CreateDatabase**方法的 locale 参数, 或者数据库最近压缩时的**CompactDatabase**方法。</span><span class="sxs-lookup"><span data-stu-id="6c539-176">The **CollatingOrder** property setting corresponds to the locale argument of the **CreateDatabase** method when the database was created or the **CompactDatabase** method when the database was most recently compacted.</span></span>

<span data-ttu-id="6c539-p102">**Index** 对象的 **Field** 集合中的 **Fields** 对象的 **CollatingOrder** 和 **Attributes** 属性设置共同确定索引中排序次序的序列和方向。但是，不能设置单个索引的整理顺序 - 只能设置整个表的整理顺序。</span><span class="sxs-lookup"><span data-stu-id="6c539-p102">The **CollatingOrder** and **Attributes** property settings of a **Field** object in a **Fields** collection of an **Index** object together determine the sequence and direction of the sort order in an index. However, you can't set a collating order for an individual index— you can only set it for an entire table.</span></span>

