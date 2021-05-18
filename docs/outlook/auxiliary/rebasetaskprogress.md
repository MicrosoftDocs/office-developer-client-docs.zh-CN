---
title: RebaseTaskProgress
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8b8368d2-b04b-42a5-fdc3-955fc873c2f5
description: 报告约会的枚举和重定义值的进度。
ms.openlocfilehash: e5df0cd6df10ab86b1a125b9807637438976726f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326451"
---
# <a name="rebasetaskprogress"></a><span data-ttu-id="49351-103">RebaseTaskProgress</span><span class="sxs-lookup"><span data-stu-id="49351-103">RebaseTaskProgress</span></span>

<span data-ttu-id="49351-104">报告约会的枚举和重定义值的进度。</span><span class="sxs-lookup"><span data-stu-id="49351-104">Reports progress for enumeration and rebasing of appointments.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="49351-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="49351-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="49351-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="49351-106">Header file:</span></span>  <br/> |<span data-ttu-id="49351-107">tzmovelib.h</span><span class="sxs-lookup"><span data-stu-id="49351-107">tzmovelib.h</span></span>  <br/> |
|<span data-ttu-id="49351-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="49351-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="49351-109">MAPI 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="49351-109">MAPI client applications</span></span>  <br/> |
|<span data-ttu-id="49351-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="49351-110">Called by:</span></span>  <br/> |<span data-ttu-id="49351-111">Outlook重做对象</span><span class="sxs-lookup"><span data-stu-id="49351-111">Outlook rebasing object</span></span>  <br/> |
|<span data-ttu-id="49351-112">指针类型：</span><span class="sxs-lookup"><span data-stu-id="49351-112">Pointer type:</span></span>  <br/> |<span data-ttu-id="49351-113">tzmovelib.h 中定义的 **PFNREBASETASKPROGRESS**</span><span class="sxs-lookup"><span data-stu-id="49351-113">**PFNREBASETASKPROGRESS** as defined in tzmovelib.h</span></span>  <br/> |
   
```cpp
void STDAPICALLTYPE RebaseTaskProgress(  
    ULONG ulMin, 
    ULONG ulMax, 
    ULONG ulCur, 
    REBASE_APPT_STATE State, 
    const SRow* pRowCur); 

```

## <a name="parameters"></a><span data-ttu-id="49351-114">参数</span><span class="sxs-lookup"><span data-stu-id="49351-114">Parameters</span></span>

<span data-ttu-id="49351-115">_ulMin_</span><span class="sxs-lookup"><span data-stu-id="49351-115">_ulMin_</span></span>
  
> <span data-ttu-id="49351-116">[in]正在处理的约会范围的低端。</span><span class="sxs-lookup"><span data-stu-id="49351-116">[in] The low end of the range of appointments being processed.</span></span> <span data-ttu-id="49351-117">通常为零。</span><span class="sxs-lookup"><span data-stu-id="49351-117">It is usually zero.</span></span>
    
<span data-ttu-id="49351-118">_ulMax_</span><span class="sxs-lookup"><span data-stu-id="49351-118">_ulMax_</span></span>
  
> <span data-ttu-id="49351-119">[in]正在处理的约会范围的较高端。</span><span class="sxs-lookup"><span data-stu-id="49351-119">[in] The high end of the range of appointments being processed.</span></span> <span data-ttu-id="49351-120">通常是正在处理的日历文件夹中的项目数。</span><span class="sxs-lookup"><span data-stu-id="49351-120">It is usually the number of items in the calendar folder being processed.</span></span>
    
<span data-ttu-id="49351-121">_ulCur_</span><span class="sxs-lookup"><span data-stu-id="49351-121">_ulCur_</span></span>
  
> <span data-ttu-id="49351-122">[in]当前正在处理的项目。</span><span class="sxs-lookup"><span data-stu-id="49351-122">[in] The current item being processed.</span></span>
    
<span data-ttu-id="49351-123">_State_</span><span class="sxs-lookup"><span data-stu-id="49351-123">_State_</span></span>
  
> <span data-ttu-id="49351-124">[in]一个值，指示正在处理的项目的状态。</span><span class="sxs-lookup"><span data-stu-id="49351-124">[in] A value that indicates the status of the item being processed.</span></span> <span data-ttu-id="49351-125">枚举 **REBASE_APPT_STATE** tzmovelib.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="49351-125">The enumeration **REBASE_APPT_STATE** is defined in tzmovelib.h.</span></span>  <span data-ttu-id="49351-126">_State_ 是以下值之一：</span><span class="sxs-lookup"><span data-stu-id="49351-126">_State_ is one of the following values:</span></span> 
    
   - <span data-ttu-id="49351-127">**REBASE_APPT_STATE_SCANNING_EXAMINING** — 扫描和检查项目。</span><span class="sxs-lookup"><span data-stu-id="49351-127">**REBASE_APPT_STATE_SCANNING_EXAMINING** —Scanning and examining an item.</span></span> 
    
   - <span data-ttu-id="49351-128">**REBASE_APPT_STATE_SCANNING_FOUND** — 扫描并找到项目。</span><span class="sxs-lookup"><span data-stu-id="49351-128">**REBASE_APPT_STATE_SCANNING_FOUND** —Scanning and found an item.</span></span> 
    
   - <span data-ttu-id="49351-129">**REBASE_APPT_STATE_BEGIN** — 修复和启动项目。</span><span class="sxs-lookup"><span data-stu-id="49351-129">**REBASE_APPT_STATE_BEGIN** —Fixing and starting an item.</span></span> 
    
   - <span data-ttu-id="49351-130">**REBASE_APPT_STATE_REBASING** — 固定和调整项目。</span><span class="sxs-lookup"><span data-stu-id="49351-130">**REBASE_APPT_STATE_REBASING** —Fixing and adjusting an item.</span></span> 
    
   - <span data-ttu-id="49351-131">**REBASE_APPT_STATE_SENDING** — 修复和发送会议更新。</span><span class="sxs-lookup"><span data-stu-id="49351-131">**REBASE_APPT_STATE_SENDING** —Fixing and sending a meeting update.</span></span> 
    
   - <span data-ttu-id="49351-132">**REBASE_APPT_STATE_DONE** — 修复项目并完成。</span><span class="sxs-lookup"><span data-stu-id="49351-132">**REBASE_APPT_STATE_DONE** —Fixing and done with an item.</span></span> 
    
<span data-ttu-id="49351-133">_pRowCur_</span><span class="sxs-lookup"><span data-stu-id="49351-133">_pRowCur_</span></span>
  
> <span data-ttu-id="49351-134">[in]指向描述正在扫描或修复的项目的 **[SRow](https://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="49351-134">[in] A pointer to an **[SRow](https://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** structure that describes the item being scanned or fixed.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="49351-135">返回值</span><span class="sxs-lookup"><span data-stu-id="49351-135">Return values</span></span>

<span data-ttu-id="49351-136">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="49351-136">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="49351-137">备注</span><span class="sxs-lookup"><span data-stu-id="49351-137">Remarks</span></span>

<span data-ttu-id="49351-138">使用 [IOlkApptRebaser](iolkapptrebaser.md) 接口的 MAPI 客户端应用程序实现此函数以跟踪项目处理。</span><span class="sxs-lookup"><span data-stu-id="49351-138">MAPI client applications that use the [IOlkApptRebaser](iolkapptrebaser.md) interface implement this function to track item processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="49351-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49351-139">See also</span></span>

- [<span data-ttu-id="49351-140">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="49351-140">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

