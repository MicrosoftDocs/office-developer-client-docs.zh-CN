---
title: IMAPIWaitResult::End
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIWaitResult.End
api_type:
- COM
ms.assetid: 7463c9e8-d065-4cc3-ac01-d428b57bbc88
description: IMAPIWaitResult::End
Last modified: April 26, 2021
ms.openlocfilehash: 3432bf3b71fa7e15cb4621d461a8d4bbe962f1ba
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062030"
---
# <a name="imapiwaitresultend"></a><span data-ttu-id="40ea5-103">IMAPIWaitResult::End</span><span class="sxs-lookup"><span data-stu-id="40ea5-103">IMAPIWaitResult::End</span></span>
  
<span data-ttu-id="40ea5-104">**适用于：** Outlook 2013 |Outlook 2016 |2019</span><span class="sxs-lookup"><span data-stu-id="40ea5-104">**Applies to**: Outlook 2013 | Outlook 2016 | 2019</span></span>

<span data-ttu-id="40ea5-105">在此线程上启动 BLOCKING 调用，该调用将在指定的毫秒数已过或 MAPI 已初始化时返回。</span><span class="sxs-lookup"><span data-stu-id="40ea5-105">Initiates a BLOCKING call on this thread, which will return either when the specified number of milliseconds have elapsed or MAPI has been initialized.</span></span> <span data-ttu-id="40ea5-106">INFINITE 可用于无限等待。</span><span class="sxs-lookup"><span data-stu-id="40ea5-106">INFINITE can be used to for an infinite wait.</span></span>

```cpp
HRESULT IMAPIWaitResult::End(DWORD timeout)
```

## <a name="parameters"></a><span data-ttu-id="40ea5-107">参数</span><span class="sxs-lookup"><span data-stu-id="40ea5-107">Parameters</span></span>

<span data-ttu-id="40ea5-108">_timeout_</span><span class="sxs-lookup"><span data-stu-id="40ea5-108">_timeout_</span></span>
> <span data-ttu-id="40ea5-109">[in]等待 MAPI 初始化的毫秒数，可以传递 INFINITE (0xFFFFFFFF) 永久等待。</span><span class="sxs-lookup"><span data-stu-id="40ea5-109">[in] The number of millisecond to wait for MAPI to be initialized, you can pass INFINITE (0xFFFFFFFF) to wait forever.</span></span>

## <a name="return-value"></a><span data-ttu-id="40ea5-110">返回值</span><span class="sxs-lookup"><span data-stu-id="40ea5-110">Return value</span></span>

<span data-ttu-id="40ea5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="40ea5-111">S_OK</span></span>
> <span data-ttu-id="40ea5-112">MAPI 已成功初始化</span><span class="sxs-lookup"><span data-stu-id="40ea5-112">MAPI has been initialized successfully</span></span>

<span data-ttu-id="40ea5-113">HRESULT_FROM_WIN32 (ERROR_TIMEOUT) </span><span class="sxs-lookup"><span data-stu-id="40ea5-113">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span></span>
> <span data-ttu-id="40ea5-114">当给定非无限超时时，这表示该期间未初始化 MAPI。</span><span class="sxs-lookup"><span data-stu-id="40ea5-114">When given a non-infinite timeout this indicates MAPI was not initialized during that period.</span></span>

## <a name="remarks"></a><span data-ttu-id="40ea5-115">备注</span><span class="sxs-lookup"><span data-stu-id="40ea5-115">Remarks</span></span>
<span data-ttu-id="40ea5-116">此 API 的行为与 [IMAPInitMonitor：：Wait 完全相同](imapiinitmonitor-wait.md)。</span><span class="sxs-lookup"><span data-stu-id="40ea5-116">This API behaves exactly the same as [IMAPInitMonitor::Wait](imapiinitmonitor-wait.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="40ea5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40ea5-117">See also</span></span>

[<span data-ttu-id="40ea5-118">IMAPIInitMonitor::IsInitialized</span><span class="sxs-lookup"><span data-stu-id="40ea5-118">IMAPIInitMonitor::IsInitialized</span></span>](imapiinitmonitor-isinitialized.md)

[<span data-ttu-id="40ea5-119">IMAPIInitMonitor::BeginWait</span><span class="sxs-lookup"><span data-stu-id="40ea5-119">IMAPIInitMonitor::BeginWait</span></span>](imapiinitmonitor-beginwait.md)

[<span data-ttu-id="40ea5-120">CreateMAPIInitializationMonitor</span><span class="sxs-lookup"><span data-stu-id="40ea5-120">CreateMAPIInitializationMonitor</span></span>](createmapiinitializationmonitor.md)

[<span data-ttu-id="40ea5-121">IMAPIWaitResult</span><span class="sxs-lookup"><span data-stu-id="40ea5-121">IMAPIWaitResult</span></span>](imapiwaitresultiunknown.md)
