---
<span data-ttu-id="b7a05-101"><<<<<<< 标头标题： PageCount 属性 (ADO) TOCTitle: PageCount 属性 (ADO) === 标题： PageCount 属性 (ADO) TOCTitle: PageCount 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b7a05-101"><<<<<<< HEAD title: PageCount Property (ADO) TOCTitle: PageCount Property (ADO) ======= title: PageCount property (ADO) TOCTitle: PageCount property (ADO)</span></span>
>>>>>>> <span data-ttu-id="b7a05-102">母版页 ms:assetid: 9cd8bf5c-b1e7-a453-4629-9cba7e408f53 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249712(v=office.15) ms:contentKeyID: 48546609 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="b7a05-102">master ms:assetid: 9cd8bf5c-b1e7-a453-4629-9cba7e408f53 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249712(v=office.15) ms:contentKeyID: 48546609 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="b7a05-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="b7a05-103"><<<<<<< HEAD</span></span>
# <a name="pagecount-property-ado"></a><span data-ttu-id="b7a05-104">PageCount 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b7a05-104">PageCount Property (ADO)</span></span>
=======
# <a name="pagecount-property-ado"></a><span data-ttu-id="b7a05-105">PageCount 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b7a05-105">PageCount property (ADO)</span></span>
>>>>>>> <span data-ttu-id="b7a05-106">master</span><span class="sxs-lookup"><span data-stu-id="b7a05-106">master</span></span>


<span data-ttu-id="b7a05-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b7a05-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b7a05-108">指示 [Recordset](recordset-object-ado.md) 对象包含的数据页数。</span><span class="sxs-lookup"><span data-stu-id="b7a05-108">Indicates how many pages of data the [Recordset](recordset-object-ado.md) object contains.</span></span>

<span data-ttu-id="b7a05-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="b7a05-109"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="b7a05-110">返回值</span><span class="sxs-lookup"><span data-stu-id="b7a05-110">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="b7a05-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b7a05-111">Return value</span></span>
>>>>>>> <span data-ttu-id="b7a05-112">master</span><span class="sxs-lookup"><span data-stu-id="b7a05-112">master</span></span>

<span data-ttu-id="b7a05-113">返回一个 **Long** 值，指示 **Recordset** 中的页数。</span><span class="sxs-lookup"><span data-stu-id="b7a05-113">Returns a **Long** value that indicates the number of pages in the **Recordset**.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7a05-114">备注</span><span class="sxs-lookup"><span data-stu-id="b7a05-114">Remarks</span></span>

<span data-ttu-id="b7a05-115">使用 **PageCount** 属性可确定 **Recordset** 对象中的数据页数。</span><span class="sxs-lookup"><span data-stu-id="b7a05-115">Use the **PageCount** property to determine how many pages of data are in the **Recordset** object.</span></span> <span data-ttu-id="b7a05-116">*页面*是其大小等于[PageSize](pagesize-property-ado.md)属性设置的记录组。</span><span class="sxs-lookup"><span data-stu-id="b7a05-116">*Pages* are groups of records whose size equals the [PageSize](pagesize-property-ado.md) property setting.</span></span> <span data-ttu-id="b7a05-117">即使最后一页由于记录数小于 **PageSize** 值而无法组成完整的一页，也仍将其算作 **PageCount** 值中的附加页。</span><span class="sxs-lookup"><span data-stu-id="b7a05-117">Even if the last page is incomplete because there are fewer records than the **PageSize** value, it counts as an additional page in the **PageCount** value.</span></span> <span data-ttu-id="b7a05-118">如果 **Recordset** 对象不支持此属性，则该值为 -1，指示 **PageCount** 不可确定。</span><span class="sxs-lookup"><span data-stu-id="b7a05-118">If the **Recordset** object does not support this property, the value will be -1 to indicate that the **PageCount** is indeterminable.</span></span>

<span data-ttu-id="b7a05-119">有关页功能的详细信息，请参阅 **PageSize** 和 [AbsolutePage](absolutepage-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="b7a05-119">See the **PageSize** and [AbsolutePage](absolutepage-property-ado.md) properties for more on page functionality.</span></span>

