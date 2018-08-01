---
title: IOlkApptRebaserBeginRebaseAppointments
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed50422e-9edf-4b73-1789-340b70532621
description: 开始约会重定基址出现的约会，通常从IOlkApptRebaser::EndEnumerateAppointments获得一系列的任务。
ms.openlocfilehash: 2becb305eebe448e2adecf91c2a111f86d97fe50
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774373"
---
# <a name="iolkapptrebaserbeginrebaseappointments"></a><span data-ttu-id="38153-103">IOlkApptRebaser::BeginRebaseAppointments</span><span class="sxs-lookup"><span data-stu-id="38153-103">IOlkApptRebaser::BeginRebaseAppointments</span></span>

<span data-ttu-id="38153-104">开始约会重定基址出现的约会，通常从[IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)获得一系列的任务。</span><span class="sxs-lookup"><span data-stu-id="38153-104">Begins a task for appointment rebasing given a list of appointments, usually obtained from [IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="38153-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="38153-105">Quick info</span></span>

<span data-ttu-id="38153-106">请参阅[IOlkApptRebaser](iolkapptrebaser.md)。</span><span class="sxs-lookup"><span data-stu-id="38153-106">See [IOlkApptRebaser](iolkapptrebaser.md).</span></span>
  
```cpp
HRESULT BeginRebaseAppointments( 
    const SRowSet *pRows, 
    PFNREBASETASKPROGRESS pfnProgress, 
    PFNREBASETASKCOMPLETE pfnComplete, 
    void **ppContext);
```

## <a name="parameters"></a><span data-ttu-id="38153-107">参数</span><span class="sxs-lookup"><span data-stu-id="38153-107">Parameters</span></span>

<span data-ttu-id="38153-108">_pRows_</span><span class="sxs-lookup"><span data-stu-id="38153-108">_pRows_</span></span>
  
> <span data-ttu-id="38153-p101">[中]所必需。指向描述需要重定基址的约会的[SRowSet](http://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)结构的指针。这种结构通常从[IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)到以前的呼叫。</span><span class="sxs-lookup"><span data-stu-id="38153-p101">[in] Required. A pointer to an [SRowSet](http://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx) structure that describes the appointments that need rebasing. This structure is usually obtained from a prior call to [IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md).</span></span>
    
<span data-ttu-id="38153-112">_pfnProgress_</span><span class="sxs-lookup"><span data-stu-id="38153-112">_pfnProgress_</span></span>
  
> <span data-ttu-id="38153-p102">[中]可选。指向用于接收进度的重定基本值任务进度函数的指针。 **PFNREBASETASKPROGRESS** 是在 tzmovelib.h 中定义的。</span><span class="sxs-lookup"><span data-stu-id="38153-p102">[in] Optional. A pointer to a rebase task progress function to receive progress. **PFNREBASETASKPROGRESS** is defined in tzmovelib.h.</span></span> 
    
<span data-ttu-id="38153-116">_pfnComplete_</span><span class="sxs-lookup"><span data-stu-id="38153-116">_pfnComplete_</span></span>
  
> <span data-ttu-id="38153-p103">[] out可选。指向用于接收通知的重定基本值完成的重定基本值任务完成函数的指针。 **PFNREBASETASKCOMPLETE** 是在 tzmovelib.h 中定义的。</span><span class="sxs-lookup"><span data-stu-id="38153-p103">[out] Optional. A pointer to a rebase task completion function to receive notification of rebase completion. **PFNREBASETASKCOMPLETE** is defined in tzmovelib.h.</span></span> 
    
<span data-ttu-id="38153-120">_ppContext_</span><span class="sxs-lookup"><span data-stu-id="38153-120">_ppContext_</span></span>
  
> <span data-ttu-id="38153-p104">[] out所必需。指向返回上下文的指针的指针。通常会将此上下文传递给[IOlkApptRebaser::EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)。</span><span class="sxs-lookup"><span data-stu-id="38153-p104">[out] Required. A pointer to a pointer to the returned context. This context will usually be passed to [IOlkApptRebaser::EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md).</span></span>
    
## <a name="return-values"></a><span data-ttu-id="38153-124">返回值</span><span class="sxs-lookup"><span data-stu-id="38153-124">Return values</span></span>

<span data-ttu-id="38153-125">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="38153-125">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="38153-126">注释</span><span class="sxs-lookup"><span data-stu-id="38153-126">Remarks</span></span>

<span data-ttu-id="38153-127">在新线程上执行此任务。</span><span class="sxs-lookup"><span data-stu-id="38153-127">This task runs on a new thread.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="38153-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38153-128">See also</span></span>

- [<span data-ttu-id="38153-129">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="38153-129">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

