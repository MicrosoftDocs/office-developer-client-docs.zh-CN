---
title: Recordset.EOF Property (DAO)
TOCTitle: EOF Property
ms:assetid: aa82c6f9-89da-1061-437c-8ffb000744b6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821459(v=office.15)
ms:contentKeyID: 48546950
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e800ce42b5ada2380dcb895814787ab4a9db6573
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466889"
---
# <a name="recordseteof-property-dao"></a><span data-ttu-id="4358a-102">Recordset.EOF Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="4358a-102">Recordset.EOF Property (DAO)</span></span>


<span data-ttu-id="4358a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4358a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4358a-p101">返回一个值，该值指示当前记录位置是否位于 **Recordset** 对象的最后一条记录之后。只读 **Boolean** 类型。</span><span class="sxs-lookup"><span data-stu-id="4358a-p101">Returns a value that indicates whether the current record position is after the last record in a **Recordset** object. Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="4358a-106">语法</span><span class="sxs-lookup"><span data-stu-id="4358a-106">Syntax</span></span>

<span data-ttu-id="4358a-107">*表达式*。EOF</span><span class="sxs-lookup"><span data-stu-id="4358a-107">*expression* .EOF</span></span>

<span data-ttu-id="4358a-108">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4358a-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4358a-109">注解</span><span class="sxs-lookup"><span data-stu-id="4358a-109">Remarks</span></span>

<span data-ttu-id="4358a-110">可以使用 **BOF** 和 **EOF** 属性确定 **Recordset** 对象是否包含记录，或确定在从一条记录移动到另一条记录时是否超出了 **Recordset** 对象的限制。</span><span class="sxs-lookup"><span data-stu-id="4358a-110">You can use the **BOF** and **EOF** properties to determine whether a **Recordset** object contains records or whether you've gone beyond the limits of a **Recordset** object when you move from record to record.</span></span>

<span data-ttu-id="4358a-111">当前记录指针的位置决定了 **BOF** 和 **EOF** 返回值。</span><span class="sxs-lookup"><span data-stu-id="4358a-111">The location of the current record pointer determines the **BOF** and **EOF** return values.</span></span>

<span data-ttu-id="4358a-112">如果 **BOF** 或 **EOF** 属性为 **True**，则没有当前记录。</span><span class="sxs-lookup"><span data-stu-id="4358a-112">If either the **BOF** or **EOF** property is **True**, there is no current record.</span></span>

<span data-ttu-id="4358a-p102">如果打开的 **Recordset** 对象不包含记录，则 **BOF** 和 **EOF** 属性设置为 **True**，且 **Recordset** 对象的 **RecordCount** 属性设置为 0。当打开的 **Recordset** 对象至少包含一条记录时，则第一条记录即是当前记录， **BOF** 和 **EOF** 属性都为 **False**；它们一直保持 **False**，直到您分别使用 **MovePrevious** 或 **MoveNext** 方法移动到 **Recordset** 对象的开头或末尾之外的位置为止。如果您移动到 **Recordset** 的开头或末尾之外，则没有当前记录或不存在记录。</span><span class="sxs-lookup"><span data-stu-id="4358a-p102">If you open a **Recordset** object containing no records, the **BOF** and **EOF** properties are set to **True**, and the **Recordset** object's **RecordCount** property setting is 0. When you open a **Recordset** object that contains at least one record, the first record is the current record and the **BOF** and **EOF** properties are **False**; they remain **False** until you move beyond the beginning or end of the **Recordset** object by using the **MovePrevious** or **MoveNext** method, respectively. When you move beyond the beginning or end of the **Recordset**, there is no current record or no record exists.</span></span>

<span data-ttu-id="4358a-116">如果删除了 **Recordset** 对象中剩下的最后一条记录，则在尝试重新定位当前记录之前， **BOF** 和 **EOF** 属性都会保持为 **False**。</span><span class="sxs-lookup"><span data-stu-id="4358a-116">If you delete the last remaining record in the **Recordset** object, the **BOF** and **EOF** properties may remain **False** until you attempt to reposition the current record.</span></span>

<span data-ttu-id="4358a-p103">如果对包含记录的 **Recordset** 对象使用 **MoveLast** 方法，则最后一条记录将成为当前记录；如果之后又使用 **MoveNext** 方法，则当前记录将变为无效， **EOF** 属性设置为 **True**。相反，如果对包含记录的 **Recordset** 对象使用 **MoveFirst** 方法，则第一条记录将成为当前记录；如果之后又使用 **MovePrevious** 方法，则没有当前记录， **BOF** 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="4358a-p103">If you use the **MoveLast** method on a **Recordset** object containing records, the last record becomes the current record; if you then use the **MoveNext** method, the current record becomes invalid and the **EOF** property is set to **True**. Conversely, if you use the **MoveFirst** method on a **Recordset** object containing records, the first record becomes the current record; if you then use the **MovePrevious** method, there is no current record and the **BOF** property is set to **True**.</span></span>

