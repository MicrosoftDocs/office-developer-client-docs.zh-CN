---
title: ITableDataHrQueryRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrQueryRow
api_type:
- COM
ms.assetid: 66ce8f36-2b2b-4a8e-b9b2-43782d8357a1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: da41fadc9a71a410dd115e28ce2cf9c81442b104
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434765"
---
# <a name="itabledatahrqueryrow"></a><span data-ttu-id="36f06-103">ITableData::HrQueryRow</span><span class="sxs-lookup"><span data-stu-id="36f06-103">ITableData::HrQueryRow</span></span>

  
  
<span data-ttu-id="36f06-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="36f06-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="36f06-105">检索表行。</span><span class="sxs-lookup"><span data-stu-id="36f06-105">Retrieves a table row.</span></span>
  
```cpp
HRESULT HrQueryRow(
  LPSPropValue lpSPropValue,
  LPSRow FAR * lppSRow,
  ULONG FAR * lpuliRow
);
```

## <a name="parameters"></a><span data-ttu-id="36f06-106">参数</span><span class="sxs-lookup"><span data-stu-id="36f06-106">Parameters</span></span>

 <span data-ttu-id="36f06-107">_lpSPropValue_</span><span class="sxs-lookup"><span data-stu-id="36f06-107">_lpSPropValue_</span></span>
  
> <span data-ttu-id="36f06-108">[in]指向描述要检索的行的索引列的属性值结构的指针。</span><span class="sxs-lookup"><span data-stu-id="36f06-108">[in] A pointer to a property value structure that describes the index column for the row to be retrieved.</span></span> <span data-ttu-id="36f06-109">属性值 **结构的 ulPropTag** 成员应包含与调用 [CreateTable](createtable.md)函数时 _ulPropTagIndexColumn_ 参数相同的属性标记，该函数访问 [ITableData](itabledataiunknown.md)实现。</span><span class="sxs-lookup"><span data-stu-id="36f06-109">The **ulPropTag** member of the property value structure should contain the same property tag as the  _ulPropTagIndexColumn_ parameter from the call to the [CreateTable](createtable.md) function, which accesses the [ITableData](itabledataiunknown.md) implementation.</span></span> 
    
 <span data-ttu-id="36f06-110">_lppSRow_</span><span class="sxs-lookup"><span data-stu-id="36f06-110">_lppSRow_</span></span>
  
> <span data-ttu-id="36f06-111">[out]指向检索到的行的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="36f06-111">[out] A pointer to a pointer to the retrieved row.</span></span> 
    
 <span data-ttu-id="36f06-112">_lp一Row_</span><span class="sxs-lookup"><span data-stu-id="36f06-112">_lpuliRow_</span></span>
  
> <span data-ttu-id="36f06-113">[in， out]输入时，表示无需返回任何信息的有效指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="36f06-113">[in, out] On input, a valid pointer or NULL, which indicates that no information needs to be returned.</span></span> <span data-ttu-id="36f06-114">在 output 上，指向行的行号的有效指针，一个标识行在表中位置的顺序编号。</span><span class="sxs-lookup"><span data-stu-id="36f06-114">On output, a valid pointer that points to the row's row number, a sequential number that identifies the row's position in the table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="36f06-115">返回值</span><span class="sxs-lookup"><span data-stu-id="36f06-115">Return value</span></span>

<span data-ttu-id="36f06-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="36f06-116">S_OK</span></span> 
  
> <span data-ttu-id="36f06-117">已成功检索行。</span><span class="sxs-lookup"><span data-stu-id="36f06-117">The row was successfully retrieved.</span></span>
    
<span data-ttu-id="36f06-118">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="36f06-118">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="36f06-119">_lpSPropValue_ 指向的 [SPropValue](spropvalue.md)结构不包含索引列属性。</span><span class="sxs-lookup"><span data-stu-id="36f06-119">The [SPropValue](spropvalue.md) structure that  _lpSPropValue_ points to does not contain the index column property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="36f06-120">备注</span><span class="sxs-lookup"><span data-stu-id="36f06-120">Remarks</span></span>

<span data-ttu-id="36f06-121">**ITableData：：HrQueryRow** 方法检索具有与 _lpSPropValue_ 指向的属性结构中包含的索引列的值匹配的索引列的行的所有属性。</span><span class="sxs-lookup"><span data-stu-id="36f06-121">The **ITableData::HrQueryRow** method retrieves all of the properties for the row that has an index column that matches the value of the index column included in the property structure pointed to by  _lpSPropValue_.</span></span> <span data-ttu-id="36f06-122">**HrQueryRow** 还会返回行号（如果调用方请求它）来标识行在表中的位置。</span><span class="sxs-lookup"><span data-stu-id="36f06-122">**HrQueryRow** also returns the row number, if the caller requests it, that identifies the row's position in the table.</span></span> 
  
<span data-ttu-id="36f06-123">因为 **HrQueryRow** 不会修改 _lpSPropValue_ 指向的 **SPropValue** 结构，所以当 **HrQueryRow** 返回时，调用方必须释放该结构。</span><span class="sxs-lookup"><span data-stu-id="36f06-123">Because **HrQueryRow** does not modify the **SPropValue** structure pointed to by  _lpSPropValue_, callers must free the structure when **HrQueryRow** returns.</span></span> <span data-ttu-id="36f06-124">调用方还必须释放包含检索到的行的 **SRow** 结构。</span><span class="sxs-lookup"><span data-stu-id="36f06-124">Callers must also free the **SRow** structure that contains the retrieved row.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="36f06-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36f06-125">See also</span></span>



[<span data-ttu-id="36f06-126">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="36f06-126">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="36f06-127">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="36f06-127">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="36f06-128">SPropValue</span><span class="sxs-lookup"><span data-stu-id="36f06-128">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="36f06-129">SRow</span><span class="sxs-lookup"><span data-stu-id="36f06-129">SRow</span></span>](srow.md)
  
[<span data-ttu-id="36f06-130">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="36f06-130">ITableData : IUnknown</span></span>](itabledataiunknown.md)

