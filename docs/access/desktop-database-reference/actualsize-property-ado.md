---
<span data-ttu-id="e2793-101"><<<<<<< 标头标题： ActualSize 属性 (ADO) TOCTitle: ActualSize 属性 (ADO) ms:assetid: 020a414d-e6aa-5fb9-9b77-bd9d10124f8a ms:mtpsurl: https://msdn.microsoft.com/library/JJ248787(v=office.15) ms:contentKeyID: 48542949 ms.date: 09/18/2015 mtps_version: v =office.15</span><span class="sxs-lookup"><span data-stu-id="e2793-101"><<<<<<< HEAD title: ActualSize Property (ADO) TOCTitle: ActualSize Property (ADO) ms:assetid: 020a414d-e6aa-5fb9-9b77-bd9d10124f8a ms:mtpsurl: https://msdn.microsoft.com/library/JJ248787(v=office.15) ms:contentKeyID: 48542949 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

# <a name="actualsize-property-ado"></a><span data-ttu-id="e2793-102">ActualSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e2793-102">ActualSize Property (ADO)</span></span>
<span data-ttu-id="e2793-103">=== 标题： ActualSize 属性 (ADO) TOCTitle: ActualSize 属性 (ADO) ms:assetid: 020a414d-e6aa-5fb9-9b77-bd9d10124f8a ms:mtpsurl: https://msdn.microsoft.com/library/JJ248787(v=office.15) ms:contentKeyID: 48542949 ms.date: 10/16/2018 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="e2793-103">======= title: ActualSize property (ADO) TOCTitle: ActualSize property (ADO) ms:assetid: 020a414d-e6aa-5fb9-9b77-bd9d10124f8a ms:mtpsurl: https://msdn.microsoft.com/library/JJ248787(v=office.15) ms:contentKeyID: 48542949 ms.date: 10/16/2018 mtps_version: v=office.15</span></span>
---

# <a name="actualsize-property-ado"></a><span data-ttu-id="e2793-104">ActualSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e2793-104">ActualSize property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e2793-105">master</span><span class="sxs-lookup"><span data-stu-id="e2793-105">master</span></span>

<span data-ttu-id="e2793-106">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e2793-106">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e2793-107">指示字段值的实际长度。</span><span class="sxs-lookup"><span data-stu-id="e2793-107">Indicates the actual length of a field's value.</span></span>

<span data-ttu-id="e2793-108"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e2793-108"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="e2793-109">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="e2793-109">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="e2793-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="e2793-110">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="e2793-111">master</span><span class="sxs-lookup"><span data-stu-id="e2793-111">master</span></span>

<span data-ttu-id="e2793-p101">返回 **Long** 值。某些提供程序可能允许设置此属性来为 BLOB 数据保留空间，此时的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="e2793-p101">Returns a **Long** value. Some providers may allow this property to be set to reserve space for BLOB data, in which case the default value is 0.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2793-114">备注</span><span class="sxs-lookup"><span data-stu-id="e2793-114">Remarks</span></span>

<span data-ttu-id="e2793-p102">使用 **ActualSize** 属性可以返回 [Field](field-object-ado.md) 对象值的实际长度。对于所有字段， **ActualSize** 属性都是只读的。如果 ADO 无法确定 **Field** 对象值的长度， **ActualSize** 属性将返回 **adUnknown** 。</span><span class="sxs-lookup"><span data-stu-id="e2793-p102">Use the **ActualSize** property to return the actual length of a [Field](field-object-ado.md) object's value. For all fields, the **ActualSize** property is read-only. If ADO cannot determine the length of the **Field** object's value, the **ActualSize** property returns **adUnknown**.</span></span>

<span data-ttu-id="e2793-118"><<<<<<< 头**ActualSize**和[DefinedSize](definedsize-property-ado.md)属性会有所不同，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="e2793-118"><<<<<<< HEAD The **ActualSize** and [DefinedSize](definedsize-property-ado.md) properties are different, as shown in the following example.</span></span> <span data-ttu-id="e2793-119">声明的类型为 **adVarChar** 且最大长度为 50 个字符的 **Field** 对象返回的 **DefinedSize** 属性值为 50，但其返回的 **ActualSize** 属性值为存储在当前记录的字段中的数据的长度。</span><span class="sxs-lookup"><span data-stu-id="e2793-119">A **Field** object with a declared type of **adVarChar** and a maximum length of 50 characters returns a **DefinedSize** property value of 50, but the **ActualSize** property value it returns is the length of the data stored in the field for the current record.</span></span> <span data-ttu-id="e2793-120">**DefinedSize** 大于 255 个字节的 **Fields** 将作为可变长度列处理。</span><span class="sxs-lookup"><span data-stu-id="e2793-120">**Fields** with a **DefinedSize** greater than 255 bytes are treated as variable length columns.</span></span>
<span data-ttu-id="e2793-121">=== **ActualSize**和[DefinedSize](definedsize-property-ado.md)属性具有不同。</span><span class="sxs-lookup"><span data-stu-id="e2793-121">======= The **ActualSize** and [DefinedSize](definedsize-property-ado.md) properties are different.</span></span> <span data-ttu-id="e2793-122">声明的类型为 **adVarChar** 且最大长度为 50 个字符的 **Field** 对象返回的 **DefinedSize** 属性值为 50，但其返回的 **ActualSize** 属性值为存储在当前记录的字段中的数据的长度。</span><span class="sxs-lookup"><span data-stu-id="e2793-122">A **Field** object with a declared type of **adVarChar** and a maximum length of 50 characters returns a **DefinedSize** property value of 50, but the **ActualSize** property value it returns is the length of the data stored in the field for the current record.</span></span> <span data-ttu-id="e2793-123">**DefinedSize** 大于 255 个字节的 **Fields** 将作为可变长度列处理。</span><span class="sxs-lookup"><span data-stu-id="e2793-123">**Fields** with a **DefinedSize** greater than 255 bytes are treated as variable length columns.</span></span>
>>>>>>> <span data-ttu-id="e2793-124">master</span><span class="sxs-lookup"><span data-stu-id="e2793-124">master</span></span>

