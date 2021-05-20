---
title: CreateMAPIInitializationMonitor
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIWAITRESULT
api_type:
- COM
ms.assetid: 32a9758a-395d-4526-9610-3e4eeaf78c96
description: MAPI 初始化监视器
Last modified: April 26, 2021
ms.openlocfilehash: da7c48a6b026ccd4cbe4cbac192a1a0760202835
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062051"
---
# <a name="createmapiinitializationmonitor"></a><span data-ttu-id="d5ba2-103">CreateMAPIInitializationMonitor</span><span class="sxs-lookup"><span data-stu-id="d5ba2-103">CreateMAPIInitializationMonitor</span></span>

<span data-ttu-id="d5ba2-104">**适用于：** Outlook 2016 |Outlook 2019 年</span><span class="sxs-lookup"><span data-stu-id="d5ba2-104">**Applies to**: Outlook 2016 | Outlook 2019</span></span>
  
## <a name="mapi-initialization-monitor"></a><span data-ttu-id="d5ba2-105">MAPI 初始化监视器</span><span class="sxs-lookup"><span data-stu-id="d5ba2-105">MAPI Initialization Monitor</span></span>

<span data-ttu-id="d5ba2-106">有时，使用 MAPI 的应用程序可能想要知道初始化何时完成。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-106">There are times when an application which consumes MAPI might want to know when the initialization is completed.</span></span> <span data-ttu-id="d5ba2-107">例如，它有多个线程，这些线程可以初始化 MAPI，或者为了响应正在初始化的 MAPI，应用程序希望执行一些工作，但不希望始终旋转 MAPI 堆栈。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-107">For example, it have multiple threads which could initialize MAPI, or in response to MAPI being initialize the application would like perform some work, but does not want to always spin up the MAPI stack.</span></span> <span data-ttu-id="d5ba2-108">初始化监视器通过从 (导出的函数OLMAPI32.DLL) 和下面介绍的一些简单接口提供此功能。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-108">The initialization monitor provides this functionality through a function (exported from OLMAPI32.DLL) and a couple of simple interfaces described below.</span></span>

<span data-ttu-id="d5ba2-109">这是从 OLMAPI32.DLL导出的入口点，这允许调用方检索接口以查询当前初始化状态、设置回调以完成初始化或阻止当前线程，直到完成。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-109">This is entry point exported from OLMAPI32.DLL this allows the caller to retrieve an interface to query the current initialization state, setup a callback for initialization completion or block the current thread until has completed.</span></span> <span data-ttu-id="d5ba2-110">从此 API 返回的对象可重用且线程安全，并且可以从任何线程调用，而不只是从检索它的线程调用。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-110">The object returned from this API is reusable and thread safe and can be invoked from any thread, not just thread which retrieved it.</span></span> <span data-ttu-id="d5ba2-111">此外，与 MAPI 公开的其他对象不同，只要加载 DLL，此对象就有效，它可以跨初始化会话重新使用，并且可在调用 MAPIInitialize 之前或之后使用。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-111">Also, unlike other objects exposed from MAPI, this object is valid as long as the DLL is loaded, it can be re-used across initialization sessions and can be consumed before or after MAPIInitialize has been called.</span></span> <span data-ttu-id="d5ba2-112">通过 COM 标准 HRESULT 返回成功或失败，并将 out 参数分配给 IMAPIInitMonitor 的实例。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-112">Returns success or failure through an COM standard HRESULT, and assigns an out parameter to an instance of IMAPIInitMonitor.</span></span>

```cpp
HRESULT CreateMAPIInitializationMonitor(IMAPIInitMonitor** ppInitMonitor); 
```
#### <a name="hresult-stdapicalltype-createmapiinitializationmonitorimapiinitmonitor-ppinitmonitor"></a><span data-ttu-id="d5ba2-113">HRESULT STDAPICALLTYPE CreateMapiInitializationMonitor (IMAPIInitMonitor ppInitMonitor) </span><span class="sxs-lookup"><span data-stu-id="d5ba2-113">HRESULT STDAPICALLTYPE CreateMapiInitializationMonitor(IMAPIInitMonitor ppInitMonitor)</span></span>