<span data-ttu-id="4358a-119">通常，在处理 **Recordset** 对象中的所有记录时，代码将使用 **MoveNext** 方法遍历所有记录，直到 **EOF** 属性设置为 **True** 为止。</span><span class="sxs-lookup"><span data-stu-id="4358a-119">Typically, when you work with all the records in a **Recordset** object, your code will loop through the records by using the **MoveNext** method until the **EOF** property is set to **True**.</span></span>

<span data-ttu-id="4358a-120">如果在 **EOF** 属性设置为 **True** 的情况下使用 **MoveNext** 方法，或者在 **BOF** 属性设置为 **True** 的情况下使用 **MovePrevious** 方法，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="4358a-120">If you use the **MoveNext** method while the **EOF** property is set to **True** or the **MovePrevious** method while the **BOF** property is set to **True**, an error occurs.</span></span>

<span data-ttu-id="4358a-121">下表显示了在使用不同的 **BOF** 和 **EOF** 属性组合时允许的 Move 方法。</span><span class="sxs-lookup"><span data-stu-id="4358a-121">This table shows which Move methods are allowed with different combinations of the **BOF** and **EOF** properties.</span></span>

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
<th><p><span data-ttu-id="4358a-122">MoveFirst，</span><span class="sxs-lookup"><span data-stu-id="4358a-122">MoveFirst,</span></span><br />
<span data-ttu-id="4358a-123">MoveLast</span><span class="sxs-lookup"><span data-stu-id="4358a-123">MoveLast</span></span></p></th>
<th><p><span data-ttu-id="4358a-124">MovePrevious、</span><span class="sxs-lookup"><span data-stu-id="4358a-124">MovePrevious,</span></span><br />
<span data-ttu-id="4358a-125">移动&lt;0</span><span class="sxs-lookup"><span data-stu-id="4358a-125">Move &lt; 0</span></span></p></th>
<th><p><br />
<span data-ttu-id="4358a-126">Move 0</span><span class="sxs-lookup"><span data-stu-id="4358a-126">Move 0</span></span></p></th>
<th><p><span data-ttu-id="4358a-127">MoveNext、</span><span class="sxs-lookup"><span data-stu-id="4358a-127">MoveNext,</span></span><br />
<span data-ttu-id="4358a-128">移动&gt;0</span><span class="sxs-lookup"><span data-stu-id="4358a-128">Move &gt; 0</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4358a-129"><strong>BOF = true，则</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-129"><strong>BOF=True,</strong></span></span><br /><span data-ttu-id="4358a-130">
<strong>EOF = False</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-130">
<strong>EOF=False</strong></span></span></p></td>
<td><p><span data-ttu-id="4358a-131">允许</span><span class="sxs-lookup"><span data-stu-id="4358a-131">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4358a-132">错误</span><span class="sxs-lookup"><span data-stu-id="4358a-132">Error</span></span></p></td>
<td><p><span data-ttu-id="4358a-133">错误</span><span class="sxs-lookup"><span data-stu-id="4358a-133">Error</span></span></p></td>
<td><p><span data-ttu-id="4358a-134">允许</span><span class="sxs-lookup"><span data-stu-id="4358a-134">Allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4358a-135"><strong>BOF = False，</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-135"><strong>BOF=False,</strong></span></span><br /><span data-ttu-id="4358a-136">
<strong>EOF = True</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-136">
<strong>EOF=True</strong></span></span></p></td>
<td><p><span data-ttu-id="4358a-137">允许</span><span class="sxs-lookup"><span data-stu-id="4358a-137">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4358a-138">允许</span><span class="sxs-lookup"><span data-stu-id="4358a-138">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4358a-139">错误</span><span class="sxs-lookup"><span data-stu-id="4358a-139">Error</span></span></p></td>
<td><p><span data-ttu-id="4358a-140">错误</span><span class="sxs-lookup"><span data-stu-id="4358a-140">Error</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4358a-141">均为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-141">Both <strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="4358a-142">错误</span><span class="sxs-lookup"><span data-stu-id="4358a-142">Error</span></span></p></td>
<td><p><span data-ttu-id="4358a-143">错误</span><span class="sxs-lookup"><span data-stu-id="4358a-143">Error</span></span></p></td>
<td><p><span data-ttu-id="4358a-144">错误</span><span class="sxs-lookup"><span data-stu-id="4358a-144">Error</span></span></p></td>
<td><p><span data-ttu-id="4358a-145">错误</span><span class="sxs-lookup"><span data-stu-id="4358a-145">Error</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4358a-146">均为 <strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-146">Both <strong>False</strong></span></span></p></td>
<td><p><span data-ttu-id="4358a-147">允许</span><span class="sxs-lookup"><span data-stu-id="4358a-147">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4358a-148">允许</span><span class="sxs-lookup"><span data-stu-id="4358a-148">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4358a-149">允许</span><span class="sxs-lookup"><span data-stu-id="4358a-149">Allowed</span></span></p></td>
<td><p><span data-ttu-id="4358a-150">允许</span><span class="sxs-lookup"><span data-stu-id="4358a-150">Allowed</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4358a-p104">允许 Move 方法并不意味着该方法可以成功定位记录。它只是表示允许尝试执行指定的 Move 方法，且不会生成错误。在尝试 Move 后， **BOF** 和 **EOF** 属性的状态可能更改。</span><span class="sxs-lookup"><span data-stu-id="4358a-p104">Allowing a Move method doesn't mean that the method will successfully locate a record. It merely indicates that an attempt to perform the specified Move method is allowed and won't generate an error. The state of the **BOF** and **EOF** properties may change as a result of the attempted Move.</span></span>

