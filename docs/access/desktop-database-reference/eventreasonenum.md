---
title: EventReasonEnum （访问桌面数据库参考 （英文）
TOCTitle: EventReasonEnum
ms:assetid: 0639928e-d0ef-3db3-887e-f3da03913bc7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248815(v=office.15)
ms:contentKeyID: 48543047
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4948cd9a5f1436e4e1afc61bef87b63675e115ff
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707414"
---
# <a name="eventreasonenum"></a><span data-ttu-id="f1400-102">EventReasonEnum</span><span class="sxs-lookup"><span data-stu-id="f1400-102">EventReasonEnum</span></span>

<span data-ttu-id="f1400-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f1400-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f1400-104">指定导致事件发生的原因。</span><span class="sxs-lookup"><span data-stu-id="f1400-104">Specifies the reason that caused an event to occur.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f1400-105">常量</span><span class="sxs-lookup"><span data-stu-id="f1400-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="f1400-106">值</span><span class="sxs-lookup"><span data-stu-id="f1400-106">Value</span></span></p></th>
<th><p><span data-ttu-id="f1400-107">说明</span><span class="sxs-lookup"><span data-stu-id="f1400-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1400-108"><strong>adRsnAddNew</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-108"><strong>adRsnAddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-109">1</span><span class="sxs-lookup"><span data-stu-id="f1400-109">1</span></span></p></td>
<td><p><span data-ttu-id="f1400-110">操作添加了新记录。</span><span class="sxs-lookup"><span data-stu-id="f1400-110">An operation added a new record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-111"><strong>adRsnClose</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-111"><strong>adRsnClose</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-112">9</span><span class="sxs-lookup"><span data-stu-id="f1400-112">9</span></span></p></td>
<td><p><span data-ttu-id="f1400-113">操作关闭了 <strong>Recordset</strong>。</span><span class="sxs-lookup"><span data-stu-id="f1400-113">An operation closed the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-114"><strong>adRsnDelete</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-114"><strong>adRsnDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-115">2</span><span class="sxs-lookup"><span data-stu-id="f1400-115">2</span></span></p></td>
<td><p><span data-ttu-id="f1400-116">操作删除了记录。</span><span class="sxs-lookup"><span data-stu-id="f1400-116">An operation deleted a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-117"><strong>adRsnFirstChange</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-117"><strong>adRsnFirstChange</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-118">11</span><span class="sxs-lookup"><span data-stu-id="f1400-118">11</span></span></p></td>
<td><p><span data-ttu-id="f1400-119">操作对某个记录做了第一次更改。</span><span class="sxs-lookup"><span data-stu-id="f1400-119">An operation made the first change to a record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-120"><strong>adRsnMove</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-120"><strong>adRsnMove</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-121">10</span><span class="sxs-lookup"><span data-stu-id="f1400-121">10</span></span></p></td>
<td><p><span data-ttu-id="f1400-122">操作移动了 <strong>Recordset</strong> 中的记录指针。</span><span class="sxs-lookup"><span data-stu-id="f1400-122">An operation moved the record pointer within the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-123"><strong>adRsnMoveFirst</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-123"><strong>adRsnMoveFirst</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-124">12</span><span class="sxs-lookup"><span data-stu-id="f1400-124">12</span></span></p></td>
<td><p><span data-ttu-id="f1400-125">操作将 <strong>Recordset</strong> 中的记录指针移到第一个记录。</span><span class="sxs-lookup"><span data-stu-id="f1400-125">An operation moved the record pointer to the first record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-126"><strong>adRsnMoveLast</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-126"><strong>adRsnMoveLast</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-127">15</span><span class="sxs-lookup"><span data-stu-id="f1400-127">15</span></span></p></td>
<td><p><span data-ttu-id="f1400-128">操作将 <strong>Recordset</strong> 中的记录指针移到最后一个记录。</span><span class="sxs-lookup"><span data-stu-id="f1400-128">An operation moved the record pointer to the last record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-129"><strong>adRsnMoveNext</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-129"><strong>adRsnMoveNext</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-130">13</span><span class="sxs-lookup"><span data-stu-id="f1400-130">13</span></span></p></td>
<td><p><span data-ttu-id="f1400-131">操作将 <strong>Recordset</strong> 中的记录指针移到下一个记录。</span><span class="sxs-lookup"><span data-stu-id="f1400-131">An operation moved the record pointer to the next record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-132"><strong>adRsnMovePrevious</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-132"><strong>adRsnMovePrevious</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-133">14</span><span class="sxs-lookup"><span data-stu-id="f1400-133">14</span></span></p></td>
<td><p><span data-ttu-id="f1400-134">操作将 <strong>Recordset</strong> 中的记录指针移到上一个记录。</span><span class="sxs-lookup"><span data-stu-id="f1400-134">An operation moved the record pointer to the previous record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-135"><strong>adRsnRequery</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-135"><strong>adRsnRequery</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-136">7</span><span class="sxs-lookup"><span data-stu-id="f1400-136">7</span></span></p></td>
<td><p><span data-ttu-id="f1400-137">操作重新查询 <a href="recordset-object-ado.md">Recordset</a>。</span><span class="sxs-lookup"><span data-stu-id="f1400-137">An operation requeried the <a href="recordset-object-ado.md">Recordset</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-138"><strong>adRsnResynch</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-138"><strong>adRsnResynch</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-139">8</span><span class="sxs-lookup"><span data-stu-id="f1400-139">8</span></span></p></td>
<td><p><span data-ttu-id="f1400-140">操作将 <strong>Recordset</strong> 与数据库重新同步。</span><span class="sxs-lookup"><span data-stu-id="f1400-140">An operation resynchronized the <strong>Recordset</strong> with the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-141"><strong>adRsnUndoAddNew</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-141"><strong>adRsnUndoAddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-142">5</span><span class="sxs-lookup"><span data-stu-id="f1400-142">5</span></span></p></td>
<td><p><span data-ttu-id="f1400-143">操作恢复了新记录的添加。</span><span class="sxs-lookup"><span data-stu-id="f1400-143">An operation reversed the addition of a new record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-144"><strong>adRsnUndoDelete</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-144"><strong>adRsnUndoDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-145">6</span><span class="sxs-lookup"><span data-stu-id="f1400-145">6</span></span></p></td>
<td><p><span data-ttu-id="f1400-146">操作恢复了记录的删除。</span><span class="sxs-lookup"><span data-stu-id="f1400-146">An operation reversed the deletion of a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-147"><strong>adRsnUndoUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-147"><strong>adRsnUndoUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-148">4</span><span class="sxs-lookup"><span data-stu-id="f1400-148">4</span></span></p></td>
<td><p><span data-ttu-id="f1400-149">操作恢复了记录的更新。</span><span class="sxs-lookup"><span data-stu-id="f1400-149">An operation reversed the update of a record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-150"><strong>adRsnUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="f1400-150"><strong>adRsnUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="f1400-151">3</span><span class="sxs-lookup"><span data-stu-id="f1400-151">3</span></span></p></td>
<td><p><span data-ttu-id="f1400-152">操作更新了现有记录。</span><span class="sxs-lookup"><span data-stu-id="f1400-152">An operation updated an existing record.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="f1400-153">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="f1400-153">ADO/WFC equivalent</span></span>