<span data-ttu-id="d5ba2-114">通过从 OLMAPI32.DLL 导出的此入口点，调用方可以检索接口以查询当前初始化状态、设置初始化完成回调或阻止当前线程直到完成。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-114">This entry point exported from OLMAPI32.DLL allows the caller to retrieve an interface to query the current initialization state, setup a callback for initialization completion or block the current thread until has completed.</span></span> <span data-ttu-id="d5ba2-115">从此 API 返回的对象可重用且线程安全，并且可以从任何线程调用，而不只是从检索它的线程调用。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-115">The object returned from this API is reusable and thread safe and can be invoked from any thread, not just thread which retrieved it.</span></span> <span data-ttu-id="d5ba2-116">此外，与 MAPI 公开的其他对象不同，只要加载 DLL，此对象就有效，它可以跨初始化会话重新使用，并且可在调用 MAPIInitialize 之前或之后使用。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-116">Also, unlike other objects exposed from MAPI, this object is valid as long as the DLL is loaded, it can be re-used across initialization sessions and can be consumed before or after MAPIInitialize has been called.</span></span> <span data-ttu-id="d5ba2-117">通过 COM 标准 HRESULT 返回成功或失败，并将 out 参数分配给 IMAPIInitMonitor 的实例。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-117">Returns success or failure through an COM standard HRESULT, and assigns an out parameter to an instance of IMAPIInitMonitor.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d5ba2-118">快速信息</span><span class="sxs-lookup"><span data-stu-id="d5ba2-118">Quick info</span></span>

| <span data-ttu-id="d5ba2-119">标识符</span><span class="sxs-lookup"><span data-stu-id="d5ba2-119">identifier</span></span> | <span data-ttu-id="d5ba2-120">result</span><span class="sxs-lookup"><span data-stu-id="d5ba2-120">result</span></span> |
|:-----|:-----|
|<span data-ttu-id="d5ba2-121">导出者：</span><span class="sxs-lookup"><span data-stu-id="d5ba2-121">Exported by:</span></span>  <br/> |<span data-ttu-id="d5ba2-122">olmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="d5ba2-122">olmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="d5ba2-123">调用者：</span><span class="sxs-lookup"><span data-stu-id="d5ba2-123">Called by:</span></span>  <br/> |<span data-ttu-id="d5ba2-124">客户端</span><span class="sxs-lookup"><span data-stu-id="d5ba2-124">Client</span></span>  <br/> |
|<span data-ttu-id="d5ba2-125">实现者：</span><span class="sxs-lookup"><span data-stu-id="d5ba2-125">Implemented by:</span></span>  <br/> |<span data-ttu-id="d5ba2-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="d5ba2-126">Outlook</span></span>  <br/> |

## <a name="parameters"></a><span data-ttu-id="d5ba2-127">参数</span><span class="sxs-lookup"><span data-stu-id="d5ba2-127">Parameters</span></span>
  
 <span data-ttu-id="d5ba2-128">_ppInitMonitor_</span><span class="sxs-lookup"><span data-stu-id="d5ba2-128">_ppInitMonitor_</span></span>
> <span data-ttu-id="d5ba2-129">[out]用于接收新创建的 MAPI 初始化监视器实例的指针。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-129">[out] A pointer to receive the newly created instance of the MAPI initialization monitor.</span></span>
  
## <a name="return-values"></a><span data-ttu-id="d5ba2-130">返回值</span><span class="sxs-lookup"><span data-stu-id="d5ba2-130">Return values</span></span>

<span data-ttu-id="d5ba2-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5ba2-131">S_OK</span></span>
> <span data-ttu-id="d5ba2-132">已成功创建初始化监视器的新实例。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-132">A new instance of the initialization monitor was created successfully.</span></span>

<span data-ttu-id="d5ba2-133">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d5ba2-133">E_OUTOFMEMORY</span></span>
> <span data-ttu-id="d5ba2-134">没有足够的内存来为新对象创建文件。</span><span class="sxs-lookup"><span data-stu-id="d5ba2-134">There was not enough memory to crate a new object.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5ba2-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5ba2-135">See also</span></span>
[<span data-ttu-id="d5ba2-136">IMAPIInitMonitor</span><span class="sxs-lookup"><span data-stu-id="d5ba2-136">IMAPIInitMonitor</span></span>](imapiinitmonitoriunknown.md)

[<span data-ttu-id="d5ba2-137">IMAPIWaitResult</span><span class="sxs-lookup"><span data-stu-id="d5ba2-137">IMAPIWaitResult</span></span>](imapiwaitresultiunknown.md)
