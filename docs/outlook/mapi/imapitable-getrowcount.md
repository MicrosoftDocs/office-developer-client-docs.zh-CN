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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328887"
---
# <a name="imapitablegetrowcount"></a><span data-ttu-id="6659b-103">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="6659b-103">IMAPITable::GetRowCount</span></span>

  
  
<span data-ttu-id="6659b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6659b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6659b-105">返回表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="6659b-105">Returns the total number of rows in the table.</span></span> 
  
```cpp
HRESULT GetRowCount(
ULONG ulFlags,
ULONG FAR * lpulCount
);
```

## <a name="parameters"></a><span data-ttu-id="6659b-106">参数</span><span class="sxs-lookup"><span data-stu-id="6659b-106">Parameters</span></span>

 <span data-ttu-id="6659b-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6659b-107">_ulFlags_</span></span>
  
> <span data-ttu-id="6659b-108">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="6659b-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="6659b-109">_lpulCount_</span><span class="sxs-lookup"><span data-stu-id="6659b-109">_lpulCount_</span></span>
  
> <span data-ttu-id="6659b-110">排除指向表中的行数的指针。</span><span class="sxs-lookup"><span data-stu-id="6659b-110">[out] Pointer to the number of rows in the table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6659b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6659b-111">Return value</span></span>

<span data-ttu-id="6659b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6659b-112">S_OK</span></span> 
  
> <span data-ttu-id="6659b-113">已成功返回行数。</span><span class="sxs-lookup"><span data-stu-id="6659b-113">The row count was successfully returned.</span></span>
    
<span data-ttu-id="6659b-114">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="6659b-114">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="6659b-115">正在进行另一个操作, 以阻止行计数检索操作开始。</span><span class="sxs-lookup"><span data-stu-id="6659b-115">Another operation is in progress that prevents the row count retrieval operation from starting.</span></span> <span data-ttu-id="6659b-116">应允许正在进行的操作完成, 或者应已停止。</span><span class="sxs-lookup"><span data-stu-id="6659b-116">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="6659b-117">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="6659b-117">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="6659b-118">该表无法计算行数。</span><span class="sxs-lookup"><span data-stu-id="6659b-118">The table cannot calculate the number of rows.</span></span>
    
<span data-ttu-id="6659b-119">MAPI_W_APPROX_COUNT</span><span class="sxs-lookup"><span data-stu-id="6659b-119">MAPI_W_APPROX_COUNT</span></span> 
  
