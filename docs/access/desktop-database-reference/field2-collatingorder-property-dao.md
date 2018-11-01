---
title: Field2.CollatingOrder Property (DAO)
TOCTitle: CollatingOrder Property
ms:assetid: cb1d6fc9-a2a6-54c2-abf5-48b609e38738
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834380(v=office.15)
ms:contentKeyID: 48547709
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 508f7f758d682dec0f1557f8a3f4dc2845e20a39
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870765"
---
# <a name="field2collatingorder-property-dao"></a><span data-ttu-id="29e9c-102">Field2.CollatingOrder Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="29e9c-102">Field2.CollatingOrder Property (DAO)</span></span>


<span data-ttu-id="29e9c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="29e9c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="29e9c-p101">返回一个值，该值指定用于字符串比较或排序的文本中排序次序的序列（仅适用于 Microsoft Access 工作区）。只读 **Long**。</span><span class="sxs-lookup"><span data-stu-id="29e9c-p101">Returns a value that specifies the sequence of the sort order in text for string comparison or sorting (Microsoft Access workspaces only). Read-only **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="29e9c-106">语法</span><span class="sxs-lookup"><span data-stu-id="29e9c-106">Syntax</span></span>

<span data-ttu-id="29e9c-107">*表达式*。CollatingOrder</span><span class="sxs-lookup"><span data-stu-id="29e9c-107">*expression* .CollatingOrder</span></span>

<span data-ttu-id="29e9c-108">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="29e9c-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="29e9c-109">注解</span><span class="sxs-lookup"><span data-stu-id="29e9c-109">Remarks</span></span>

