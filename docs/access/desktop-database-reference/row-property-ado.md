---
<span data-ttu-id="4fd21-101">标题： Row 属性-ActiveX 数据对象 (ADO) <<<<<<< 标头 TOCTitle： 行属性 (ADO) === TOCTitle： 行属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="4fd21-101">title: Row Property - ActiveX Data Objects (ADO) <<<<<<< HEAD TOCTitle: Row Property (ADO) ======= TOCTitle: Row property (ADO)</span></span>
>>>>>>> <span data-ttu-id="4fd21-102">母版页 ms:assetid: 1c2b0e27-7232-4b1c-826c-9dc15d758851 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248959(v=office.15) ms:contentKeyID: 48543562 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="4fd21-102">master ms:assetid: 1c2b0e27-7232-4b1c-826c-9dc15d758851 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248959(v=office.15) ms:contentKeyID: 48543562 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="4fd21-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="4fd21-103"><<<<<<< HEAD</span></span>
# <a name="row-property-ado"></a><span data-ttu-id="4fd21-104">Row 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="4fd21-104">Row Property (ADO)</span></span>
=======
# <a name="row-property-ado"></a><span data-ttu-id="4fd21-105">Row 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="4fd21-105">Row property (ADO)</span></span>
>>>>>>> <span data-ttu-id="4fd21-106">master</span><span class="sxs-lookup"><span data-stu-id="4fd21-106">master</span></span>


<span data-ttu-id="4fd21-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4fd21-107">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="4fd21-108">获取或设置 **ADORecordConstruction** 对象的 OLE DB **Row** 对象。</span><span class="sxs-lookup"><span data-stu-id="4fd21-108">Gets or sets an OLE DB **Row** object from/on an **ADORecordConstruction** object.</span></span> <span data-ttu-id="4fd21-109">当您使用**放置\_行**设置**Row**对象，行转换为 ADO **Record**对象。</span><span class="sxs-lookup"><span data-stu-id="4fd21-109">When you use **put\_Row** to set a **Row** object, a row is turned into an ADO **Record** object.</span></span> <span data-ttu-id="4fd21-110">为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="4fd21-110">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="4fd21-111">语法</span><span class="sxs-lookup"><span data-stu-id="4fd21-111">Syntax</span></span>

<span data-ttu-id="4fd21-112">HRESULT get\_行 (\[out，retval\] IUnknown\* \* ppRow);</span><span class="sxs-lookup"><span data-stu-id="4fd21-112">HRESULT get\_Row(\[out, retval\] IUnknown\*\* ppRow);</span></span>

<span data-ttu-id="4fd21-113">HRESULT 放置\_行 (\[的\]IUnknown\* pRow);</span><span class="sxs-lookup"><span data-stu-id="4fd21-113">HRESULT put\_Row(\[in\] IUnknown\* pRow);</span></span>

## <a name="parameters"></a><span data-ttu-id="4fd21-114">参数</span><span class="sxs-lookup"><span data-stu-id="4fd21-114">Parameters</span></span>

  - <span data-ttu-id="4fd21-115">*ppRow*</span><span class="sxs-lookup"><span data-stu-id="4fd21-115">*ppRow*</span></span>

  - <span data-ttu-id="4fd21-116">指向 OLE DB **Row** 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4fd21-116">Pointer to an OLE DB **Row** object.</span></span>

  - <span data-ttu-id="4fd21-117">*PRow*</span><span class="sxs-lookup"><span data-stu-id="4fd21-117">*PRow*</span></span>

  - <span data-ttu-id="4fd21-118">一个 OLE DB **Row** 对象。</span><span class="sxs-lookup"><span data-stu-id="4fd21-118">An OLE DB **Row** object.</span></span>

<span data-ttu-id="4fd21-119"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="4fd21-119"><<<<<<< HEAD</span></span>
## <a name="return-values"></a><span data-ttu-id="4fd21-120">返回值</span><span class="sxs-lookup"><span data-stu-id="4fd21-120">Return Values</span></span>
=======
## <a name="return-values"></a><span data-ttu-id="4fd21-121">返回值</span><span class="sxs-lookup"><span data-stu-id="4fd21-121">Return values</span></span>
>>>>>>> <span data-ttu-id="4fd21-122">master</span><span class="sxs-lookup"><span data-stu-id="4fd21-122">master</span></span>

<span data-ttu-id="4fd21-123">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="4fd21-123">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="4fd21-124">应用于</span><span class="sxs-lookup"><span data-stu-id="4fd21-124">Applies To</span></span>

[<span data-ttu-id="4fd21-125">ADORecordConstruction</span><span class="sxs-lookup"><span data-stu-id="4fd21-125">ADORecordConstruction</span></span>](adorecordconstruction-interface-ado.md)