> <span data-ttu-id="6659b-120">调用成功, 但返回了大概的行计数, 因为无法确定确切的行计数, 因为可能由于内存约束而无法确定。</span><span class="sxs-lookup"><span data-stu-id="6659b-120">The call succeeded, but an approximate row count was returned because the exact row count could not be determined possibly due to memory constraints.</span></span> <span data-ttu-id="6659b-121">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="6659b-121">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="6659b-122">请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="6659b-122">See [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6659b-123">注解</span><span class="sxs-lookup"><span data-stu-id="6659b-123">Remarks</span></span>

<span data-ttu-id="6659b-124">**IMAPITable:: GetRowCount**方法检索表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="6659b-124">The **IMAPITable::GetRowCount** method retrieves the total number of rows in a table.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="6659b-125">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="6659b-125">Notes to implementers</span></span>

<span data-ttu-id="6659b-126">如果您无法确定表的确切行计数, 请在_lpulCount_参数的内容中返回 MAPI_W_APPROX_COUNT 和大约的行数。</span><span class="sxs-lookup"><span data-stu-id="6659b-126">If you cannot determine the table's exact row count, return MAPI_W_APPROX_COUNT and an approximate row count in the contents of the  _lpulCount_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="6659b-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="6659b-127">Notes to callers</span></span>

<span data-ttu-id="6659b-128">在调用[IMAPITable:: QueryRows](imapitable-queryrows.md)方法以检索数据之前, 可以使用**GetRowCount**来查找表所包含的行数。</span><span class="sxs-lookup"><span data-stu-id="6659b-128">Use **GetRowCount** to find out how many rows a table holds before making a call to the [IMAPITable::QueryRows](imapitable-queryrows.md) method to retrieve the data.</span></span> <span data-ttu-id="6659b-129">如果表中的行数少于20行, 则可以安全地调用**QueryPosition**以检索整个表。</span><span class="sxs-lookup"><span data-stu-id="6659b-129">If there are less than twenty rows in the table, it is safe to call **QueryPosition** to retrieve the whole table.</span></span> <span data-ttu-id="6659b-130">如果表中的行数超过20行, 请考虑对**QueryPosition**进行多次调用并限制在每次调用中检索的行数。</span><span class="sxs-lookup"><span data-stu-id="6659b-130">If there are more than twenty rows in the table, consider making multiple calls to **QueryPosition** and limit the number of rows retrieved in each call.</span></span> 
  
<span data-ttu-id="6659b-131">有些表不支持**GetRowCount** , 而是返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="6659b-131">Some tables do not support **GetRowCount** and return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="6659b-132">如果不支持**GetRowCount** , 另一种方法可能是调用[IMAPITable:: QueryPosition](imapitable-queryposition.md)。</span><span class="sxs-lookup"><span data-stu-id="6659b-132">If **GetRowCount** is not supported, an alternative might be to call [IMAPITable::QueryPosition](imapitable-queryposition.md).</span></span> <span data-ttu-id="6659b-133">使用**QueryPosition**中的结果, 您可以确定当前行与最后一行之间的关系。</span><span class="sxs-lookup"><span data-stu-id="6659b-133">With the results from **QueryPosition**, you can determine the relationship between the current row and last row.</span></span> 
  
<span data-ttu-id="6659b-134">如果**GetRowCount**返回 MAPI_E_BUSY, 因为它暂时无法检索行计数, 请调用[IMAPITable:: WaitForCompletion](imapitable-waitforcompletion.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6659b-134">When **GetRowCount** returns MAPI_E_BUSY because it is temporarily unable to retrieve a row count, call the [IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md) method.</span></span> <span data-ttu-id="6659b-135">当**WaitForCompletion**返回时, 重试对**GetRowCount**的调用。</span><span class="sxs-lookup"><span data-stu-id="6659b-135">When **WaitForCompletion** returns, retry the call to **GetRowCount**.</span></span> <span data-ttu-id="6659b-136">检测异步操作是否正在进行的另一种方法是调用[IMAPITable:: GetStatus](imapitable-getstatus.md)方法, 并检查_lpulTableState_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="6659b-136">Another way to detect whether an asynchronous operation is in progress is to call the [IMAPITable::GetStatus](imapitable-getstatus.md) method and check the contents of the  _lpulTableState_ parameter.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6659b-137">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="6659b-137">MFCMAPI reference</span></span>

<span data-ttu-id="6659b-138">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6659b-138">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6659b-139">**文件**</span><span class="sxs-lookup"><span data-stu-id="6659b-139">**File**</span></span>|<span data-ttu-id="6659b-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="6659b-140">**Function**</span></span>|<span data-ttu-id="6659b-141">**备注**</span><span class="sxs-lookup"><span data-stu-id="6659b-141">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6659b-142">MAPIFunctions</span><span class="sxs-lookup"><span data-stu-id="6659b-142">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="6659b-143">CopyFolderContents</span><span class="sxs-lookup"><span data-stu-id="6659b-143">CopyFolderContents</span></span>  <br/> |<span data-ttu-id="6659b-144">MFCMAPI 使用**IMAPITable:: GetRowCount**方法来确定源表中的行数, 以便可以分配内存以执行复制。</span><span class="sxs-lookup"><span data-stu-id="6659b-144">MFCMAPI uses the **IMAPITable::GetRowCount** method to determine how many rows are in the source table so memory can be allocated to perform the copy.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6659b-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6659b-145">See also</span></span>



[<span data-ttu-id="6659b-146">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="6659b-146">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md)
  
[<span data-ttu-id="6659b-147">IMAPITable::QueryPosition</span><span class="sxs-lookup"><span data-stu-id="6659b-147">IMAPITable::QueryPosition</span></span>](imapitable-queryposition.md)
  
[<span data-ttu-id="6659b-148">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="6659b-148">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="6659b-149">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="6659b-149">IMAPITable::WaitForCompletion</span></span>](imapitable-waitforcompletion.md)
  
[<span data-ttu-id="6659b-150">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6659b-150">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="6659b-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6659b-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

