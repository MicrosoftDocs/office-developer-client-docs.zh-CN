---
<span data-ttu-id="5ebd0-101"><<<<<<< 标头标题： 章属性 (ADO) TOCTitle： 章属性 (ADO) === 标题： Chapter 属性 (ADO) TOCTitle: Chapter 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5ebd0-101"><<<<<<< HEAD title: Chapter Property (ADO) TOCTitle: Chapter Property (ADO) ======= title: Chapter property (ADO) TOCTitle: Chapter property (ADO)</span></span>
>>>>>>> <span data-ttu-id="5ebd0-102">母版页 ms:assetid: d7c9478e-487f-7023-1dd8-5313433dbc5e ms:mtpsurl: https://msdn.microsoft.com/library/JJ250085(v=office.15) ms:contentKeyID: 48548014 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="5ebd0-102">master ms:assetid: d7c9478e-487f-7023-1dd8-5313433dbc5e ms:mtpsurl: https://msdn.microsoft.com/library/JJ250085(v=office.15) ms:contentKeyID: 48548014 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="5ebd0-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="5ebd0-103"><<<<<<< HEAD</span></span>
# <a name="chapter-property-ado"></a><span data-ttu-id="5ebd0-104">Chapter 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5ebd0-104">Chapter Property (ADO)</span></span>
=======
# <a name="chapter-property-ado"></a><span data-ttu-id="5ebd0-105">Chapter 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5ebd0-105">Chapter property (ADO)</span></span>
>>>>>>> <span data-ttu-id="5ebd0-106">master</span><span class="sxs-lookup"><span data-stu-id="5ebd0-106">master</span></span>


<span data-ttu-id="5ebd0-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5ebd0-107">**Applies to**: Access 2013 | Office 2013</span></span>
 

<span data-ttu-id="5ebd0-108">从 **ADORecordsetConstruction** 对象获取（或对它设置）OLE DB **Chapter** 对象。</span><span class="sxs-lookup"><span data-stu-id="5ebd0-108">Gets or sets an OLE DB **Chapter** object from/on an **ADORecordsetConstruction** object.</span></span> <span data-ttu-id="5ebd0-109">当您使用**放置\_章**设置**Chapter**对象，行的子集处于到 ADO **Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="5ebd0-109">When you use **put\_Chapter** to set the **Chapter** object, a subset of rows is turned into an ADO **Recordset** object.</span></span> <span data-ttu-id="5ebd0-110">这将设置**Rowset**对象的当前一章。</span><span class="sxs-lookup"><span data-stu-id="5ebd0-110">This sets the current chapter of the **Rowset** object.</span></span> <span data-ttu-id="5ebd0-111">为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="5ebd0-111">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ebd0-112">语法</span><span class="sxs-lookup"><span data-stu-id="5ebd0-112">Syntax</span></span>

<span data-ttu-id="5ebd0-113">HRESULT get\_章 (\[out，retval\]长\*plChapter);</span><span class="sxs-lookup"><span data-stu-id="5ebd0-113">HRESULT get\_Chapter(\[out, retval\] long\* plChapter);</span></span>

<span data-ttu-id="5ebd0-114">HRESULT 放置\_章 (\[的\]长 lChapter);</span><span class="sxs-lookup"><span data-stu-id="5ebd0-114">HRESULT put\_Chapter(\[in\] long lChapter);</span></span>

## <a name="parameters"></a><span data-ttu-id="5ebd0-115">参数</span><span class="sxs-lookup"><span data-stu-id="5ebd0-115">Parameters</span></span>

  - <span data-ttu-id="5ebd0-116">*plChapter*</span><span class="sxs-lookup"><span data-stu-id="5ebd0-116">*plChapter*</span></span>

  - <span data-ttu-id="5ebd0-117">指向子集的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="5ebd0-117">Pointer to the handle of a chapter.</span></span>

  - <span data-ttu-id="5ebd0-118">*LChapter*</span><span class="sxs-lookup"><span data-stu-id="5ebd0-118">*LChapter*</span></span>

  - <span data-ttu-id="5ebd0-119">子集的句柄。</span><span class="sxs-lookup"><span data-stu-id="5ebd0-119">Handle of a chapter.</span></span>

<span data-ttu-id="5ebd0-120"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="5ebd0-120"><<<<<<< HEAD</span></span>
## <a name="return-values"></a><span data-ttu-id="5ebd0-121">返回值</span><span class="sxs-lookup"><span data-stu-id="5ebd0-121">Return Values</span></span>
=======
## <a name="return-values"></a><span data-ttu-id="5ebd0-122">返回值</span><span class="sxs-lookup"><span data-stu-id="5ebd0-122">Return values</span></span>
>>>>>>> <span data-ttu-id="5ebd0-123">master</span><span class="sxs-lookup"><span data-stu-id="5ebd0-123">master</span></span>

<span data-ttu-id="5ebd0-124">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="5ebd0-124">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="5ebd0-125">应用于</span><span class="sxs-lookup"><span data-stu-id="5ebd0-125">Applies To</span></span>

[<span data-ttu-id="5ebd0-126">ADORecordsetConstruction</span><span class="sxs-lookup"><span data-stu-id="5ebd0-126">ADORecordsetConstruction</span></span>](adorecordsetconstruction-interface-ado.md)

