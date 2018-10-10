---
title: BOF、EOF 属性 (ADO)
TOCTitle: BOF, EOF Properties (ADO)
ms:assetid: f797e140-5572-1a4d-9afc-285f6a3868a8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250260(v=office.15)
ms:contentKeyID: 48548768
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 14cd61f6bd2985d71321d848a6426c06c4c7a94d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466239"
---
# <a name="bof-eof-properties-ado"></a><span data-ttu-id="d9dc2-102">BOF、EOF 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="d9dc2-102">BOF, EOF Properties (ADO)</span></span>


<span data-ttu-id="d9dc2-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d9dc2-103">**Applies to**: Access 2013 | Office 2013</span></span>

  - <span data-ttu-id="d9dc2-104">**BOF**  指示当前记录位置在 [Recordset](recordset-object-ado.md) 对象中的第一条记录之前。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-104">**BOF** — Indicates that the current record position is before the first record in a [Recordset](recordset-object-ado.md) object.</span></span>

  - <span data-ttu-id="d9dc2-105">**EOF**  指示当前记录位置在 **Recordset** 对象中的最后一条记录之后。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-105">**EOF** — Indicates that the current record position is after the last record in a **Recordset** object.</span></span>

## <a name="return-value"></a><span data-ttu-id="d9dc2-106">返回值</span><span class="sxs-lookup"><span data-stu-id="d9dc2-106">Return Value</span></span>

<span data-ttu-id="d9dc2-107">**BOF** 和 **EOF** 属性将返回 **Boolean** 值。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-107">The **BOF** and **EOF** properties return **Boolean** values.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9dc2-108">备注</span><span class="sxs-lookup"><span data-stu-id="d9dc2-108">Remarks</span></span>

<span data-ttu-id="d9dc2-109">使用 **BOF** 和 **EOF** 属性可以确定 **Recordset** 对象是否包含记录，或确定在从一条记录移动到另一条记录时是否超出了 **Recordset** 对象的限制。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-109">Use the **BOF** and **EOF** properties to determine whether a **Recordset** object contains records or whether you've gone beyond the limits of a **Recordset** object when you move from record to record.</span></span>

<span data-ttu-id="d9dc2-110">如果当前记录位于第一个记录之前，则 **BOF** 属性返回 **True** (-1)，如果当前记录就是第一个记录或者位于第一个记录之后，则返回 **False** (0)。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-110">The **BOF** property returns **True** (-1) if the current record position is before the first record and **False** (0) if the current record position is on or after the first record.</span></span>

<span data-ttu-id="d9dc2-111">如果当前记录位于最后一个记录之后，则 **EOF** 属性返回 **True** ，如果当前记录就是最后一个记录或者位于最后一个记录之前，则返回 **False** 。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-111">The **EOF** property returns **True** if the current record position is after the last record and **False** if the current record position is on or before the last record.</span></span>

<span data-ttu-id="d9dc2-112">如果 **BOF** 或 **EOF** 属性为 **True** ，则没有当前记录。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-112">If either the **BOF** or **EOF** property is **True**, there is no current record.</span></span>

<span data-ttu-id="d9dc2-p101">如果打开不包含任何记录的 **Recordset** 对象，**BOF** 和 **EOF** 属性都会设置为 **True**（有关 **Recordset** 的此状态的详细信息，请参阅 [RecordCount](recordcount-property-ado.md) 属性）。当打开至少包含一条记录的 **Recordset** 对象时，第一条记录为当前记录，且 **BOF** 和 **EOF** 属性均为 **False**。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-p101">If you open a **Recordset** object containing no records, the **BOF** and **EOF** properties are set to **True** (see the [RecordCount](recordcount-property-ado.md) property for more information about this state of a **Recordset**). When you open a **Recordset** object that contains at least one record, the first record is the current record and the **BOF** and **EOF** properties are **False**.</span></span>

<span data-ttu-id="d9dc2-115">如果删除了 **Recordset** 对象中剩下的最后一条记录，则在尝试重新定位当前记录之前， **BOF** 和 **EOF** 属性都会保持为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-115">If you delete the last remaining record in the **Recordset** object, the **BOF** and **EOF** properties may remain **False** until you attempt to reposition the current record.</span></span>

