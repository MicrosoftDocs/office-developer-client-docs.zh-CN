---
title: IOlkApptRebaserBeginEnumerateAppointments
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8946703a-aaa8-6b3f-aa68-931365db620d
description: 从开始的任务在日历文件夹以查找需要重定基址的约会的约会枚举。
ms.openlocfilehash: 2ad26692483d87166a538ec2f04d3fc13b9ea930
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774354"
---
# <a name="iolkapptrebaserbeginenumerateappointments"></a><span data-ttu-id="5e1aa-103">IOlkApptRebaser::BeginEnumerateAppointments</span><span class="sxs-lookup"><span data-stu-id="5e1aa-103">IOlkApptRebaser::BeginEnumerateAppointments</span></span>

<span data-ttu-id="5e1aa-104">从开始的任务在日历文件夹以查找需要重定基址的约会的约会枚举。</span><span class="sxs-lookup"><span data-stu-id="5e1aa-104">Begins a task for appointment enumeration in a calendar folder to find the appointments that need rebasing.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5e1aa-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="5e1aa-105">Quick info</span></span>

<span data-ttu-id="5e1aa-106">请参阅[IOlkApptRebaser](iolkapptrebaser.md)。</span><span class="sxs-lookup"><span data-stu-id="5e1aa-106">See [IOlkApptRebaser](iolkapptrebaser.md).</span></span>
  
```cpp
HRESULT BeginEnumerateAppointments( 
    PFNREBASETASKPROGRESS pfnProgress, 
    void **ppContext);
```

## <a name="parameters"></a><span data-ttu-id="5e1aa-107">参数</span><span class="sxs-lookup"><span data-stu-id="5e1aa-107">Parameters</span></span>

<span data-ttu-id="5e1aa-108">_pfnProgress_</span><span class="sxs-lookup"><span data-stu-id="5e1aa-108">_pfnProgress_</span></span>
  
> <span data-ttu-id="5e1aa-p101">[中]可选。指向用于接收进度的重定基本值任务进度函数的指针。 **PFNREBASETASKPROGRESS** 是在 tzmovelib.h 中定义的。</span><span class="sxs-lookup"><span data-stu-id="5e1aa-p101">[in] Optional. A pointer to a rebase task progress function to receive progress. **PFNREBASETASKPROGRESS** is defined in tzmovelib.h.</span></span> 
    
<span data-ttu-id="5e1aa-112">_ppContext_</span><span class="sxs-lookup"><span data-stu-id="5e1aa-112">_ppContext_</span></span>
  
> <span data-ttu-id="5e1aa-p102">[] out所必需。指向返回上下文的指针的指针。此上下文将被传递到[IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)。</span><span class="sxs-lookup"><span data-stu-id="5e1aa-p102">[out] Required. A pointer to a pointer to the returned context. This context will be passed to [IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md).</span></span>
    
## <a name="return-values"></a><span data-ttu-id="5e1aa-116">返回值</span><span class="sxs-lookup"><span data-stu-id="5e1aa-116">Return values</span></span>

<span data-ttu-id="5e1aa-117">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="5e1aa-117">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5e1aa-118">注释</span><span class="sxs-lookup"><span data-stu-id="5e1aa-118">Remarks</span></span>

<span data-ttu-id="5e1aa-119">在新线程上执行此任务。</span><span class="sxs-lookup"><span data-stu-id="5e1aa-119">This task runs on a new thread.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e1aa-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e1aa-120">See also</span></span>

- [<span data-ttu-id="5e1aa-121">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="5e1aa-121">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

