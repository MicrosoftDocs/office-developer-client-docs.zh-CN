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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cdd3db3f3779c2078b90352e19f8da6b29cffb8d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573205"
---
# <a name="imapisyncprogresscallbackdone"></a><span data-ttu-id="1bc5f-103">IMAPISyncProgressCallback::Done</span><span class="sxs-lookup"><span data-stu-id="1bc5f-103">IMAPISyncProgressCallback::Done</span></span>

  
  
<span data-ttu-id="1bc5f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1bc5f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="1bc5f-105">通知 Microsoft Outlook 同步已完成。</span><span class="sxs-lookup"><span data-stu-id="1bc5f-105">Informs Microsoft Outlook that synchronization is complete.</span></span> 
  
```cpp
HRESULT Done(
  HANDLE hThreadDoneEvent, 
  HRESULT hResult
);
```

## <a name="parameters"></a><span data-ttu-id="1bc5f-106">参数</span><span class="sxs-lookup"><span data-stu-id="1bc5f-106">Parameters</span></span>

 <span data-ttu-id="1bc5f-107">**hThreadDoneEvent**</span><span class="sxs-lookup"><span data-stu-id="1bc5f-107">**hThreadDoneEvent**</span></span>
  
> <span data-ttu-id="1bc5f-108">传递回要允许 Microsoft Outlook 关闭窗口的句事件。</span><span class="sxs-lookup"><span data-stu-id="1bc5f-108">An event that is passed back to allow Microsoft Outlook to close the handle.</span></span> <span data-ttu-id="1bc5f-109">它可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="1bc5f-109">It can be NULL.</span></span>
    
 <span data-ttu-id="1bc5f-110">**hResult**</span><span class="sxs-lookup"><span data-stu-id="1bc5f-110">**hResult**</span></span>
  
> <span data-ttu-id="1bc5f-111">HRESULT 指示进度的最终状态。</span><span class="sxs-lookup"><span data-stu-id="1bc5f-111">An HRESULT indicating final status of the progress.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1bc5f-112">返回值</span><span class="sxs-lookup"><span data-stu-id="1bc5f-112">Return value</span></span>

<span data-ttu-id="1bc5f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1bc5f-113">S_OK</span></span> 
  
> <span data-ttu-id="1bc5f-114">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="1bc5f-114">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1bc5f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bc5f-115">See also</span></span>



[<span data-ttu-id="1bc5f-116">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1bc5f-116">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)

