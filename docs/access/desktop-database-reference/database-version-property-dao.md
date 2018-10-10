---
title: Database.Version Property (DAO)
TOCTitle: Version Property
ms:assetid: 40faaa0c-e764-e968-f606-7e06ded80c3f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192887(v=office.15)
ms:contentKeyID: 48544440
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4bcb360caa71131f4892409805c7afe3ceb2dcce
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468865"
---
# <a name="databaseversion-property-dao"></a><span data-ttu-id="5fda9-102">Database.Version Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="5fda9-102">Database.Version Property (DAO)</span></span>


<span data-ttu-id="5fda9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5fda9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5fda9-p101">在 Microsoft Access 工作区中，返回创建数据库的 Microsoft Jet 或 Microsoft Access 数据库引擎的版本。 **String** 类型，只读。</span><span class="sxs-lookup"><span data-stu-id="5fda9-p101">In a Microsoft Access workspace, returns the vesion of the Microsoft Jet or Microsoft Access database engine that created the database. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="5fda9-106">语法</span><span class="sxs-lookup"><span data-stu-id="5fda9-106">Syntax</span></span>

<span data-ttu-id="5fda9-107">*表达式*。版本</span><span class="sxs-lookup"><span data-stu-id="5fda9-107">*expression* .Version</span></span>

<span data-ttu-id="5fda9-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="5fda9-108">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="5fda9-109">注解</span><span class="sxs-lookup"><span data-stu-id="5fda9-109">Remarks</span></span>

<span data-ttu-id="5fda9-110">返回值是一个 String，其计算结果为版本号，格式如下所示。</span><span class="sxs-lookup"><span data-stu-id="5fda9-110">The return value is a String that evaluates to a version number, formatted as follows.</span></span>

  - <span data-ttu-id="5fda9-p102">Microsoft Access 工作区以“*major.minor*”的形式表示版本号。例如，“3.0”。产品版本号由版本号 (3)、句点和发行版本号 (0) 组成。</span><span class="sxs-lookup"><span data-stu-id="5fda9-p102">Microsoft Access workspace represents the version number in the form "*major.minor*". For example, "3.0". The product version number consists of the version number (3), a period, and the release number (0).</span></span>

