---
title: RebaseTaskComplete
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 2de5c77c-3fac-cfb6-3719-68df4013cf11
description: 报告重定约会的完成情况。
ms.openlocfilehash: 9fab0d06bf0b9856b9a968f5c0db1bb15b0fe0bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328320"
---
# <a name="rebasetaskcomplete"></a><span data-ttu-id="576c8-103">RebaseTaskComplete</span><span class="sxs-lookup"><span data-stu-id="576c8-103">RebaseTaskComplete</span></span>

<span data-ttu-id="576c8-104">报告重定约会的完成情况。</span><span class="sxs-lookup"><span data-stu-id="576c8-104">Reports completion for rebasing of appointments.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="576c8-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="576c8-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="576c8-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="576c8-106">Header file:</span></span>  <br/> |<span data-ttu-id="576c8-107">tzmovelib。h</span><span class="sxs-lookup"><span data-stu-id="576c8-107">tzmovelib.h</span></span>  <br/> |
|<span data-ttu-id="576c8-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="576c8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="576c8-109">MAPI 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="576c8-109">MAPI client applications</span></span>  <br/> |
|<span data-ttu-id="576c8-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="576c8-110">Called by:</span></span>  <br/> |<span data-ttu-id="576c8-111">Outlook 重定对象</span><span class="sxs-lookup"><span data-stu-id="576c8-111">Outlook rebasing object</span></span>  <br/> |
|<span data-ttu-id="576c8-112">指针类型:</span><span class="sxs-lookup"><span data-stu-id="576c8-112">Pointer type:</span></span>  <br/> |<span data-ttu-id="576c8-113">**PFNREBASETASKCOMPLETE**中定义的 tzmovelib。h</span><span class="sxs-lookup"><span data-stu-id="576c8-113">**PFNREBASETASKCOMPLETE** as defined in tzmovelib.h</span></span>  <br/> |
   
```cpp
void STDAPICALLTYPE RebaseTaskComplete(  
    ULONG ulRowIndex, 
    const SRow* pRowCur, 
    HRESULT hrResult, 
    BOOL fModified, 
    BOOL fSentUpdate, 
    const MAPIERROR* pError); 

```

## <a name="parameters"></a><span data-ttu-id="576c8-114">参数</span><span class="sxs-lookup"><span data-stu-id="576c8-114">Parameters</span></span>

<span data-ttu-id="576c8-115">_ulRowIndex_</span><span class="sxs-lookup"><span data-stu-id="576c8-115">_ulRowIndex_</span></span>
  
> <span data-ttu-id="576c8-116">实时已处理的行。</span><span class="sxs-lookup"><span data-stu-id="576c8-116">[in] The row that was processed.</span></span> <span data-ttu-id="576c8-117">此索引是指传递给[IOlkApptRebaser:: BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)的**[SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)** 结构。</span><span class="sxs-lookup"><span data-stu-id="576c8-117">This index refers to the **[SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)** structure passed to [IOlkApptRebaser::BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md).</span></span>
    
<span data-ttu-id="576c8-118">_pRowCur_</span><span class="sxs-lookup"><span data-stu-id="576c8-118">_pRowCur_</span></span>
  
> <span data-ttu-id="576c8-119">in] 指向描述已处理的项目的**[SRow](https://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="576c8-119">in] A pointer to an **[SRow](https://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** structure describing the item that was processed.</span></span> 
    
<span data-ttu-id="576c8-120">_hrResult_</span><span class="sxs-lookup"><span data-stu-id="576c8-120">_hrResult_</span></span>
  
> <span data-ttu-id="576c8-121">实时一个**HRESULT** , 它指示重定操作的结果。</span><span class="sxs-lookup"><span data-stu-id="576c8-121">[in] An **HRESULT** indicating the result of the rebasing operation.</span></span> 
    
<span data-ttu-id="576c8-122">_fModified_</span><span class="sxs-lookup"><span data-stu-id="576c8-122">_fModified_</span></span>
  
> <span data-ttu-id="576c8-123">实时指定是否修改项目。</span><span class="sxs-lookup"><span data-stu-id="576c8-123">[in] Specifies whether the item was modified.</span></span>
    
<span data-ttu-id="576c8-124">_fSentUpdate_</span><span class="sxs-lookup"><span data-stu-id="576c8-124">_fSentUpdate_</span></span>
  
> <span data-ttu-id="576c8-125">实时指定是否发送了会议更新邮件。</span><span class="sxs-lookup"><span data-stu-id="576c8-125">[in] Specifies whether a meeting update message was sent.</span></span> 
    
<span data-ttu-id="576c8-126">_pError_</span><span class="sxs-lookup"><span data-stu-id="576c8-126">_pError_</span></span>
  
> <span data-ttu-id="576c8-127">实时指向带有扩展错误信息的**MAPIERROR**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="576c8-127">[in] A pointer to a **MAPIERROR** structure with extended error information.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="576c8-128">返回值</span><span class="sxs-lookup"><span data-stu-id="576c8-128">Return values</span></span>

<span data-ttu-id="576c8-129">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="576c8-129">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="576c8-130">注解</span><span class="sxs-lookup"><span data-stu-id="576c8-130">Remarks</span></span>

<span data-ttu-id="576c8-131">使用[IOlkApptRebaser](iolkapptrebaser.md)接口的 MAPI 客户端应用程序实现此函数以跟踪项更新的完成。</span><span class="sxs-lookup"><span data-stu-id="576c8-131">MAPI client applications that use the [IOlkApptRebaser](iolkapptrebaser.md) interface implement this function to track completion of item updates.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="576c8-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="576c8-132">See also</span></span>

- [<span data-ttu-id="576c8-133">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="576c8-133">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

