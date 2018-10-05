---
title: RebaseTaskComplete
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 2de5c77c-3fac-cfb6-3719-68df4013cf11
description: 报告完成定位的约会。
ms.openlocfilehash: 9fab0d06bf0b9856b9a968f5c0db1bb15b0fe0bd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388915"
---
# <a name="rebasetaskcomplete"></a><span data-ttu-id="fadbb-103">RebaseTaskComplete</span><span class="sxs-lookup"><span data-stu-id="fadbb-103">RebaseTaskComplete</span></span>

<span data-ttu-id="fadbb-104">报告完成定位的约会。</span><span class="sxs-lookup"><span data-stu-id="fadbb-104">Reports completion for rebasing of appointments.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="fadbb-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="fadbb-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fadbb-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fadbb-106">Header file:</span></span>  <br/> |<span data-ttu-id="fadbb-107">tzmovelib.h</span><span class="sxs-lookup"><span data-stu-id="fadbb-107">tzmovelib.h</span></span>  <br/> |
|<span data-ttu-id="fadbb-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="fadbb-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="fadbb-109">MAPI 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="fadbb-109">MAPI client applications</span></span>  <br/> |
|<span data-ttu-id="fadbb-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="fadbb-110">Called by:</span></span>  <br/> |<span data-ttu-id="fadbb-111">Outlook 调整对象</span><span class="sxs-lookup"><span data-stu-id="fadbb-111">Outlook rebasing object</span></span>  <br/> |
|<span data-ttu-id="fadbb-112">指针类型：</span><span class="sxs-lookup"><span data-stu-id="fadbb-112">Pointer type:</span></span>  <br/> |<span data-ttu-id="fadbb-113">**PFNREBASETASKCOMPLETE** tzmovelib.h 中定义</span><span class="sxs-lookup"><span data-stu-id="fadbb-113">**PFNREBASETASKCOMPLETE** as defined in tzmovelib.h</span></span>  <br/> |
   
```cpp
void STDAPICALLTYPE RebaseTaskComplete(  
    ULONG ulRowIndex, 
    const SRow* pRowCur, 
    HRESULT hrResult, 
    BOOL fModified, 
    BOOL fSentUpdate, 
    const MAPIERROR* pError); 

```

## <a name="parameters"></a><span data-ttu-id="fadbb-114">参数</span><span class="sxs-lookup"><span data-stu-id="fadbb-114">Parameters</span></span>

<span data-ttu-id="fadbb-115">_ulRowIndex_</span><span class="sxs-lookup"><span data-stu-id="fadbb-115">_ulRowIndex_</span></span>
  
> <span data-ttu-id="fadbb-116">[in]已处理的行。</span><span class="sxs-lookup"><span data-stu-id="fadbb-116">[in] The row that was processed.</span></span> <span data-ttu-id="fadbb-117">此索引引用传递到[IOlkApptRebaser::BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md) **[SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)** 结构。</span><span class="sxs-lookup"><span data-stu-id="fadbb-117">This index refers to the **[SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)** structure passed to [IOlkApptRebaser::BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md).</span></span>
    
<span data-ttu-id="fadbb-118">_pRowCur_</span><span class="sxs-lookup"><span data-stu-id="fadbb-118">_pRowCur_</span></span>
  
> <span data-ttu-id="fadbb-119">输入] 指向**[SRow](https://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** 结构的描述所处理的项。</span><span class="sxs-lookup"><span data-stu-id="fadbb-119">in] A pointer to an **[SRow](https://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** structure describing the item that was processed.</span></span> 
    
<span data-ttu-id="fadbb-120">_hrResult_</span><span class="sxs-lookup"><span data-stu-id="fadbb-120">_hrResult_</span></span>
  
> <span data-ttu-id="fadbb-121">[in]**HRESULT**指示调整操作的结果。</span><span class="sxs-lookup"><span data-stu-id="fadbb-121">[in] An **HRESULT** indicating the result of the rebasing operation.</span></span> 
    
<span data-ttu-id="fadbb-122">_fModified_</span><span class="sxs-lookup"><span data-stu-id="fadbb-122">_fModified_</span></span>
  
> <span data-ttu-id="fadbb-123">[in]指定项目是否已修改。</span><span class="sxs-lookup"><span data-stu-id="fadbb-123">[in] Specifies whether the item was modified.</span></span>
    
<span data-ttu-id="fadbb-124">_fSentUpdate_</span><span class="sxs-lookup"><span data-stu-id="fadbb-124">_fSentUpdate_</span></span>
  
> <span data-ttu-id="fadbb-125">[in]指定会议是否更新消息发送。</span><span class="sxs-lookup"><span data-stu-id="fadbb-125">[in] Specifies whether a meeting update message was sent.</span></span> 
    
<span data-ttu-id="fadbb-126">_pError_</span><span class="sxs-lookup"><span data-stu-id="fadbb-126">_pError_</span></span>
  
> <span data-ttu-id="fadbb-127">[in]指向与扩展的错误信息**MAPIERROR**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="fadbb-127">[in] A pointer to a **MAPIERROR** structure with extended error information.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="fadbb-128">返回值</span><span class="sxs-lookup"><span data-stu-id="fadbb-128">Return values</span></span>

<span data-ttu-id="fadbb-129">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="fadbb-129">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fadbb-130">注释</span><span class="sxs-lookup"><span data-stu-id="fadbb-130">Remarks</span></span>

<span data-ttu-id="fadbb-131">MAPI 客户端应用程序使用[IOlkApptRebaser](iolkapptrebaser.md)接口实现跟踪项目更新完成此函数。</span><span class="sxs-lookup"><span data-stu-id="fadbb-131">MAPI client applications that use the [IOlkApptRebaser](iolkapptrebaser.md) interface implement this function to track completion of item updates.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fadbb-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fadbb-132">See also</span></span>

- [<span data-ttu-id="fadbb-133">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="fadbb-133">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

