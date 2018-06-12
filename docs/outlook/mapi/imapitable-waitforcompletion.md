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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c7859e033924786e415f9faa9f75021ea47968c6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775723"
---
# <a name="imapitablewaitforcompletion"></a><span data-ttu-id="cf8db-103">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="cf8db-103">IMAPITable::WaitForCompletion</span></span>

  
  
<span data-ttu-id="cf8db-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cf8db-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cf8db-105">挂起处理，直到完成一个或多个异步正在进行的操作在表上。</span><span class="sxs-lookup"><span data-stu-id="cf8db-105">Suspends processing until one or more asynchronous operations in progress on the table have completed.</span></span>
  
```cpp
HRESULT WaitForCompletion(
ULONG ulFlags,
ULONG ulTimeout,
ULONG FAR * lpulTableStatus
);
```

## <a name="parameters"></a><span data-ttu-id="cf8db-106">参数</span><span class="sxs-lookup"><span data-stu-id="cf8db-106">Parameters</span></span>

 <span data-ttu-id="cf8db-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cf8db-107">_ulFlags_</span></span>
  
> <span data-ttu-id="cf8db-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="cf8db-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="cf8db-109">_ulTimeout_</span><span class="sxs-lookup"><span data-stu-id="cf8db-109">_ulTimeout_</span></span>
  
> <span data-ttu-id="cf8db-110">[in]最大等待操作完成的异步操作的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="cf8db-110">[in] Maximum number of milliseconds to wait for the asynchronous operation or operations to complete.</span></span> <span data-ttu-id="cf8db-111">若要完成之前无限期等待，设置为 0xFFFFFFFF _ulTimeout_ 。</span><span class="sxs-lookup"><span data-stu-id="cf8db-111">To wait indefinitely until completion occurs, set  _ulTimeout_ to 0xFFFFFFFF.</span></span> 
    
 <span data-ttu-id="cf8db-112">_lpulTableStatus_</span><span class="sxs-lookup"><span data-stu-id="cf8db-112">_lpulTableStatus_</span></span>
  
> <span data-ttu-id="cf8db-113">[传入、 传出]在输入有效的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="cf8db-113">[in, out] On input, either a valid pointer or NULL.</span></span> <span data-ttu-id="cf8db-114">输出，如果_lpulTableStatus_是有效的指针，它指向表的最新状态。</span><span class="sxs-lookup"><span data-stu-id="cf8db-114">On output, if  _lpulTableStatus_ is a valid pointer, it points to the most recent status of the table.</span></span> <span data-ttu-id="cf8db-115">如果_lpulTableStatus_为 NULL，则不返回任何状态信息。</span><span class="sxs-lookup"><span data-stu-id="cf8db-115">If  _lpulTableStatus_ is NULL, no status information is returned.</span></span> <span data-ttu-id="cf8db-116">如果**WaitForCompletion**返回一个失败的 HRESULT 值，则_lpulTableStatus_的内容是未定义。</span><span class="sxs-lookup"><span data-stu-id="cf8db-116">If **WaitForCompletion** returns an unsuccessful HRESULT value, the contents of  _lpulTableStatus_ are undefined.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="cf8db-117">返回值</span><span class="sxs-lookup"><span data-stu-id="cf8db-117">Return value</span></span>

<span data-ttu-id="cf8db-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf8db-118">S_OK</span></span> 
  
> <span data-ttu-id="cf8db-119">等待操作已成功。</span><span class="sxs-lookup"><span data-stu-id="cf8db-119">The wait operation was successful.</span></span>
    
<span data-ttu-id="cf8db-120">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="cf8db-120">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="cf8db-121">表不支持的异步操作完成后的等待。</span><span class="sxs-lookup"><span data-stu-id="cf8db-121">The table does not support waiting for the completion of asynchronous operations.</span></span>
    
<span data-ttu-id="cf8db-122">MAPI_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cf8db-122">MAPI_E_TIMEOUT</span></span> 
  
> <span data-ttu-id="cf8db-123">在指定时间的异步操作未完成。</span><span class="sxs-lookup"><span data-stu-id="cf8db-123">The asynchronous operation or operations did not complete in the specified time.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cf8db-124">备注</span><span class="sxs-lookup"><span data-stu-id="cf8db-124">Remarks</span></span>

<span data-ttu-id="cf8db-125">**IMAPITable::WaitForCompletion**方法挂起处理，直到表当前正在进行任何异步操作完成。</span><span class="sxs-lookup"><span data-stu-id="cf8db-125">The **IMAPITable::WaitForCompletion** method suspends processing until any asynchronous operations currently under way for the table have completed.</span></span> <span data-ttu-id="cf8db-126">**WaitForCompletion**可以允许异步操作到完全完成或运行一定数量的毫秒，由_ulTimeout_之前被打扰。</span><span class="sxs-lookup"><span data-stu-id="cf8db-126">**WaitForCompletion** can allow the asynchronous operations either to fully complete or to run for a certain number of milliseconds, as indicated by  _ulTimeout_, before being interrupted.</span></span> <span data-ttu-id="cf8db-127">若要检测正在进行的异步操作，请调用[IMAPITable::GetStatus](imapitable-getstatus.md)方法。</span><span class="sxs-lookup"><span data-stu-id="cf8db-127">To detect asynchronous operations in progress, call the [IMAPITable::GetStatus](imapitable-getstatus.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cf8db-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf8db-128">See also</span></span>



[<span data-ttu-id="cf8db-129">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="cf8db-129">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
  
[<span data-ttu-id="cf8db-130">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="cf8db-130">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md)
  
[<span data-ttu-id="cf8db-131">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="cf8db-131">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
  
[<span data-ttu-id="cf8db-132">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="cf8db-132">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="cf8db-133">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="cf8db-133">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="cf8db-134">IMAPITable: IUnknown</span><span class="sxs-lookup"><span data-stu-id="cf8db-134">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

