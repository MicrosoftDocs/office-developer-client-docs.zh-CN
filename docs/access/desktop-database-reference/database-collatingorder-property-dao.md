---
title: Database.CollatingOrder Property (DAO)
TOCTitle: CollatingOrder Property
ms:assetid: 7f6c35bf-e5f9-8423-608e-bc072ca09141
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196459(v=office.15)
ms:contentKeyID: 48545901
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1eddad35508fb3182b50ecdca2f0fb413569aa12
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25889530"
---
# <a name="databasecollatingorder-property-dao"></a><span data-ttu-id="094d8-102">Database.CollatingOrder Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="094d8-102">Database.CollatingOrder Property (DAO)</span></span>


<span data-ttu-id="094d8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="094d8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="094d8-p101">返回一个值，该值指定用于字符串比较或排序的文本中排序次序的序列（仅适用于 Microsoft Access 工作区）。只读 **Long**。</span><span class="sxs-lookup"><span data-stu-id="094d8-p101">Returns a value that specifies the sequence of the sort order in text for string comparison or sorting (Microsoft Access workspaces only). Read-only **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="094d8-106">语法</span><span class="sxs-lookup"><span data-stu-id="094d8-106">Syntax</span></span>

<span data-ttu-id="094d8-107">*表达式*。CollatingOrder</span><span class="sxs-lookup"><span data-stu-id="094d8-107">*expression* .CollatingOrder</span></span>

<span data-ttu-id="094d8-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="094d8-108">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="094d8-109">注解</span><span class="sxs-lookup"><span data-stu-id="094d8-109">Remarks</span></span>

