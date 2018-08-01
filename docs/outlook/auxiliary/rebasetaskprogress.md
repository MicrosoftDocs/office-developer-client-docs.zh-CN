---
title: RebaseTaskProgress
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8b8368d2-b04b-42a5-fdc3-955fc873c2f5
description: 报告进度枚举和定位的约会。
ms.openlocfilehash: 4219ab1d59b596bebbe3ced03651716b04b51f81
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774454"
---
# <a name="rebasetaskprogress"></a><span data-ttu-id="db9c2-103">RebaseTaskProgress</span><span class="sxs-lookup"><span data-stu-id="db9c2-103">RebaseTaskProgress</span></span>

<span data-ttu-id="db9c2-104">报告进度枚举和定位的约会。</span><span class="sxs-lookup"><span data-stu-id="db9c2-104">Reports progress for enumeration and rebasing of appointments.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="db9c2-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="db9c2-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="db9c2-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="db9c2-106">Header file:</span></span>  <br/> |<span data-ttu-id="db9c2-107">tzmovelib.h</span><span class="sxs-lookup"><span data-stu-id="db9c2-107">tzmovelib.h</span></span>  <br/> |
|<span data-ttu-id="db9c2-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="db9c2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="db9c2-109">MAPI 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="db9c2-109">MAPI client applications</span></span>  <br/> |
|<span data-ttu-id="db9c2-110">调用：</span><span class="sxs-lookup"><span data-stu-id="db9c2-110">Called by:</span></span>  <br/> |<span data-ttu-id="db9c2-111">Outlook 调整对象</span><span class="sxs-lookup"><span data-stu-id="db9c2-111">Outlook rebasing object</span></span>  <br/> |
|<span data-ttu-id="db9c2-112">指针类型：</span><span class="sxs-lookup"><span data-stu-id="db9c2-112">Pointer type:</span></span>  <br/> |<span data-ttu-id="db9c2-113">**PFNREBASETASKPROGRESS** tzmovelib.h 中定义</span><span class="sxs-lookup"><span data-stu-id="db9c2-113">**PFNREBASETASKPROGRESS** as defined in tzmovelib.h</span></span>  <br/> |
   
```cpp
void STDAPICALLTYPE RebaseTaskProgress(  
    ULONG ulMin, 
    ULONG ulMax, 
    ULONG ulCur, 
    REBASE_APPT_STATE State, 
    const SRow* pRowCur); 

```

## <a name="parameters"></a><span data-ttu-id="db9c2-114">参数</span><span class="sxs-lookup"><span data-stu-id="db9c2-114">Parameters</span></span>

<span data-ttu-id="db9c2-115">_ulMin_</span><span class="sxs-lookup"><span data-stu-id="db9c2-115">_ulMin_</span></span>
  
> <span data-ttu-id="db9c2-116">[in]正在处理的约会的区域的低末尾。</span><span class="sxs-lookup"><span data-stu-id="db9c2-116">[in] The low end of the range of appointments being processed.</span></span> <span data-ttu-id="db9c2-117">通常为零。</span><span class="sxs-lookup"><span data-stu-id="db9c2-117">It is usually zero.</span></span>
    
<span data-ttu-id="db9c2-118">_ulMax_</span><span class="sxs-lookup"><span data-stu-id="db9c2-118">_ulMax_</span></span>
  
> <span data-ttu-id="db9c2-119">[in]正在处理的约会的区域的高末尾。</span><span class="sxs-lookup"><span data-stu-id="db9c2-119">[in] The high end of the range of appointments being processed.</span></span> <span data-ttu-id="db9c2-120">它通常是正在处理的日历文件夹中的项目数。</span><span class="sxs-lookup"><span data-stu-id="db9c2-120">It is usually the number of items in the calendar folder being processed.</span></span>
    
<span data-ttu-id="db9c2-121">_ulCur_</span><span class="sxs-lookup"><span data-stu-id="db9c2-121">_ulCur_</span></span>
  
