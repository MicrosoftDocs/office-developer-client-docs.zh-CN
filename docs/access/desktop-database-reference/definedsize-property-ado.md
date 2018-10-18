---
<span data-ttu-id="1dd49-101"><<<<<<< 标头标题： DefinedSize 属性 (ADO) TOCTitle: DefinedSize 属性 (ADO) === 标题： DefinedSize 属性 (ADO) TOCTitle: DefinedSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="1dd49-101"><<<<<<< HEAD title: DefinedSize Property (ADO) TOCTitle: DefinedSize Property (ADO) ======= title: DefinedSize property (ADO) TOCTitle: DefinedSize property (ADO)</span></span>
>>>>>>> <span data-ttu-id="1dd49-102">母版页 ms:assetid: 8d6db4c9-fbdc-9fcd-63f0-bd677c5ebcf6 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249619(v=office.15) ms:contentKeyID: 48546257 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="1dd49-102">master ms:assetid: 8d6db4c9-fbdc-9fcd-63f0-bd677c5ebcf6 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249619(v=office.15) ms:contentKeyID: 48546257 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="1dd49-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="1dd49-103"><<<<<<< HEAD</span></span>
# <a name="definedsize-property-ado"></a><span data-ttu-id="1dd49-104">DefinedSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="1dd49-104">DefinedSize Property (ADO)</span></span>
=======
# <a name="definedsize-property-ado"></a><span data-ttu-id="1dd49-105">DefinedSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="1dd49-105">DefinedSize property (ADO)</span></span>
>>>>>>> <span data-ttu-id="1dd49-106">master</span><span class="sxs-lookup"><span data-stu-id="1dd49-106">master</span></span>


<span data-ttu-id="1dd49-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1dd49-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1dd49-108">指示 [Field](field-object-ado.md) 对象的数据容量。</span><span class="sxs-lookup"><span data-stu-id="1dd49-108">Indicates the data capacity of a [Field](field-object-ado.md) object.</span></span>

<span data-ttu-id="1dd49-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="1dd49-109"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="1dd49-110">返回值</span><span class="sxs-lookup"><span data-stu-id="1dd49-110">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="1dd49-111">返回值</span><span class="sxs-lookup"><span data-stu-id="1dd49-111">Return value</span></span>
>>>>>>> <span data-ttu-id="1dd49-112">master</span><span class="sxs-lookup"><span data-stu-id="1dd49-112">master</span></span>

<span data-ttu-id="1dd49-113">返回一个 **Long** 值，该值以字节数反映字段的定义大小。</span><span class="sxs-lookup"><span data-stu-id="1dd49-113">Returns a **Long** value that reflects the defined size of a field as a number of bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="1dd49-114">备注</span><span class="sxs-lookup"><span data-stu-id="1dd49-114">Remarks</span></span>

<span data-ttu-id="1dd49-115">使用 **DefinedSize** 属性可以确定 **Field** 对象的数据容量。</span><span class="sxs-lookup"><span data-stu-id="1dd49-115">Use the **DefinedSize** property to determine the data capacity of a **Field** object.</span></span>

<span data-ttu-id="1dd49-p101">**DefinedSize** 和 [ActualSize](actualsize-property-ado.md) 属性不同。例如，假如声明类型为 **adVarChar** 且 **DefinedSize** 属性值为 50 的 **Field** 对象中只包含了一个字符。其返回的 **ActualSize** 属性值为单个字符所占的字节长度。</span><span class="sxs-lookup"><span data-stu-id="1dd49-p101">The **DefinedSize** and [ActualSize](actualsize-property-ado.md) properties are different. For example, consider a **Field** object with a declared type of **adVarChar** and a **DefinedSize** property value of 50, containing a single character. The **ActualSize** property value it returns is the length in bytes of the single character.</span></span>

