---
title: EventReasonEnum （访问桌面数据库参考 （英文）
TOCTitle: EventReasonEnum
ms:assetid: 0639928e-d0ef-3db3-887e-f3da03913bc7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248815(v=office.15)
ms:contentKeyID: 48543047
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: a243e3aa71248fe61f7b73f163e706c8ceb22457
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861965"
---
# <a name="eventreasonenum"></a><span data-ttu-id="646d5-102">EventReasonEnum</span><span class="sxs-lookup"><span data-stu-id="646d5-102">EventReasonEnum</span></span>

<span data-ttu-id="646d5-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="646d5-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="646d5-104">指定导致事件发生的原因。</span><span class="sxs-lookup"><span data-stu-id="646d5-104">Specifies the reason that caused an event to occur.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="646d5-105">常量</span><span class="sxs-lookup"><span data-stu-id="646d5-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="646d5-106">值</span><span class="sxs-lookup"><span data-stu-id="646d5-106">Value</span></span></p></th>
<th><p><span data-ttu-id="646d5-107">说明</span><span class="sxs-lookup"><span data-stu-id="646d5-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="646d5-108"><strong>adRsnAddNew</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-108"><strong>adRsnAddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-109">1</span><span class="sxs-lookup"><span data-stu-id="646d5-109">1</span></span></p></td>
<td><p><span data-ttu-id="646d5-110">操作添加了新记录。</span><span class="sxs-lookup"><span data-stu-id="646d5-110">An operation added a new record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-111"><strong>adRsnClose</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-111"><strong>adRsnClose</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-112">9</span><span class="sxs-lookup"><span data-stu-id="646d5-112">9</span></span></p></td>
<td><p><span data-ttu-id="646d5-113">操作关闭了 <strong>Recordset</strong>。</span><span class="sxs-lookup"><span data-stu-id="646d5-113">An operation closed the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-114"><strong>adRsnDelete</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-114"><strong>adRsnDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-115">2</span><span class="sxs-lookup"><span data-stu-id="646d5-115">2</span></span></p></td>
<td><p><span data-ttu-id="646d5-116">操作删除了记录。</span><span class="sxs-lookup"><span data-stu-id="646d5-116">An operation deleted a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-117"><strong>adRsnFirstChange</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-117"><strong>adRsnFirstChange</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-118">11</span><span class="sxs-lookup"><span data-stu-id="646d5-118">11</span></span></p></td>
<td><p><span data-ttu-id="646d5-119">操作对某个记录做了第一次更改。</span><span class="sxs-lookup"><span data-stu-id="646d5-119">An operation made the first change to a record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-120"><strong>adRsnMove</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-120"><strong>adRsnMove</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-121">10</span><span class="sxs-lookup"><span data-stu-id="646d5-121">10</span></span></p></td>
<td><p><span data-ttu-id="646d5-122">操作移动了 <strong>Recordset</strong> 中的记录指针。</span><span class="sxs-lookup"><span data-stu-id="646d5-122">An operation moved the record pointer within the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-123"><strong>adRsnMoveFirst</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-123"><strong>adRsnMoveFirst</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-124">12</span><span class="sxs-lookup"><span data-stu-id="646d5-124">12</span></span></p></td>
<td><p><span data-ttu-id="646d5-125">操作将 <strong>Recordset</strong> 中的记录指针移到第一个记录。</span><span class="sxs-lookup"><span data-stu-id="646d5-125">An operation moved the record pointer to the first record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-126"><strong>adRsnMoveLast</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-126"><strong>adRsnMoveLast</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-127">15</span><span class="sxs-lookup"><span data-stu-id="646d5-127">15</span></span></p></td>
<td><p><span data-ttu-id="646d5-128">操作将 <strong>Recordset</strong> 中的记录指针移到最后一个记录。</span><span class="sxs-lookup"><span data-stu-id="646d5-128">An operation moved the record pointer to the last record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-129"><strong>adRsnMoveNext</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-129"><strong>adRsnMoveNext</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-130">13</span><span class="sxs-lookup"><span data-stu-id="646d5-130">13</span></span></p></td>
<td><p><span data-ttu-id="646d5-131">操作将 <strong>Recordset</strong> 中的记录指针移到下一个记录。</span><span class="sxs-lookup"><span data-stu-id="646d5-131">An operation moved the record pointer to the next record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-132"><strong>adRsnMovePrevious</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-132"><strong>adRsnMovePrevious</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-133">14</span><span class="sxs-lookup"><span data-stu-id="646d5-133">14</span></span></p></td>
<td><p><span data-ttu-id="646d5-134">操作将 <strong>Recordset</strong> 中的记录指针移到上一个记录。</span><span class="sxs-lookup"><span data-stu-id="646d5-134">An operation moved the record pointer to the previous record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-135"><strong>adRsnRequery</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-135"><strong>adRsnRequery</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-136">7</span><span class="sxs-lookup"><span data-stu-id="646d5-136">7</span></span></p></td>
<td><p><span data-ttu-id="646d5-137">操作重新查询 <a href="recordset-object-ado.md">Recordset</a>。</span><span class="sxs-lookup"><span data-stu-id="646d5-137">An operation requeried the <a href="recordset-object-ado.md">Recordset</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-138"><strong>adRsnResynch</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-138"><strong>adRsnResynch</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-139">8</span><span class="sxs-lookup"><span data-stu-id="646d5-139">8</span></span></p></td>
<td><p><span data-ttu-id="646d5-140">操作将 <strong>Recordset</strong> 与数据库重新同步。</span><span class="sxs-lookup"><span data-stu-id="646d5-140">An operation resynchronized the <strong>Recordset</strong> with the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-141"><strong>adRsnUndoAddNew</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-141"><strong>adRsnUndoAddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-142">5</span><span class="sxs-lookup"><span data-stu-id="646d5-142">5</span></span></p></td>
<td><p><span data-ttu-id="646d5-143">操作恢复了新记录的添加。</span><span class="sxs-lookup"><span data-stu-id="646d5-143">An operation reversed the addition of a new record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-144"><strong>adRsnUndoDelete</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-144"><strong>adRsnUndoDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-145">6</span><span class="sxs-lookup"><span data-stu-id="646d5-145">6</span></span></p></td>
<td><p><span data-ttu-id="646d5-146">操作恢复了记录的删除。</span><span class="sxs-lookup"><span data-stu-id="646d5-146">An operation reversed the deletion of a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-147"><strong>adRsnUndoUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-147"><strong>adRsnUndoUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-148">4</span><span class="sxs-lookup"><span data-stu-id="646d5-148">4</span></span></p></td>
<td><p><span data-ttu-id="646d5-149">操作恢复了记录的更新。</span><span class="sxs-lookup"><span data-stu-id="646d5-149">An operation reversed the update of a record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-150"><strong>adRsnUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="646d5-150"><strong>adRsnUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="646d5-151">3</span><span class="sxs-lookup"><span data-stu-id="646d5-151">3</span></span></p></td>
<td><p><span data-ttu-id="646d5-152">操作更新了现有记录。</span><span class="sxs-lookup"><span data-stu-id="646d5-152">An operation updated an existing record.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="646d5-153">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="646d5-153">ADO/WFC equivalent</span></span>

