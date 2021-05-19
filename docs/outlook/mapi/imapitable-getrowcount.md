---
title: IMAPITableGetRowCount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.GetRowCount
api_type:
- COM
ms.assetid: 44a12c92-7462-4acf-9520-5d4c2d7f1d47
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b13bf3bdd8392efc42ad189e48dffad8636f0708
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425601"
---
# <a name="imapitablegetrowcount"></a><span data-ttu-id="fca63-103">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="fca63-103">IMAPITable::GetRowCount</span></span>

  
  
<span data-ttu-id="fca63-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fca63-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fca63-105">返回表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="fca63-105">Returns the total number of rows in the table.</span></span> 
  
```cpp
HRESULT GetRowCount(
ULONG ulFlags,
ULONG FAR * lpulCount
);
```

## <a name="parameters"></a><span data-ttu-id="fca63-106">参数</span><span class="sxs-lookup"><span data-stu-id="fca63-106">Parameters</span></span>

 <span data-ttu-id="fca63-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fca63-107">_ulFlags_</span></span>
  
> <span data-ttu-id="fca63-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="fca63-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="fca63-109">_lpulCount_</span><span class="sxs-lookup"><span data-stu-id="fca63-109">_lpulCount_</span></span>
  
> <span data-ttu-id="fca63-110">[out]指向表中行数的指针。</span><span class="sxs-lookup"><span data-stu-id="fca63-110">[out] Pointer to the number of rows in the table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fca63-111">返回值</span><span class="sxs-lookup"><span data-stu-id="fca63-111">Return value</span></span>

<span data-ttu-id="fca63-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fca63-112">S_OK</span></span> 
  
> <span data-ttu-id="fca63-113">已成功返回行数。</span><span class="sxs-lookup"><span data-stu-id="fca63-113">The row count was successfully returned.</span></span>
    
<span data-ttu-id="fca63-114">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="fca63-114">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="fca63-115">正在进行另一个操作，以防止行计数检索操作启动。</span><span class="sxs-lookup"><span data-stu-id="fca63-115">Another operation is in progress that prevents the row count retrieval operation from starting.</span></span> <span data-ttu-id="fca63-116">应允许完成或停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="fca63-116">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="fca63-117">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="fca63-117">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="fca63-118">表格无法计算行数。</span><span class="sxs-lookup"><span data-stu-id="fca63-118">The table cannot calculate the number of rows.</span></span>
    
<span data-ttu-id="fca63-119">MAPI_W_APPROX_COUNT</span><span class="sxs-lookup"><span data-stu-id="fca63-119">MAPI_W_APPROX_COUNT</span></span> 
  
