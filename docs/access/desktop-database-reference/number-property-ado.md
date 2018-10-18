---
<span data-ttu-id="89755-101"><<<<<<< 标头标题： 号码属性 (ADO) TOCTitle： 号码属性 (ADO) === 标题： Number 属性 (ADO) TOCTitle: Number 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="89755-101"><<<<<<< HEAD title: Number Property (ADO) TOCTitle: Number Property (ADO) ======= title: Number property (ADO) TOCTitle: Number property (ADO)</span></span>
>>>>>>> <span data-ttu-id="89755-102">母版页 ms:assetid: b5103af5-356b-ec74-cd62-86e59467d491 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249868(v=office.15) ms:contentKeyID: 48547243 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="89755-102">master ms:assetid: b5103af5-356b-ec74-cd62-86e59467d491 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249868(v=office.15) ms:contentKeyID: 48547243 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="89755-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="89755-103"><<<<<<< HEAD</span></span>
# <a name="number-property-ado"></a><span data-ttu-id="89755-104">Number 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="89755-104">Number Property (ADO)</span></span>
=======
# <a name="number-property-ado"></a><span data-ttu-id="89755-105">Number 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="89755-105">Number property (ADO)</span></span>
>>>>>>> <span data-ttu-id="89755-106">master</span><span class="sxs-lookup"><span data-stu-id="89755-106">master</span></span>


<span data-ttu-id="89755-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="89755-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="89755-108">指示用于唯一标识 [Error](error-object-ado.md) 对象的编号。</span><span class="sxs-lookup"><span data-stu-id="89755-108">Indicates the number that uniquely identifies an [Error](error-object-ado.md) object.</span></span>

<span data-ttu-id="89755-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="89755-109"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="89755-110">返回值</span><span class="sxs-lookup"><span data-stu-id="89755-110">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="89755-111">返回值</span><span class="sxs-lookup"><span data-stu-id="89755-111">Return value</span></span>
>>>>>>> <span data-ttu-id="89755-112">master</span><span class="sxs-lookup"><span data-stu-id="89755-112">master</span></span>

<span data-ttu-id="89755-113">返回一个 **Long** 值，该值与 [ErrorValueEnum](errorvalueenum.md) 中的一个常量对应。</span><span class="sxs-lookup"><span data-stu-id="89755-113">Returns a **Long** value that may correspond to one of the [ErrorValueEnum](errorvalueenum.md) constants.</span></span>

## <a name="remarks"></a><span data-ttu-id="89755-114">备注</span><span class="sxs-lookup"><span data-stu-id="89755-114">Remarks</span></span>

<span data-ttu-id="89755-p101">使用 **Number** 属性可确定发生了哪种错误。此属性的值是与错误条件对应的唯一数字。</span><span class="sxs-lookup"><span data-stu-id="89755-p101">Use the **Number** property to determine which error occurred. The value of the property is a unique number that corresponds to the error condition.</span></span>

<span data-ttu-id="89755-117">[Errors](errors-collection-ado.md) 集合返回一个 HRESULT，格式为十六进制（例如，0x80004005）或长整型值（例如，2147467259）。</span><span class="sxs-lookup"><span data-stu-id="89755-117">The [Errors](errors-collection-ado.md) collection returns an HRESULT in either hexadecimal format (for example, 0x80004005) or long value (for example, 2147467259).</span></span> <span data-ttu-id="89755-118">这些 HRESULT 可由基础组件引发，如 OLE DB，甚至 OLE 本身。</span><span class="sxs-lookup"><span data-stu-id="89755-118">These HRESULTs can be raised by underlying components, such as OLE DB or even OLE itself.</span></span> <span data-ttu-id="89755-119">有关这些号码的详细信息，请参阅第 16 章*OLE DB 程序员参考 （英文）。*</span><span class="sxs-lookup"><span data-stu-id="89755-119">For more information about these numbers, see Chapter 16 of the *OLE DB Programmer's Reference.*</span></span>

