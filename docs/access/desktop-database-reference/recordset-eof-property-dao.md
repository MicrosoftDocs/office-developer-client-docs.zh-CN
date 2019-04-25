---
title: Recordset.EOF 属性 (DAO)
TOCTitle: EOF Property
ms:assetid: aa82c6f9-89da-1061-437c-8ffb000744b6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821459(v=office.15)
ms:contentKeyID: 48546950
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 931de7dfc2cfb80726aafe7077c6107ec65d2f40
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300607"
---
# <a name="recordseteof-property-dao"></a><span data-ttu-id="4f0f1-102">Recordset.EOF 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="4f0f1-102">Recordset.EOF property (DAO)</span></span>


<span data-ttu-id="4f0f1-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="4f0f1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4f0f1-104">返回一个值，该值指示当前记录位置是否位于 **Recordset** 对象的最后一条记录之后。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-104">Returns a value that indicates whether the current record position is after the last record in a **Recordset** object.</span></span> <span data-ttu-id="4f0f1-105">只读 **Boolean**。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-105">Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f0f1-106">语法</span><span class="sxs-lookup"><span data-stu-id="4f0f1-106">Syntax</span></span>

<span data-ttu-id="4f0f1-107">*表达式* .EOF</span><span class="sxs-lookup"><span data-stu-id="4f0f1-107">expression  . EOF</span></span>

<span data-ttu-id="4f0f1-108">*表达式* 一个表示 **Recordset** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-108">*expression*  A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f0f1-109">说明</span><span class="sxs-lookup"><span data-stu-id="4f0f1-109">Remarks</span></span>

<span data-ttu-id="4f0f1-110">可以使用 **BOF** 和 **EOF** 属性确定 **Recordset** 对象是否包含记录，或确定在从一条记录移动到另一条记录时是否超出了 **Recordset** 对象的限制。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-110">You can use the **BOF** and **EOF** properties to determine whether a **Recordset** object contains records or whether you've gone beyond the limits of a **Recordset** object when you move from record to record.</span></span>

<span data-ttu-id="4f0f1-111">当前记录指针的位置决定了 **BOF** 和 **EOF** 返回值。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-111">The location of the current record pointer determines the **BOF** and **EOF** return values.</span></span>

<span data-ttu-id="4f0f1-112">如果 **BOF** 或 **EOF** 属性为 **True**，则没有当前记录。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-112">If either the **BOF** or **EOF** property is **True**, there is no current record.</span></span>

<span data-ttu-id="4f0f1-p102">如果打开的 **Recordset** 对象不包含记录，则 **BOF** 和 **EOF** 属性设置为 **True**，且 **Recordset** 对象的 **RecordCount** 属性设置为 0。当打开的 **Recordset** 对象至少包含一条记录时，则第一条记录即是当前记录， **BOF** 和 **EOF** 属性都为 **False**；它们一直保持 **False**，直到您分别使用 **MovePrevious** 或 **MoveNext** 方法移动到 **Recordset** 对象的开头或末尾之外为止。如果您移动到 **Recordset** 的开头或末尾之外，则没有当前记录或不存在记录。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-p102">If you open a **Recordset** object containing no records, the **BOF** and **EOF** properties are set to **True**, and the **Recordset** object's **RecordCount** property setting is 0. When you open a **Recordset** object that contains at least one record, the first record is the current record and the **BOF** and **EOF** properties are **False**; they remain **False** until you move beyond the beginning or end of the **Recordset** object by using the **MovePrevious** or **MoveNext** method, respectively. When you move beyond the beginning or end of the **Recordset**, there is no current record or no record exists.</span></span>

<span data-ttu-id="4f0f1-116">如果删除了 **Recordset** 对象中剩下的最后一条记录，则在尝试重新定位当前记录之前， **BOF** 和 **EOF** 属性都会保持为 **False**。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-116">If you delete the last remaining record in the **Recordset** object, the **BOF** and **EOF** properties may remain **False** until you attempt to reposition the current record.</span></span>

<span data-ttu-id="4f0f1-p103">如果对包含记录的 **Recordset** 对象使用 **MoveLast** 方法，则最后一条记录将成为当前记录；如果之后又使用 **MoveNext** 方法，则当前记录将变为无效， **EOF** 属性设置为 **True**。相反，如果对包含记录的 **Recordset** 对象使用 **MoveFirst** 方法，则第一条记录将成为当前记录；如果之后又使用 **MovePrevious** 方法，则没有当前记录， **BOF** 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-p103">If you use the **MoveLast** method on a **Recordset** object containing records, the last record becomes the current record; if you then use the **MoveNext** method, the current record becomes invalid and the **EOF** property is set to **True**. Conversely, if you use the **MoveFirst** method on a **Recordset** object containing records, the first record becomes the current record; if you then use the **MovePrevious** method, there is no current record and the **BOF** property is set to **True**.</span></span>

