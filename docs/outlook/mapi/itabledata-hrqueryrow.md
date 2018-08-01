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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 92540159386e6f37d93684aff037b235071010f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776100"
---
# <a name="itabledatahrqueryrow"></a><span data-ttu-id="105f4-103">ITableData::HrQueryRow</span><span class="sxs-lookup"><span data-stu-id="105f4-103">ITableData::HrQueryRow</span></span>

  
  
<span data-ttu-id="105f4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="105f4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="105f4-105">检索表格行。</span><span class="sxs-lookup"><span data-stu-id="105f4-105">Retrieves a table row.</span></span>
  
```cpp
HRESULT HrQueryRow(
  LPSPropValue lpSPropValue,
  LPSRow FAR * lppSRow,
  ULONG FAR * lpuliRow
);
```

## <a name="parameters"></a><span data-ttu-id="105f4-106">参数</span><span class="sxs-lookup"><span data-stu-id="105f4-106">Parameters</span></span>

 <span data-ttu-id="105f4-107">_lpSPropValue_</span><span class="sxs-lookup"><span data-stu-id="105f4-107">_lpSPropValue_</span></span>
  
> <span data-ttu-id="105f4-108">[in]指向描述要检索的行的索引列的属性值结构的指针。</span><span class="sxs-lookup"><span data-stu-id="105f4-108">[in] A pointer to a property value structure that describes the index column for the row to be retrieved.</span></span> <span data-ttu-id="105f4-109">属性值结构的**ulPropTag**成员应包含作为_ulPropTagIndexColumn_参数从访问[ITableData](itabledataiunknown.md)实现[CreateTable](createtable.md)函数调用的相同属性标记。</span><span class="sxs-lookup"><span data-stu-id="105f4-109">The **ulPropTag** member of the property value structure should contain the same property tag as the  _ulPropTagIndexColumn_ parameter from the call to the [CreateTable](createtable.md) function, which accesses the [ITableData](itabledataiunknown.md) implementation.</span></span> 
    
 <span data-ttu-id="105f4-110">_lppSRow_</span><span class="sxs-lookup"><span data-stu-id="105f4-110">_lppSRow_</span></span>
  
> <span data-ttu-id="105f4-111">[输出]指向到检索行的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="105f4-111">[out] A pointer to a pointer to the retrieved row.</span></span> 
    
 <span data-ttu-id="105f4-112">_lpuliRow_</span><span class="sxs-lookup"><span data-stu-id="105f4-112">_lpuliRow_</span></span>
  
> <span data-ttu-id="105f4-113">[传入、 传出]在输入、 有效的指针或 NULL，表示不需要返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="105f4-113">[in, out] On input, a valid pointer or NULL, which indicates that no information needs to be returned.</span></span> <span data-ttu-id="105f4-114">在输出中、 有效的指针指向行的行号，标识表中的行的位置的顺序编号。</span><span class="sxs-lookup"><span data-stu-id="105f4-114">On output, a valid pointer that points to the row's row number, a sequential number that identifies the row's position in the table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="105f4-115">返回值</span><span class="sxs-lookup"><span data-stu-id="105f4-115">Return value</span></span>

<span data-ttu-id="105f4-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="105f4-116">S_OK</span></span> 
  
> <span data-ttu-id="105f4-117">已成功检索行。</span><span class="sxs-lookup"><span data-stu-id="105f4-117">The row was successfully retrieved.</span></span>
    
<span data-ttu-id="105f4-118">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="105f4-118">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="105f4-119">[SPropValue](spropvalue.md)结构不包含索引列属性的_lpSPropValue_点。</span><span class="sxs-lookup"><span data-stu-id="105f4-119">The [SPropValue](spropvalue.md) structure that  _lpSPropValue_ points to does not contain the index column property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="105f4-120">说明</span><span class="sxs-lookup"><span data-stu-id="105f4-120">Remarks</span></span>

<span data-ttu-id="105f4-121">**ITableData::HrQueryRow**方法检索的所有行已索引列包含指向_lpSPropValue_属性结构中的索引列的值相匹配的属性。</span><span class="sxs-lookup"><span data-stu-id="105f4-121">The **ITableData::HrQueryRow** method retrieves all of the properties for the row that has an index column that matches the value of the index column included in the property structure pointed to by  _lpSPropValue_.</span></span> <span data-ttu-id="105f4-122">**HrQueryRow**还返回行数，如果呼叫者请求其标识表中的行的位置。</span><span class="sxs-lookup"><span data-stu-id="105f4-122">**HrQueryRow** also returns the row number, if the caller requests it, that identifies the row's position in the table.</span></span> 
  
<span data-ttu-id="105f4-123">因为**HrQueryRow**不修改所指的_lpSPropValue_ **SPropValue**结构，呼叫者时**HrQueryRow**返回必须释放结构。</span><span class="sxs-lookup"><span data-stu-id="105f4-123">Because **HrQueryRow** does not modify the **SPropValue** structure pointed to by  _lpSPropValue_, callers must free the structure when **HrQueryRow** returns.</span></span> <span data-ttu-id="105f4-124">呼叫者还必须释放**SRow**结构包含检索的行。</span><span class="sxs-lookup"><span data-stu-id="105f4-124">Callers must also free the **SRow** structure that contains the retrieved row.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="105f4-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="105f4-125">See also</span></span>



[<span data-ttu-id="105f4-126">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="105f4-126">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="105f4-127">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="105f4-127">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="105f4-128">SPropValue</span><span class="sxs-lookup"><span data-stu-id="105f4-128">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="105f4-129">SRow</span><span class="sxs-lookup"><span data-stu-id="105f4-129">SRow</span></span>](srow.md)
  
[<span data-ttu-id="105f4-130">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="105f4-130">ITableData : IUnknown</span></span>](itabledataiunknown.md)

