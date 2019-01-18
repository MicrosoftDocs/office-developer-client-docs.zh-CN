---
title: Field2.CollatingOrder 属性 (DAO)
TOCTitle: CollatingOrder Property
ms:assetid: cb1d6fc9-a2a6-54c2-abf5-48b609e38738
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834380(v=office.15)
ms:contentKeyID: 48547709
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 02711fbbf39b058bb88e9568716169825ae4a923
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700729"
---
# <a name="field2collatingorder-property-dao"></a><span data-ttu-id="8e4c9-102">Field2.CollatingOrder 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="8e4c9-102">Field2.CollatingOrder property (DAO)</span></span>


<span data-ttu-id="8e4c9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8e4c9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8e4c9-p101">返回一个值，该值指定用于字符串比较或排序的文本中排序次序的序列（仅适用于 Microsoft Access 工作区）。只读 **Long**。</span><span class="sxs-lookup"><span data-stu-id="8e4c9-p101">Returns a value that specifies the sequence of the sort order in text for string comparison or sorting (Microsoft Access workspaces only). Read-only **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e4c9-106">语法</span><span class="sxs-lookup"><span data-stu-id="8e4c9-106">Syntax</span></span>

<span data-ttu-id="8e4c9-107">*表达式*。CollatingOrder</span><span class="sxs-lookup"><span data-stu-id="8e4c9-107">*expression* .CollatingOrder</span></span>

<span data-ttu-id="8e4c9-108">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="8e4c9-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e4c9-109">注解</span><span class="sxs-lookup"><span data-stu-id="8e4c9-109">Remarks</span></span>

