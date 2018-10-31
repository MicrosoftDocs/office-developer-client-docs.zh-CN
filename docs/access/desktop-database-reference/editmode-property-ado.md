---
<span data-ttu-id="e1d36-101"><<<<<<< 标头标题： EditMode 属性 (ADO) TOCTitle: EditMode 属性 (ADO) === 标题： EditMode 属性 (ADO) TOCTitle: EditMode 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e1d36-101"><<<<<<< HEAD title: EditMode Property (ADO) TOCTitle: EditMode Property (ADO) ======= title: EditMode property (ADO) TOCTitle: EditMode property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e1d36-102">母版页 ms:assetid: 28ca8f14-abee-ad20-9c16-11bb36b487e4 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249045(v=office.15) ms:contentKeyID: 48543867 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="e1d36-102">master ms:assetid: 28ca8f14-abee-ad20-9c16-11bb36b487e4 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249045(v=office.15) ms:contentKeyID: 48543867 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="e1d36-103"><<<<<<< 头</span><span class="sxs-lookup"><span data-stu-id="e1d36-103"><<<<<<< HEAD</span></span>
# <a name="editmode-property-ado"></a><span data-ttu-id="e1d36-104">EditMode 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e1d36-104">EditMode Property (ADO)</span></span>
=======
# <a name="editmode-property-ado"></a><span data-ttu-id="e1d36-105">EditMode 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e1d36-105">EditMode property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e1d36-106">母版</span><span class="sxs-lookup"><span data-stu-id="e1d36-106">master</span></span>


<span data-ttu-id="e1d36-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e1d36-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e1d36-108">指示当前记录的编辑状态。</span><span class="sxs-lookup"><span data-stu-id="e1d36-108">Indicates the editing status of the current record.</span></span>

<span data-ttu-id="e1d36-109"><<<<<<< 头</span><span class="sxs-lookup"><span data-stu-id="e1d36-109"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="e1d36-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e1d36-110">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="e1d36-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e1d36-111">Return value</span></span>
>>>>>>> <span data-ttu-id="e1d36-112">母版</span><span class="sxs-lookup"><span data-stu-id="e1d36-112">master</span></span>

<span data-ttu-id="e1d36-113">返回 [EditModeEnum](editmodeenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="e1d36-113">Returns an [EditModeEnum](editmodeenum.md) value.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1d36-114">备注</span><span class="sxs-lookup"><span data-stu-id="e1d36-114">Remarks</span></span>

<span data-ttu-id="e1d36-p101">ADO 维护着一个与当前记录关联的编辑缓冲区。此属性指示是否对此缓冲区进行了更改，或是否创建了新记录。通过使用 **EditMode** 属性，可以确定当前记录的编辑状态。如果编辑进程已中断，可以检测是否存在待定更改，并确定是否需要使用 [Update](update-method-ado.md) 或 [CancelUpdate](cancelupdate-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e1d36-p101">ADO maintains an editing buffer associated with the current record. This property indicates whether changes have been made to this buffer, or whether a new record has been created. Use the **EditMode** property to determine the editing status of the current record. You can test for pending changes if an editing process has been interrupted and determine whether you need to use the [Update](update-method-ado.md) or [CancelUpdate](cancelupdate-method-ado.md) method.</span></span>

<span data-ttu-id="e1d36-119">有关 [EditMode](addnew-method-ado.md) 属性在各种不同编辑情况下的更为详细的说明，请参阅 **AddNew** 方法。</span><span class="sxs-lookup"><span data-stu-id="e1d36-119">See the [AddNew](addnew-method-ado.md) method for a more detailed description of the **EditMode** property under different editing conditions.</span></span>

<span data-ttu-id="e1d36-120">[删除](delete-method-ado-recordset.md)呼叫不会成功删除记录或[Recordset](recordset-object-ado.md) （由于参照完整性冲突，例如），源中数据的记录时仍处于编辑模式 (**EditMode** = **adEditInProgress**).</span><span class="sxs-lookup"><span data-stu-id="e1d36-120">When a call to [Delete](delete-method-ado-recordset.md) does not successfully delete the record or records in the data source (due to referential integrity violations, for example), the [Recordset](recordset-object-ado.md) will remain in edit mode (**EditMode** = **adEditInProgress**).</span></span> <span data-ttu-id="e1d36-121">这意味着在从当前记录移动到别的位置（例如，使用 **Move**、[NextRecordset](move-method-ado.md) 或 [Close](nextrecordset-method-ado.md)）前，必须调用 [CancelUpdate](close-method-ado.md) 。</span><span class="sxs-lookup"><span data-stu-id="e1d36-121">This means that **CancelUpdate** must be called before moving off the current record (with [Move](move-method-ado.md), [NextRecordset](nextrecordset-method-ado.md), or [Close](close-method-ado.md), for example).</span></span>


> [!NOTE]
> <span data-ttu-id="e1d36-p103">[!注释] **EditMode** 仅在存在当前记录时才能返回有效值。如果 **BOF 或 EOF** 为 True 或当前记录已删除， [EditMode](bof-eof-properties-ado.md) 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="e1d36-p103">**EditMode** can return a valid value only if there is a current record. **EditMode** will return an error if [BOF or EOF](bof-eof-properties-ado.md) is true, or if the current record has been deleted.</span></span>