<span data-ttu-id="29e9c-110">返回值为 **Long** 类型值，或者为下列值之一的常量。</span><span class="sxs-lookup"><span data-stu-id="29e9c-110">The return value is a **Long** value or constant that can be one of the following values.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="29e9c-111">常量</span><span class="sxs-lookup"><span data-stu-id="29e9c-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="29e9c-112">排序次序</span><span class="sxs-lookup"><span data-stu-id="29e9c-112">Sort order</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-113"><strong>dbSortGeneral</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-113"><strong>dbSortGeneral</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-114">常规（英语、法语、德语、葡萄牙语、意大利语和现代西班牙语）</span><span class="sxs-lookup"><span data-stu-id="29e9c-114">General (English, French, German, Portuguese, Italian, and Modern Spanish)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-115"><strong>dbSortArabic</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-115"><strong>dbSortArabic</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-116">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="29e9c-116">Arabic</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-117"><strong>dbSortChineseSimplified</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-117"><strong>dbSortChineseSimplified</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-118">简体中文</span><span class="sxs-lookup"><span data-stu-id="29e9c-118">Simplified Chinese</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-119"><strong>dbSortChineseTraditional</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-119"><strong>dbSortChineseTraditional</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-120">繁体中文</span><span class="sxs-lookup"><span data-stu-id="29e9c-120">Traditional Chinese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-121"><strong>dbSortCyrillic</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-121"><strong>dbSortCyrillic</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-122">俄语</span><span class="sxs-lookup"><span data-stu-id="29e9c-122">Russian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-123"><strong>dbSortCzech</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-123"><strong>dbSortCzech</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-124">捷克语</span><span class="sxs-lookup"><span data-stu-id="29e9c-124">Czech</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-125"><strong>dbSortDutch</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-125"><strong>dbSortDutch</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-126">荷兰语</span><span class="sxs-lookup"><span data-stu-id="29e9c-126">Dutch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-127"><strong>dbSortGreek</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-127"><strong>dbSortGreek</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-128">希腊语</span><span class="sxs-lookup"><span data-stu-id="29e9c-128">Greek</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-129"><strong>dbSortHebrew</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-129"><strong>dbSortHebrew</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-130">希伯来语</span><span class="sxs-lookup"><span data-stu-id="29e9c-130">Hebrew</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-131"><strong>dbSortHungarian</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-131"><strong>dbSortHungarian</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-132">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="29e9c-132">Hungarian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-133"><strong>dbSortIcelandic</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-133"><strong>dbSortIcelandic</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-134">冰岛语</span><span class="sxs-lookup"><span data-stu-id="29e9c-134">Icelandic</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-135"><strong>dbSortJapanese</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-135"><strong>dbSortJapanese</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-136">日语</span><span class="sxs-lookup"><span data-stu-id="29e9c-136">Japanese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-137"><strong>dbSortKorean</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-137"><strong>dbSortKorean</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-138">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="29e9c-138">Korean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-139"><strong>dbSortNeutral</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-139"><strong>dbSortNeutral</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-140">非特定语言</span><span class="sxs-lookup"><span data-stu-id="29e9c-140">Neutral</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-141"><strong>dbSortNorwDan</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-141"><strong>dbSortNorwDan</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-142">挪威语或丹麦语</span><span class="sxs-lookup"><span data-stu-id="29e9c-142">Norwegian or Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-143"><strong>dbSortPDXIntl</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-143"><strong>dbSortPDXIntl</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-144">Paradox 国际型</span><span class="sxs-lookup"><span data-stu-id="29e9c-144">Paradox International</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-145"><strong>dbSortPDXNor</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-145"><strong>dbSortPDXNor</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-146">Paradox 挪威语或丹麦语</span><span class="sxs-lookup"><span data-stu-id="29e9c-146">Paradox Norwegian or Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-147"><strong>dbSortPDXSwe</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-147"><strong>dbSortPDXSwe</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-148">Paradox 瑞典语或芬兰语</span><span class="sxs-lookup"><span data-stu-id="29e9c-148">Paradox Swedish or Finnish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-149"><strong>dbSortPolish</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-149"><strong>dbSortPolish</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-150">波兰语</span><span class="sxs-lookup"><span data-stu-id="29e9c-150">Polish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-151"><strong>dbSortSlovenian</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-151"><strong>dbSortSlovenian</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-152">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="29e9c-152">Slovenian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-153"><strong>dbSortSpanish</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-153"><strong>dbSortSpanish</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-154">西班牙语</span><span class="sxs-lookup"><span data-stu-id="29e9c-154">Spanish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-155"><strong>dbSortSwedFin</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-155"><strong>dbSortSwedFin</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-156">瑞典语或芬兰语</span><span class="sxs-lookup"><span data-stu-id="29e9c-156">Swedish or Finnish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-157"><strong>dbSortThai</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-157"><strong>dbSortThai</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-158">泰语</span><span class="sxs-lookup"><span data-stu-id="29e9c-158">Thai</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-159"><strong>dbSortTurkish</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-159"><strong>dbSortTurkish</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-160">土耳其语</span><span class="sxs-lookup"><span data-stu-id="29e9c-160">Turkish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-161"><strong>dbSortUndefined</strong></span><span class="sxs-lookup"><span data-stu-id="29e9c-161"><strong>dbSortUndefined</strong></span></span></p></td>
<td><p><span data-ttu-id="29e9c-162">不确定或未知</span><span class="sxs-lookup"><span data-stu-id="29e9c-162">Undefined or unknown</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="29e9c-163">**CollatingOrder** 属性的可用性取决于包含 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="29e9c-163">The availability of the **CollatingOrder** property depends on the object that contains the **Fields** collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="29e9c-164">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="29e9c-164">If the Fields collection belongs to an</span></span></p></th>
<th><p><span data-ttu-id="29e9c-165">则 CollatingOrder</span><span class="sxs-lookup"><span data-stu-id="29e9c-165">Then CollatingOrder is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-166"><strong>Index</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="29e9c-166"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="29e9c-167">不支持</span><span class="sxs-lookup"><span data-stu-id="29e9c-167">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-168"><strong>QueryDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="29e9c-168"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="29e9c-169">只读</span><span class="sxs-lookup"><span data-stu-id="29e9c-169">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-170"><strong>Recordset</strong>对象</span><span class="sxs-lookup"><span data-stu-id="29e9c-170"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="29e9c-171">只读</span><span class="sxs-lookup"><span data-stu-id="29e9c-171">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e9c-172"><strong>Relation</strong>对象</span><span class="sxs-lookup"><span data-stu-id="29e9c-172"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="29e9c-173">不支持</span><span class="sxs-lookup"><span data-stu-id="29e9c-173">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e9c-174"><strong>TableDef</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="29e9c-174"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="29e9c-175">只读</span><span class="sxs-lookup"><span data-stu-id="29e9c-175">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="29e9c-176">最近压缩数据库时， **CollatingOrder**属性设置对应于**CreateDatabase**方法创建数据库时或**CompactDatabase**方法的 locale 参数。</span><span class="sxs-lookup"><span data-stu-id="29e9c-176">The **CollatingOrder** property setting corresponds to the locale argument of the **CreateDatabase** method when the database was created or the **CompactDatabase** method when the database was most recently compacted.</span></span>

<span data-ttu-id="29e9c-p102">**Index** 对象的 **Fields** 集合中的 **Field2** 对象的 **CollatingOrder** 和 **Attributes** 属性设置共同确定索引中排序次序的序列和方向。但是，不能设置单个索引的整理顺序 - 只能设置整个表的整理顺序。</span><span class="sxs-lookup"><span data-stu-id="29e9c-p102">The **CollatingOrder** and **Attributes** property settings of a **Field2** object in a **Fields** collection of an **Index** object together determine the sequence and direction of the sort order in an index. However, you can't set a collating order for an individual index— you can only set it for an entire table.</span></span>

