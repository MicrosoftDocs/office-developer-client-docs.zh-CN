---
title: IMAPIProgressGetFlags
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.GetFlags
api_type:
- COM
ms.assetid: 7af74fcc-c0df-4f58-a2d4-0a79c96b2e81
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 810192bfc85c9934a282f02a0839aaed539f744d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423641"
---
# <a name="imapiprogressgetflags"></a><span data-ttu-id="7594e-103">IMAPIProgress::GetFlags</span><span class="sxs-lookup"><span data-stu-id="7594e-103">IMAPIProgress::GetFlags</span></span>

  
  
<span data-ttu-id="7594e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7594e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7594e-105">从计算进度信息的操作级别的进度对象中返回标志设置。</span><span class="sxs-lookup"><span data-stu-id="7594e-105">Returns flag settings from the progress object for the level of operation on which progress information is calculated.</span></span>
  
```cpp
HRESULT GetFlags(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="7594e-106">参数</span><span class="sxs-lookup"><span data-stu-id="7594e-106">Parameters</span></span>

 <span data-ttu-id="7594e-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="7594e-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="7594e-108">[out]控制计算进度信息的操作级别的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="7594e-108">[out] A bitmask of flags that controls the level of operation on which progress information is calculated.</span></span> <span data-ttu-id="7594e-109">可以返回以下标志：</span><span class="sxs-lookup"><span data-stu-id="7594e-109">The following flag can be returned:</span></span>
    
<span data-ttu-id="7594e-110">MAPI_TOP_LEVEL</span><span class="sxs-lookup"><span data-stu-id="7594e-110">MAPI_TOP_LEVEL</span></span> 
  
> <span data-ttu-id="7594e-111">正在计算顶级对象的进度，该对象由客户端调用以开始操作。</span><span class="sxs-lookup"><span data-stu-id="7594e-111">Progress is being calculated for the top-level object, the object that is called by the client to begin the operation.</span></span> <span data-ttu-id="7594e-112">例如，文件夹复制操作中的顶级对象是正在复制的文件夹。</span><span class="sxs-lookup"><span data-stu-id="7594e-112">For example, the top-level object in a folder copy operation is the folder that is being copied.</span></span> <span data-ttu-id="7594e-113">未MAPI_TOP_LEVEL时，将计算较低级别对象或子对象的进度。</span><span class="sxs-lookup"><span data-stu-id="7594e-113">When MAPI_TOP_LEVEL is not set, progress is calculated for a lower level object, or subobject.</span></span> <span data-ttu-id="7594e-114">在文件夹复制操作中，较低级别的对象是正在复制的文件夹中的子文件夹之一。</span><span class="sxs-lookup"><span data-stu-id="7594e-114">In the folder copy operation, a lower level object is one of the subfolders in the folder that is being copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7594e-115">返回值</span><span class="sxs-lookup"><span data-stu-id="7594e-115">Return value</span></span>

<span data-ttu-id="7594e-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="7594e-116">S_OK</span></span> 
  
> <span data-ttu-id="7594e-117">标志值已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7594e-117">The flags value was returned successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7594e-118">备注</span><span class="sxs-lookup"><span data-stu-id="7594e-118">Remarks</span></span>

<span data-ttu-id="7594e-119">MAPI 使服务提供商能够区分具有 MAPI_TOP_LEVEL 标志的顶级对象和子对象，以便操作中涉及的所有对象可以使用同一 [IMAPIProgress](imapiprogressiunknown.md) 实现来显示进度。</span><span class="sxs-lookup"><span data-stu-id="7594e-119">MAPI enables service providers to differentiate between top-level objects and subobjects with the MAPI_TOP_LEVEL flag so that all objects involved in an operation can use the same [IMAPIProgress](imapiprogressiunknown.md) implementation to show progress.</span></span> <span data-ttu-id="7594e-120">这将导致指示器在单个正方向上平稳地显示。</span><span class="sxs-lookup"><span data-stu-id="7594e-120">This causes the indicator display to proceed smoothly in a single positive direction.</span></span> <span data-ttu-id="7594e-121">是否设置MAPI_TOP_LEVEL标记确定服务提供商如何在后续对 progress 对象的调用中设置其他参数。</span><span class="sxs-lookup"><span data-stu-id="7594e-121">Whether the MAPI_TOP_LEVEL flag is set determines how service providers set the other parameters in subsequent calls to the progress object.</span></span> 
  
<span data-ttu-id="7594e-122">**GetFlags** 返回的值最初由实现者设置，随后由服务提供商通过调用 [IMAPIProgress：：SetLimits](imapiprogress-setlimits.md)方法进行设置。</span><span class="sxs-lookup"><span data-stu-id="7594e-122">The value returned by **GetFlags** is set initially by the implementer and subsequently by the service provider through a call to the [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="7594e-123">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="7594e-123">Notes to implementers</span></span>

<span data-ttu-id="7594e-124">始终将标志初始化为MAPI_TOP_LEVEL，然后依赖服务提供商在适当的时候清除它。</span><span class="sxs-lookup"><span data-stu-id="7594e-124">Always initialize the flag to MAPI_TOP_LEVEL and then rely on service providers to clear it when appropriate.</span></span> <span data-ttu-id="7594e-125">服务提供商可以通过调用 **IMAPIProgress：：SetLimits** 方法清除和重置标志。</span><span class="sxs-lookup"><span data-stu-id="7594e-125">Service providers can clear and reset the flag by calling the **IMAPIProgress::SetLimits** method.</span></span> <span data-ttu-id="7594e-126">若要详细了解如何实现 **GetFlags** 和其他 **IMAPIProgress** 方法，请参阅 [实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="7594e-126">For more information about how to implement **GetFlags** and the other **IMAPIProgress** methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="7594e-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7594e-127">Notes to callers</span></span>

<span data-ttu-id="7594e-128">当你显示进度指示器时，请首先调用 **IMAPIProgress：：GetFlags**。</span><span class="sxs-lookup"><span data-stu-id="7594e-128">When you display a progress indicator, make your first call a call to **IMAPIProgress::GetFlags**.</span></span> <span data-ttu-id="7594e-129">返回的值应MAPI_TOP_LEVEL，因为所有实现将  _lpulFlags_ 参数的内容初始化为此值。</span><span class="sxs-lookup"><span data-stu-id="7594e-129">The returned value should be MAPI_TOP_LEVEL, because all implementations initialize the contents of the  _lpulFlags_ parameter to this value.</span></span> <span data-ttu-id="7594e-130">有关对进度对象的调用顺序详细信息，请参阅 [显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="7594e-130">For more information about the sequence of calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7594e-131">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="7594e-131">MFCMAPI reference</span></span>

<span data-ttu-id="7594e-132">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7594e-132">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7594e-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="7594e-133">**File**</span></span>|<span data-ttu-id="7594e-134">**函数**</span><span class="sxs-lookup"><span data-stu-id="7594e-134">**Function**</span></span>|<span data-ttu-id="7594e-135">**备注**</span><span class="sxs-lookup"><span data-stu-id="7594e-135">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7594e-136">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="7594e-136">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="7594e-137">CMAPIProgress：：GetFlags</span><span class="sxs-lookup"><span data-stu-id="7594e-137">CMAPIProgress::GetFlags</span></span>  <br/> |<span data-ttu-id="7594e-138">MFCMAPI 使用 **IMAPIProgress：：GetFlags** 方法确定设置的标志。</span><span class="sxs-lookup"><span data-stu-id="7594e-138">MFCMAPI uses the **IMAPIProgress::GetFlags** method to determine which flags are set.</span></span> <span data-ttu-id="7594e-139">除非MAPI_TOP_LEVEL **IMAPIProgress：：SetLimits** 方法设置了标志，否则返回值。</span><span class="sxs-lookup"><span data-stu-id="7594e-139">Returns MAPI_TOP_LEVEL unless flags have been set by using the **IMAPIProgress::SetLimits** method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7594e-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7594e-140">See also</span></span>



[<span data-ttu-id="7594e-141">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="7594e-141">IMAPIProgress::SetLimits</span></span>](imapiprogress-setlimits.md)
  
[<span data-ttu-id="7594e-142">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7594e-142">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="7594e-143">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7594e-143">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="7594e-144">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="7594e-144">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="7594e-145">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="7594e-145">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

