---
<span data-ttu-id="23add-101"><<<<<<< 标头标题： BOF、 EOF 属性 (ADO) TOCTitle: BOF、 EOF 属性 (ADO) === 标题： BOF、 EOF 属性 (ADO) TOCTitle: BOF、 EOF 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="23add-101"><<<<<<< HEAD title: BOF, EOF Properties (ADO) TOCTitle: BOF, EOF Properties (ADO) ======= title: BOF, EOF properties (ADO) TOCTitle: BOF, EOF properties (ADO)</span></span>
>>>>>>> <span data-ttu-id="23add-102">母版页 ms:assetid: f797e140-5572-1a4d-9afc-285f6a3868a8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250260(v=office.15) ms:contentKeyID: 48548768 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="23add-102">master ms:assetid: f797e140-5572-1a4d-9afc-285f6a3868a8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250260(v=office.15) ms:contentKeyID: 48548768 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="23add-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="23add-103"><<<<<<< HEAD</span></span>
# <a name="bof-eof-properties-ado"></a><span data-ttu-id="23add-104">BOF、EOF 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="23add-104">BOF, EOF Properties (ADO)</span></span>
=======
# <a name="bof-eof-properties-ado"></a><span data-ttu-id="23add-105">BOF、 EOF 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="23add-105">BOF, EOF properties (ADO)</span></span>
>>>>>>> <span data-ttu-id="23add-106">master</span><span class="sxs-lookup"><span data-stu-id="23add-106">master</span></span>


<span data-ttu-id="23add-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="23add-107">**Applies to**: Access 2013 | Office 2013</span></span>

  - <span data-ttu-id="23add-108">**BOF**  指示当前记录位置在 [Recordset](recordset-object-ado.md) 对象中的第一条记录之前。</span><span class="sxs-lookup"><span data-stu-id="23add-108">**BOF** — Indicates that the current record position is before the first record in a [Recordset](recordset-object-ado.md) object.</span></span>

  - <span data-ttu-id="23add-109">**EOF**  指示当前记录位置在 **Recordset** 对象中的最后一条记录之后。</span><span class="sxs-lookup"><span data-stu-id="23add-109">**EOF** — Indicates that the current record position is after the last record in a **Recordset** object.</span></span>

<span data-ttu-id="23add-110"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="23add-110"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="23add-111">返回值</span><span class="sxs-lookup"><span data-stu-id="23add-111">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="23add-112">返回值</span><span class="sxs-lookup"><span data-stu-id="23add-112">Return value</span></span>
>>>>>>> <span data-ttu-id="23add-113">master</span><span class="sxs-lookup"><span data-stu-id="23add-113">master</span></span>

<span data-ttu-id="23add-114">**BOF** 和 **EOF** 属性将返回 **Boolean** 值。</span><span class="sxs-lookup"><span data-stu-id="23add-114">The **BOF** and **EOF** properties return **Boolean** values.</span></span>

## <a name="remarks"></a><span data-ttu-id="23add-115">备注</span><span class="sxs-lookup"><span data-stu-id="23add-115">Remarks</span></span>

<span data-ttu-id="23add-116">使用 **BOF** 和 **EOF** 属性可以确定 **Recordset** 对象是否包含记录，或确定在从一条记录移动到另一条记录时是否超出了 **Recordset** 对象的限制。</span><span class="sxs-lookup"><span data-stu-id="23add-116">Use the **BOF** and **EOF** properties to determine whether a **Recordset** object contains records or whether you've gone beyond the limits of a **Recordset** object when you move from record to record.</span></span>

<span data-ttu-id="23add-117">如果当前记录位于第一个记录之前，则 **BOF** 属性返回 **True** (-1)，如果当前记录就是第一个记录或者位于第一个记录之后，则返回 **False** (0)。</span><span class="sxs-lookup"><span data-stu-id="23add-117">The **BOF** property returns **True** (-1) if the current record position is before the first record and **False** (0) if the current record position is on or after the first record.</span></span>

<span data-ttu-id="23add-118">如果当前记录位于最后一个记录之后，则 **EOF** 属性返回 **True** ，如果当前记录就是最后一个记录或者位于最后一个记录之前，则返回 **False** 。</span><span class="sxs-lookup"><span data-stu-id="23add-118">The **EOF** property returns **True** if the current record position is after the last record and **False** if the current record position is on or before the last record.</span></span>

