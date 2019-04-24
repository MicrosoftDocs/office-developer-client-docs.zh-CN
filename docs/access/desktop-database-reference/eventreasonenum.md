---
title: EventReasonEnum (Access desktop database reference)
TOCTitle: EventReasonEnum
ms:assetid: 0639928e-d0ef-3db3-887e-f3da03913bc7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248815(v=office.15)
ms:contentKeyID: 48543047
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4948cd9a5f1436e4e1afc61bef87b63675e115ff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293327"
---
# <a name="eventreasonenum"></a><span data-ttu-id="6cd52-102">EventReasonEnum</span><span class="sxs-lookup"><span data-stu-id="6cd52-102">EventReasonEnum</span></span>

<span data-ttu-id="6cd52-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6cd52-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6cd52-104">指定导致事件发生的原因。</span><span class="sxs-lookup"><span data-stu-id="6cd52-104">Specifies the reason that caused an event to occur.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6cd52-105">常量</span><span class="sxs-lookup"><span data-stu-id="6cd52-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="6cd52-106">值</span><span class="sxs-lookup"><span data-stu-id="6cd52-106">Value</span></span></p></th>
<th><p><span data-ttu-id="6cd52-107">说明</span><span class="sxs-lookup"><span data-stu-id="6cd52-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-108"><strong>adRsnAddNew</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-108"><strong>adRsnAddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-109">1</span><span class="sxs-lookup"><span data-stu-id="6cd52-109">1</span></span></p></td>
<td><p><span data-ttu-id="6cd52-110">操作添加了新记录。</span><span class="sxs-lookup"><span data-stu-id="6cd52-110">An operation added a new record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-111"><strong>adRsnClose</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-111"><strong>adRsnClose</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-112">第</span><span class="sxs-lookup"><span data-stu-id="6cd52-112">9</span></span></p></td>
<td><p><span data-ttu-id="6cd52-113">操作关闭了 <strong>Recordset</strong>。</span><span class="sxs-lookup"><span data-stu-id="6cd52-113">An operation closed the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-114"><strong>adRsnDelete</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-114"><strong>adRsnDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-115">双面</span><span class="sxs-lookup"><span data-stu-id="6cd52-115">2</span></span></p></td>
<td><p><span data-ttu-id="6cd52-116">操作删除了记录。</span><span class="sxs-lookup"><span data-stu-id="6cd52-116">An operation deleted a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-117"><strong>adRsnFirstChange</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-117"><strong>adRsnFirstChange</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-118">11x17</span><span class="sxs-lookup"><span data-stu-id="6cd52-118">11</span></span></p></td>
<td><p><span data-ttu-id="6cd52-119">操作对某个记录做了第一次更改。</span><span class="sxs-lookup"><span data-stu-id="6cd52-119">An operation made the first change to a record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-120"><strong>adRsnMove</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-120"><strong>adRsnMove</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-121">10</span><span class="sxs-lookup"><span data-stu-id="6cd52-121">10</span></span></p></td>
<td><p><span data-ttu-id="6cd52-122">操作移动了 <strong>Recordset</strong> 中的记录指针。</span><span class="sxs-lookup"><span data-stu-id="6cd52-122">An operation moved the record pointer within the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-123"><strong>adRsnMoveFirst</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-123"><strong>adRsnMoveFirst</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-124">12</span><span class="sxs-lookup"><span data-stu-id="6cd52-124">12</span></span></p></td>
<td><p><span data-ttu-id="6cd52-125">操作将 <strong>Recordset</strong> 中的记录指针移到第一个记录。</span><span class="sxs-lookup"><span data-stu-id="6cd52-125">An operation moved the record pointer to the first record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-126"><strong>adRsnMoveLast</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-126"><strong>adRsnMoveLast</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-127">个</span><span class="sxs-lookup"><span data-stu-id="6cd52-127">15</span></span></p></td>
<td><p><span data-ttu-id="6cd52-128">操作将 <strong>Recordset</strong> 中的记录指针移到最后一个记录。</span><span class="sxs-lookup"><span data-stu-id="6cd52-128">An operation moved the record pointer to the last record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-129"><strong>adRsnMoveNext</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-129"><strong>adRsnMoveNext</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-130">13</span><span class="sxs-lookup"><span data-stu-id="6cd52-130">13</span></span></p></td>
<td><p><span data-ttu-id="6cd52-131">操作将 <strong>Recordset</strong> 中的记录指针移到下一个记录。</span><span class="sxs-lookup"><span data-stu-id="6cd52-131">An operation moved the record pointer to the next record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-132"><strong>adRsnMovePrevious</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-132"><strong>adRsnMovePrevious</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-133">日</span><span class="sxs-lookup"><span data-stu-id="6cd52-133">14</span></span></p></td>
<td><p><span data-ttu-id="6cd52-134">操作将 <strong>Recordset</strong> 中的记录指针移到上一个记录。</span><span class="sxs-lookup"><span data-stu-id="6cd52-134">An operation moved the record pointer to the previous record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-135"><strong>adRsnRequery</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-135"><strong>adRsnRequery</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-136">步</span><span class="sxs-lookup"><span data-stu-id="6cd52-136">7</span></span></p></td>
<td><p><span data-ttu-id="6cd52-137">操作重新查询 <a href="recordset-object-ado.md">Recordset</a>。</span><span class="sxs-lookup"><span data-stu-id="6cd52-137">An operation requeried the <a href="recordset-object-ado.md">Recordset</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-138"><strong>adRsnResynch</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-138"><strong>adRsnResynch</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-139">utf-8</span><span class="sxs-lookup"><span data-stu-id="6cd52-139">8</span></span></p></td>
<td><p><span data-ttu-id="6cd52-140">操作将 <strong>Recordset</strong> 与数据库重新同步。</span><span class="sxs-lookup"><span data-stu-id="6cd52-140">An operation resynchronized the <strong>Recordset</strong> with the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-141"><strong>adRsnUndoAddNew</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-141"><strong>adRsnUndoAddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-142">5</span><span class="sxs-lookup"><span data-stu-id="6cd52-142">5</span></span></p></td>
<td><p><span data-ttu-id="6cd52-143">操作恢复了新记录的添加。</span><span class="sxs-lookup"><span data-stu-id="6cd52-143">An operation reversed the addition of a new record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-144"><strong>adRsnUndoDelete</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-144"><strong>adRsnUndoDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-145">型</span><span class="sxs-lookup"><span data-stu-id="6cd52-145">6</span></span></p></td>
<td><p><span data-ttu-id="6cd52-146">操作恢复了记录的删除。</span><span class="sxs-lookup"><span data-stu-id="6cd52-146">An operation reversed the deletion of a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-147"><strong>adRsnUndoUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-147"><strong>adRsnUndoUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-148">4</span><span class="sxs-lookup"><span data-stu-id="6cd52-148">4</span></span></p></td>
<td><p><span data-ttu-id="6cd52-149">操作恢复了记录的更新。</span><span class="sxs-lookup"><span data-stu-id="6cd52-149">An operation reversed the update of a record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-150"><strong>adRsnUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="6cd52-150"><strong>adRsnUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd52-151">第三章</span><span class="sxs-lookup"><span data-stu-id="6cd52-151">3</span></span></p></td>
<td><p><span data-ttu-id="6cd52-152">操作更新了现有记录。</span><span class="sxs-lookup"><span data-stu-id="6cd52-152">An operation updated an existing record.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="6cd52-153">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="6cd52-153">ADO/WFC equivalent</span></span>

