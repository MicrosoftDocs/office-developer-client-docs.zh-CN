---
title: IMAPISyncProgressCallbackDone
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISyncProgressCallback.Done
api_type:
- COM
ms.assetid: aaa8eb56-f22f-4c5a-a224-807ff001e0ca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8d397e12b8b24c5031e6e6d89d98134d487a815b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422346"
---
# <a name="imapisyncprogresscallbackdone"></a><span data-ttu-id="d7e5e-103">IMAPISyncProgressCallback::Done</span><span class="sxs-lookup"><span data-stu-id="d7e5e-103">IMAPISyncProgressCallback::Done</span></span>

  
  
<span data-ttu-id="d7e5e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d7e5e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="d7e5e-105">通知 Microsoft Outlook同步已完成。</span><span class="sxs-lookup"><span data-stu-id="d7e5e-105">Informs Microsoft Outlook that synchronization is complete.</span></span> 
  
```cpp
HRESULT Done(
  HANDLE hThreadDoneEvent, 
  HRESULT hResult
);
```

## <a name="parameters"></a><span data-ttu-id="d7e5e-106">参数</span><span class="sxs-lookup"><span data-stu-id="d7e5e-106">Parameters</span></span>

 <span data-ttu-id="d7e5e-107">**hThreadDoneEvent**</span><span class="sxs-lookup"><span data-stu-id="d7e5e-107">**hThreadDoneEvent**</span></span>
  
> <span data-ttu-id="d7e5e-108">传递回以允许 Microsoft Outlook关闭句柄的事件。</span><span class="sxs-lookup"><span data-stu-id="d7e5e-108">An event that is passed back to allow Microsoft Outlook to close the handle.</span></span> <span data-ttu-id="d7e5e-109">它可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="d7e5e-109">It can be NULL.</span></span>
    
 <span data-ttu-id="d7e5e-110">**hResult**</span><span class="sxs-lookup"><span data-stu-id="d7e5e-110">**hResult**</span></span>
  
> <span data-ttu-id="d7e5e-111">一个 HRESULT，指示进度的最终状态。</span><span class="sxs-lookup"><span data-stu-id="d7e5e-111">An HRESULT indicating final status of the progress.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d7e5e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="d7e5e-112">Return value</span></span>

<span data-ttu-id="d7e5e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7e5e-113">S_OK</span></span> 
  
> <span data-ttu-id="d7e5e-114">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="d7e5e-114">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d7e5e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7e5e-115">See also</span></span>



[<span data-ttu-id="d7e5e-116">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d7e5e-116">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)

