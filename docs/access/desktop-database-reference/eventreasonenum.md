---
title: EventReasonEnum （访问桌面数据库参考 （英文）
TOCTitle: EventReasonEnum
ms:assetid: 0639928e-d0ef-3db3-887e-f3da03913bc7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248815(v=office.15)
ms:contentKeyID: 48543047
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 5ef716bd28092cdb173fc9bd54a71ed7572e810a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888018"
---
# <a name="eventreasonenum"></a><span data-ttu-id="8bc87-102">EventReasonEnum</span><span class="sxs-lookup"><span data-stu-id="8bc87-102">EventReasonEnum</span></span>

<span data-ttu-id="8bc87-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8bc87-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8bc87-104">指定导致事件发生的原因。</span><span class="sxs-lookup"><span data-stu-id="8bc87-104">Specifies the reason that caused an event to occur.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8bc87-105">常量</span><span class="sxs-lookup"><span data-stu-id="8bc87-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="8bc87-106">值</span><span class="sxs-lookup"><span data-stu-id="8bc87-106">Value</span></span></p></th>
<th><p><span data-ttu-id="8bc87-107">说明</span><span class="sxs-lookup"><span data-stu-id="8bc87-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-108"><strong>adRsnAddNew</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-108"><strong>adRsnAddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-109">1</span><span class="sxs-lookup"><span data-stu-id="8bc87-109">1</span></span></p></td>
<td><p><span data-ttu-id="8bc87-110">操作添加了新记录。</span><span class="sxs-lookup"><span data-stu-id="8bc87-110">An operation added a new record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-111"><strong>adRsnClose</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-111"><strong>adRsnClose</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-112">9</span><span class="sxs-lookup"><span data-stu-id="8bc87-112">9</span></span></p></td>
<td><p><span data-ttu-id="8bc87-113">操作关闭了 <strong>Recordset</strong>。</span><span class="sxs-lookup"><span data-stu-id="8bc87-113">An operation closed the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-114"><strong>adRsnDelete</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-114"><strong>adRsnDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-115">2</span><span class="sxs-lookup"><span data-stu-id="8bc87-115">2</span></span></p></td>
<td><p><span data-ttu-id="8bc87-116">操作删除了记录。</span><span class="sxs-lookup"><span data-stu-id="8bc87-116">An operation deleted a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-117"><strong>adRsnFirstChange</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-117"><strong>adRsnFirstChange</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-118">11</span><span class="sxs-lookup"><span data-stu-id="8bc87-118">11</span></span></p></td>
<td><p><span data-ttu-id="8bc87-119">操作对某个记录做了第一次更改。</span><span class="sxs-lookup"><span data-stu-id="8bc87-119">An operation made the first change to a record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-120"><strong>adRsnMove</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-120"><strong>adRsnMove</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-121">10</span><span class="sxs-lookup"><span data-stu-id="8bc87-121">10</span></span></p></td>
<td><p><span data-ttu-id="8bc87-122">操作移动了 <strong>Recordset</strong> 中的记录指针。</span><span class="sxs-lookup"><span data-stu-id="8bc87-122">An operation moved the record pointer within the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-123"><strong>adRsnMoveFirst</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-123"><strong>adRsnMoveFirst</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-124">12</span><span class="sxs-lookup"><span data-stu-id="8bc87-124">12</span></span></p></td>
<td><p><span data-ttu-id="8bc87-125">操作将 <strong>Recordset</strong> 中的记录指针移到第一个记录。</span><span class="sxs-lookup"><span data-stu-id="8bc87-125">An operation moved the record pointer to the first record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-126"><strong>adRsnMoveLast</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-126"><strong>adRsnMoveLast</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-127">15</span><span class="sxs-lookup"><span data-stu-id="8bc87-127">15</span></span></p></td>
<td><p><span data-ttu-id="8bc87-128">操作将 <strong>Recordset</strong> 中的记录指针移到最后一个记录。</span><span class="sxs-lookup"><span data-stu-id="8bc87-128">An operation moved the record pointer to the last record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-129"><strong>adRsnMoveNext</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-129"><strong>adRsnMoveNext</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-130">13</span><span class="sxs-lookup"><span data-stu-id="8bc87-130">13</span></span></p></td>
<td><p><span data-ttu-id="8bc87-131">操作将 <strong>Recordset</strong> 中的记录指针移到下一个记录。</span><span class="sxs-lookup"><span data-stu-id="8bc87-131">An operation moved the record pointer to the next record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-132"><strong>adRsnMovePrevious</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-132"><strong>adRsnMovePrevious</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-133">14</span><span class="sxs-lookup"><span data-stu-id="8bc87-133">14</span></span></p></td>
<td><p><span data-ttu-id="8bc87-134">操作将 <strong>Recordset</strong> 中的记录指针移到上一个记录。</span><span class="sxs-lookup"><span data-stu-id="8bc87-134">An operation moved the record pointer to the previous record in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-135"><strong>adRsnRequery</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-135"><strong>adRsnRequery</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-136">7</span><span class="sxs-lookup"><span data-stu-id="8bc87-136">7</span></span></p></td>
<td><p><span data-ttu-id="8bc87-137">操作重新查询 <a href="recordset-object-ado.md">Recordset</a>。</span><span class="sxs-lookup"><span data-stu-id="8bc87-137">An operation requeried the <a href="recordset-object-ado.md">Recordset</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-138"><strong>adRsnResynch</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-138"><strong>adRsnResynch</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-139">8</span><span class="sxs-lookup"><span data-stu-id="8bc87-139">8</span></span></p></td>
<td><p><span data-ttu-id="8bc87-140">操作将 <strong>Recordset</strong> 与数据库重新同步。</span><span class="sxs-lookup"><span data-stu-id="8bc87-140">An operation resynchronized the <strong>Recordset</strong> with the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-141"><strong>adRsnUndoAddNew</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-141"><strong>adRsnUndoAddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-142">5</span><span class="sxs-lookup"><span data-stu-id="8bc87-142">5</span></span></p></td>
<td><p><span data-ttu-id="8bc87-143">操作恢复了新记录的添加。</span><span class="sxs-lookup"><span data-stu-id="8bc87-143">An operation reversed the addition of a new record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-144"><strong>adRsnUndoDelete</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-144"><strong>adRsnUndoDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-145">6</span><span class="sxs-lookup"><span data-stu-id="8bc87-145">6</span></span></p></td>
<td><p><span data-ttu-id="8bc87-146">操作恢复了记录的删除。</span><span class="sxs-lookup"><span data-stu-id="8bc87-146">An operation reversed the deletion of a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-147"><strong>adRsnUndoUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-147"><strong>adRsnUndoUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-148">4</span><span class="sxs-lookup"><span data-stu-id="8bc87-148">4</span></span></p></td>
<td><p><span data-ttu-id="8bc87-149">操作恢复了记录的更新。</span><span class="sxs-lookup"><span data-stu-id="8bc87-149">An operation reversed the update of a record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-150"><strong>adRsnUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="8bc87-150"><strong>adRsnUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="8bc87-151">3</span><span class="sxs-lookup"><span data-stu-id="8bc87-151">3</span></span></p></td>
<td><p><span data-ttu-id="8bc87-152">操作更新了现有记录。</span><span class="sxs-lookup"><span data-stu-id="8bc87-152">An operation updated an existing record.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="8bc87-153">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="8bc87-153">ADO/WFC equivalent</span></span>