<span data-ttu-id="6cd52-154">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="6cd52-154">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6cd52-155">常量</span><span class="sxs-lookup"><span data-stu-id="6cd52-155">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-156">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-156">AdoEnums.EventReason.ADDNEW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-157">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-157">AdoEnums.EventReason.CLOSE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-158">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-158">AdoEnums.EventReason.DELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-159">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-159">AdoEnums.EventReason.FIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-160">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-160">AdoEnums.EventReason.MOVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-161">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-161">AdoEnums.EventReason.MOVEFIRST</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-162">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-162">AdoEnums.EventReason.MOVELAST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-163">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-163">AdoEnums.EventReason.MOVENEXT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-164">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-164">AdoEnums.EventReason.MOVEPREVIOUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-165">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-165">AdoEnums.EventReason.REQUERY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-166">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-166">AdoEnums.EventReason.RESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-167">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-167">AdoEnums.EventReason.UNDOADDNEW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-168">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-168">AdoEnums.EventReason.UNDODELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd52-169">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-169">AdoEnums.EventReason.UNDOUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd52-170">AdoEnums EventReason</span><span class="sxs-lookup"><span data-stu-id="6cd52-170">AdoEnums.EventReason.UPDATE</span></span></p></td>
</tr>
</tbody>
</table>

