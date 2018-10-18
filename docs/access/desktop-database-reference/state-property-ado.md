---
<span data-ttu-id="ee80c-101"><<<<<<< 标头标题： State 属性 (ADO) TOCTitle: State 属性 (ADO) === 标题： State 属性 (ADO) TOCTitle: State 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="ee80c-101"><<<<<<< HEAD title: State Property (ADO) TOCTitle: State Property (ADO) ======= title: State property (ADO) TOCTitle: State property (ADO)</span></span>
>>>>>>> <span data-ttu-id="ee80c-102">母版页 ms:assetid: ade0a50c-e2d8-23ac-4ea9-b012fedcd5db ms:mtpsurl: https://msdn.microsoft.com/library/JJ249819(v=office.15) ms:contentKeyID: 48547053 ms.date: 09/18/2015 mtps_version: office.15.aspx f1_keywords:</span><span class="sxs-lookup"><span data-stu-id="ee80c-102">master ms:assetid: ade0a50c-e2d8-23ac-4ea9-b012fedcd5db ms:mtpsurl: https://msdn.microsoft.com/library/JJ249819(v=office.15) ms:contentKeyID: 48547053 ms.date: 09/18/2015 mtps_version: v=office.15 f1_keywords:</span></span>
- <span data-ttu-id="ee80c-103">ado210.chm1231176 f1_categories:</span><span class="sxs-lookup"><span data-stu-id="ee80c-103">ado210.chm1231176 f1_categories:</span></span>
- <span data-ttu-id="ee80c-104">Office.Version=v15</span><span class="sxs-lookup"><span data-stu-id="ee80c-104">Office.Version=v15</span></span>
---

<span data-ttu-id="ee80c-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="ee80c-105"><<<<<<< HEAD</span></span>
# <a name="state-property-ado"></a><span data-ttu-id="ee80c-106">State 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="ee80c-106">State Property (ADO)</span></span>
=======
# <a name="state-property-ado"></a><span data-ttu-id="ee80c-107">State 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="ee80c-107">State property (ADO)</span></span>
>>>>>>> <span data-ttu-id="ee80c-108">master</span><span class="sxs-lookup"><span data-stu-id="ee80c-108">master</span></span>


<span data-ttu-id="ee80c-109">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ee80c-109">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ee80c-110">对所有适用的对象，指示其状态是打开还是关闭。</span><span class="sxs-lookup"><span data-stu-id="ee80c-110">Indicates for all applicable objects whether the state of the object is open or closed.</span></span>

<span data-ttu-id="ee80c-111">对执行异步方法的所有适用对象，指示其当前状态是正在连接、正在执行还是正在检索。</span><span class="sxs-lookup"><span data-stu-id="ee80c-111">Indicates for all applicable objects executing an asynchronous method, whether the current state of the object is connecting, executing, or retrieving.</span></span>

<span data-ttu-id="ee80c-112"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="ee80c-112"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="ee80c-113">返回值</span><span class="sxs-lookup"><span data-stu-id="ee80c-113">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="ee80c-114">返回值</span><span class="sxs-lookup"><span data-stu-id="ee80c-114">Return value</span></span>
>>>>>>> <span data-ttu-id="ee80c-115">master</span><span class="sxs-lookup"><span data-stu-id="ee80c-115">master</span></span>

<span data-ttu-id="ee80c-p101">返回一个 **Long** 值，该值可以为 [ObjectStateEnum](objectstateenum.md) 值之一。默认值是 **adStateClosed** 。</span><span class="sxs-lookup"><span data-stu-id="ee80c-p101">Returns a **Long** value that can be an [ObjectStateEnum](objectstateenum.md) value. The default value is **adStateClosed**.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee80c-118">备注</span><span class="sxs-lookup"><span data-stu-id="ee80c-118">Remarks</span></span>

<span data-ttu-id="ee80c-119">可以随时使用 **State** 属性确定给定对象的当前状态。</span><span class="sxs-lookup"><span data-stu-id="ee80c-119">You can use the **State** property to determine the current state of a given object at any time.</span></span>

<span data-ttu-id="ee80c-p102">对象的 **State** 属性可以是组合值。例如，如果正在执行某个语句，则此属性的值将为 **adStateOpen** 和 **adStateExecuting** 的组合值。</span><span class="sxs-lookup"><span data-stu-id="ee80c-p102">The object's **State** property can have a combination of values. For example, if a statement is executing, this property will have a combined value of **adStateOpen** and **adStateExecuting**.</span></span>

<span data-ttu-id="ee80c-122">**State** 为只读属性。</span><span class="sxs-lookup"><span data-stu-id="ee80c-122">The **State** property is read-only.</span></span>