<span data-ttu-id="4358a-p105">**OpenRecordset** 方法在内部调用 **MoveFirst** 方法。因此，对空记录集使用 **OpenRecordset** 方法会将 **BOF** 和 **EOF** 属性设置为 **True**。（有关失败的 **MoveFirst** 方法的行为，请参阅下表。）</span><span class="sxs-lookup"><span data-stu-id="4358a-p105">An **OpenRecordset** method internally invokes a **MoveFirst** method. Therefore, using an **OpenRecordset** method on an empty set of records sets the **BOF** and **EOF** properties to **True**. (See the following table for the behavior of a failed **MoveFirst** method.)</span></span>

<span data-ttu-id="4358a-157">所有成功定位记录的 Move 方法都会将 **BOF** 和 **EOF** 均设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="4358a-157">All Move methods that successfully locate a record will set both **BOF** and **EOF** to **False**.</span></span>

<span data-ttu-id="4358a-158">在 Microsoft Access 工作区中，如果向空 **Recordset** 添加记录， **BOF** 将成为 **False**，但是 **EOF** 将保持 **True**，指示当前位置位于 **Recordset** 的末尾。</span><span class="sxs-lookup"><span data-stu-id="4358a-158">In a Microsoft Access workspace, if you add a record to an empty **Recordset**, **BOF** will become **False**, but **EOF** will remain **True**, indicating that the current position is at the end of **Recordset**.</span></span>

<span data-ttu-id="4358a-159">任何 **Delete** 方法都不会更改 **BOF** 或 **EOF** 属性的设置，即使它从 **Recordset** 删除了唯一的剩余记录也是如此。</span><span class="sxs-lookup"><span data-stu-id="4358a-159">Any **Delete** method, even if it removes the only remaining record from a **Recordset**, won't change the setting of the **BOF** or **EOF** property.</span></span>

<span data-ttu-id="4358a-160">下表显示不定位记录的 Move 方法如何影响 **BOF** 和 **EOF** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="4358a-160">The following table shows how Move methods that don't locate a record affect the **BOF** and **EOF** property settings.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p><span data-ttu-id="4358a-161">BOF</span><span class="sxs-lookup"><span data-stu-id="4358a-161">BOF</span></span></p></th>
<th><p><span data-ttu-id="4358a-162">EOF</span><span class="sxs-lookup"><span data-stu-id="4358a-162">EOF</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4358a-163"><strong>MoveFirst</strong> <strong>MoveLast</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-163"><strong>MoveFirst</strong>, <strong>MoveLast</strong></span></span></p></td>
<td><p><span data-ttu-id="4358a-164"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-164"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="4358a-165"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-165"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4358a-166"><strong>Move</strong> 0</span><span class="sxs-lookup"><span data-stu-id="4358a-166"><strong>Move</strong> 0</span></span></p></td>
<td><p><span data-ttu-id="4358a-167">没有变化</span><span class="sxs-lookup"><span data-stu-id="4358a-167">No change</span></span></p></td>
<td><p><span data-ttu-id="4358a-168">没有变化</span><span class="sxs-lookup"><span data-stu-id="4358a-168">No change</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4358a-169"><strong>MovePrevious</strong>、<strong>移动</strong> &lt; 0</span><span class="sxs-lookup"><span data-stu-id="4358a-169"><strong>MovePrevious</strong>, <strong>Move</strong> &lt; 0</span></span></p></td>
<td><p><span data-ttu-id="4358a-170"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-170"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="4358a-171">没有变化</span><span class="sxs-lookup"><span data-stu-id="4358a-171">No change</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4358a-172"><strong>MoveNext</strong>、<strong>移动</strong> &gt; 0</span><span class="sxs-lookup"><span data-stu-id="4358a-172"><strong>MoveNext</strong>, <strong>Move</strong> &gt; 0</span></span></p></td>
<td><p><span data-ttu-id="4358a-173">没有变化</span><span class="sxs-lookup"><span data-stu-id="4358a-173">No change</span></span></p></td>
<td><p><span data-ttu-id="4358a-174"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="4358a-174"><strong>True</strong></span></span></p></td>
</tr>
</tbody>
</table>