> <span data-ttu-id="fca63-120">调用成功，但返回了近似的行计数，因为可能由于内存限制无法确定确切的行计数。</span><span class="sxs-lookup"><span data-stu-id="fca63-120">The call succeeded, but an approximate row count was returned because the exact row count could not be determined possibly due to memory constraints.</span></span> <span data-ttu-id="fca63-121">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="fca63-121">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="fca63-122">请参阅 [使用宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="fca63-122">See [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fca63-123">备注</span><span class="sxs-lookup"><span data-stu-id="fca63-123">Remarks</span></span>

<span data-ttu-id="fca63-124">**IMAPITable：：GetRowCount** 方法检索表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="fca63-124">The **IMAPITable::GetRowCount** method retrieves the total number of rows in a table.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="fca63-125">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="fca63-125">Notes to implementers</span></span>

<span data-ttu-id="fca63-126">如果无法确定表的确切行数，则返回 MAPI_W_APPROX_COUNT  _lpulCount_ 参数的内容中的近似行数。</span><span class="sxs-lookup"><span data-stu-id="fca63-126">If you cannot determine the table's exact row count, return MAPI_W_APPROX_COUNT and an approximate row count in the contents of the  _lpulCount_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="fca63-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="fca63-127">Notes to callers</span></span>

<span data-ttu-id="fca63-128">在调用 [IMAPITable：：QueryRows](imapitable-queryrows.md)方法以检索数据之前，使用 **GetRowCount** 可了解表包含的行数。</span><span class="sxs-lookup"><span data-stu-id="fca63-128">Use **GetRowCount** to find out how many rows a table holds before making a call to the [IMAPITable::QueryRows](imapitable-queryrows.md) method to retrieve the data.</span></span> <span data-ttu-id="fca63-129">如果表中少于 20 行，可以安全地调用 **QueryPosition** 来检索整个表。</span><span class="sxs-lookup"><span data-stu-id="fca63-129">If there are less than twenty rows in the table, it is safe to call **QueryPosition** to retrieve the whole table.</span></span> <span data-ttu-id="fca63-130">如果表中超过 20 行，请考虑多次调用 **QueryPosition** 并限制每次调用中检索到的行数。</span><span class="sxs-lookup"><span data-stu-id="fca63-130">If there are more than twenty rows in the table, consider making multiple calls to **QueryPosition** and limit the number of rows retrieved in each call.</span></span> 
  
<span data-ttu-id="fca63-131">某些表不支持 **GetRowCount** 并返回MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="fca63-131">Some tables do not support **GetRowCount** and return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="fca63-132">如果 **不支持 GetRowCount，** 另一种可能调用 [IMAPITable：：QueryPosition](imapitable-queryposition.md)。</span><span class="sxs-lookup"><span data-stu-id="fca63-132">If **GetRowCount** is not supported, an alternative might be to call [IMAPITable::QueryPosition](imapitable-queryposition.md).</span></span> <span data-ttu-id="fca63-133">使用 **QueryPosition 中的结果**，可以确定当前行和最后一行之间的关系。</span><span class="sxs-lookup"><span data-stu-id="fca63-133">With the results from **QueryPosition**, you can determine the relationship between the current row and last row.</span></span> 
  
<span data-ttu-id="fca63-134">当 **GetRowCount** 由于MAPI_E_BUSY检索行数而返回值时，请调用 [IMAPITable：：WaitForCompletion](imapitable-waitforcompletion.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="fca63-134">When **GetRowCount** returns MAPI_E_BUSY because it is temporarily unable to retrieve a row count, call the [IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md) method.</span></span> <span data-ttu-id="fca63-135">当 **WaitForCompletion** 返回时，重试对 **GetRowCount 的调用**。</span><span class="sxs-lookup"><span data-stu-id="fca63-135">When **WaitForCompletion** returns, retry the call to **GetRowCount**.</span></span> <span data-ttu-id="fca63-136">检测异步操作是否正在进行的另一个方法是调用 [IMAPITable：：GetStatus](imapitable-getstatus.md) 方法并检查  _lpulTableState_ 参数的内容。</span><span class="sxs-lookup"><span data-stu-id="fca63-136">Another way to detect whether an asynchronous operation is in progress is to call the [IMAPITable::GetStatus](imapitable-getstatus.md) method and check the contents of the  _lpulTableState_ parameter.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="fca63-137">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="fca63-137">MFCMAPI reference</span></span>

<span data-ttu-id="fca63-138">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="fca63-138">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="fca63-139">**文件**</span><span class="sxs-lookup"><span data-stu-id="fca63-139">**File**</span></span>|<span data-ttu-id="fca63-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="fca63-140">**Function**</span></span>|<span data-ttu-id="fca63-141">**备注**</span><span class="sxs-lookup"><span data-stu-id="fca63-141">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fca63-142">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="fca63-142">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="fca63-143">CopyFolderContents</span><span class="sxs-lookup"><span data-stu-id="fca63-143">CopyFolderContents</span></span>  <br/> |<span data-ttu-id="fca63-144">MFCMAPI 使用 **IMAPITable：：GetRowCount** 方法确定源表中有多少行，以便分配内存以执行复制。</span><span class="sxs-lookup"><span data-stu-id="fca63-144">MFCMAPI uses the **IMAPITable::GetRowCount** method to determine how many rows are in the source table so memory can be allocated to perform the copy.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fca63-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fca63-145">See also</span></span>



[<span data-ttu-id="fca63-146">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="fca63-146">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md)
  
[<span data-ttu-id="fca63-147">IMAPITable::QueryPosition</span><span class="sxs-lookup"><span data-stu-id="fca63-147">IMAPITable::QueryPosition</span></span>](imapitable-queryposition.md)
  
[<span data-ttu-id="fca63-148">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="fca63-148">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="fca63-149">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="fca63-149">IMAPITable::WaitForCompletion</span></span>](imapitable-waitforcompletion.md)
  
[<span data-ttu-id="fca63-150">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fca63-150">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="fca63-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="fca63-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

