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
ms.openlocfilehash: 71178f1a531bd381387e0aa7fbacb02d4431a401
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584322"
---
# <a name="imapitablegetrowcount"></a><span data-ttu-id="900a7-103">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="900a7-103">IMAPITable::GetRowCount</span></span>

  
  
<span data-ttu-id="900a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="900a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="900a7-105">返回表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="900a7-105">Returns the total number of rows in the table.</span></span> 
  
```cpp
HRESULT GetRowCount(
ULONG ulFlags,
ULONG FAR * lpulCount
);
```

## <a name="parameters"></a><span data-ttu-id="900a7-106">参数</span><span class="sxs-lookup"><span data-stu-id="900a7-106">Parameters</span></span>

 <span data-ttu-id="900a7-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="900a7-107">_ulFlags_</span></span>
  
> <span data-ttu-id="900a7-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="900a7-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="900a7-109">_lpulCount_</span><span class="sxs-lookup"><span data-stu-id="900a7-109">_lpulCount_</span></span>
  
> <span data-ttu-id="900a7-110">[输出]指向的表中的行数。</span><span class="sxs-lookup"><span data-stu-id="900a7-110">[out] Pointer to the number of rows in the table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="900a7-111">返回值</span><span class="sxs-lookup"><span data-stu-id="900a7-111">Return value</span></span>

<span data-ttu-id="900a7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="900a7-112">S_OK</span></span> 
  
> <span data-ttu-id="900a7-113">已成功返回的行计数。</span><span class="sxs-lookup"><span data-stu-id="900a7-113">The row count was successfully returned.</span></span>
    
<span data-ttu-id="900a7-114">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="900a7-114">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="900a7-115">正在阻止从起始行计数检索操作是另一个操作。</span><span class="sxs-lookup"><span data-stu-id="900a7-115">Another operation is in progress that prevents the row count retrieval operation from starting.</span></span> <span data-ttu-id="900a7-116">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="900a7-116">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="900a7-117">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="900a7-117">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="900a7-118">表无法计算行的数。</span><span class="sxs-lookup"><span data-stu-id="900a7-118">The table cannot calculate the number of rows.</span></span>
    
<span data-ttu-id="900a7-119">MAPI_W_APPROX_COUNT</span><span class="sxs-lookup"><span data-stu-id="900a7-119">MAPI_W_APPROX_COUNT</span></span> 
  
