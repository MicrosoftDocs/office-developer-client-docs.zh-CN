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
ms.openlocfilehash: e0a34e1cc0b1da1b5e2127d0697cce472c8530c5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775677"
---
# <a name="imapisyncprogresscallbackdone"></a><span data-ttu-id="1ffe0-103">IMAPISyncProgressCallback::Done</span><span class="sxs-lookup"><span data-stu-id="1ffe0-103">IMAPISyncProgressCallback::Done</span></span>

  
  
<span data-ttu-id="1ffe0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1ffe0-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="1ffe0-105">通知 Microsoft Outlook 同步已完成。</span><span class="sxs-lookup"><span data-stu-id="1ffe0-105">Informs Microsoft Outlook that synchronization is complete.</span></span> 
  
```cpp
HRESULT Done(
  HANDLE hThreadDoneEvent, 
  HRESULT hResult
);
```

## <a name="parameters"></a><span data-ttu-id="1ffe0-106">参数</span><span class="sxs-lookup"><span data-stu-id="1ffe0-106">Parameters</span></span>

 <span data-ttu-id="1ffe0-107">**hThreadDoneEvent**</span><span class="sxs-lookup"><span data-stu-id="1ffe0-107">**hThreadDoneEvent**</span></span>
  
> <span data-ttu-id="1ffe0-108">传递回要允许 Microsoft Outlook 关闭窗口的句事件。</span><span class="sxs-lookup"><span data-stu-id="1ffe0-108">An event that is passed back to allow Microsoft Outlook to close the handle.</span></span> <span data-ttu-id="1ffe0-109">它可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="1ffe0-109">It can be NULL.</span></span>
    
 <span data-ttu-id="1ffe0-110">**hResult**</span><span class="sxs-lookup"><span data-stu-id="1ffe0-110">**hResult**</span></span>
  
> <span data-ttu-id="1ffe0-111">HRESULT 指示进度的最终状态。</span><span class="sxs-lookup"><span data-stu-id="1ffe0-111">An HRESULT indicating final status of the progress.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1ffe0-112">返回值</span><span class="sxs-lookup"><span data-stu-id="1ffe0-112">Return value</span></span>

<span data-ttu-id="1ffe0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ffe0-113">S_OK</span></span> 
  
> <span data-ttu-id="1ffe0-114">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="1ffe0-114">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1ffe0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ffe0-115">See also</span></span>



[<span data-ttu-id="1ffe0-116">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1ffe0-116">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)