<span data-ttu-id="8bc87-154">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="8bc87-154">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8bc87-155">常量</span><span class="sxs-lookup"><span data-stu-id="8bc87-155">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-156">AdoEnums.EventReason.ADDNEW</span><span class="sxs-lookup"><span data-stu-id="8bc87-156">AdoEnums.EventReason.ADDNEW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-157">AdoEnums.EventReason.CLOSE</span><span class="sxs-lookup"><span data-stu-id="8bc87-157">AdoEnums.EventReason.CLOSE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-158">AdoEnums.EventReason.DELETE</span><span class="sxs-lookup"><span data-stu-id="8bc87-158">AdoEnums.EventReason.DELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-159">AdoEnums.EventReason.FIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="8bc87-159">AdoEnums.EventReason.FIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-160">AdoEnums.EventReason.MOVE</span><span class="sxs-lookup"><span data-stu-id="8bc87-160">AdoEnums.EventReason.MOVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-161">AdoEnums.EventReason.MOVEFIRST</span><span class="sxs-lookup"><span data-stu-id="8bc87-161">AdoEnums.EventReason.MOVEFIRST</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-162">AdoEnums.EventReason.MOVELAST</span><span class="sxs-lookup"><span data-stu-id="8bc87-162">AdoEnums.EventReason.MOVELAST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-163">AdoEnums.EventReason.MOVENEXT</span><span class="sxs-lookup"><span data-stu-id="8bc87-163">AdoEnums.EventReason.MOVENEXT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-164">AdoEnums.EventReason.MOVEPREVIOUS</span><span class="sxs-lookup"><span data-stu-id="8bc87-164">AdoEnums.EventReason.MOVEPREVIOUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-165">AdoEnums.EventReason.REQUERY</span><span class="sxs-lookup"><span data-stu-id="8bc87-165">AdoEnums.EventReason.REQUERY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-166">AdoEnums.EventReason.RESYNCH</span><span class="sxs-lookup"><span data-stu-id="8bc87-166">AdoEnums.EventReason.RESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-167">AdoEnums.EventReason.UNDOADDNEW</span><span class="sxs-lookup"><span data-stu-id="8bc87-167">AdoEnums.EventReason.UNDOADDNEW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-168">AdoEnums.EventReason.UNDODELETE</span><span class="sxs-lookup"><span data-stu-id="8bc87-168">AdoEnums.EventReason.UNDODELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc87-169">AdoEnums.EventReason.UNDOUPDATE</span><span class="sxs-lookup"><span data-stu-id="8bc87-169">AdoEnums.EventReason.UNDOUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc87-170">AdoEnums.EventReason.UPDATE</span><span class="sxs-lookup"><span data-stu-id="8bc87-170">AdoEnums.EventReason.UPDATE</span></span></p></td>
</tr>
</tbody>
</table>

