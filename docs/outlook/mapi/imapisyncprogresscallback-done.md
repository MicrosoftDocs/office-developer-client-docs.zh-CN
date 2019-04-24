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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341270"
---
# <a name="imapisyncprogresscallbackdone"></a><span data-ttu-id="e939f-103">IMAPISyncProgressCallback::Done</span><span class="sxs-lookup"><span data-stu-id="e939f-103">IMAPISyncProgressCallback::Done</span></span>

  
  
<span data-ttu-id="e939f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e939f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="e939f-105">通知 Microsoft Outlook 同步已完成。</span><span class="sxs-lookup"><span data-stu-id="e939f-105">Informs Microsoft Outlook that synchronization is complete.</span></span> 
  
```cpp
HRESULT Done(
  HANDLE hThreadDoneEvent, 
  HRESULT hResult
);
```

## <a name="parameters"></a><span data-ttu-id="e939f-106">参数</span><span class="sxs-lookup"><span data-stu-id="e939f-106">Parameters</span></span>

 <span data-ttu-id="e939f-107">**hThreadDoneEvent**</span><span class="sxs-lookup"><span data-stu-id="e939f-107">**hThreadDoneEvent**</span></span>
  
> <span data-ttu-id="e939f-108">传递回的事件, 以允许 Microsoft Outlook 关闭该句柄。</span><span class="sxs-lookup"><span data-stu-id="e939f-108">An event that is passed back to allow Microsoft Outlook to close the handle.</span></span> <span data-ttu-id="e939f-109">它可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="e939f-109">It can be NULL.</span></span>
    
 <span data-ttu-id="e939f-110">**hResult**</span><span class="sxs-lookup"><span data-stu-id="e939f-110">**hResult**</span></span>
  
> <span data-ttu-id="e939f-111">HRESULT, 用于指示进度的最终状态。</span><span class="sxs-lookup"><span data-stu-id="e939f-111">An HRESULT indicating final status of the progress.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e939f-112">返回值</span><span class="sxs-lookup"><span data-stu-id="e939f-112">Return value</span></span>

<span data-ttu-id="e939f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e939f-113">S_OK</span></span> 
  
> <span data-ttu-id="e939f-114">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="e939f-114">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e939f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e939f-115">See also</span></span>



[<span data-ttu-id="e939f-116">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e939f-116">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)

