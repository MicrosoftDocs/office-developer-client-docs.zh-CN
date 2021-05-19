---
title: imapiinitmonitor-wait
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIINITMONITOR.Wait
api_type:
- COM
ms.assetid: ed566cae-35a2-4716-817b-54d1ba6825c6
description: IMAPIAMonitor：：Wait
Last modified: April 26, 2021
ms.openlocfilehash: ee46a2744e67804c9dfdac8d7512db1d7b07f8ba
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062009"
---
# <a name="imapiinitmonitorwait"></a><span data-ttu-id="57b16-103">IMAPIInitMonitor::Wait</span><span class="sxs-lookup"><span data-stu-id="57b16-103">IMAPIInitMonitor::Wait</span></span>
  
<span data-ttu-id="57b16-104">**适用于：** Outlook 2013 |Outlook 2016 |2019</span><span class="sxs-lookup"><span data-stu-id="57b16-104">**Applies to**: Outlook 2013 | Outlook 2016 | 2019</span></span>
  
<span data-ttu-id="57b16-105">在此线程上启动 BLOCKING 调用，该调用将在指定的毫秒数已过或 MAPI 已初始化时返回。</span><span class="sxs-lookup"><span data-stu-id="57b16-105">Initiates a BLOCKING call on this thread, which will return either when the specified number of milliseconds have elapsed or MAPI has been initialized.</span></span> <span data-ttu-id="57b16-106">INFINITE 可用于无限等待。</span><span class="sxs-lookup"><span data-stu-id="57b16-106">INFINITE can be used to for an infinite wait.</span></span>

```cpp
HRESULT IMAPIInitMonitor::Wait(DWORD timeout)
```

## <a name="parameters"></a><span data-ttu-id="57b16-107">参数</span><span class="sxs-lookup"><span data-stu-id="57b16-107">Parameters</span></span>
<span data-ttu-id="57b16-108">_timeout_</span><span class="sxs-lookup"><span data-stu-id="57b16-108">_timeout_</span></span>
> <span data-ttu-id="57b16-109">[in]等待 MAPI 初始化的毫秒数，可以传递 INFINITE (0xFFFFFFFF) 永久等待。</span><span class="sxs-lookup"><span data-stu-id="57b16-109">[in] The number of milliseconds to wait for MAPI to be initialized, you can pass INFINITE (0xFFFFFFFF) to wait forever.</span></span>

## <a name="return-value"></a><span data-ttu-id="57b16-110">返回值</span><span class="sxs-lookup"><span data-stu-id="57b16-110">Return value</span></span>

<span data-ttu-id="57b16-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="57b16-111">S_OK</span></span>
> <span data-ttu-id="57b16-112">MAPI 已成功初始化。</span><span class="sxs-lookup"><span data-stu-id="57b16-112">MAPI has been initialized successfully.</span></span>

<span data-ttu-id="57b16-113">HRESULT_FROM_WIN32 (ERROR_TIMEOUT) </span><span class="sxs-lookup"><span data-stu-id="57b16-113">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span></span>
> <span data-ttu-id="57b16-114">当给定非无限超时时，这表示该期间未初始化 MAPI。</span><span class="sxs-lookup"><span data-stu-id="57b16-114">When given a non-infinite timeout this indicates MAPI was not initialized during that period.</span></span>

## <a name="remarks"></a><span data-ttu-id="57b16-115">备注</span><span class="sxs-lookup"><span data-stu-id="57b16-115">Remarks</span></span>
  
## <a name="see-also"></a><span data-ttu-id="57b16-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57b16-116">See also</span></span>

[<span data-ttu-id="57b16-117">IMAPIInitMonitor</span><span class="sxs-lookup"><span data-stu-id="57b16-117">IMAPIInitMonitor</span></span>](imapiinitmonitoriunknown.md)

[<span data-ttu-id="57b16-118">IMAPIInitMonitor::IsInitialized</span><span class="sxs-lookup"><span data-stu-id="57b16-118">IMAPIInitMonitor::IsInitialized</span></span>](imapiinitmonitor-isinitialized.md)

[<span data-ttu-id="57b16-119">IMAPIInitMonitor::BeginWait</span><span class="sxs-lookup"><span data-stu-id="57b16-119">IMAPIInitMonitor::BeginWait</span></span>](imapiinitmonitor-beginwait.md)

[<span data-ttu-id="57b16-120">CreateMAPIInitializationMonitor</span><span class="sxs-lookup"><span data-stu-id="57b16-120">CreateMAPIInitializationMonitor</span></span>](createmapiinitializationmonitor.md)

[<span data-ttu-id="57b16-121">IMAPIWaitResult</span><span class="sxs-lookup"><span data-stu-id="57b16-121">IMAPIWaitResult</span></span>](imapiwaitresultiunknown.md)