<span data-ttu-id="646d5-154">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="646d5-154">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="646d5-155">常量</span><span class="sxs-lookup"><span data-stu-id="646d5-155">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="646d5-156">AdoEnums.EventReason.ADDNEW</span><span class="sxs-lookup"><span data-stu-id="646d5-156">AdoEnums.EventReason.ADDNEW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-157">AdoEnums.EventReason.CLOSE</span><span class="sxs-lookup"><span data-stu-id="646d5-157">AdoEnums.EventReason.CLOSE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-158">AdoEnums.EventReason.DELETE</span><span class="sxs-lookup"><span data-stu-id="646d5-158">AdoEnums.EventReason.DELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-159">AdoEnums.EventReason.FIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="646d5-159">AdoEnums.EventReason.FIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-160">AdoEnums.EventReason.MOVE</span><span class="sxs-lookup"><span data-stu-id="646d5-160">AdoEnums.EventReason.MOVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-161">AdoEnums.EventReason.MOVEFIRST</span><span class="sxs-lookup"><span data-stu-id="646d5-161">AdoEnums.EventReason.MOVEFIRST</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-162">AdoEnums.EventReason.MOVELAST</span><span class="sxs-lookup"><span data-stu-id="646d5-162">AdoEnums.EventReason.MOVELAST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-163">AdoEnums.EventReason.MOVENEXT</span><span class="sxs-lookup"><span data-stu-id="646d5-163">AdoEnums.EventReason.MOVENEXT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-164">AdoEnums.EventReason.MOVEPREVIOUS</span><span class="sxs-lookup"><span data-stu-id="646d5-164">AdoEnums.EventReason.MOVEPREVIOUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-165">AdoEnums.EventReason.REQUERY</span><span class="sxs-lookup"><span data-stu-id="646d5-165">AdoEnums.EventReason.REQUERY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-166">AdoEnums.EventReason.RESYNCH</span><span class="sxs-lookup"><span data-stu-id="646d5-166">AdoEnums.EventReason.RESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-167">AdoEnums.EventReason.UNDOADDNEW</span><span class="sxs-lookup"><span data-stu-id="646d5-167">AdoEnums.EventReason.UNDOADDNEW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-168">AdoEnums.EventReason.UNDODELETE</span><span class="sxs-lookup"><span data-stu-id="646d5-168">AdoEnums.EventReason.UNDODELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="646d5-169">AdoEnums.EventReason.UNDOUPDATE</span><span class="sxs-lookup"><span data-stu-id="646d5-169">AdoEnums.EventReason.UNDOUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="646d5-170">AdoEnums.EventReason.UPDATE</span><span class="sxs-lookup"><span data-stu-id="646d5-170">AdoEnums.EventReason.UPDATE</span></span></p></td>
</tr>
</tbody>
</table>

