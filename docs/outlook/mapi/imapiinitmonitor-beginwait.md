---
title: imapiinitmonitor-beginwait
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIINITMONITOR.BeginWait
api_type:
- COM
ms.assetid: 71f565a9-651c-42b5-9102-91b728b681ae
description: IMAPIInitMonitor：：BeginWait"
Last modified: April 26, 2021
ms.openlocfilehash: 43a88507cbfc23b3b842f51e69eb4bd791bcfda8
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062016"
---
# <a name="imapiinitmonitorbeginwait"></a><span data-ttu-id="8a69d-103">IMAPIInitMonitor：：BeginWait</span><span class="sxs-lookup"><span data-stu-id="8a69d-103">IMAPIInitMonitor::BeginWait</span></span>
  
<span data-ttu-id="8a69d-104">**适用于：** Outlook 2016 |2019</span><span class="sxs-lookup"><span data-stu-id="8a69d-104">**Applies to**: Outlook 2016 | 2019</span></span>
  
<span data-ttu-id="8a69d-105">开始等待 MAPI 初始化或经过的指定毫秒数。</span><span class="sxs-lookup"><span data-stu-id="8a69d-105">Start a wait for MAPI initialization or the specified number of milliseconds to elapse.</span></span> <span data-ttu-id="8a69d-106">这将返回 IMAPIWaitResult 接口，该接口应调用 **IMAPIWaitResult：：End** 以启动等待。</span><span class="sxs-lookup"><span data-stu-id="8a69d-106">This returns an IMAPIWaitResult interface which should have **IMAPIWaitResult::End** called in order initiate the wait.</span></span> <span data-ttu-id="8a69d-107">这允许调用方控制我们在等待时被阻止的线程。</span><span class="sxs-lookup"><span data-stu-id="8a69d-107">This allows the caller to control which thread is blocked while we are waiting.</span></span>

```cpp
HRESULT IMAPIInitMonitor::BeginWait(DWORD timeout, IMAPIWaitResult** ppResult)
```

## <a name="parameters"></a><span data-ttu-id="8a69d-108">参数</span><span class="sxs-lookup"><span data-stu-id="8a69d-108">Parameters</span></span>
<span data-ttu-id="8a69d-109">_timeout_</span><span class="sxs-lookup"><span data-stu-id="8a69d-109">_timeout_</span></span>
><span data-ttu-id="8a69d-110">[in]等待 MAPI 初始化的毫秒数，可以设置为 INFINITE 以永久等待初始化发生。</span><span class="sxs-lookup"><span data-stu-id="8a69d-110">[in] The number of millisecond to wait for MAPI initialization, this can set to INFINITE to wait forever for the initialization to happen.</span></span>

<span data-ttu-id="8a69d-111">_ppResult_</span><span class="sxs-lookup"><span data-stu-id="8a69d-111">_ppResult_</span></span>
><span data-ttu-id="8a69d-112">[out]用于接收新创建的等待接口的指针。</span><span class="sxs-lookup"><span data-stu-id="8a69d-112">[out] A pointer to recieve the newly create wait interface.</span></span>

## <a name="return-value"></a><span data-ttu-id="8a69d-113">返回值</span><span class="sxs-lookup"><span data-stu-id="8a69d-113">Return value</span></span>
<span data-ttu-id="8a69d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a69d-114">S_OK</span></span>
><span data-ttu-id="8a69d-115">已成功启动等待操作。</span><span class="sxs-lookup"><span data-stu-id="8a69d-115">A wait operation was successfully started.</span></span>

<span data-ttu-id="8a69d-116">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8a69d-116">E_OUTOFMEMORY</span></span>
><span data-ttu-id="8a69d-117">没有足够的内存创建新对象</span><span class="sxs-lookup"><span data-stu-id="8a69d-117">There was not enough memory to create a new object</span></span>

## <a name="remarks"></a><span data-ttu-id="8a69d-118">备注</span><span class="sxs-lookup"><span data-stu-id="8a69d-118">Remarks</span></span>
<span data-ttu-id="8a69d-119">此 API 为调用方提供了一个 (接口，该接口是线程) ，可用于启动阻止等待 MAPI 初始化。</span><span class="sxs-lookup"><span data-stu-id="8a69d-119">This API provided the caller with an interface (which is thread-safe) which can be used initiate a blocking wait for MAPI initialization.</span></span> <span data-ttu-id="8a69d-120">这使使用者能够确定等待其应用程序的最佳等待时间。</span><span class="sxs-lookup"><span data-stu-id="8a69d-120">This allows the consumer to deterime the best wait to wait for thier application.</span></span>   <span data-ttu-id="8a69d-121">调用 IMAPIWaitResult：：End 的行为与调用 IMAPIInitMonitor：：Wait 的行为相同。</span><span class="sxs-lookup"><span data-stu-id="8a69d-121">The behavior of calling IMAPIWaitResult::End is identical to calling IMAPIInitMonitor::Wait.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a69d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a69d-122">See also</span></span>

[<span data-ttu-id="8a69d-123">IMAPIInitMonitor</span><span class="sxs-lookup"><span data-stu-id="8a69d-123">IMAPIInitMonitor</span></span>](imapiinitmonitoriunknown.md)

[<span data-ttu-id="8a69d-124">IMAPIInitMonitor：：IsInitialized</span><span class="sxs-lookup"><span data-stu-id="8a69d-124">IMAPIInitMonitor::IsInitialized</span></span>](imapiinitmonitor-isinitialized.md)

[<span data-ttu-id="8a69d-125">IMAPIInitMonitor：：Wait</span><span class="sxs-lookup"><span data-stu-id="8a69d-125">IMAPIInitMonitor::Wait</span></span>](imapiinitmonitor-wait.md)

[<span data-ttu-id="8a69d-126">CreateMAPIInitializationMonitor</span><span class="sxs-lookup"><span data-stu-id="8a69d-126">CreateMAPIInitializationMonitor</span></span>](createmapiinitializationmonitor.md)

[<span data-ttu-id="8a69d-127">IMAPIWaitResult</span><span class="sxs-lookup"><span data-stu-id="8a69d-127">IMAPIWaitResult</span></span>](imapiwaitresultiunknown.md)