<span data-ttu-id="4f0f1-119">通常，在处理 **Recordset** 对象中的所有记录时，代码将使用 **MoveNext** 方法遍历所有记录，直到 **EOF** 属性设置为 **True** 为止。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-119">Typically, when you work with all the records in a **Recordset** object, your code will loop through the records by using the **MoveNext** method until the **EOF** property is set to **True**.</span></span>

<span data-ttu-id="4f0f1-120">如果在 **EOF** 属性设置为 **True** 的情况下使用 **MoveNext** 方法，或者在 **BOF** 属性设置为 **True** 的情况下使用 **MovePrevious** 方法，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-120">If you use the **MoveNext** method while the **EOF** property is set to **True** or the **MovePrevious** method while the **BOF** property is set to **True**, an error occurs.</span></span>

<span data-ttu-id="4f0f1-121">下表显示了在使用不同的 **BOF** 和 **EOF** 属性组合时允许的 Move 方法。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-121">This table shows which Move methods are allowed with different combinations of the **BOF** and **EOF** properties.</span></span>

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
<th><p><span data-ttu-id="4f0f1-122">MoveFirst、</span><span class="sxs-lookup"><span data-stu-id="4f0f1-122">MoveFirst method</span></span><br />
<span data-ttu-id="4f0f1-123">MoveLast</span><span class="sxs-lookup"><span data-stu-id="4f0f1-123">MoveLast method</span></span></p></th>
<th><p><span data-ttu-id="4f0f1-124">MovePrevious、</span><span class="sxs-lookup"><span data-stu-id="4f0f1-124">MovePrevious method</span></span><br />
<span data-ttu-id="4f0f1-125">Move &lt; 0</span><span class="sxs-lookup"><span data-stu-id="4f0f1-125">&lt; 0</span></span></p></th>
<th><p><br />
<span data-ttu-id="4f0f1-126">Move 0</span><span class="sxs-lookup"><span data-stu-id="4f0f1-126">Move 0</span></span></p></th>
<th><p><span data-ttu-id="4f0f1-127">MoveNext、</span><span class="sxs-lookup"><span data-stu-id="4f0f1-127">MoveNext method</span></span><br />
<span data-ttu-id="4f0f1-128">Move &gt; 0</span><span class="sxs-lookup"><span data-stu-id="4f0f1-128">&gt; 0</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f0f1-129"><strong>BOF=True、</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-129"><strong>BOF=True,EOF=False</strong></span></span><br /><span data-ttu-id="4f0f1-130">
<strong>EOF=False</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-130">
<strong>BOF=True,EOF=False</strong></span></span></p></td>
<td><p><span data-ttu-id="4f0f1-131">Allowed</span><span class="sxs-lookup"><span data-stu-id="4f0f1-131">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-132">错误</span><span class="sxs-lookup"><span data-stu-id="4f0f1-132">Error</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-133">错误</span><span class="sxs-lookup"><span data-stu-id="4f0f1-133">Error</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-134">允许</span><span class="sxs-lookup"><span data-stu-id="4f0f1-134">Allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0f1-135"><strong>BOF=False、</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-135"><strong>BOF=False,EOF=True</strong></span></span><br /><span data-ttu-id="4f0f1-136">
<strong>EOF=True</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-136">
<strong>BOF=False,EOF=True</strong></span></span></p></td>
<td><p><span data-ttu-id="4f0f1-137">允许</span><span class="sxs-lookup"><span data-stu-id="4f0f1-137">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-138">Allowed</span><span class="sxs-lookup"><span data-stu-id="4f0f1-138">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-139">错误</span><span class="sxs-lookup"><span data-stu-id="4f0f1-139">Error</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-140">错误</span><span class="sxs-lookup"><span data-stu-id="4f0f1-140">Error</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0f1-141">均为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-141">Both <strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="4f0f1-142">错误</span><span class="sxs-lookup"><span data-stu-id="4f0f1-142">Error</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-143">错误</span><span class="sxs-lookup"><span data-stu-id="4f0f1-143">Error</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-144">错误</span><span class="sxs-lookup"><span data-stu-id="4f0f1-144">Error</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-145">错误</span><span class="sxs-lookup"><span data-stu-id="4f0f1-145">Error</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0f1-146">均为 <strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-146">Both <strong>False</strong></span></span></p></td>
<td><p><span data-ttu-id="4f0f1-147">Allowed</span><span class="sxs-lookup"><span data-stu-id="4f0f1-147">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-148">允许</span><span class="sxs-lookup"><span data-stu-id="4f0f1-148">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-149">允许</span><span class="sxs-lookup"><span data-stu-id="4f0f1-149">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-150">允许</span><span class="sxs-lookup"><span data-stu-id="4f0f1-150">Allowed</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f0f1-p104">允许 Move 方法并不意味着该方法可以成功定位记录。它只是表示允许尝试执行指定的 Move 方法，且不会生成错误。在尝试 Move 后， **BOF** 和 **EOF** 属性的状态可能更改。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-p104">Allowing a Move method doesn't mean that the method will successfully locate a record. It merely indicates that an attempt to perform the specified Move method is allowed and won't generate an error. The state of the **BOF** and **EOF** properties may change as a result of the attempted Move.</span></span>

