---
title: IMAPIProgressGetMax
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.GetMax
api_type:
- COM
ms.assetid: 88a910ed-b55a-4e5b-a43d-eb3ea795a70e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2dadad410b9aaf1401d792de373e561c29183a12
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567235"
---
# <a name="imapiprogressgetmax"></a><span data-ttu-id="9f9a6-103">IMAPIProgress::GetMax</span><span class="sxs-lookup"><span data-stu-id="9f9a6-103">IMAPIProgress::GetMax</span></span>

  
  
<span data-ttu-id="9f9a6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9f9a6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9f9a6-105">对于的进度的信息将显示的操作中返回的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-105">Returns the maximum number of items in the operation for which progress information is displayed.</span></span>
  
```cpp
HRESULT GetMax(
  ULONG FAR * lpulMax
);
```

## <a name="parameters"></a><span data-ttu-id="9f9a6-106">参数</span><span class="sxs-lookup"><span data-stu-id="9f9a6-106">Parameters</span></span>

 <span data-ttu-id="9f9a6-107">_lpulMax_</span><span class="sxs-lookup"><span data-stu-id="9f9a6-107">_lpulMax_</span></span>
  
> <span data-ttu-id="9f9a6-108">[输出]一个指向的最大操作中的项目数。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-108">[out] A pointer to the maximum number of items in the operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9f9a6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9f9a6-109">Return value</span></span>

<span data-ttu-id="9f9a6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f9a6-110">S_OK</span></span> 
  
> <span data-ttu-id="9f9a6-111">已检索的最大操作中的项目数。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-111">The maximum number of items in the operation has been retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9f9a6-112">注解</span><span class="sxs-lookup"><span data-stu-id="9f9a6-112">Remarks</span></span>

<span data-ttu-id="9f9a6-113">最大值表示数字的窗体中的操作的末尾。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-113">The maximum value represents the end of the operation in numeric form.</span></span> <span data-ttu-id="9f9a6-114">值可以是全局的最大值，用于表示显示整个进度的范围或本地值，用于表示仅显示的一部分。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-114">The value can be a global maximum value, used to represent the scope of the entire progress display, or a local value, used to represent only a part of the display.</span></span> 
  
<span data-ttu-id="9f9a6-115">是否正在进行对象能够理解的最大值为本地域或全局设置会影响标志的值。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-115">The value of the flag setting affects whether the progress object understands the maximum value to be local or global.</span></span> <span data-ttu-id="9f9a6-116">当设置 MAPI_TOP_LEVEL 标志时，最大值被视为全局和用于计算整个操作的进度。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-116">When the MAPI_TOP_LEVEL flag is set, the maximum value is considered to be global and is used to calculate progress for the entire operation.</span></span> <span data-ttu-id="9f9a6-117">时未设置 MAPI_TOP_LEVEL，最大值被视为本地，并提供程序将其内部来显示较低级别的子对象的进度。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-117">When MAPI_TOP_LEVEL is not set, the maximum value is considered to be local, and providers use it internally to display progress for lower level subobjects.</span></span> <span data-ttu-id="9f9a6-118">进度对象保存仅使它返回到通过**GetMax**呼叫提供程序的本地最大值。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-118">Progress objects save the local maximum value only to return it to a provider through a **GetMax** call.</span></span> 
  
<span data-ttu-id="9f9a6-119">有关详细了解如何以及何时调用进度对象，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-119">For more information about how and when to make calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="9f9a6-120">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="9f9a6-120">Notes to implementers</span></span>

<span data-ttu-id="9f9a6-121">初始化的最大值为 1000年。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-121">Initialize the maximum value to 1000.</span></span> <span data-ttu-id="9f9a6-122">服务提供商可以通过调用[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法重置此值。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-122">Service providers can reset this value by calling the [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method.</span></span> <span data-ttu-id="9f9a6-123">有关如何实施**GetMax**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-123">For more information about how to implement **GetMax** and the other [IMAPIProgress](imapiprogressiunknown.md) methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9f9a6-124">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="9f9a6-124">MFCMAPI reference</span></span>

<span data-ttu-id="9f9a6-125">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9f9a6-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="9f9a6-126">**File**</span></span>|<span data-ttu-id="9f9a6-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="9f9a6-127">**Function**</span></span>|<span data-ttu-id="9f9a6-128">**Comment**</span><span class="sxs-lookup"><span data-stu-id="9f9a6-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9f9a6-129">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="9f9a6-129">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="9f9a6-130">CMAPIProgress::GetMax</span><span class="sxs-lookup"><span data-stu-id="9f9a6-130">CMAPIProgress::GetMax</span></span>  <br/> |<span data-ttu-id="9f9a6-131">MFCMAPI 使用**IMAPIProgress::GetMax**方法来获取进度对象的最大值。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-131">MFCMAPI uses the **IMAPIProgress::GetMax** method to get the maximum value for the progress object.</span></span> <span data-ttu-id="9f9a6-132">除非限制之前已经设置了与**IMAPIProgress::SetLimits**方法返回 1000年。</span><span class="sxs-lookup"><span data-stu-id="9f9a6-132">Returns 1000 unless limits have previously been set with the **IMAPIProgress::SetLimits** method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9f9a6-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f9a6-133">See also</span></span>



[<span data-ttu-id="9f9a6-134">IMAPIProgress::GetMin</span><span class="sxs-lookup"><span data-stu-id="9f9a6-134">IMAPIProgress::GetMin</span></span>](imapiprogress-getmin.md)
  
[<span data-ttu-id="9f9a6-135">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="9f9a6-135">IMAPIProgress::Progress</span></span>](imapiprogress-progress.md)
  
[<span data-ttu-id="9f9a6-136">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="9f9a6-136">IMAPIProgress::SetLimits</span></span>](imapiprogress-setlimits.md)
  
[<span data-ttu-id="9f9a6-137">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9f9a6-137">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="9f9a6-138">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9f9a6-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="9f9a6-139">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="9f9a6-139">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="9f9a6-140">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="9f9a6-140">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