> <span data-ttu-id="db9c2-122">[in]正在处理的当前项目。</span><span class="sxs-lookup"><span data-stu-id="db9c2-122">[in] The current item being processed.</span></span>
    
<span data-ttu-id="db9c2-123">_State_</span><span class="sxs-lookup"><span data-stu-id="db9c2-123">_State_</span></span>
  
> <span data-ttu-id="db9c2-124">[in]一个值，指示正在处理的项目的状态。</span><span class="sxs-lookup"><span data-stu-id="db9c2-124">[in] A value that indicates the status of the item being processed.</span></span> <span data-ttu-id="db9c2-125">枚举**REBASE_APPT_STATE** tzmovelib.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="db9c2-125">The enumeration **REBASE_APPT_STATE** is defined in tzmovelib.h.</span></span>  <span data-ttu-id="db9c2-126">_状态_是以下值之一：</span><span class="sxs-lookup"><span data-stu-id="db9c2-126">_State_ is one of the following values:</span></span> 
    
   - <span data-ttu-id="db9c2-127">**REBASE_APPT_STATE_SCANNING_EXAMINING** — 扫描和检查项目。</span><span class="sxs-lookup"><span data-stu-id="db9c2-127">**REBASE_APPT_STATE_SCANNING_EXAMINING** —Scanning and examining an item.</span></span> 
    
   - <span data-ttu-id="db9c2-128">**REBASE_APPT_STATE_SCANNING_FOUND** — 扫描和发现项目。</span><span class="sxs-lookup"><span data-stu-id="db9c2-128">**REBASE_APPT_STATE_SCANNING_FOUND** —Scanning and found an item.</span></span> 
    
   - <span data-ttu-id="db9c2-129">**REBASE_APPT_STATE_BEGIN** — 正在修复和启动项目。</span><span class="sxs-lookup"><span data-stu-id="db9c2-129">**REBASE_APPT_STATE_BEGIN** —Fixing and starting an item.</span></span> 
    
   - <span data-ttu-id="db9c2-130">**REBASE_APPT_STATE_REBASING** — 正在修复和调整项目。</span><span class="sxs-lookup"><span data-stu-id="db9c2-130">**REBASE_APPT_STATE_REBASING** —Fixing and adjusting an item.</span></span> 
    
   - <span data-ttu-id="db9c2-131">**REBASE_APPT_STATE_SENDING** — 正在修复和发送会议更新。</span><span class="sxs-lookup"><span data-stu-id="db9c2-131">**REBASE_APPT_STATE_SENDING** —Fixing and sending a meeting update.</span></span> 
    
   - <span data-ttu-id="db9c2-132">**REBASE_APPT_STATE_DONE** — 解决并与项目完成。</span><span class="sxs-lookup"><span data-stu-id="db9c2-132">**REBASE_APPT_STATE_DONE** —Fixing and done with an item.</span></span> 
    
<span data-ttu-id="db9c2-133">_pRowCur_</span><span class="sxs-lookup"><span data-stu-id="db9c2-133">_pRowCur_</span></span>
  
> <span data-ttu-id="db9c2-134">[in]指向描述所扫描或修复的项的**[SRow](http://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="db9c2-134">[in] A pointer to an **[SRow](http://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** structure that describes the item being scanned or fixed.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="db9c2-135">返回值</span><span class="sxs-lookup"><span data-stu-id="db9c2-135">Return values</span></span>

<span data-ttu-id="db9c2-136">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="db9c2-136">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="db9c2-137">注释</span><span class="sxs-lookup"><span data-stu-id="db9c2-137">Remarks</span></span>

<span data-ttu-id="db9c2-138">MAPI 客户端应用程序使用[IOlkApptRebaser](iolkapptrebaser.md)接口实现此函数来跟踪项目处理。</span><span class="sxs-lookup"><span data-stu-id="db9c2-138">MAPI client applications that use the [IOlkApptRebaser](iolkapptrebaser.md) interface implement this function to track item processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="db9c2-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db9c2-139">See also</span></span>

- [<span data-ttu-id="db9c2-140">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="db9c2-140">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

