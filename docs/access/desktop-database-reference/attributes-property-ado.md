---
<span data-ttu-id="191f3-101"><<<<<<< 标头标题： 属性属性 (ADO) TOCTitle： 属性属性 (ADO) === 标题： 属性属性 (ADO) TOCTitle： 属性属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="191f3-101"><<<<<<< HEAD title: Attributes Property (ADO) TOCTitle: Attributes Property (ADO) ======= title: Attributes property (ADO) TOCTitle: Attributes property (ADO)</span></span>
>>>>>>> <span data-ttu-id="191f3-102">母版页 ms:assetid: 4cc1f036-606e-7d4b-d270-af374e9d99fa ms:mtpsurl: https://msdn.microsoft.com/library/JJ249242(v=office.15) ms:contentKeyID: 48544716 ms.date: 09/18/2015 mtps_version: office.15.aspx f1_keywords:</span><span class="sxs-lookup"><span data-stu-id="191f3-102">master ms:assetid: 4cc1f036-606e-7d4b-d270-af374e9d99fa ms:mtpsurl: https://msdn.microsoft.com/library/JJ249242(v=office.15) ms:contentKeyID: 48544716 ms.date: 09/18/2015 mtps_version: v=office.15 f1_keywords:</span></span>
- <span data-ttu-id="191f3-103">ado210.chm1231117 f1_categories:</span><span class="sxs-lookup"><span data-stu-id="191f3-103">ado210.chm1231117 f1_categories:</span></span>
- <span data-ttu-id="191f3-104">Office.Version=v15</span><span class="sxs-lookup"><span data-stu-id="191f3-104">Office.Version=v15</span></span>
---

<span data-ttu-id="191f3-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="191f3-105"><<<<<<< HEAD</span></span>
# <a name="attributes-property-ado"></a><span data-ttu-id="191f3-106">Attributes 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="191f3-106">Attributes Property (ADO)</span></span>
=======
# <a name="attributes-property-ado"></a><span data-ttu-id="191f3-107">Attributes 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="191f3-107">Attributes property (ADO)</span></span>
>>>>>>> <span data-ttu-id="191f3-108">master</span><span class="sxs-lookup"><span data-stu-id="191f3-108">master</span></span>


<span data-ttu-id="191f3-109">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="191f3-109">**Applies to**: Access 2013 | Office 2013</span></span>


## <a name="attributes-property"></a><span data-ttu-id="191f3-110">Attributes 属性</span><span class="sxs-lookup"><span data-stu-id="191f3-110">Attributes Property</span></span>

<span data-ttu-id="191f3-111">指示对象的一个或多个特征。</span><span class="sxs-lookup"><span data-stu-id="191f3-111">Indicates one or more characteristics of an object.</span></span>

<span data-ttu-id="191f3-112"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="191f3-112"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="191f3-113">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="191f3-113">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="191f3-114">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="191f3-114">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="191f3-115">master</span><span class="sxs-lookup"><span data-stu-id="191f3-115">master</span></span>

<span data-ttu-id="191f3-116">设置或返回 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="191f3-116">Sets or returns a **Long** value.</span></span>

<span data-ttu-id="191f3-p101">对于 [Connection](connection-object-ado.md) 对象， **Attributes** 属性为可读/写属性，其值可以为一个或多个 [XactAttributeEnum](xactattributeenum.md) 值的总和。默认值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="191f3-p101">For a [Connection](connection-object-ado.md) object, the **Attributes** property is read/write, and its value can be the sum of one or more [XactAttributeEnum](xactattributeenum.md) values. The default is zero (0).</span></span>

<span data-ttu-id="191f3-p102">对于 [Parameter](parameter-object-ado.md) 对象， **Attributes** 属性为可读/写属性，其值可以为任何一个或多个 [ParameterAttributesEnum](parameterattributesenum.md) 值的总和。默认值为 **adParamSigned** 。</span><span class="sxs-lookup"><span data-stu-id="191f3-p102">For a [Parameter](parameter-object-ado.md) object, the **Attributes** property is read/write, and its value can be the sum of any one or more [ParameterAttributesEnum](parameterattributesenum.md) values. The default is **adParamSigned**.</span></span>

<span data-ttu-id="191f3-p103">对于 [Field](field-object-ado.md) 对象， **Attributes** 属性可以为一个或多个 [FieldAttributeEnum](fieldattributeenum.md) 值的总和。该属性通常为只读属性。不过，对于追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合的新 [Field](record-object-ado.md) 对象，其 **Attributes** 属性仅在以下情况时为可读/写属性： [Field](value-property-ado.md) 的 **Value** 属性已指定，且新 **Field** 已由数据提供程序通过调用 [Fields](update-method-ado.md) 集合的 **Update** 方法成功添加。</span><span class="sxs-lookup"><span data-stu-id="191f3-p103">For a [Field](field-object-ado.md) object, the **Attributes** property can be the sum of one or more [FieldAttributeEnum](fieldattributeenum.md) values. It is normally read-only, However, for new **Field** objects that have been appended to the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md), **Attributes** is read/write only after the [Value](value-property-ado.md) property for the **Field** has been specified and the new **Field** has been successfully added by the data provider by calling the [Update](update-method-ado.md) method of the **Fields** collection.</span></span>

<span data-ttu-id="191f3-123">对于 [Property](property-object-ado.md) 对象， **Attributes** 属性为只读属性，其值可以为任何一个或多个 [PropertyAttributesEnum](propertyattributesenum.md) 值的总和。</span><span class="sxs-lookup"><span data-stu-id="191f3-123">For a [Property](property-object-ado.md) object, the **Attributes** property is read-only, and its value can be the sum of any one or more [PropertyAttributesEnum](propertyattributesenum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="191f3-124">备注</span><span class="sxs-lookup"><span data-stu-id="191f3-124">Remarks</span></span>

<span data-ttu-id="191f3-125">使用 **Attributes** 属性可以设置或返回 **Connection** 对象、 **Parameter** 对象、 [Field](field-object-ado.md) 对象或 [Property](property-object-ado.md) 对象的各种特征。</span><span class="sxs-lookup"><span data-stu-id="191f3-125">Use the **Attributes** property to set or return characteristics of **Connection** objects, **Parameter** objects, [Field](field-object-ado.md) objects, or [Property](property-object-ado.md) objects.</span></span>

<span data-ttu-id="191f3-p104">设置多个属性 (attribute) 时，可以对相应的常量求和。如果将属性 (property) 值设置为包含相互不兼容的常量的总和，则将发生错误。</span><span class="sxs-lookup"><span data-stu-id="191f3-p104">When you set multiple attributes, you can sum the appropriate constants. If you set the property value to a sum including incompatible constants, an error occurs.</span></span>

<span data-ttu-id="191f3-128">**远程数据服务用法**此属性不是在客户端**Connection**对象上可用。</span><span class="sxs-lookup"><span data-stu-id="191f3-128">**Remote Data Service Usage**This property is not available on a client-side **Connection** object.</span></span>

