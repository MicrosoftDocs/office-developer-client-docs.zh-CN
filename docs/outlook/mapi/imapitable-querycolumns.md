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
ms.openlocfilehash: d142e19fc4721cec4dde0df7fc030a001121da63
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328880"
---
# <a name="imapitablequerycolumns"></a><span data-ttu-id="7320c-103">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="7320c-103">IMAPITable::QueryColumns</span></span>

  
  
<span data-ttu-id="7320c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7320c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7320c-105">返回表的列的列表。</span><span class="sxs-lookup"><span data-stu-id="7320c-105">Returns a list of columns for the table.</span></span>
  
```cpp
HRESULT QueryColumns(
ULONG ulFlags,
LPSPropTagArray FAR * lpPropTagArray
);
```

## <a name="parameters"></a><span data-ttu-id="7320c-106">参数</span><span class="sxs-lookup"><span data-stu-id="7320c-106">Parameters</span></span>

 <span data-ttu-id="7320c-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7320c-107">_ulFlags_</span></span>
  
> <span data-ttu-id="7320c-108">实时指示应返回哪一列集的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="7320c-108">[in] Bitmask of flags that indicates which column set should be returned.</span></span> <span data-ttu-id="7320c-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="7320c-109">The following flag can be set:</span></span>
    
<span data-ttu-id="7320c-110">TBL_ALL_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="7320c-110">TBL_ALL_COLUMNS</span></span> 
  
> <span data-ttu-id="7320c-111">该表应返回所有可用的列。</span><span class="sxs-lookup"><span data-stu-id="7320c-111">The table should return all available columns.</span></span>
    
 <span data-ttu-id="7320c-112">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="7320c-112">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="7320c-113">排除指向包含列集的属性标记的[SPropTagArray](sproptagarray.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="7320c-113">[out] Pointer to an [SPropTagArray](sproptagarray.md) structure containing the property tags for the column set.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7320c-114">返回值</span><span class="sxs-lookup"><span data-stu-id="7320c-114">Return value</span></span>

<span data-ttu-id="7320c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="7320c-115">S_OK</span></span> 
  
> <span data-ttu-id="7320c-116">成功返回列集。</span><span class="sxs-lookup"><span data-stu-id="7320c-116">The column set was successfully returned.</span></span>
    
<span data-ttu-id="7320c-117">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="7320c-117">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="7320c-118">正在进行另一个操作, 以防止启动列集检索操作。</span><span class="sxs-lookup"><span data-stu-id="7320c-118">Another operation is in progress that prevents the column set retrieval operation from starting.</span></span> <span data-ttu-id="7320c-119">应允许正在进行的操作完成, 或者应已停止。</span><span class="sxs-lookup"><span data-stu-id="7320c-119">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7320c-120">注解</span><span class="sxs-lookup"><span data-stu-id="7320c-120">Remarks</span></span>

<span data-ttu-id="7320c-121">可以调用**IMAPITable:: QueryColumns**方法来检索:</span><span class="sxs-lookup"><span data-stu-id="7320c-121">The **IMAPITable::QueryColumns** method can be called to retrieve:</span></span> 
  
- <span data-ttu-id="7320c-122">为表格设置的默认列。</span><span class="sxs-lookup"><span data-stu-id="7320c-122">The default column set for a table.</span></span>
    
- <span data-ttu-id="7320c-123">为表设置的当前列, 这是通过调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法建立的。</span><span class="sxs-lookup"><span data-stu-id="7320c-123">The current column set for a table, as established by a call to the [IMAPITable::SetColumns](imapitable-setcolumns.md) method.</span></span> 
    
- <span data-ttu-id="7320c-124">表的完整列集、可用的列, 但不一定是当前集合的一部分。</span><span class="sxs-lookup"><span data-stu-id="7320c-124">The complete column set for a table, the columns that are available, but not necessarily part of the current set.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="7320c-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7320c-125">Notes to callers</span></span>

<span data-ttu-id="7320c-126">如果未设置 TBL_ALL_COLUMNS 标志, 则**IMAPITable:: QueryColumns**将返回表的默认值或当前列集, 具体取决于表是否受到对**IMAPITable:: SetColumns**的调用的影响。</span><span class="sxs-lookup"><span data-stu-id="7320c-126">If you do not set the TBL_ALL_COLUMNS flag, **IMAPITable::QueryColumns** returns either a table's default or current column set, depending on whether the table has been affected by a call to **IMAPITable::SetColumns**.</span></span> <span data-ttu-id="7320c-127">**SetColumns**更改表的列集合中列的顺序和选择。</span><span class="sxs-lookup"><span data-stu-id="7320c-127">**SetColumns** changes the order and selection of columns in a table's column set.</span></span> 
  
<span data-ttu-id="7320c-128">如果设置 TBL_ALL_COLUMNS 标志, 则**QueryColumns**将返回能够在表的列集中进行的所有列。</span><span class="sxs-lookup"><span data-stu-id="7320c-128">If you set the TBL_ALL_COLUMNS flag, **QueryColumns** returns all of the columns that are capable of being in the table's column set.</span></span> 
  
<span data-ttu-id="7320c-129">通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 释放由_lpPropTagArray_参数指向的属性标记数组的内存。</span><span class="sxs-lookup"><span data-stu-id="7320c-129">Free the memory for the property tag array pointed to by the  _lpPropTagArray_ parameter by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7320c-130">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="7320c-130">MFCMAPI reference</span></span>

<span data-ttu-id="7320c-131">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7320c-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7320c-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="7320c-132">**File**</span></span>|<span data-ttu-id="7320c-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="7320c-133">**Function**</span></span>|<span data-ttu-id="7320c-134">**备注**</span><span class="sxs-lookup"><span data-stu-id="7320c-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7320c-135">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="7320c-135">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="7320c-136">CContentsTableListCtrl::D osetcolumns</span><span class="sxs-lookup"><span data-stu-id="7320c-136">CContentsTableListCtrl::DoSetColumns</span></span>  <br/> |<span data-ttu-id="7320c-137">MFCMAPI 使用**IMAPITable:: QueryColumns**方法检索表的当前列集, 以便用户可以对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="7320c-137">MFCMAPI uses the **IMAPITable::QueryColumns** method to retrieve the current column set for a table so the user can edit it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7320c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7320c-138">See also</span></span>



[<span data-ttu-id="7320c-139">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="7320c-139">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="7320c-140">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="7320c-140">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="7320c-141">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="7320c-141">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="7320c-142">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7320c-142">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="7320c-143">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7320c-143">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

