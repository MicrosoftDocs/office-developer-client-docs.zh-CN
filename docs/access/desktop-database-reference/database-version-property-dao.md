---
title: 数据库版本属性 (DAO)
TOCTitle: Version Property
ms:assetid: 40faaa0c-e764-e968-f606-7e06ded80c3f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192887(v=office.15)
ms:contentKeyID: 48544440
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 41b408f63522902fd1d4f806090eef7563a3492a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294650"
---
# <a name="databaseversion-property-dao"></a><span data-ttu-id="c5b6b-102">数据库版本属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-102">Database.Version property (DAO)</span></span>

<span data-ttu-id="c5b6b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c5b6b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c5b6b-104">在 Microsoft Access 工作区中，返回创建数据库的 Microsoft Jet 或 Microsoft Access 数据库引擎的版本。</span><span class="sxs-lookup"><span data-stu-id="c5b6b-104">In a Microsoft Access workspace, returns the vesion of the Microsoft Jet or Microsoft Access database engine that created the database.</span></span> <span data-ttu-id="c5b6b-105">**String** 类型，只读。</span><span class="sxs-lookup"><span data-stu-id="c5b6b-105">Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="c5b6b-106">语法</span><span class="sxs-lookup"><span data-stu-id="c5b6b-106">Syntax</span></span>

<span data-ttu-id="c5b6b-107">*表达式*。版本</span><span class="sxs-lookup"><span data-stu-id="c5b6b-107">*expression* .Version</span></span>

<span data-ttu-id="c5b6b-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c5b6b-108">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5b6b-109">注解</span><span class="sxs-lookup"><span data-stu-id="c5b6b-109">Remarks</span></span>

<span data-ttu-id="c5b6b-110">返回值是一个 String，其计算结果为版本号，格式如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5b6b-110">The return value is a String that evaluates to a version number, formatted as follows.</span></span>

- <span data-ttu-id="c5b6b-p102">Microsoft Access 工作区以“*major.minor*”的形式表示版本号。例如，“3.0”。产品版本号由版本号 (3)、句点和发行版本号 (0) 组成。</span><span class="sxs-lookup"><span data-stu-id="c5b6b-p102">Microsoft Access workspace represents the version number in the form "*major.minor*". For example, "3.0". The product version number consists of the version number (3), a period, and the release number (0).</span></span>

<span data-ttu-id="c5b6b-114">下表显示不同版本的 Microsoft 产品中包含的数据库引擎版本。</span><span class="sxs-lookup"><span data-stu-id="c5b6b-114">The following table shows which version of the database engine was included with various versions of Microsoft products.</span></span>

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
<th><p><span data-ttu-id="c5b6b-115">数据库引擎</span><span class="sxs-lookup"><span data-stu-id="c5b6b-115">Database Engine</span></span></p></th>
<th><p><span data-ttu-id="c5b6b-116">版本（发行年份）</span><span class="sxs-lookup"><span data-stu-id="c5b6b-116">Version (year released)</span></span></p></th>
<th><p><span data-ttu-id="c5b6b-117">Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="c5b6b-117">Microsoft Access</span></span></p></th>
<th><p><span data-ttu-id="c5b6b-118">Microsoft Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c5b6b-118">Microsoft Visual Basic</span></span></p></th>
<th><p><span data-ttu-id="c5b6b-119">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="c5b6b-119">Microsoft Excel</span></span></p></th>
<th><p><span data-ttu-id="c5b6b-120">Microsoft Visual C++</span><span class="sxs-lookup"><span data-stu-id="c5b6b-120">Microsoft Visual C++</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5b6b-121">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="c5b6b-121">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-122">1.0 (1992)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-122">1.0 (1992)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-123">1.0</span><span class="sxs-lookup"><span data-stu-id="c5b6b-123">1.0</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-124">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-124">N/A</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-125">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-125">N/A</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-126">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-126">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5b6b-127">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="c5b6b-127">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-128">1.1 (1993)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-128">1.1 (1993)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-129">1.1</span><span class="sxs-lookup"><span data-stu-id="c5b6b-129">1.1</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-130">3。0</span><span class="sxs-lookup"><span data-stu-id="c5b6b-130">3.0</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-131">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-131">N/A</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-132">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-132">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5b6b-133">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="c5b6b-133">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-134">2.0 (1994)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-134">2.0 (1994)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-135">2.0</span><span class="sxs-lookup"><span data-stu-id="c5b6b-135">2.0</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-136">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-136">N/A</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-137">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-137">N/A</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-138">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-138">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5b6b-139">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="c5b6b-139">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-140">2.5 (1995)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-140">2.5 (1995)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-141">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-141">N/A</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-142">4.0（16 位）</span><span class="sxs-lookup"><span data-stu-id="c5b6b-142">4.0 (16-bit)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-143">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-143">N/A</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-144">不适用</span><span class="sxs-lookup"><span data-stu-id="c5b6b-144">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5b6b-145">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="c5b6b-145">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-146">3.0 (1995)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-146">3.0 (1995)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-147">‘95 (7.0)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-147">‘95 (7.0)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-148">4.0（32 位）</span><span class="sxs-lookup"><span data-stu-id="c5b6b-148">4.0 (32-bit)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-149">‘95 (7.0)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-149">‘95 (7.0)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-150">版</span><span class="sxs-lookup"><span data-stu-id="c5b6b-150">4.x</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5b6b-151">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="c5b6b-151">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-152">3.5 (1996)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-152">3.5 (1996)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-153">‘97 (8.0)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-153">‘97 (8.0)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-154">5。0</span><span class="sxs-lookup"><span data-stu-id="c5b6b-154">5.0</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-155">‘97 (8.0)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-155">‘97 (8.0)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-156">5。0</span><span class="sxs-lookup"><span data-stu-id="c5b6b-156">5.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5b6b-157">Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="c5b6b-157">Microsoft Jet</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-158">4.0 (2000)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-158">4.0 (2000)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-159">2000 (9.0)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-159">2000 (9.0)</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="c5b6b-160">2000 (9.0)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-160">2000 (9.0)</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5b6b-161">Microsoft Access 数据库引擎</span><span class="sxs-lookup"><span data-stu-id="c5b6b-161">Microsoft Access database engine</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-162">12.0 (2007)</span><span class="sxs-lookup"><span data-stu-id="c5b6b-162">12.0 (2007)</span></span></p></td>
<td><p><span data-ttu-id="c5b6b-163">2007</span><span class="sxs-lookup"><span data-stu-id="c5b6b-163">2007</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

