---
title: IOlkApptRebaserBeginRebaseAppointments
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed50422e-9edf-4b73-1789-340b70532621
description: 开始约会重定基址出现的约会，通常从IOlkApptRebaser::EndEnumerateAppointments获得一系列的任务。
ms.openlocfilehash: f0f2377f30de7688aaa4196e3a046c664c2128aa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321908"
---
# <a name="iolkapptrebaserbeginrebaseappointments"></a><span data-ttu-id="0679a-103">IOlkApptRebaser::BeginRebaseAppointments</span><span class="sxs-lookup"><span data-stu-id="0679a-103">IOlkApptRebaser::BeginRebaseAppointments</span></span>

<span data-ttu-id="0679a-104">开始约会重定基址出现的约会，通常从[IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)获得一系列的任务。</span><span class="sxs-lookup"><span data-stu-id="0679a-104">Begins a task for appointment rebasing given a list of appointments, usually obtained from [IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="0679a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="0679a-105">Quick info</span></span>

<span data-ttu-id="0679a-106">请参阅[IOlkApptRebaser](iolkapptrebaser.md)。</span><span class="sxs-lookup"><span data-stu-id="0679a-106">See [IOlkApptRebaser](iolkapptrebaser.md).</span></span>
  
```cpp
HRESULT BeginRebaseAppointments( 
    const SRowSet *pRows, 
    PFNREBASETASKPROGRESS pfnProgress, 
    PFNREBASETASKCOMPLETE pfnComplete, 
    void **ppContext);
```

## <a name="parameters"></a><span data-ttu-id="0679a-107">参数</span><span class="sxs-lookup"><span data-stu-id="0679a-107">Parameters</span></span>

<span data-ttu-id="0679a-108">_pRows_</span><span class="sxs-lookup"><span data-stu-id="0679a-108">_pRows_</span></span>
  
> <span data-ttu-id="0679a-p101">[中]所必需。指向描述需要重定基址的约会的[SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)结构的指针。这种结构通常从[IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)到以前的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0679a-p101">[in] Required. A pointer to an [SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx) structure that describes the appointments that need rebasing. This structure is usually obtained from a prior call to [IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md).</span></span>
    
<span data-ttu-id="0679a-112">_pfnProgress_</span><span class="sxs-lookup"><span data-stu-id="0679a-112">_pfnProgress_</span></span>
  
> <span data-ttu-id="0679a-p102">[中]可选。指向用于接收进度的重定基本值任务进度函数的指针。 **PFNREBASETASKPROGRESS** 是在 tzmovelib.h 中定义的。</span><span class="sxs-lookup"><span data-stu-id="0679a-p102">[in] Optional. A pointer to a rebase task progress function to receive progress. **PFNREBASETASKPROGRESS** is defined in tzmovelib.h.</span></span> 
    
<span data-ttu-id="0679a-116">_pfnComplete_</span><span class="sxs-lookup"><span data-stu-id="0679a-116">_pfnComplete_</span></span>
  
> <span data-ttu-id="0679a-p103">[] out可选。指向用于接收通知的重定基本值完成的重定基本值任务完成函数的指针。 **PFNREBASETASKCOMPLETE** 是在 tzmovelib.h 中定义的。</span><span class="sxs-lookup"><span data-stu-id="0679a-p103">[out] Optional. A pointer to a rebase task completion function to receive notification of rebase completion. **PFNREBASETASKCOMPLETE** is defined in tzmovelib.h.</span></span> 
    
<span data-ttu-id="0679a-120">_ppContext_</span><span class="sxs-lookup"><span data-stu-id="0679a-120">_ppContext_</span></span>
  
> <span data-ttu-id="0679a-p104">[] out所必需。指向返回上下文的指针的指针。通常会将此上下文传递给[IOlkApptRebaser::EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)。</span><span class="sxs-lookup"><span data-stu-id="0679a-p104">[out] Required. A pointer to a pointer to the returned context. This context will usually be passed to [IOlkApptRebaser::EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md).</span></span>
    
## <a name="return-values"></a><span data-ttu-id="0679a-124">返回值</span><span class="sxs-lookup"><span data-stu-id="0679a-124">Return values</span></span>

<span data-ttu-id="0679a-125">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="0679a-125">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0679a-126">注解</span><span class="sxs-lookup"><span data-stu-id="0679a-126">Remarks</span></span>

<span data-ttu-id="0679a-127">在新线程上执行此任务。</span><span class="sxs-lookup"><span data-stu-id="0679a-127">This task runs on a new thread.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0679a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0679a-128">See also</span></span>

- [<span data-ttu-id="0679a-129">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="0679a-129">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