<span data-ttu-id="23add-119">如果 **BOF** 或 **EOF** 属性为 **True** ，则没有当前记录。</span><span class="sxs-lookup"><span data-stu-id="23add-119">If either the **BOF** or **EOF** property is **True**, there is no current record.</span></span>

<span data-ttu-id="23add-p101">如果打开不包含任何记录的 **Recordset** 对象，**BOF** 和 **EOF** 属性都会设置为 **True**（有关 **Recordset** 的此状态的详细信息，请参阅 [RecordCount](recordcount-property-ado.md) 属性）。当打开至少包含一条记录的 **Recordset** 对象时，第一条记录为当前记录，且 **BOF** 和 **EOF** 属性均为 **False**。</span><span class="sxs-lookup"><span data-stu-id="23add-p101">If you open a **Recordset** object containing no records, the **BOF** and **EOF** properties are set to **True** (see the [RecordCount](recordcount-property-ado.md) property for more information about this state of a **Recordset**). When you open a **Recordset** object that contains at least one record, the first record is the current record and the **BOF** and **EOF** properties are **False**.</span></span>

<span data-ttu-id="23add-122">如果删除了 **Recordset** 对象中剩下的最后一条记录，则在尝试重新定位当前记录之前， **BOF** 和 **EOF** 属性都会保持为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="23add-122">If you delete the last remaining record in the **Recordset** object, the **BOF** and **EOF** properties may remain **False** until you attempt to reposition the current record.</span></span>

<span data-ttu-id="23add-123">下表显示了在使用不同的 **BOF** 和 **EOF** 属性组合时允许的 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="23add-123">This table shows which **Move** methods are allowed with different combinations of the **BOF** and **EOF** properties.</span></span>

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
<th><p><span data-ttu-id="23add-124">MoveFirst，</span><span class="sxs-lookup"><span data-stu-id="23add-124">MoveFirst,</span></span><br />
<span data-ttu-id="23add-125">MoveLast</span><span class="sxs-lookup"><span data-stu-id="23add-125">MoveLast</span></span></p></th>
<th><p><span data-ttu-id="23add-126">MovePrevious、</span><span class="sxs-lookup"><span data-stu-id="23add-126">MovePrevious,</span></span><br />
<span data-ttu-id="23add-127">移动&lt;0</span><span class="sxs-lookup"><span data-stu-id="23add-127">Move &lt; 0</span></span></p></th>
<th><p><br />
<span data-ttu-id="23add-128">Move 0</span><span class="sxs-lookup"><span data-stu-id="23add-128">Move 0</span></span></p></th>
<th><p><span data-ttu-id="23add-129">MoveNext、</span><span class="sxs-lookup"><span data-stu-id="23add-129">MoveNext,</span></span><br />
<span data-ttu-id="23add-130">移动&gt;0</span><span class="sxs-lookup"><span data-stu-id="23add-130">Move &gt; 0</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23add-131"><strong>BOF = true，则</strong></span><span class="sxs-lookup"><span data-stu-id="23add-131"><strong>BOF=True,</strong></span></span><br /><span data-ttu-id="23add-132">
<strong>EOF = False</strong></span><span class="sxs-lookup"><span data-stu-id="23add-132">
<strong>EOF=False</strong></span></span></p></td>
<td><p><span data-ttu-id="23add-133">允许</span><span class="sxs-lookup"><span data-stu-id="23add-133">Allowed</span></span></p></td>
<td><p><span data-ttu-id="23add-134">错误</span><span class="sxs-lookup"><span data-stu-id="23add-134">Error</span></span></p></td>
<td><p><span data-ttu-id="23add-135">错误</span><span class="sxs-lookup"><span data-stu-id="23add-135">Error</span></span></p></td>
<td><p><span data-ttu-id="23add-136">允许</span><span class="sxs-lookup"><span data-stu-id="23add-136">Allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23add-137"><strong>BOF = False，</strong></span><span class="sxs-lookup"><span data-stu-id="23add-137"><strong>BOF=False,</strong></span></span><br /><span data-ttu-id="23add-138">
<strong>EOF = True</strong></span><span class="sxs-lookup"><span data-stu-id="23add-138">
<strong>EOF=True</strong></span></span></p></td>
<td><p><span data-ttu-id="23add-139">允许</span><span class="sxs-lookup"><span data-stu-id="23add-139">Allowed</span></span></p></td>
<td><p><span data-ttu-id="23add-140">允许</span><span class="sxs-lookup"><span data-stu-id="23add-140">Allowed</span></span></p></td>
<td><p><span data-ttu-id="23add-141">错误</span><span class="sxs-lookup"><span data-stu-id="23add-141">Error</span></span></p></td>
<td><p><span data-ttu-id="23add-142">错误</span><span class="sxs-lookup"><span data-stu-id="23add-142">Error</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23add-143">均为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="23add-143">Both <strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="23add-144">错误</span><span class="sxs-lookup"><span data-stu-id="23add-144">Error</span></span></p></td>
<td><p><span data-ttu-id="23add-145">错误</span><span class="sxs-lookup"><span data-stu-id="23add-145">Error</span></span></p></td>
<td><p><span data-ttu-id="23add-146">错误</span><span class="sxs-lookup"><span data-stu-id="23add-146">Error</span></span></p></td>
<td><p><span data-ttu-id="23add-147">错误</span><span class="sxs-lookup"><span data-stu-id="23add-147">Error</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23add-148">均为 <strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="23add-148">Both <strong>False</strong></span></span></p></td>
<td><p><span data-ttu-id="23add-149">允许</span><span class="sxs-lookup"><span data-stu-id="23add-149">Allowed</span></span></p></td>
<td><p><span data-ttu-id="23add-150">允许</span><span class="sxs-lookup"><span data-stu-id="23add-150">Allowed</span></span></p></td>
<td><p><span data-ttu-id="23add-151">允许</span><span class="sxs-lookup"><span data-stu-id="23add-151">Allowed</span></span></p></td>
<td><p><span data-ttu-id="23add-152">允许</span><span class="sxs-lookup"><span data-stu-id="23add-152">Allowed</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23add-153">允许某个 **Move** 方法并不保证该方法将成功地定位到一条记录；这仅意味着调用指定的 **Move** 方法不会生成错误。</span><span class="sxs-lookup"><span data-stu-id="23add-153">Allowing a **Move** method doesn't guarantee that the method will successfully locate a record; it only means that calling the specified **Move** method won't generate an error.</span></span>