<span data-ttu-id="d9dc2-116">下表显示了在使用不同的 **BOF** 和 **EOF** 属性组合时允许的 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-116">This table shows which **Move** methods are allowed with different combinations of the **BOF** and **EOF** properties.</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p><span data-ttu-id="d9dc2-117">MoveFirst，</span><span class="sxs-lookup"><span data-stu-id="d9dc2-117">MoveFirst,</span></span><br />
<span data-ttu-id="d9dc2-118">MoveLast</span><span class="sxs-lookup"><span data-stu-id="d9dc2-118">MoveLast</span></span></p></th>
<th><p><span data-ttu-id="d9dc2-119">MovePrevious、</span><span class="sxs-lookup"><span data-stu-id="d9dc2-119">MovePrevious,</span></span><br />
<span data-ttu-id="d9dc2-120">移动&lt;0</span><span class="sxs-lookup"><span data-stu-id="d9dc2-120">Move &lt; 0</span></span></p></th>
<th><p><br />
<span data-ttu-id="d9dc2-121">Move 0</span><span class="sxs-lookup"><span data-stu-id="d9dc2-121">Move 0</span></span></p></th>
<th><p><span data-ttu-id="d9dc2-122">MoveNext、</span><span class="sxs-lookup"><span data-stu-id="d9dc2-122">MoveNext,</span></span><br />
<span data-ttu-id="d9dc2-123">移动&gt;0</span><span class="sxs-lookup"><span data-stu-id="d9dc2-123">Move &gt; 0</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9dc2-124"><strong>BOF = true，则</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-124"><strong>BOF=True,</strong></span></span><br /><span data-ttu-id="d9dc2-125">
<strong>EOF = False</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-125">
<strong>EOF=False</strong></span></span></p></td>
<td><p><span data-ttu-id="d9dc2-126">允许</span><span class="sxs-lookup"><span data-stu-id="d9dc2-126">Allowed</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-127">错误</span><span class="sxs-lookup"><span data-stu-id="d9dc2-127">Error</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-128">错误</span><span class="sxs-lookup"><span data-stu-id="d9dc2-128">Error</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-129">允许</span><span class="sxs-lookup"><span data-stu-id="d9dc2-129">Allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9dc2-130"><strong>BOF = False，</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-130"><strong>BOF=False,</strong></span></span><br /><span data-ttu-id="d9dc2-131">
<strong>EOF = True</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-131">
<strong>EOF=True</strong></span></span></p></td>
<td><p><span data-ttu-id="d9dc2-132">允许</span><span class="sxs-lookup"><span data-stu-id="d9dc2-132">Allowed</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-133">允许</span><span class="sxs-lookup"><span data-stu-id="d9dc2-133">Allowed</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-134">错误</span><span class="sxs-lookup"><span data-stu-id="d9dc2-134">Error</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-135">错误</span><span class="sxs-lookup"><span data-stu-id="d9dc2-135">Error</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9dc2-136">均为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-136">Both <strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="d9dc2-137">错误</span><span class="sxs-lookup"><span data-stu-id="d9dc2-137">Error</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-138">错误</span><span class="sxs-lookup"><span data-stu-id="d9dc2-138">Error</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-139">错误</span><span class="sxs-lookup"><span data-stu-id="d9dc2-139">Error</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-140">错误</span><span class="sxs-lookup"><span data-stu-id="d9dc2-140">Error</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9dc2-141">均为 <strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-141">Both <strong>False</strong></span></span></p></td>
<td><p><span data-ttu-id="d9dc2-142">允许</span><span class="sxs-lookup"><span data-stu-id="d9dc2-142">Allowed</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-143">允许</span><span class="sxs-lookup"><span data-stu-id="d9dc2-143">Allowed</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-144">允许</span><span class="sxs-lookup"><span data-stu-id="d9dc2-144">Allowed</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-145">允许</span><span class="sxs-lookup"><span data-stu-id="d9dc2-145">Allowed</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d9dc2-146">允许某个 **Move** 方法并不保证该方法将成功地定位到一条记录；这仅意味着调用指定的 **Move** 方法不会生成错误。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-146">Allowing a **Move** method doesn't guarantee that the method will successfully locate a record; it only means that calling the specified **Move** method won't generate an error.</span></span>

<span data-ttu-id="d9dc2-147">下表显示了在调用各种 **Move** 方法但不能成功定位到记录时， **BOF** 和 **EOF** 属性的设置会发生什么变化。</span><span class="sxs-lookup"><span data-stu-id="d9dc2-147">The following table shows what happens to the **BOF** and **EOF** property settings when you call various **Move** methods but are unable to successfully locate a record.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p><span data-ttu-id="d9dc2-148">BOF</span><span class="sxs-lookup"><span data-stu-id="d9dc2-148">BOF</span></span></p></th>
<th><p><span data-ttu-id="d9dc2-149">EOF</span><span class="sxs-lookup"><span data-stu-id="d9dc2-149">EOF</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9dc2-150"><strong>MoveFirst</strong> <strong>MoveLast</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-150"><strong>MoveFirst</strong>, <strong>MoveLast</strong></span></span></p></td>
<td><p><span data-ttu-id="d9dc2-151">设置为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-151">Set to <strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="d9dc2-152">设置为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-152">Set to <strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9dc2-153"><strong>Move</strong> 0</span><span class="sxs-lookup"><span data-stu-id="d9dc2-153"><strong>Move</strong> 0</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-154">没有变化</span><span class="sxs-lookup"><span data-stu-id="d9dc2-154">No change</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-155">没有变化</span><span class="sxs-lookup"><span data-stu-id="d9dc2-155">No change</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9dc2-156"><strong>MovePrevious</strong>、<strong>移动</strong> &lt; 0</span><span class="sxs-lookup"><span data-stu-id="d9dc2-156"><strong>MovePrevious</strong>, <strong>Move</strong> &lt; 0</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-157">设置为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-157">Set to <strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="d9dc2-158">没有变化</span><span class="sxs-lookup"><span data-stu-id="d9dc2-158">No change</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9dc2-159"><strong>MoveNext</strong>、<strong>移动</strong> &gt; 0</span><span class="sxs-lookup"><span data-stu-id="d9dc2-159"><strong>MoveNext</strong>, <strong>Move</strong> &gt; 0</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-160">没有变化</span><span class="sxs-lookup"><span data-stu-id="d9dc2-160">No change</span></span></p></td>
<td><p><span data-ttu-id="d9dc2-161">设置为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="d9dc2-161">Set to <strong>True</strong></span></span></p></td>
</tr>
</tbody>
</table>

