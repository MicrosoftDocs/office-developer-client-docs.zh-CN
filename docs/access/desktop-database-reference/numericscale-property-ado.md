---
<span data-ttu-id="07374-101"><<<<<<< 标头标题： NumericScale 属性 (ADO) TOCTitle: NumericScale 属性 (ADO) === 标题： NumericScale 属性 (ADO) TOCTitle: NumericScale 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="07374-101"><<<<<<< HEAD title: NumericScale Property (ADO) TOCTitle: NumericScale Property (ADO) ======= title: NumericScale property (ADO) TOCTitle: NumericScale property (ADO)</span></span>
>>>>>>> <span data-ttu-id="07374-102">母版页 ms:assetid: 51b232d2-5bfd-521c-f4e9-65655ecc7c70 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249263(v=office.15) ms:contentKeyID: 48544824 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="07374-102">master ms:assetid: 51b232d2-5bfd-521c-f4e9-65655ecc7c70 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249263(v=office.15) ms:contentKeyID: 48544824 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="07374-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="07374-103"><<<<<<< HEAD</span></span>
# <a name="numericscale-property-ado"></a><span data-ttu-id="07374-104">NumericScale 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="07374-104">NumericScale Property (ADO)</span></span>
=======
# <a name="numericscale-property-ado"></a><span data-ttu-id="07374-105">NumericScale 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="07374-105">NumericScale property (ADO)</span></span>
>>>>>>> <span data-ttu-id="07374-106">master</span><span class="sxs-lookup"><span data-stu-id="07374-106">master</span></span>


<span data-ttu-id="07374-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="07374-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="07374-108">指示 [Parameter](parameter-object-ado.md) 或 [Field](field-object-ado.md) 对象中数值的小数位数。</span><span class="sxs-lookup"><span data-stu-id="07374-108">Indicates the scale of numeric values in a [Parameter](parameter-object-ado.md) or [Field](field-object-ado.md) object.</span></span>

<span data-ttu-id="07374-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="07374-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="07374-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="07374-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="07374-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="07374-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="07374-112">master</span><span class="sxs-lookup"><span data-stu-id="07374-112">master</span></span>

<span data-ttu-id="07374-113">设置或返回一个 **Byte** 值，指示数值的小数位数。</span><span class="sxs-lookup"><span data-stu-id="07374-113">Sets or returns a **Byte** value that indicates the number of decimal places to which numeric values will be resolved.</span></span>

## <a name="remarks"></a><span data-ttu-id="07374-114">备注</span><span class="sxs-lookup"><span data-stu-id="07374-114">Remarks</span></span>

<span data-ttu-id="07374-115">使用 **NumericScale** 属性可确定将用于表示数字型 **Parameter** 或 **Field** 对象的小数点后的数字个数。</span><span class="sxs-lookup"><span data-stu-id="07374-115">Use the **NumericScale** property to determine how many digits to the right of the decimal point will be used to represent values for a numeric **Parameter** or **Field** object.</span></span>

<span data-ttu-id="07374-116">对于 **Parameter** 对象， **NumericScale** 属性为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="07374-116">For **Parameter** objects, the **NumericScale** property is read/write.</span></span>

<span data-ttu-id="07374-p101">对于 **Field** 对象， **NumericScale** 通常为只读。然而，对于已追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合的新 [Field](record-object-ado.md) 对象，只有在指定了 **Field** 的 [Value](value-property-ado.md) 属性并且数据提供程序已通过调用 **Fields** 集合的 **Update** 方法成功添加新 [Field](update-method-ado.md) 之后， **NumericScale** 才为可读/写。</span><span class="sxs-lookup"><span data-stu-id="07374-p101">For a **Field** object, **NumericScale** is normally read-only. However, for new **Field** objects that have been appended to the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md), **NumericScale** is read/write only after the [Value](value-property-ado.md) property for the **Field** has been specified and the data provider has successfully added the new **Field** by calling the [Update](update-method-ado.md) method of the **Fields** collection.</span></span>

