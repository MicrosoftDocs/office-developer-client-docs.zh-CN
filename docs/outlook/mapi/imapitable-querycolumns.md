---
title: IMAPITableQueryColumns
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.QueryColumns
api_type:
- COM
ms.assetid: d6341acc-c6ca-4605-93af-77230040339d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 86dfaa8fbc9ff24d38472f1339a22534086d890b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593744"
---
# <a name="imapitablequerycolumns"></a><span data-ttu-id="b9838-103">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="b9838-103">IMAPITable::QueryColumns</span></span>

  
  
<span data-ttu-id="b9838-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9838-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9838-105">返回表格列的列表。</span><span class="sxs-lookup"><span data-stu-id="b9838-105">Returns a list of columns for the table.</span></span>
  
```cpp
HRESULT QueryColumns(
ULONG ulFlags,
LPSPropTagArray FAR * lpPropTagArray
);
```

## <a name="parameters"></a><span data-ttu-id="b9838-106">参数</span><span class="sxs-lookup"><span data-stu-id="b9838-106">Parameters</span></span>

 <span data-ttu-id="b9838-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b9838-107">_ulFlags_</span></span>
  
> <span data-ttu-id="b9838-108">[in]应返回的标志，指示哪些列设置的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b9838-108">[in] Bitmask of flags that indicates which column set should be returned.</span></span> <span data-ttu-id="b9838-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="b9838-109">The following flag can be set:</span></span>
    
<span data-ttu-id="b9838-110">TBL_ALL_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="b9838-110">TBL_ALL_COLUMNS</span></span> 
  
> <span data-ttu-id="b9838-111">表应返回所有可用的列。</span><span class="sxs-lookup"><span data-stu-id="b9838-111">The table should return all available columns.</span></span>
    
 <span data-ttu-id="b9838-112">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="b9838-112">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="b9838-113">[输出]指向包含属性标记为列[SPropTagArray](sproptagarray.md)结构设置。</span><span class="sxs-lookup"><span data-stu-id="b9838-113">[out] Pointer to an [SPropTagArray](sproptagarray.md) structure containing the property tags for the column set.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b9838-114">返回值</span><span class="sxs-lookup"><span data-stu-id="b9838-114">Return value</span></span>

<span data-ttu-id="b9838-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9838-115">S_OK</span></span> 
  
> <span data-ttu-id="b9838-116">已成功返回列集。</span><span class="sxs-lookup"><span data-stu-id="b9838-116">The column set was successfully returned.</span></span>
    
<span data-ttu-id="b9838-117">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="b9838-117">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="b9838-118">另一个操作阻止列的正在进行中设置启动的检索操作。</span><span class="sxs-lookup"><span data-stu-id="b9838-118">Another operation is in progress that prevents the column set retrieval operation from starting.</span></span> <span data-ttu-id="b9838-119">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="b9838-119">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b9838-120">注解</span><span class="sxs-lookup"><span data-stu-id="b9838-120">Remarks</span></span>

<span data-ttu-id="b9838-121">**IMAPITable::QueryColumns**方法可调用它以检索：</span><span class="sxs-lookup"><span data-stu-id="b9838-121">The **IMAPITable::QueryColumns** method can be called to retrieve:</span></span> 
  
- <span data-ttu-id="b9838-122">为表设置默认列。</span><span class="sxs-lookup"><span data-stu-id="b9838-122">The default column set for a table.</span></span>
    
- <span data-ttu-id="b9838-123">由调用[IMAPITable::SetColumns](imapitable-setcolumns.md)方法建立为表，设置当前列。</span><span class="sxs-lookup"><span data-stu-id="b9838-123">The current column set for a table, as established by a call to the [IMAPITable::SetColumns](imapitable-setcolumns.md) method.</span></span> 
    
- <span data-ttu-id="b9838-124">完整的列设置的表、 列可用，而不是一定是当前集的一部分。</span><span class="sxs-lookup"><span data-stu-id="b9838-124">The complete column set for a table, the columns that are available, but not necessarily part of the current set.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="b9838-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b9838-125">Notes to callers</span></span>

<span data-ttu-id="b9838-126">如果未设置 TBL_ALL_COLUMNS 标志， **IMAPITable::QueryColumns**返回表的默认或当前列集，具体取决于是否表已经受到**IMAPITable::SetColumns**调用。</span><span class="sxs-lookup"><span data-stu-id="b9838-126">If you do not set the TBL_ALL_COLUMNS flag, **IMAPITable::QueryColumns** returns either a table's default or current column set, depending on whether the table has been affected by a call to **IMAPITable::SetColumns**.</span></span> <span data-ttu-id="b9838-127">**SetColumns**更改顺序和所选内容中表的列集的列。</span><span class="sxs-lookup"><span data-stu-id="b9838-127">**SetColumns** changes the order and selection of columns in a table's column set.</span></span> 
  
<span data-ttu-id="b9838-128">如果设置 TBL_ALL_COLUMNS 标志， **QueryColumns**返回的所有能够在表的列组列。</span><span class="sxs-lookup"><span data-stu-id="b9838-128">If you set the TBL_ALL_COLUMNS flag, **QueryColumns** returns all of the columns that are capable of being in the table's column set.</span></span> 
  
<span data-ttu-id="b9838-129">释放内存为通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数_lpPropTagArray_参数指向的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="b9838-129">Free the memory for the property tag array pointed to by the  _lpPropTagArray_ parameter by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b9838-130">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="b9838-130">MFCMAPI reference</span></span>

<span data-ttu-id="b9838-131">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b9838-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b9838-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="b9838-132">**File**</span></span>|<span data-ttu-id="b9838-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="b9838-133">**Function**</span></span>|<span data-ttu-id="b9838-134">**Comment**</span><span class="sxs-lookup"><span data-stu-id="b9838-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9838-135">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="b9838-135">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="b9838-136">CContentsTableListCtrl::DoSetColumns</span><span class="sxs-lookup"><span data-stu-id="b9838-136">CContentsTableListCtrl::DoSetColumns</span></span>  <br/> |<span data-ttu-id="b9838-137">MFCMAPI 使用**IMAPITable::QueryColumns**方法检索当前为表设置，以便用户可以编辑的列。</span><span class="sxs-lookup"><span data-stu-id="b9838-137">MFCMAPI uses the **IMAPITable::QueryColumns** method to retrieve the current column set for a table so the user can edit it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b9838-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9838-138">See also</span></span>



[<span data-ttu-id="b9838-139">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="b9838-139">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="b9838-140">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="b9838-140">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="b9838-141">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="b9838-141">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="b9838-142">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b9838-142">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="b9838-143">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b9838-143">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

