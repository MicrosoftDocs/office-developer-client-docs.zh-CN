---
title: IMAPITableWaitForCompletion
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.WaitForCompletion
api_type:
- COM
ms.assetid: 7663c640-396e-4720-9345-370d0856bd49
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 778ff8f36478740e5ee23ba439db1e328eca2e06
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407058"
---
# <a name="imapitablewaitforcompletion"></a><span data-ttu-id="b5c5e-103">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="b5c5e-103">IMAPITable::WaitForCompletion</span></span>

  
  
<span data-ttu-id="b5c5e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b5c5e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b5c5e-105">在表上的一个或多个异步操作完成之前暂停处理。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-105">Suspends processing until one or more asynchronous operations in progress on the table have completed.</span></span>
  
```cpp
HRESULT WaitForCompletion(
ULONG ulFlags,
ULONG ulTimeout,
ULONG FAR * lpulTableStatus
);
```

## <a name="parameters"></a><span data-ttu-id="b5c5e-106">参数</span><span class="sxs-lookup"><span data-stu-id="b5c5e-106">Parameters</span></span>

 <span data-ttu-id="b5c5e-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b5c5e-107">_ulFlags_</span></span>
  
> <span data-ttu-id="b5c5e-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="b5c5e-109">_ulTimeout_</span><span class="sxs-lookup"><span data-stu-id="b5c5e-109">_ulTimeout_</span></span>
  
> <span data-ttu-id="b5c5e-110">[in]等待异步操作完成的最大毫秒数。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-110">[in] Maximum number of milliseconds to wait for the asynchronous operation or operations to complete.</span></span> <span data-ttu-id="b5c5e-111">若要无限期地等待直到完成，请设置  _ulTimeout_ 以0xFFFFFFFF。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-111">To wait indefinitely until completion occurs, set  _ulTimeout_ to 0xFFFFFFFF.</span></span> 
    
 <span data-ttu-id="b5c5e-112">_lpulTableStatus_</span><span class="sxs-lookup"><span data-stu-id="b5c5e-112">_lpulTableStatus_</span></span>
  
> <span data-ttu-id="b5c5e-113">[in， out]在输入时，有效指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-113">[in, out] On input, either a valid pointer or NULL.</span></span> <span data-ttu-id="b5c5e-114">在输出上，如果  _lpulTableStatus_ 是有效的指针，则它指向表的最新状态。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-114">On output, if  _lpulTableStatus_ is a valid pointer, it points to the most recent status of the table.</span></span> <span data-ttu-id="b5c5e-115">如果  _lpulTableStatus_ 为 NULL，则不返回任何状态信息。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-115">If  _lpulTableStatus_ is NULL, no status information is returned.</span></span> <span data-ttu-id="b5c5e-116">如果 **WaitForCompletion** 返回不成功的 HRESULT 值，  _则 lpulTableStatus_ 的内容未定义。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-116">If **WaitForCompletion** returns an unsuccessful HRESULT value, the contents of  _lpulTableStatus_ are undefined.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b5c5e-117">返回值</span><span class="sxs-lookup"><span data-stu-id="b5c5e-117">Return value</span></span>

<span data-ttu-id="b5c5e-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5c5e-118">S_OK</span></span> 
  
> <span data-ttu-id="b5c5e-119">等待操作成功。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-119">The wait operation was successful.</span></span>
    
<span data-ttu-id="b5c5e-120">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b5c5e-120">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="b5c5e-121">该表不支持等待异步操作完成。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-121">The table does not support waiting for the completion of asynchronous operations.</span></span>
    
<span data-ttu-id="b5c5e-122">MAPI_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b5c5e-122">MAPI_E_TIMEOUT</span></span> 
  
> <span data-ttu-id="b5c5e-123">异步操作没有在指定的时间完成。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-123">The asynchronous operation or operations did not complete in the specified time.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b5c5e-124">备注</span><span class="sxs-lookup"><span data-stu-id="b5c5e-124">Remarks</span></span>

<span data-ttu-id="b5c5e-125">**IMAPITable：：WaitForCompletion 方法将暂停** 处理，直到表当前正在执行的任何异步操作完成。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-125">The **IMAPITable::WaitForCompletion** method suspends processing until any asynchronous operations currently under way for the table have completed.</span></span> <span data-ttu-id="b5c5e-126">**WaitForCompletion** 可以允许异步操作完全完成或运行一定数量的毫秒，如  _ulTimeout_ 所指示，然后再中断。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-126">**WaitForCompletion** can allow the asynchronous operations either to fully complete or to run for a certain number of milliseconds, as indicated by  _ulTimeout_, before being interrupted.</span></span> <span data-ttu-id="b5c5e-127">若要检测正在进行中的异步操作，请调用 [IMAPITable：：GetStatus](imapitable-getstatus.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b5c5e-127">To detect asynchronous operations in progress, call the [IMAPITable::GetStatus](imapitable-getstatus.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b5c5e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5c5e-128">See also</span></span>



[<span data-ttu-id="b5c5e-129">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="b5c5e-129">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
  
[<span data-ttu-id="b5c5e-130">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="b5c5e-130">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md)
  
[<span data-ttu-id="b5c5e-131">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="b5c5e-131">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
  
[<span data-ttu-id="b5c5e-132">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="b5c5e-132">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="b5c5e-133">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="b5c5e-133">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="b5c5e-134">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b5c5e-134">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