<span data-ttu-id="094d8-110">返回值为 **Long** 类型值，或者为下列值之一的常量。</span><span class="sxs-lookup"><span data-stu-id="094d8-110">The return value is a **Long** value or constant that can be one of the following values.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="094d8-111">常量</span><span class="sxs-lookup"><span data-stu-id="094d8-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="094d8-112">排序次序</span><span class="sxs-lookup"><span data-stu-id="094d8-112">Sort order</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="094d8-113"><strong>dbSortGeneral</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-113"><strong>dbSortGeneral</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-114">常规（英语、法语、德语、葡萄牙语、意大利语和现代西班牙语）</span><span class="sxs-lookup"><span data-stu-id="094d8-114">General (English, French, German, Portuguese, Italian, and Modern Spanish)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-115"><strong>dbSortArabic</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-115"><strong>dbSortArabic</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-116">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="094d8-116">Arabic</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-117"><strong>dbSortChineseSimplified</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-117"><strong>dbSortChineseSimplified</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-118">简体中文</span><span class="sxs-lookup"><span data-stu-id="094d8-118">Simplified Chinese</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-119"><strong>dbSortChineseTraditional</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-119"><strong>dbSortChineseTraditional</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-120">繁体中文</span><span class="sxs-lookup"><span data-stu-id="094d8-120">Traditional Chinese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-121"><strong>dbSortCyrillic</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-121"><strong>dbSortCyrillic</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-122">俄语</span><span class="sxs-lookup"><span data-stu-id="094d8-122">Russian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-123"><strong>dbSortCzech</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-123"><strong>dbSortCzech</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-124">捷克语</span><span class="sxs-lookup"><span data-stu-id="094d8-124">Czech</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-125"><strong>dbSortDutch</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-125"><strong>dbSortDutch</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-126">荷兰语</span><span class="sxs-lookup"><span data-stu-id="094d8-126">Dutch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-127"><strong>dbSortGreek</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-127"><strong>dbSortGreek</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-128">希腊语</span><span class="sxs-lookup"><span data-stu-id="094d8-128">Greek</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-129"><strong>dbSortHebrew</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-129"><strong>dbSortHebrew</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-130">希伯来语</span><span class="sxs-lookup"><span data-stu-id="094d8-130">Hebrew</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-131"><strong>dbSortHungarian</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-131"><strong>dbSortHungarian</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-132">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="094d8-132">Hungarian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-133"><strong>dbSortIcelandic</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-133"><strong>dbSortIcelandic</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-134">冰岛语</span><span class="sxs-lookup"><span data-stu-id="094d8-134">Icelandic</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-135"><strong>dbSortJapanese</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-135"><strong>dbSortJapanese</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-136">日语</span><span class="sxs-lookup"><span data-stu-id="094d8-136">Japanese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-137"><strong>dbSortKorean</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-137"><strong>dbSortKorean</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-138">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="094d8-138">Korean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-139"><strong>dbSortNeutral</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-139"><strong>dbSortNeutral</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-140">非特定语言</span><span class="sxs-lookup"><span data-stu-id="094d8-140">Neutral</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-141"><strong>dbSortNorwDan</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-141"><strong>dbSortNorwDan</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-142">挪威语或丹麦语</span><span class="sxs-lookup"><span data-stu-id="094d8-142">Norwegian or Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-143"><strong>dbSortPDXIntl</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-143"><strong>dbSortPDXIntl</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-144">Paradox 国际型</span><span class="sxs-lookup"><span data-stu-id="094d8-144">Paradox International</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-145"><strong>dbSortPDXNor</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-145"><strong>dbSortPDXNor</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-146">Paradox 挪威语或丹麦语</span><span class="sxs-lookup"><span data-stu-id="094d8-146">Paradox Norwegian or Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-147"><strong>dbSortPDXSwe</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-147"><strong>dbSortPDXSwe</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-148">Paradox 瑞典语或芬兰语</span><span class="sxs-lookup"><span data-stu-id="094d8-148">Paradox Swedish or Finnish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-149"><strong>dbSortPolish</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-149"><strong>dbSortPolish</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-150">波兰语</span><span class="sxs-lookup"><span data-stu-id="094d8-150">Polish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-151"><strong>dbSortSlovenian</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-151"><strong>dbSortSlovenian</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-152">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="094d8-152">Slovenian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-153"><strong>dbSortSpanish</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-153"><strong>dbSortSpanish</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-154">西班牙语</span><span class="sxs-lookup"><span data-stu-id="094d8-154">Spanish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-155"><strong>dbSortSwedFin</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-155"><strong>dbSortSwedFin</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-156">瑞典语或芬兰语</span><span class="sxs-lookup"><span data-stu-id="094d8-156">Swedish or Finnish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-157"><strong>dbSortThai</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-157"><strong>dbSortThai</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-158">泰语</span><span class="sxs-lookup"><span data-stu-id="094d8-158">Thai</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="094d8-159"><strong>dbSortTurkish</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-159"><strong>dbSortTurkish</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-160">土耳其语</span><span class="sxs-lookup"><span data-stu-id="094d8-160">Turkish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="094d8-161"><strong>dbSortUndefined</strong></span><span class="sxs-lookup"><span data-stu-id="094d8-161"><strong>dbSortUndefined</strong></span></span></p></td>
<td><p><span data-ttu-id="094d8-162">不确定或未知</span><span class="sxs-lookup"><span data-stu-id="094d8-162">Undefined or unknown</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="094d8-163">最近压缩数据库时， **CollatingOrder**属性设置对应于**CreateDatabase**方法创建数据库时或**CompactDatabase**方法的 locale 参数。</span><span class="sxs-lookup"><span data-stu-id="094d8-163">The **CollatingOrder** property setting corresponds to the locale argument of the **CreateDatabase** method when the database was created or the **CompactDatabase** method when the database was most recently compacted.</span></span>

<span data-ttu-id="094d8-p102">检查 **Database** 或 **Field** 对象的 **CollatingOrder** 属性设置，以确定数据库或字段的字符串比较方法。要使 **Field** 对象的设置不同于包含该对象的 **Database** 对象的设置，可以设置一个未追加的新 **Field** 对象的 **CollatingOrder** 属性。</span><span class="sxs-lookup"><span data-stu-id="094d8-p102">Check the **CollatingOrder** property setting of a **Database** or **Field** object to determine the string comparison method for the database or field. You can set the **CollatingOrder** property of a new, unappended **Field** object if you want the setting of the **Field** object to differ from that of the **Database** object that contains it.</span></span>