<span data-ttu-id="23add-154">下表显示了在调用各种 **Move** 方法但不能成功定位到记录时， **BOF** 和 **EOF** 属性的设置会发生什么变化。</span><span class="sxs-lookup"><span data-stu-id="23add-154">The following table shows what happens to the **BOF** and **EOF** property settings when you call various **Move** methods but are unable to successfully locate a record.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p><span data-ttu-id="23add-155">BOF</span><span class="sxs-lookup"><span data-stu-id="23add-155">BOF</span></span></p></th>
<th><p><span data-ttu-id="23add-156">EOF</span><span class="sxs-lookup"><span data-stu-id="23add-156">EOF</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23add-157"><strong>MoveFirst</strong> <strong>MoveLast</strong></span><span class="sxs-lookup"><span data-stu-id="23add-157"><strong>MoveFirst</strong>, <strong>MoveLast</strong></span></span></p></td>
<td><p><span data-ttu-id="23add-158">设置为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="23add-158">Set to <strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="23add-159">设置为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="23add-159">Set to <strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23add-160"><strong>Move</strong> 0</span><span class="sxs-lookup"><span data-stu-id="23add-160"><strong>Move</strong> 0</span></span></p></td>
<td><p><span data-ttu-id="23add-161">没有变化</span><span class="sxs-lookup"><span data-stu-id="23add-161">No change</span></span></p></td>
<td><p><span data-ttu-id="23add-162">没有变化</span><span class="sxs-lookup"><span data-stu-id="23add-162">No change</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23add-163"><strong>MovePrevious</strong>、<strong>移动</strong> &lt; 0</span><span class="sxs-lookup"><span data-stu-id="23add-163"><strong>MovePrevious</strong>, <strong>Move</strong> &lt; 0</span></span></p></td>
<td><p><span data-ttu-id="23add-164">设置为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="23add-164">Set to <strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="23add-165">没有变化</span><span class="sxs-lookup"><span data-stu-id="23add-165">No change</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23add-166"><strong>MoveNext</strong>、<strong>移动</strong> &gt; 0</span><span class="sxs-lookup"><span data-stu-id="23add-166"><strong>MoveNext</strong>, <strong>Move</strong> &gt; 0</span></span></p></td>
<td><p><span data-ttu-id="23add-167">没有变化</span><span class="sxs-lookup"><span data-stu-id="23add-167">No change</span></span></p></td>
<td><p><span data-ttu-id="23add-168">设置为 <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="23add-168">Set to <strong>True</strong></span></span></p></td>
</tr>
</tbody>
</table>

