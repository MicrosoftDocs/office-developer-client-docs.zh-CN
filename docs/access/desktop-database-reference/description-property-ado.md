---
<span data-ttu-id="cbada-101"><<<<<<< 标头标题： 说明属性 (ADO) TOCTitle： 说明属性 (ADO) === 标题： Description 属性 (ADO) TOCTitle: Description 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cbada-101"><<<<<<< HEAD title: Description Property (ADO) TOCTitle: Description Property (ADO) ======= title: Description property (ADO) TOCTitle: Description property (ADO)</span></span>
>>>>>>> <span data-ttu-id="cbada-102">母版页 ms:assetid: 31df5e36-641c-d213-31fc-6244e2983327 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249092(v=office.15) ms:contentKeyID: 48544064 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="cbada-102">master ms:assetid: 31df5e36-641c-d213-31fc-6244e2983327 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249092(v=office.15) ms:contentKeyID: 48544064 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="cbada-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="cbada-103"><<<<<<< HEAD</span></span>
# <a name="description-property-ado"></a><span data-ttu-id="cbada-104">Description 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cbada-104">Description Property (ADO)</span></span>
=======
# <a name="description-property-ado"></a><span data-ttu-id="cbada-105">Description 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cbada-105">Description property (ADO)</span></span>
>>>>>>> <span data-ttu-id="cbada-106">master</span><span class="sxs-lookup"><span data-stu-id="cbada-106">master</span></span>


<span data-ttu-id="cbada-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cbada-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cbada-108">描述 [Error](error-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="cbada-108">Describes an [Error](error-object-ado.md) object.</span></span>

<span data-ttu-id="cbada-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="cbada-109"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="cbada-110">返回值</span><span class="sxs-lookup"><span data-stu-id="cbada-110">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="cbada-111">返回值</span><span class="sxs-lookup"><span data-stu-id="cbada-111">Return value</span></span>
>>>>>>> <span data-ttu-id="cbada-112">master</span><span class="sxs-lookup"><span data-stu-id="cbada-112">master</span></span>

<span data-ttu-id="cbada-113">返回一个包含错误说明的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="cbada-113">Returns a **String** value that contains a description of the error.</span></span>

## <a name="remarks"></a><span data-ttu-id="cbada-114">备注</span><span class="sxs-lookup"><span data-stu-id="cbada-114">Remarks</span></span>

<span data-ttu-id="cbada-p101">使用 **Description** 属性可以获得错误的简短说明。对于无法处理或不希望处理的错误，可以显示此属性来向用户发出警告。该字符串将来自 ADO 或提供程序。</span><span class="sxs-lookup"><span data-stu-id="cbada-p101">Use the **Description** property to obtain a short description of the error. Display this property to alert the user to an error that you cannot or do not want to handle. The string will come from either ADO or a provider.</span></span>

<span data-ttu-id="cbada-p102">提供程序负责向 ADO 传递具体的错误文本。对于收到的每个提供程序错误或警告，ADO 都会向 [Errors](error-object-ado.md) 集合添加一个 **Error** 对象。通过枚举 **Errors** 集合，可以跟踪提供程序所传递的错误。</span><span class="sxs-lookup"><span data-stu-id="cbada-p102">Providers are responsible for passing specific error text to ADO. ADO adds an [Error](error-object-ado.md) object to the **Errors** collection for each provider error or warning it receives. Enumerate the **Errors** collection to trace the errors that the provider passes.</span></span>

