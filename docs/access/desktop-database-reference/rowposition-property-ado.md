---
<span data-ttu-id="bc55c-101"><<<<<<< 标头标题： RowPosition 属性 (ADO) TOCTitle: RowPosition 属性 (ADO) === 标题： RowPosition 属性 (ADO) TOCTitle: RowPosition 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bc55c-101"><<<<<<< HEAD title: RowPosition Property (ADO) TOCTitle: RowPosition Property (ADO) ======= title: RowPosition property (ADO) TOCTitle: RowPosition property (ADO)</span></span>
>>>>>>> <span data-ttu-id="bc55c-102">母版页 ms:assetid: b87f14b0-136b-0564-3e12-f9d5ecc4f7c8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249887(v=office.15) ms:contentKeyID: 48547325 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="bc55c-102">master ms:assetid: b87f14b0-136b-0564-3e12-f9d5ecc4f7c8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249887(v=office.15) ms:contentKeyID: 48547325 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="bc55c-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="bc55c-103"><<<<<<< HEAD</span></span>
# <a name="rowposition-property-ado"></a><span data-ttu-id="bc55c-104">RowPosition 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bc55c-104">RowPosition Property (ADO)</span></span>
=======
# <a name="rowposition-property-ado"></a><span data-ttu-id="bc55c-105">RowPosition 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bc55c-105">RowPosition property (ADO)</span></span>
>>>>>>> <span data-ttu-id="bc55c-106">master</span><span class="sxs-lookup"><span data-stu-id="bc55c-106">master</span></span>


<span data-ttu-id="bc55c-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="bc55c-107">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="bc55c-108">通过 **ADORecordsetConstruction** 对象获取或设置一个 OLE DB **RowPosition** 对象。</span><span class="sxs-lookup"><span data-stu-id="bc55c-108">Gets or sets an OLE DB **RowPosition** object from/on an **ADORecordsetConstruction** object.</span></span> <span data-ttu-id="bc55c-109">当您使用**放置\_RowPosition**设置**RowPosition**对象，生成的**Recordset**对象使用**RowPosition**对象来确定当前行。</span><span class="sxs-lookup"><span data-stu-id="bc55c-109">When you use **put\_RowPosition** to set the **RowPosition** object, the resulting **Recordset** object uses the **RowPosition** object to determine the current row.</span></span>

<span data-ttu-id="bc55c-110">为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="bc55c-110">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="bc55c-111">语法</span><span class="sxs-lookup"><span data-stu-id="bc55c-111">Syntax</span></span>

<span data-ttu-id="bc55c-112">HRESULT get\_RowPosition (\[out，retval\] IUnknown\* \* ppRowPos);</span><span class="sxs-lookup"><span data-stu-id="bc55c-112">HRESULT get\_RowPosition(\[out, retval\] IUnknown\*\* ppRowPos);</span></span>

<span data-ttu-id="bc55c-113">HRESULT 放置\_RowPosition (\[的\]IUnknown\* pRowPos);</span><span class="sxs-lookup"><span data-stu-id="bc55c-113">HRESULT put\_RowPosition(\[in\] IUnknown\* pRowPos);</span></span>

## <a name="parameters"></a><span data-ttu-id="bc55c-114">参数</span><span class="sxs-lookup"><span data-stu-id="bc55c-114">Parameters</span></span>

  - <span data-ttu-id="bc55c-115">*ppRowPos*</span><span class="sxs-lookup"><span data-stu-id="bc55c-115">*ppRowPos*</span></span>

  - <span data-ttu-id="bc55c-116">指向 OLE DB **RowPosition** 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="bc55c-116">Pointer to an OLE DB **RowPosition** object.</span></span>

  - <span data-ttu-id="bc55c-117">*PRowPos*</span><span class="sxs-lookup"><span data-stu-id="bc55c-117">*PRowPos*</span></span>

  - <span data-ttu-id="bc55c-118">一个 OLE DB **RowPosition** 对象。</span><span class="sxs-lookup"><span data-stu-id="bc55c-118">An OLE DB **RowPosition** object.</span></span>

<span data-ttu-id="bc55c-119"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="bc55c-119"><<<<<<< HEAD</span></span>
## <a name="return-values"></a><span data-ttu-id="bc55c-120">返回值</span><span class="sxs-lookup"><span data-stu-id="bc55c-120">Return Values</span></span>
=======
## <a name="return-values"></a><span data-ttu-id="bc55c-121">返回值</span><span class="sxs-lookup"><span data-stu-id="bc55c-121">Return values</span></span>
>>>>>>> <span data-ttu-id="bc55c-122">master</span><span class="sxs-lookup"><span data-stu-id="bc55c-122">master</span></span>

<span data-ttu-id="bc55c-123">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="bc55c-123">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc55c-124">备注</span><span class="sxs-lookup"><span data-stu-id="bc55c-124">Remarks</span></span>

<span data-ttu-id="bc55c-p102">设置此属性时，如果 **RowPosition** 对象上的 **Rowset** 对象与 **Recordset** 对象上的 **Rowset** 对象不同，则前者将覆盖后者。 **RowPosition** 的当前 **Chapter** 也是如此。</span><span class="sxs-lookup"><span data-stu-id="bc55c-p102">When this property is set, if the **Rowset** object on the **RowPosition** object is different from the **Rowset** object on the **Recordset** object, the former overrides the latter. The same behavior applies to the current **Chapter** of the **RowPosition** as well.</span></span>

## <a name="applies-to"></a><span data-ttu-id="bc55c-127">应用于</span><span class="sxs-lookup"><span data-stu-id="bc55c-127">Applies To</span></span>

[<span data-ttu-id="bc55c-128">ADORecordsetConstruction</span><span class="sxs-lookup"><span data-stu-id="bc55c-128">ADORecordsetConstruction</span></span>](adorecordsetconstruction-interface-ado.md)

