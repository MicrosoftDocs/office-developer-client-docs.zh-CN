---
<span data-ttu-id="a241f-101"><<<<<<< 标头标题： Count 属性 (ADO) TOCTitle: Count 属性 (ADO) === 标题： Count 属性 (ADO) TOCTitle: Count 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a241f-101"><<<<<<< HEAD title: Count Property (ADO) TOCTitle: Count Property (ADO) ======= title: Count property (ADO) TOCTitle: Count property (ADO)</span></span>
>>>>>>> <span data-ttu-id="a241f-102">母版页 ms:assetid: b59f9581-ffd1-471d-44fa-3c1bb812e140 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249871(v=office.15) ms:contentKeyID: 48547253 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="a241f-102">master ms:assetid: b59f9581-ffd1-471d-44fa-3c1bb812e140 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249871(v=office.15) ms:contentKeyID: 48547253 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="a241f-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a241f-103"><<<<<<< HEAD</span></span>
# <a name="count-property-ado"></a><span data-ttu-id="a241f-104">Count 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a241f-104">Count Property (ADO)</span></span>
=======
# <a name="count-property-ado"></a><span data-ttu-id="a241f-105">Count 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a241f-105">Count property (ADO)</span></span>
>>>>>>> <span data-ttu-id="a241f-106">master</span><span class="sxs-lookup"><span data-stu-id="a241f-106">master</span></span>


<span data-ttu-id="a241f-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a241f-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a241f-108">指示集合中的对象数。</span><span class="sxs-lookup"><span data-stu-id="a241f-108">Indicates the number of objects in a collection.</span></span>

<span data-ttu-id="a241f-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a241f-109"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="a241f-110">返回值</span><span class="sxs-lookup"><span data-stu-id="a241f-110">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="a241f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a241f-111">Return value</span></span>
>>>>>>> <span data-ttu-id="a241f-112">master</span><span class="sxs-lookup"><span data-stu-id="a241f-112">master</span></span>

<span data-ttu-id="a241f-113">返回 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="a241f-113">Returns a **Long** value.</span></span>

## <a name="remarks"></a><span data-ttu-id="a241f-114">备注</span><span class="sxs-lookup"><span data-stu-id="a241f-114">Remarks</span></span>

<span data-ttu-id="a241f-115">使用 **Count** 属性可确定在给定集合中有多少个对象。</span><span class="sxs-lookup"><span data-stu-id="a241f-115">Use the **Count** property to determine how many objects are in a given collection.</span></span>

<span data-ttu-id="a241f-p101">由于集合中的成员是从零开始进行编号的，因此应始终将循环编写为从第零个成员开始，而在 **Count** 属性的值减 1 处终止。如果在使用 Microsoft Visual Basic，而希望在不检查 **Count** 属性的情况下遍历集合的成员，则请使用 **For** **Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="a241f-p101">Because numbering for members of a collection begins with zero, you should always code loops starting with the zero member and ending with the value of the **Count** property minus 1. If you are using Microsoft Visual Basic and want to loop through the members of a collection without checking the **Count** property, use the **For** **Each...Next** command.</span></span>

<span data-ttu-id="a241f-118">如果 **Count** 属性为零，则表明集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="a241f-118">If the **Count** property is zero, there are no objects in the collection.</span></span>