<span data-ttu-id="f1400-154">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="f1400-154">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f1400-155">常量</span><span class="sxs-lookup"><span data-stu-id="f1400-155">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1400-156">AdoEnums.EventReason.ADDNEW</span><span class="sxs-lookup"><span data-stu-id="f1400-156">AdoEnums.EventReason.ADDNEW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-157">AdoEnums.EventReason.CLOSE</span><span class="sxs-lookup"><span data-stu-id="f1400-157">AdoEnums.EventReason.CLOSE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-158">AdoEnums.EventReason.DELETE</span><span class="sxs-lookup"><span data-stu-id="f1400-158">AdoEnums.EventReason.DELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-159">AdoEnums.EventReason.FIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="f1400-159">AdoEnums.EventReason.FIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-160">AdoEnums.EventReason.MOVE</span><span class="sxs-lookup"><span data-stu-id="f1400-160">AdoEnums.EventReason.MOVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-161">AdoEnums.EventReason.MOVEFIRST</span><span class="sxs-lookup"><span data-stu-id="f1400-161">AdoEnums.EventReason.MOVEFIRST</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-162">AdoEnums.EventReason.MOVELAST</span><span class="sxs-lookup"><span data-stu-id="f1400-162">AdoEnums.EventReason.MOVELAST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-163">AdoEnums.EventReason.MOVENEXT</span><span class="sxs-lookup"><span data-stu-id="f1400-163">AdoEnums.EventReason.MOVENEXT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-164">AdoEnums.EventReason.MOVEPREVIOUS</span><span class="sxs-lookup"><span data-stu-id="f1400-164">AdoEnums.EventReason.MOVEPREVIOUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-165">AdoEnums.EventReason.REQUERY</span><span class="sxs-lookup"><span data-stu-id="f1400-165">AdoEnums.EventReason.REQUERY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-166">AdoEnums.EventReason.RESYNCH</span><span class="sxs-lookup"><span data-stu-id="f1400-166">AdoEnums.EventReason.RESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-167">AdoEnums.EventReason.UNDOADDNEW</span><span class="sxs-lookup"><span data-stu-id="f1400-167">AdoEnums.EventReason.UNDOADDNEW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-168">AdoEnums.EventReason.UNDODELETE</span><span class="sxs-lookup"><span data-stu-id="f1400-168">AdoEnums.EventReason.UNDODELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1400-169">AdoEnums.EventReason.UNDOUPDATE</span><span class="sxs-lookup"><span data-stu-id="f1400-169">AdoEnums.EventReason.UNDOUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1400-170">AdoEnums.EventReason.UPDATE</span><span class="sxs-lookup"><span data-stu-id="f1400-170">AdoEnums.EventReason.UPDATE</span></span></p></td>
</tr>
</tbody>
</table>

