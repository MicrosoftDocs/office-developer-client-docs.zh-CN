---
title: IMAPITableRestrict
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Restrict
api_type:
- COM
ms.assetid: a5bfc190-b58f-44c3-893c-8727df14ee58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ab069728f872d82246e8925c5ad35c07f41f02e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775724"
---
# <a name="imapitablerestrict"></a><span data-ttu-id="1a139-103">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="1a139-103">IMAPITable::Restrict</span></span>

  
  
<span data-ttu-id="1a139-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1a139-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1a139-105">筛选器应用于表格，从而减少了设置为仅与指定的条件匹配这些行的行。</span><span class="sxs-lookup"><span data-stu-id="1a139-105">Applies a filter to a table, reducing the row set to only those rows matching the specified criteria.</span></span>
  
```cpp
HRESULT Restrict(
LPSRestriction lpRestriction,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="1a139-106">参数</span><span class="sxs-lookup"><span data-stu-id="1a139-106">Parameters</span></span>

 <span data-ttu-id="1a139-107">_lpRestriction_</span><span class="sxs-lookup"><span data-stu-id="1a139-107">_lpRestriction_</span></span>
  
> <span data-ttu-id="1a139-108">[in]定义筛选器的条件[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="1a139-108">[in] Pointer to an [SRestriction](srestriction.md) structure defining the conditions of the filter.</span></span> <span data-ttu-id="1a139-109">传递 NULL _lpRestriction_参数中删除当前的筛选器。</span><span class="sxs-lookup"><span data-stu-id="1a139-109">Passing NULL in the  _lpRestriction_ parameter removes the current filter.</span></span> 
    
 <span data-ttu-id="1a139-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1a139-110">_ulFlags_</span></span>
  
> <span data-ttu-id="1a139-111">[in]位掩码的标志，控制限制操作的时间。</span><span class="sxs-lookup"><span data-stu-id="1a139-111">[in] Bitmask of flags that controls the timing of the restriction operation.</span></span> <span data-ttu-id="1a139-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="1a139-112">The following flags can be set:</span></span>
    
<span data-ttu-id="1a139-113">TBL_ASYNC</span><span class="sxs-lookup"><span data-stu-id="1a139-113">TBL_ASYNC</span></span> 
  
> <span data-ttu-id="1a139-114">异步启动操作并返回之前操作完成。</span><span class="sxs-lookup"><span data-stu-id="1a139-114">Starts the operation asynchronously and returns before the operation completes.</span></span>
    
<span data-ttu-id="1a139-115">TBL_BATCH</span><span class="sxs-lookup"><span data-stu-id="1a139-115">TBL_BATCH</span></span> 
  
> <span data-ttu-id="1a139-116">延迟的筛选器评估，直到表中的数据，则需要。</span><span class="sxs-lookup"><span data-stu-id="1a139-116">Defers evaluation of the filter until the data in the table is required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1a139-117">返回值</span><span class="sxs-lookup"><span data-stu-id="1a139-117">Return value</span></span>

<span data-ttu-id="1a139-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a139-118">S_OK</span></span> 
  
> <span data-ttu-id="1a139-119">已成功应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="1a139-119">The filter was successfully applied.</span></span>
    
<span data-ttu-id="1a139-120">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="1a139-120">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="1a139-121">阻止限制操作启动的正在进行中是另一个操作。</span><span class="sxs-lookup"><span data-stu-id="1a139-121">Another operation is in progress that prevents the restriction operation from starting.</span></span> <span data-ttu-id="1a139-122">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="1a139-122">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="1a139-123">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="1a139-123">MAPI_E_TOO_COMPLEX</span></span> 
  
> <span data-ttu-id="1a139-124">表无法执行操作，因为太复杂_lpRestriction_参数指向特定筛选器。</span><span class="sxs-lookup"><span data-stu-id="1a139-124">The table cannot perform the operation because the particular filter pointed to by the  _lpRestriction_ parameter is too complicated.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1a139-125">说明</span><span class="sxs-lookup"><span data-stu-id="1a139-125">Remarks</span></span>

<span data-ttu-id="1a139-126">**IMAPITable::Restrict**方法建立的限制或筛选，请在表。</span><span class="sxs-lookup"><span data-stu-id="1a139-126">The **IMAPITable::Restrict** method establishes a restriction, or filter, on a table.</span></span> <span data-ttu-id="1a139-127">如果没有前面限制，则它会丢弃并新建一个应用。</span><span class="sxs-lookup"><span data-stu-id="1a139-127">If there is a previous restriction, it is discarded and the new one applied.</span></span> <span data-ttu-id="1a139-128">应用了限制对基础数据的表; 没有影响它只会改变视图通过限制可以检索到包含满足在限制的数据行的行。</span><span class="sxs-lookup"><span data-stu-id="1a139-128">Applying a restriction has no affect on the underlying data of a table; it simply alters the view by limiting the rows that can be retrieved to rows containing data that satisfy the restriction.</span></span> 
  
<span data-ttu-id="1a139-129">有几种不同类型的限制，每个具有不同结构所述。</span><span class="sxs-lookup"><span data-stu-id="1a139-129">There are several different types of restrictions, each described with a different structure.</span></span> <span data-ttu-id="1a139-130">[SRestriction](srestriction.md)结构包含两个成员： 一个值，指示限制和适用于该类型的特定结构的类型。</span><span class="sxs-lookup"><span data-stu-id="1a139-130">The [SRestriction](srestriction.md) structure contains two members: a value that indicates the type of restriction and the specific structure applicable for that type.</span></span> 
  
<span data-ttu-id="1a139-131">永远不会生成的已**Restrict**呼叫被隐藏视图中的表格行的通知。</span><span class="sxs-lookup"><span data-stu-id="1a139-131">Notifications for table rows that are hidden from view by calls to **Restrict** are never generated.</span></span> 
  
<span data-ttu-id="1a139-132">对多值属性的属性限制的工作方式类似的单值属性限制。</span><span class="sxs-lookup"><span data-stu-id="1a139-132">A property restriction on a multivalued property works like a restriction on a single-valued property.</span></span> <span data-ttu-id="1a139-133">在属性限制中使用的多值的属性必须设置 MVI_FLAG 标志。</span><span class="sxs-lookup"><span data-stu-id="1a139-133">A multivalued property to be used in a property restriction must have the MVI_FLAG flag set.</span></span> <span data-ttu-id="1a139-134">如果它没有设置此标志，则将其视为完全有序元组。</span><span class="sxs-lookup"><span data-stu-id="1a139-134">If it doesn't have this flag set, it is treated as a totally ordered tuple.</span></span> <span data-ttu-id="1a139-135">两个多值列的比较比较中报告的第一个不相等中的列的关系的顺序的列元素。</span><span class="sxs-lookup"><span data-stu-id="1a139-135">A comparison of two multivalued columns compares the column elements in order, reporting the relation of the columns at the first inequality.</span></span> <span data-ttu-id="1a139-136">仅当比较的列包含相同的顺序相同的值，则返回相等。</span><span class="sxs-lookup"><span data-stu-id="1a139-136">Equality is returned only if the columns compared contain the same values in the same order.</span></span> <span data-ttu-id="1a139-137">如果一个列具有比其他值少，报告的关系是 null 值为其他值。</span><span class="sxs-lookup"><span data-stu-id="1a139-137">If one column has fewer values than the other, the reported relation is that of a null value to the other value.</span></span>
  
<span data-ttu-id="1a139-138">有关限制的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="1a139-138">For more information about restrictions, see [About Restrictions](about-restrictions.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a139-139">如果您创建动态查询搜索服务器上的数据，而不是使用**Restrict**方法和**QueryRows**方法一起使用**FindRow**方法。</span><span class="sxs-lookup"><span data-stu-id="1a139-139">If you create dynamic queries to search for data on the server, use the **FindRow** method instead of using the **Restrict** method and the **QueryRows** method together.</span></span> <span data-ttu-id="1a139-140">**Restrict**方法创建的用于评估添加或修改的基文件夹中的所有邮件缓存的视图。</span><span class="sxs-lookup"><span data-stu-id="1a139-140">The **Restrict** method creates a cached view that is used to evaluate all messages added to or modified in the base folder.</span></span> <span data-ttu-id="1a139-141">如果客户端应用程序的每个动态查询使用**Restrict**方法，将创建每个查询的缓存的视图。</span><span class="sxs-lookup"><span data-stu-id="1a139-141">If a client application uses the **Restrict** method for each dynamic query, a cached view will be created for each query.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1a139-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1a139-142">Notes to callers</span></span>

<span data-ttu-id="1a139-143">放弃而无需创建一个新的当前限制，请在_lpRestriction_传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="1a139-143">To discard the current restriction without creating a new one, pass NULL in  _lpRestriction_.</span></span>
  
<span data-ttu-id="1a139-144">如果另一个异步表呼叫正在进行，导致**Restrict**返回 MAPI_E_BUSY，您可以调用[IMAPITable::Abort](imapitable-abort.md)停止呼叫。</span><span class="sxs-lookup"><span data-stu-id="1a139-144">If another asynchronous table call is in progress, causing **Restrict** to return MAPI_E_BUSY, you can call [IMAPITable::Abort](imapitable-abort.md) to stop the call.</span></span> 
  
 <span data-ttu-id="1a139-145">除非将其中一个标志设置**限制**进行同步操作。</span><span class="sxs-lookup"><span data-stu-id="1a139-145">**Restrict** operates synchronously unless you set one of the flags.</span></span> <span data-ttu-id="1a139-146">如果设置 TBL_BATCH 标志， **Restrict**推迟评估版的限制，除非您请求的数据。</span><span class="sxs-lookup"><span data-stu-id="1a139-146">If you set the TBL_BATCH flag, **Restrict** postpones the evaluation of the restriction unless you request the data.</span></span> <span data-ttu-id="1a139-147">如果设置 TBL_ASYNC 标志，则**Restrict**操作以异步方式，可能返回之前完成操作。</span><span class="sxs-lookup"><span data-stu-id="1a139-147">If the TBL_ASYNC flag is set, **Restrict**operates asynchronously, potentially returning before the completion of the operation.</span></span>
  
<span data-ttu-id="1a139-148">当调用**Restrict**不进行，并且 BOOKMARK_CURRENT，当前光标位置，设置为表的开头，则将被丢弃的表的所有书签。</span><span class="sxs-lookup"><span data-stu-id="1a139-148">All bookmarks for a table are discarded when a call to **Restrict** is made, and BOOKMARK_CURRENT, the current cursor position, is set to the beginning of the table.</span></span> 
  
<span data-ttu-id="1a139-149">如果尝试为多少属性限制中表的列集不是一个属性，则结果是未定义。</span><span class="sxs-lookup"><span data-stu-id="1a139-149">If you attempt to impose a property restriction on a property that is not in the table's column set, the results are undefined.</span></span> <span data-ttu-id="1a139-150">只要您不确定来对属性的表中是否受支持，结合使用属性限制存在限制。</span><span class="sxs-lookup"><span data-stu-id="1a139-150">Whenever you are unsure as to whether a property is supported in a table, combine the property restriction with an exists restriction.</span></span> <span data-ttu-id="1a139-151">存在限制检查尝试实施属性限制之前的属性是否存在。</span><span class="sxs-lookup"><span data-stu-id="1a139-151">The exists restriction checks for the existence of the property before attempting to impose the property restriction.</span></span> 
  
<span data-ttu-id="1a139-152">不希望接收由于限制表中的已筛选的行上的表通知。</span><span class="sxs-lookup"><span data-stu-id="1a139-152">Do not expect to receive a table notification on a row that has been filtered from a table due to a restriction.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1a139-153">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1a139-153">MFCMAPI reference</span></span>

<span data-ttu-id="1a139-154">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1a139-154">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1a139-155">**文件**</span><span class="sxs-lookup"><span data-stu-id="1a139-155">**File**</span></span>|<span data-ttu-id="1a139-156">**函数**</span><span class="sxs-lookup"><span data-stu-id="1a139-156">**Function**</span></span>|<span data-ttu-id="1a139-157">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1a139-157">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a139-158">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="1a139-158">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="1a139-159">CContentsTableListCtrl::ApplyRestriction</span><span class="sxs-lookup"><span data-stu-id="1a139-159">CContentsTableListCtrl::ApplyRestriction</span></span>  <br/> |<span data-ttu-id="1a139-160">MFCMAPI 使用**IMAPITable::Restrict**方法在表上设置限制。</span><span class="sxs-lookup"><span data-stu-id="1a139-160">MFCMAPI uses the **IMAPITable::Restrict** method to set a restriction on a table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1a139-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a139-161">See also</span></span>



[<span data-ttu-id="1a139-162">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="1a139-162">IMAPITable::Abort</span></span>](imapitable-abort.md)
  
[<span data-ttu-id="1a139-163">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="1a139-163">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
  
[<span data-ttu-id="1a139-164">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="1a139-164">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
  
[<span data-ttu-id="1a139-165">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="1a139-165">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="1a139-166">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="1a139-166">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="1a139-167">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1a139-167">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="1a139-168">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1a139-168">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