<span data-ttu-id="5fda9-114">下表显示不同版本的 Microsoft 产品中包含的数据库引擎版本。</span><span class="sxs-lookup"><span data-stu-id="5fda9-114">The following table shows which version of the database engine was included with various versions of Microsoft products.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5fda9-115">数据库引擎</span><span class="sxs-lookup"><span data-stu-id="5fda9-115">Database Engine</span></span></p></th>
<th><p><span data-ttu-id="5fda9-116">版本（发行年份）</span><span class="sxs-lookup"><span data-stu-id="5fda9-116">Version (year released)</span></span></p></th>
<th><p><span data-ttu-id="5fda9-117">Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="5fda9-117">Microsoft Access</span></span></p></th>
<th><p><span data-ttu-id="5fda9-118">Microsoft Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5fda9-118">Microsoft Visual Basic</span></span></p></th>
<th><p><span data-ttu-id="5fda9-119">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="5fda9-119">Microsoft Excel</span></span></p></th>
<th><p><span data-ttu-id="5fda9-120">Microsoft Visual C++</span><span class="sxs-lookup"><span data-stu-id="5fda9-120">Microsoft Visual C++</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fda9-121">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="5fda9-121">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="5fda9-122">1.0 (1992)</span><span class="sxs-lookup"><span data-stu-id="5fda9-122">1.0 (1992)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-123">1.0</span><span class="sxs-lookup"><span data-stu-id="5fda9-123">1.0</span></span></p></td>
<td><p><span data-ttu-id="5fda9-124">无</span><span class="sxs-lookup"><span data-stu-id="5fda9-124">N/A</span></span></p></td>
<td><p><span data-ttu-id="5fda9-125">不适用</span><span class="sxs-lookup"><span data-stu-id="5fda9-125">N/A</span></span></p></td>
<td><p><span data-ttu-id="5fda9-126">无</span><span class="sxs-lookup"><span data-stu-id="5fda9-126">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fda9-127">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="5fda9-127">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="5fda9-128">1.1 (1993)</span><span class="sxs-lookup"><span data-stu-id="5fda9-128">1.1 (1993)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-129">1.1</span><span class="sxs-lookup"><span data-stu-id="5fda9-129">1.1</span></span></p></td>
<td><p><span data-ttu-id="5fda9-130">3.0</span><span class="sxs-lookup"><span data-stu-id="5fda9-130">3.0</span></span></p></td>
<td><p><span data-ttu-id="5fda9-131">无</span><span class="sxs-lookup"><span data-stu-id="5fda9-131">N/A</span></span></p></td>
<td><p><span data-ttu-id="5fda9-132">无</span><span class="sxs-lookup"><span data-stu-id="5fda9-132">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fda9-133">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="5fda9-133">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="5fda9-134">2.0 (1994)</span><span class="sxs-lookup"><span data-stu-id="5fda9-134">2.0 (1994)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-135">2.0</span><span class="sxs-lookup"><span data-stu-id="5fda9-135">2.0</span></span></p></td>
<td><p><span data-ttu-id="5fda9-136">无</span><span class="sxs-lookup"><span data-stu-id="5fda9-136">N/A</span></span></p></td>
<td><p><span data-ttu-id="5fda9-137">不适用</span><span class="sxs-lookup"><span data-stu-id="5fda9-137">N/A</span></span></p></td>
<td><p><span data-ttu-id="5fda9-138">无</span><span class="sxs-lookup"><span data-stu-id="5fda9-138">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fda9-139">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="5fda9-139">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="5fda9-140">2.5 （1995 年）</span><span class="sxs-lookup"><span data-stu-id="5fda9-140">2.5 (1995)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-141">无</span><span class="sxs-lookup"><span data-stu-id="5fda9-141">N/A</span></span></p></td>
<td><p><span data-ttu-id="5fda9-142">4.0（16 位）</span><span class="sxs-lookup"><span data-stu-id="5fda9-142">4.0 (16-bit)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-143">无</span><span class="sxs-lookup"><span data-stu-id="5fda9-143">N/A</span></span></p></td>
<td><p><span data-ttu-id="5fda9-144">无</span><span class="sxs-lookup"><span data-stu-id="5fda9-144">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fda9-145">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="5fda9-145">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="5fda9-146">3.0 （1995 年）</span><span class="sxs-lookup"><span data-stu-id="5fda9-146">3.0 (1995)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-147">"95 (7.0)</span><span class="sxs-lookup"><span data-stu-id="5fda9-147">‘95 (7.0)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-148">4.0（32 位）</span><span class="sxs-lookup"><span data-stu-id="5fda9-148">4.0 (32-bit)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-149">"95 (7.0)</span><span class="sxs-lookup"><span data-stu-id="5fda9-149">‘95 (7.0)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-150">4.x</span><span class="sxs-lookup"><span data-stu-id="5fda9-150">4.x</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fda9-151">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="5fda9-151">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="5fda9-152">3.5 （1996 年）</span><span class="sxs-lookup"><span data-stu-id="5fda9-152">3.5 (1996)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-153">' 97 (8.0)</span><span class="sxs-lookup"><span data-stu-id="5fda9-153">‘97 (8.0)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-154">5.0</span><span class="sxs-lookup"><span data-stu-id="5fda9-154">5.0</span></span></p></td>
<td><p><span data-ttu-id="5fda9-155">' 97 (8.0)</span><span class="sxs-lookup"><span data-stu-id="5fda9-155">‘97 (8.0)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-156">5.0</span><span class="sxs-lookup"><span data-stu-id="5fda9-156">5.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fda9-157">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="5fda9-157">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="5fda9-158">4.0 (2000)</span><span class="sxs-lookup"><span data-stu-id="5fda9-158">4.0 (2000)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-159">2000 (9.0)</span><span class="sxs-lookup"><span data-stu-id="5fda9-159">2000 (9.0)</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="5fda9-160">2000 (9.0)</span><span class="sxs-lookup"><span data-stu-id="5fda9-160">2000 (9.0)</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fda9-161">Microsoft Access 数据库引擎</span><span class="sxs-lookup"><span data-stu-id="5fda9-161">Microsoft Access database engine</span></span></p></td>
<td><p><span data-ttu-id="5fda9-162">12.0 (2007)</span><span class="sxs-lookup"><span data-stu-id="5fda9-162">12.0 (2007)</span></span></p></td>
<td><p><span data-ttu-id="5fda9-163">2007</span><span class="sxs-lookup"><span data-stu-id="5fda9-163">2007</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

