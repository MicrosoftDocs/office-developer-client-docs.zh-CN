---
<span data-ttu-id="e5c6b-101"><<<<<<< 标头标题： Rowset 属性 (ADO) TOCTitle: Rowset 属性 (ADO) === 标题： Rowset 属性 (ADO) TOCTitle: Rowset 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e5c6b-101"><<<<<<< HEAD title: Rowset Property (ADO) TOCTitle: Rowset Property (ADO) ======= title: Rowset property (ADO) TOCTitle: Rowset property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e5c6b-102">母版页 ms:assetid: 1a1cb3ef-8f3c-30c1-3eb0-8618fdcacd53 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248946(v=office.15) ms:contentKeyID: 48543515 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="e5c6b-102">master ms:assetid: 1a1cb3ef-8f3c-30c1-3eb0-8618fdcacd53 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248946(v=office.15) ms:contentKeyID: 48543515 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="e5c6b-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e5c6b-103"><<<<<<< HEAD</span></span>
# <a name="rowset-property-ado"></a><span data-ttu-id="e5c6b-104">Rowset 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e5c6b-104">Rowset Property (ADO)</span></span>
=======
# <a name="rowset-property-ado"></a><span data-ttu-id="e5c6b-105">Rowset 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e5c6b-105">Rowset property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e5c6b-106">master</span><span class="sxs-lookup"><span data-stu-id="e5c6b-106">master</span></span>


<span data-ttu-id="e5c6b-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e5c6b-107">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="e5c6b-108">通过 **ADORecordsetConstruction** 对象获取或设置一个 OLE DB **Rowset** 对象。</span><span class="sxs-lookup"><span data-stu-id="e5c6b-108">Gets or sets an OLE DB **Rowset** object from/on an **ADORecordsetConstruction** object.</span></span> <span data-ttu-id="e5c6b-109">当您使用 put\_行集，行集转换为 ADO **Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="e5c6b-109">When you use put\_Rowset, the rowset is turned into an ADO **Recordset** object.</span></span>

<span data-ttu-id="e5c6b-110">为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="e5c6b-110">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="e5c6b-111">语法</span><span class="sxs-lookup"><span data-stu-id="e5c6b-111">Syntax</span></span>

<span data-ttu-id="e5c6b-112">HRESULT get\_行集 (\[out，retval\] IUnknown\* \* ppRowset);</span><span class="sxs-lookup"><span data-stu-id="e5c6b-112">HRESULT get\_Rowset(\[out, retval\] IUnknown\*\* ppRowset);</span></span>

<span data-ttu-id="e5c6b-113">HRESULT 放置\_行集 (\[的\]IUnknown\* pRowset);</span><span class="sxs-lookup"><span data-stu-id="e5c6b-113">HRESULT put\_Rowset(\[in\] IUnknown\* pRowset);</span></span>

## <a name="parameters"></a><span data-ttu-id="e5c6b-114">参数</span><span class="sxs-lookup"><span data-stu-id="e5c6b-114">Parameters</span></span>

  - <span data-ttu-id="e5c6b-115">*ppRowset*</span><span class="sxs-lookup"><span data-stu-id="e5c6b-115">*ppRowset*</span></span>

  - <span data-ttu-id="e5c6b-116">指向 OLE DB **Rowset** 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e5c6b-116">Pointer to an OLE DB **Rowset** object.</span></span>

  - <span data-ttu-id="e5c6b-117">*PRowset*</span><span class="sxs-lookup"><span data-stu-id="e5c6b-117">*PRowset*</span></span>

  - <span data-ttu-id="e5c6b-118">一个 OLE DB **Rowset** 对象。</span><span class="sxs-lookup"><span data-stu-id="e5c6b-118">An OLE DB **Rowset** object.</span></span>

<span data-ttu-id="e5c6b-119"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e5c6b-119"><<<<<<< HEAD</span></span>
## <a name="return-values"></a><span data-ttu-id="e5c6b-120">返回值</span><span class="sxs-lookup"><span data-stu-id="e5c6b-120">Return Values</span></span>
=======
## <a name="return-values"></a><span data-ttu-id="e5c6b-121">返回值</span><span class="sxs-lookup"><span data-stu-id="e5c6b-121">Return values</span></span>
>>>>>>> <span data-ttu-id="e5c6b-122">master</span><span class="sxs-lookup"><span data-stu-id="e5c6b-122">master</span></span>

<span data-ttu-id="e5c6b-123">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="e5c6b-123">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="e5c6b-124">应用于</span><span class="sxs-lookup"><span data-stu-id="e5c6b-124">Applies To</span></span>

[<span data-ttu-id="e5c6b-125">ADORecordsetConstruction</span><span class="sxs-lookup"><span data-stu-id="e5c6b-125">ADORecordsetConstruction</span></span>](adorecordsetconstruction-interface-ado.md)