<span data-ttu-id="8e4c9-110">返回值为 **Long** 类型值，或者为下列值之一的常量。</span><span class="sxs-lookup"><span data-stu-id="8e4c9-110">The return value is a **Long** value or constant that can be one of the following values.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8e4c9-111">常量</span><span class="sxs-lookup"><span data-stu-id="8e4c9-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="8e4c9-112">排序次序</span><span class="sxs-lookup"><span data-stu-id="8e4c9-112">Sort order</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-113"><strong>dbSortGeneral</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-113"><strong>dbSortGeneral</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-114">常规（英语、法语、德语、葡萄牙语、意大利语和现代西班牙语）</span><span class="sxs-lookup"><span data-stu-id="8e4c9-114">General (English, French, German, Portuguese, Italian, and Modern Spanish)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-115"><strong>dbSortArabic</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-115"><strong>dbSortArabic</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-116">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-116">Arabic</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-117"><strong>dbSortChineseSimplified</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-117"><strong>dbSortChineseSimplified</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-118">简体中文</span><span class="sxs-lookup"><span data-stu-id="8e4c9-118">Simplified Chinese</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-119"><strong>dbSortChineseTraditional</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-119"><strong>dbSortChineseTraditional</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-120">繁体中文</span><span class="sxs-lookup"><span data-stu-id="8e4c9-120">Traditional Chinese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-121"><strong>dbSortCyrillic</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-121"><strong>dbSortCyrillic</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-122">俄语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-122">Russian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-123"><strong>dbSortCzech</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-123"><strong>dbSortCzech</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-124">捷克语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-124">Czech</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-125"><strong>dbSortDutch</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-125"><strong>dbSortDutch</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-126">荷兰语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-126">Dutch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-127"><strong>dbSortGreek</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-127"><strong>dbSortGreek</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-128">希腊语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-128">Greek</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-129"><strong>dbSortHebrew</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-129"><strong>dbSortHebrew</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-130">希伯来语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-130">Hebrew</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-131"><strong>dbSortHungarian</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-131"><strong>dbSortHungarian</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-132">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-132">Hungarian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-133"><strong>dbSortIcelandic</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-133"><strong>dbSortIcelandic</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-134">冰岛语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-134">Icelandic</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-135"><strong>dbSortJapanese</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-135"><strong>dbSortJapanese</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-136">日语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-136">Japanese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-137"><strong>dbSortKorean</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-137"><strong>dbSortKorean</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-138">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-138">Korean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-139"><strong>dbSortNeutral</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-139"><strong>dbSortNeutral</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-140">适中</span><span class="sxs-lookup"><span data-stu-id="8e4c9-140">Neutral</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-141"><strong>dbSortNorwDan</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-141"><strong>dbSortNorwDan</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-142">挪威语或丹麦语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-142">Norwegian or Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-143"><strong>dbSortPDXIntl</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-143"><strong>dbSortPDXIntl</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-144">Paradox 国际型</span><span class="sxs-lookup"><span data-stu-id="8e4c9-144">Paradox International</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-145"><strong>dbSortPDXNor</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-145"><strong>dbSortPDXNor</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-146">Paradox 挪威语或丹麦语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-146">Paradox Norwegian or Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-147"><strong>dbSortPDXSwe</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-147"><strong>dbSortPDXSwe</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-148">Paradox 瑞典语或芬兰语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-148">Paradox Swedish or Finnish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-149"><strong>dbSortPolish</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-149"><strong>dbSortPolish</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-150">波兰语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-150">Polish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-151"><strong>dbSortSlovenian</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-151"><strong>dbSortSlovenian</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-152">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-152">Slovenian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-153"><strong>dbSortSpanish</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-153"><strong>dbSortSpanish</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-154">西班牙语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-154">Spanish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-155"><strong>dbSortSwedFin</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-155"><strong>dbSortSwedFin</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-156">瑞典语或芬兰语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-156">Swedish or Finnish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-157"><strong>dbSortThai</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-157"><strong>dbSortThai</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-158">泰语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-158">Thai</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-159"><strong>dbSortTurkish</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-159"><strong>dbSortTurkish</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-160">土耳其语</span><span class="sxs-lookup"><span data-stu-id="8e4c9-160">Turkish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-161"><strong>dbSortUndefined</strong></span><span class="sxs-lookup"><span data-stu-id="8e4c9-161"><strong>dbSortUndefined</strong></span></span></p></td>
<td><p><span data-ttu-id="8e4c9-162">不确定或未知</span><span class="sxs-lookup"><span data-stu-id="8e4c9-162">Undefined or unknown</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8e4c9-163">**CollatingOrder** 属性的可用性取决于包含 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="8e4c9-163">The availability of the **CollatingOrder** property depends on the object that contains the **Fields** collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8e4c9-164">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="8e4c9-164">If the Fields collection belongs to an</span></span></p></th>
<th><p><span data-ttu-id="8e4c9-165">则 CollatingOrder</span><span class="sxs-lookup"><span data-stu-id="8e4c9-165">Then CollatingOrder is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-166"><strong>Index</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="8e4c9-166"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="8e4c9-167">不支持</span><span class="sxs-lookup"><span data-stu-id="8e4c9-167">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-168"><strong>QueryDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="8e4c9-168"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="8e4c9-169">只读</span><span class="sxs-lookup"><span data-stu-id="8e4c9-169">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-170"><strong>Recordset</strong>对象</span><span class="sxs-lookup"><span data-stu-id="8e4c9-170"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="8e4c9-171">只读</span><span class="sxs-lookup"><span data-stu-id="8e4c9-171">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4c9-172"><strong>Relation</strong>对象</span><span class="sxs-lookup"><span data-stu-id="8e4c9-172"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="8e4c9-173">不支持</span><span class="sxs-lookup"><span data-stu-id="8e4c9-173">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4c9-174"><strong>TableDef</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="8e4c9-174"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="8e4c9-175">只读</span><span class="sxs-lookup"><span data-stu-id="8e4c9-175">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8e4c9-176">最近压缩数据库时， **CollatingOrder**属性设置对应于**CreateDatabase**方法创建数据库时或**CompactDatabase**方法的 locale 参数。</span><span class="sxs-lookup"><span data-stu-id="8e4c9-176">The **CollatingOrder** property setting corresponds to the locale argument of the **CreateDatabase** method when the database was created or the **CompactDatabase** method when the database was most recently compacted.</span></span>

<span data-ttu-id="8e4c9-p102">**Index** 对象的 **Fields** 集合中的 **Field2** 对象的 **CollatingOrder** 和 **Attributes** 属性设置共同确定索引中排序次序的序列和方向。但是，不能设置单个索引的整理顺序 - 只能设置整个表的整理顺序。</span><span class="sxs-lookup"><span data-stu-id="8e4c9-p102">The **CollatingOrder** and **Attributes** property settings of a **Field2** object in a **Fields** collection of an **Index** object together determine the sequence and direction of the sort order in an index. However, you can't set a collating order for an individual index— you can only set it for an entire table.</span></span>