> <span data-ttu-id="900a7-120">调用成功，但因为完全行计数无法确定可能是由于内存限制返回近似行计数。</span><span class="sxs-lookup"><span data-stu-id="900a7-120">The call succeeded, but an approximate row count was returned because the exact row count could not be determined possibly due to memory constraints.</span></span> <span data-ttu-id="900a7-121">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="900a7-121">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="900a7-122">请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="900a7-122">See [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="900a7-123">注解</span><span class="sxs-lookup"><span data-stu-id="900a7-123">Remarks</span></span>

<span data-ttu-id="900a7-124">**IMAPITable::GetRowCount**方法检索表中的行的总数。</span><span class="sxs-lookup"><span data-stu-id="900a7-124">The **IMAPITable::GetRowCount** method retrieves the total number of rows in a table.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="900a7-125">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="900a7-125">Notes to implementers</span></span>

<span data-ttu-id="900a7-126">如果无法确定表的确切的行数，返回 MAPI_W_APPROX_COUNT 和近似行计数中_lpulCount_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="900a7-126">If you cannot determine the table's exact row count, return MAPI_W_APPROX_COUNT and an approximate row count in the contents of the  _lpulCount_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="900a7-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="900a7-127">Notes to callers</span></span>

<span data-ttu-id="900a7-128">使用**GetRowCount**以找出多少行表包含在调用[IMAPITable::QueryRows](imapitable-queryrows.md)方法来检索数据之前。</span><span class="sxs-lookup"><span data-stu-id="900a7-128">Use **GetRowCount** to find out how many rows a table holds before making a call to the [IMAPITable::QueryRows](imapitable-queryrows.md) method to retrieve the data.</span></span> <span data-ttu-id="900a7-129">如果表中有小于 20 个行，则安全地呼叫**QueryPosition**检索整张表格。</span><span class="sxs-lookup"><span data-stu-id="900a7-129">If there are less than twenty rows in the table, it is safe to call **QueryPosition** to retrieve the whole table.</span></span> <span data-ttu-id="900a7-130">如果表中有超过 20 个行，请考虑使多个调用**QueryPosition**和限制的每个呼叫中检索的行数。</span><span class="sxs-lookup"><span data-stu-id="900a7-130">If there are more than twenty rows in the table, consider making multiple calls to **QueryPosition** and limit the number of rows retrieved in each call.</span></span> 
  
<span data-ttu-id="900a7-131">某些表格中不支持**GetRowCount** ，并返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="900a7-131">Some tables do not support **GetRowCount** and return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="900a7-132">如果不支持**GetRowCount** ，另一个方法可能是呼叫[IMAPITable::QueryPosition](imapitable-queryposition.md)。</span><span class="sxs-lookup"><span data-stu-id="900a7-132">If **GetRowCount** is not supported, an alternative might be to call [IMAPITable::QueryPosition](imapitable-queryposition.md).</span></span> <span data-ttu-id="900a7-133">使用**QueryPosition**的结果，您可以确定当前行和最后一行之间的关系。</span><span class="sxs-lookup"><span data-stu-id="900a7-133">With the results from **QueryPosition**, you can determine the relationship between the current row and last row.</span></span> 
  
<span data-ttu-id="900a7-134">**GetRowCount**返回 MAPI_E_BUSY，因为它是暂时无法检索行数时, 调用[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md)方法。</span><span class="sxs-lookup"><span data-stu-id="900a7-134">When **GetRowCount** returns MAPI_E_BUSY because it is temporarily unable to retrieve a row count, call the [IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md) method.</span></span> <span data-ttu-id="900a7-135">返回**WaitForCompletion**时, 重试**GetRowCount**调用。</span><span class="sxs-lookup"><span data-stu-id="900a7-135">When **WaitForCompletion** returns, retry the call to **GetRowCount**.</span></span> <span data-ttu-id="900a7-136">另一种方法检测是否正在执行异步操作是调用[IMAPITable::GetStatus](imapitable-getstatus.md)方法，并检查_lpulTableState_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="900a7-136">Another way to detect whether an asynchronous operation is in progress is to call the [IMAPITable::GetStatus](imapitable-getstatus.md) method and check the contents of the  _lpulTableState_ parameter.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="900a7-137">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="900a7-137">MFCMAPI reference</span></span>

<span data-ttu-id="900a7-138">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="900a7-138">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="900a7-139">**文件**</span><span class="sxs-lookup"><span data-stu-id="900a7-139">**File**</span></span>|<span data-ttu-id="900a7-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="900a7-140">**Function**</span></span>|<span data-ttu-id="900a7-141">**Comment**</span><span class="sxs-lookup"><span data-stu-id="900a7-141">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="900a7-142">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="900a7-142">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="900a7-143">CopyFolderContents</span><span class="sxs-lookup"><span data-stu-id="900a7-143">CopyFolderContents</span></span>  <br/> |<span data-ttu-id="900a7-144">MFCMAPI 使用**IMAPITable::GetRowCount**方法确定源表中多少行，因此可以分配内存要进行复制。</span><span class="sxs-lookup"><span data-stu-id="900a7-144">MFCMAPI uses the **IMAPITable::GetRowCount** method to determine how many rows are in the source table so memory can be allocated to perform the copy.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="900a7-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="900a7-145">See also</span></span>



[<span data-ttu-id="900a7-146">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="900a7-146">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md)
  
[<span data-ttu-id="900a7-147">IMAPITable::QueryPosition</span><span class="sxs-lookup"><span data-stu-id="900a7-147">IMAPITable::QueryPosition</span></span>](imapitable-queryposition.md)
  
[<span data-ttu-id="900a7-148">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="900a7-148">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="900a7-149">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="900a7-149">IMAPITable::WaitForCompletion</span></span>](imapitable-waitforcompletion.md)
  
[<span data-ttu-id="900a7-150">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="900a7-150">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="900a7-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="900a7-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

