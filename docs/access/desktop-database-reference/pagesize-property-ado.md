---
<span data-ttu-id="fea8e-101"><<<<<<< 标头标题： PageSize 属性 (ADO) TOCTitle: PageSize 属性 (ADO) === 标题： PageSize 属性 (ADO) TOCTitle: PageSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="fea8e-101"><<<<<<< HEAD title: PageSize Property (ADO) TOCTitle: PageSize Property (ADO) ======= title: PageSize property (ADO) TOCTitle: PageSize property (ADO)</span></span>
>>>>>>> <span data-ttu-id="fea8e-102">母版页 ms:assetid: da56edd8-8947-aeff-2ef5-a8535c66575b ms:mtpsurl: https://msdn.microsoft.com/library/JJ250099(v=office.15) ms:contentKeyID: 48548079 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="fea8e-102">master ms:assetid: da56edd8-8947-aeff-2ef5-a8535c66575b ms:mtpsurl: https://msdn.microsoft.com/library/JJ250099(v=office.15) ms:contentKeyID: 48548079 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="fea8e-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="fea8e-103"><<<<<<< HEAD</span></span>
# <a name="pagesize-property-ado"></a><span data-ttu-id="fea8e-104">PageSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="fea8e-104">PageSize Property (ADO)</span></span>
=======
# <a name="pagesize-property-ado"></a><span data-ttu-id="fea8e-105">PageSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="fea8e-105">PageSize property (ADO)</span></span>
>>>>>>> <span data-ttu-id="fea8e-106">master</span><span class="sxs-lookup"><span data-stu-id="fea8e-106">master</span></span>


<span data-ttu-id="fea8e-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="fea8e-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="fea8e-108">指示由多少记录构成 [Recordset](recordset-object-ado.md) 中的一页。</span><span class="sxs-lookup"><span data-stu-id="fea8e-108">Indicates how many records constitute one page in the [Recordset](recordset-object-ado.md).</span></span>

<span data-ttu-id="fea8e-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="fea8e-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="fea8e-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="fea8e-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="fea8e-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="fea8e-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="fea8e-112">master</span><span class="sxs-lookup"><span data-stu-id="fea8e-112">master</span></span>

<span data-ttu-id="fea8e-p101">设置或返回一个 **Long** 值，指示页上的记录数。默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="fea8e-p101">Sets or returns a **Long** value that indicates how many records are on a page. The default is 10.</span></span>

## <a name="remarks"></a><span data-ttu-id="fea8e-115">备注</span><span class="sxs-lookup"><span data-stu-id="fea8e-115">Remarks</span></span>

<span data-ttu-id="fea8e-116"><<<<<<< 标头**PageSize**属性用于确定多少记录构成数据逻辑页。</span><span class="sxs-lookup"><span data-stu-id="fea8e-116"><<<<<<< HEAD Use the **PageSize** property to determine how many records make up a logical page of data.</span></span> <span data-ttu-id="fea8e-117">建立页大小后就可以使用 [AbsolutePage](absolutepage-property-ado.md) 属性移至特定页的首条记录。</span><span class="sxs-lookup"><span data-stu-id="fea8e-117">Establishing a page size allows you to use the [AbsolutePage](absolutepage-property-ado.md) property to move to the first record of a particular page.</span></span> <span data-ttu-id="fea8e-118">在 Web 服务器方案中，若要允许用户分页浏览数据，每次查看特定数量的记录，该属性将非常有用。</span><span class="sxs-lookup"><span data-stu-id="fea8e-118">This is useful in Web server scenarios when you want to allow the user to page through data, viewing a certain number of records at a time.</span></span>
<span data-ttu-id="fea8e-119">=== **PageSize**属性用于确定多少记录构成数据逻辑页。</span><span class="sxs-lookup"><span data-stu-id="fea8e-119">======= Use the **PageSize** property to determine how many records make up a logical page of data.</span></span> <span data-ttu-id="fea8e-120">建立页大小允许您使用 [AbsolutePage](absolutepage-property-ado.md) 属性来移到特定页的第一个记录。</span><span class="sxs-lookup"><span data-stu-id="fea8e-120">Establishing a page size allows you to use the [AbsolutePage](absolutepage-property-ado.md) property to move to the first record of a particular page.</span></span> <span data-ttu-id="fea8e-121">当您希望允许逐页浏览数据，用户一次查看一定数量的记录时，这很有用在 web 服务器方案。</span><span class="sxs-lookup"><span data-stu-id="fea8e-121">This is useful in web server scenarios when you want to allow the user to page through data, viewing a certain number of records at a time.</span></span>
>>>>>>> <span data-ttu-id="fea8e-122">master</span><span class="sxs-lookup"><span data-stu-id="fea8e-122">master</span></span>

<span data-ttu-id="fea8e-123">可随时设置此属性，并将其值用于计算特定页的首条记录的位置。</span><span class="sxs-lookup"><span data-stu-id="fea8e-123">This property can be set at any time, and its value will be used for calculating the location of the first record of a particular page.</span></span>

