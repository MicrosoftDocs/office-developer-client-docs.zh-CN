---
<span data-ttu-id="cfc18-101"><<<<<<< 标头标题： UnderlyingValue 属性 (ADO) TOCTitle: UnderlyingValue 属性 (ADO) === 标题： UnderlyingValue 属性 (ADO) TOCTitle: UnderlyingValue 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cfc18-101"><<<<<<< HEAD title: UnderlyingValue Property (ADO) TOCTitle: UnderlyingValue Property (ADO) ======= title: UnderlyingValue property (ADO) TOCTitle: UnderlyingValue property (ADO)</span></span>
>>>>>>> <span data-ttu-id="cfc18-102">母版页 ms:assetid: f84f4c1c-2bd4-a725-3575-ed063ead13c8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250262(v=office.15) ms:contentKeyID: 48548782 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="cfc18-102">master ms:assetid: f84f4c1c-2bd4-a725-3575-ed063ead13c8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250262(v=office.15) ms:contentKeyID: 48548782 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="cfc18-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="cfc18-103"><<<<<<< HEAD</span></span>
# <a name="underlyingvalue-property-ado"></a><span data-ttu-id="cfc18-104">UnderlyingValue 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cfc18-104">UnderlyingValue Property (ADO)</span></span>
=======
# <a name="underlyingvalue-property-ado"></a><span data-ttu-id="cfc18-105">UnderlyingValue 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cfc18-105">UnderlyingValue property (ADO)</span></span>
>>>>>>> <span data-ttu-id="cfc18-106">master</span><span class="sxs-lookup"><span data-stu-id="cfc18-106">master</span></span>


<span data-ttu-id="cfc18-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cfc18-107">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="cfc18-108">指示数据库中 [Field](field-object-ado.md) 对象的当前值。</span><span class="sxs-lookup"><span data-stu-id="cfc18-108">Indicates a [Field](field-object-ado.md) object's current value in the database.</span></span>

<span data-ttu-id="cfc18-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="cfc18-109"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="cfc18-110">返回值</span><span class="sxs-lookup"><span data-stu-id="cfc18-110">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="cfc18-111">返回值</span><span class="sxs-lookup"><span data-stu-id="cfc18-111">Return value</span></span>
>>>>>>> <span data-ttu-id="cfc18-112">master</span><span class="sxs-lookup"><span data-stu-id="cfc18-112">master</span></span>

<span data-ttu-id="cfc18-113">返回一个指示 **Field** 的值的 **Variant** 值。</span><span class="sxs-lookup"><span data-stu-id="cfc18-113">Returns a **Variant** value that indicates the value of the **Field**.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfc18-114">备注</span><span class="sxs-lookup"><span data-stu-id="cfc18-114">Remarks</span></span>

<span data-ttu-id="cfc18-p101">使用 **UnderlyingValue** 属性可以返回数据库中的当前字段的值。 **UnderlyingValue** 属性中的字段值是事务可见的值，而且可能是其他事务所进行的最近更新的结果。此值可能不同于 [OriginalValue](originalvalue-property-ado.md) 属性，后者反映的是最初返回到 [Recordset](recordset-object-ado.md) 的值。</span><span class="sxs-lookup"><span data-stu-id="cfc18-p101">Use the **UnderlyingValue** property to return the current field value from the database. The field value in the **UnderlyingValue** property is the value that is visible to your transaction and may be the result of a recent update by another transaction. This may differ from the [OriginalValue](originalvalue-property-ado.md) property, which reflects the value that was originally returned to the [Recordset](recordset-object-ado.md).</span></span>

<span data-ttu-id="cfc18-p102">这类似于使用 [Resync](resync-method-ado.md) 方法，但是 **UnderlyingValue** 属性仅返回当前记录中的特定字段的值。该值与 [Resync](resync-method-ado.md) 方法用于替换 [Value](value-property-ado.md) 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="cfc18-p102">This is similar to using the [Resync](resync-method-ado.md) method, but the **UnderlyingValue** property returns only the value for a specific field from the current record. This is the same value that the [Resync](resync-method-ado.md) method uses to replace the [Value](value-property-ado.md) property.</span></span>

<span data-ttu-id="cfc18-120">将此属性与 **OriginalValue** 属性结合使用时，可以解决因批更新而引发的冲突。</span><span class="sxs-lookup"><span data-stu-id="cfc18-120">When you use this property with the **OriginalValue** property, you can resolve conflicts that arise from batch updates.</span></span>

## <a name="record"></a><span data-ttu-id="cfc18-121">Record</span><span class="sxs-lookup"><span data-stu-id="cfc18-121">Record</span></span>

<span data-ttu-id="cfc18-122">对于调用 [Update](record-object-ado.md) 之前添加的字段，此属性将为空（适用于 [Record](update-method-ado.md) 对象）。</span><span class="sxs-lookup"><span data-stu-id="cfc18-122">For [Record](record-object-ado.md) objects, this property will be empty for fields added before [Update](update-method-ado.md) is called.</span></span>