<span data-ttu-id="4f0f1-p105">**OpenRecordset** 方法在内部调用 **MoveFirst** 方法。因此，对空记录集使用 **OpenRecordset** 方法会将 **BOF** 和 **EOF** 属性设置为 **True**。（有关失败的 **MoveFirst** 方法的行为，请参阅下表。）</span><span class="sxs-lookup"><span data-stu-id="4f0f1-p105">An **OpenRecordset** method internally invokes a **MoveFirst** method. Therefore, using an **OpenRecordset** method on an empty set of records sets the **BOF** and **EOF** properties to **True**. (See the following table for the behavior of a failed **MoveFirst** method.)</span></span>

<span data-ttu-id="4f0f1-157">所有成功定位记录的 Move 方法都会将 **BOF** 和 **EOF** 均设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-157">All Move methods that successfully locate a record will set both **BOF** and **EOF** to **False**.</span></span>

<span data-ttu-id="4f0f1-158">在 Microsoft Access 工作区中，如果向空 **Recordset** 添加记录， **BOF** 将成为 **False**，但是 **EOF** 将保持 **True**，指示当前位置位于 **Recordset** 的末尾。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-158">In a Microsoft Access workspace, if you add a record to an empty **Recordset**, **BOF** will become **False**, but **EOF** will remain **True**, indicating that the current position is at the end of **Recordset**.</span></span>

<span data-ttu-id="4f0f1-159">任何 **Delete** 方法都不会更改 **BOF** 或 **EOF** 属性的设置，即使它从 **Recordset** 删除了唯一的剩余记录也是如此。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-159">Any **Delete** method, even if it removes the only remaining record from a **Recordset**, won't change the setting of the **BOF** or **EOF** property.</span></span>

<span data-ttu-id="4f0f1-160">下表显示不定位记录的 Move 方法如何影响 **BOF** 和 **EOF** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="4f0f1-160">The following table shows how Move methods that don't locate a record affect the **BOF** and **EOF** property settings.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p><span data-ttu-id="4f0f1-161">BOF</span><span class="sxs-lookup"><span data-stu-id="4f0f1-161">BOF</span></span></p></th>
<th><p><span data-ttu-id="4f0f1-162">EOF</span><span class="sxs-lookup"><span data-stu-id="4f0f1-162">EOF</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f0f1-163"><strong>MoveFirst</strong>、<strong>MoveLast</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-163"><strong>MoveFirst</strong>, <strong>MoveLast</strong></span></span></p></td>
<td><p><span data-ttu-id="4f0f1-164"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-164"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="4f0f1-165"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-165"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0f1-166"><strong>Move</strong> 0</span><span class="sxs-lookup"><span data-stu-id="4f0f1-166"><strong>Move</strong> 0</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-167">无变化</span><span class="sxs-lookup"><span data-stu-id="4f0f1-167">No change</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-168">无变化</span><span class="sxs-lookup"><span data-stu-id="4f0f1-168">No change</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0f1-169"><strong>MovePrevious</strong>、<strong>Move</strong> &lt; 0</span><span class="sxs-lookup"><span data-stu-id="4f0f1-169">MovePrevious, Move < 0</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-170"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-170"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="4f0f1-171">无变化</span><span class="sxs-lookup"><span data-stu-id="4f0f1-171">No change</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0f1-172"><strong>MoveNext</strong>、<strong>Move</strong> &gt; 0</span><span class="sxs-lookup"><span data-stu-id="4f0f1-172">MoveNext, Move > 0</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-173">无变化</span><span class="sxs-lookup"><span data-stu-id="4f0f1-173">No change</span></span></p></td>
<td><p><span data-ttu-id="4f0f1-174"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4f0f1-174"><strong>True</strong></span></span></p></td>
</tr>
</tbody>
</table>

