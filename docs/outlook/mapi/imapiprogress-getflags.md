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
ms.openlocfilehash: 8964ba8c4341bec431bdbc1690d639b345df8b1d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775503"
---
# <a name="imapiprogressgetflags"></a><span data-ttu-id="0f94f-103">IMAPIProgress::GetFlags</span><span class="sxs-lookup"><span data-stu-id="0f94f-103">IMAPIProgress::GetFlags</span></span>

  
  
<span data-ttu-id="0f94f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0f94f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0f94f-105">返回标记的操作对其计算进度信息的级别的进度对象中的设置。</span><span class="sxs-lookup"><span data-stu-id="0f94f-105">Returns flag settings from the progress object for the level of operation on which progress information is calculated.</span></span>
  
```cpp
HRESULT GetFlags(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="0f94f-106">参数</span><span class="sxs-lookup"><span data-stu-id="0f94f-106">Parameters</span></span>

 <span data-ttu-id="0f94f-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="0f94f-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="0f94f-108">[输出]位掩码的标志控制级别的操作的进度信息的计算公式的。</span><span class="sxs-lookup"><span data-stu-id="0f94f-108">[out] A bitmask of flags that controls the level of operation on which progress information is calculated.</span></span> <span data-ttu-id="0f94f-109">可以返回以下标记：</span><span class="sxs-lookup"><span data-stu-id="0f94f-109">The following flag can be returned:</span></span>
    
<span data-ttu-id="0f94f-110">MAPI_TOP_LEVEL</span><span class="sxs-lookup"><span data-stu-id="0f94f-110">MAPI_TOP_LEVEL</span></span> 
  
> <span data-ttu-id="0f94f-111">正在计算进度的顶级对象，由客户端开始操作调用的对象。</span><span class="sxs-lookup"><span data-stu-id="0f94f-111">Progress is being calculated for the top-level object, the object that is called by the client to begin the operation.</span></span> <span data-ttu-id="0f94f-112">例如，文件夹复制操作中的顶级对象是正在将复制的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0f94f-112">For example, the top-level object in a folder copy operation is the folder that is being copied.</span></span> <span data-ttu-id="0f94f-113">如果未设置 MAPI_TOP_LEVEL，进度计算较低级别的对象或子对象。</span><span class="sxs-lookup"><span data-stu-id="0f94f-113">When MAPI_TOP_LEVEL is not set, progress is calculated for a lower level object, or subobject.</span></span> <span data-ttu-id="0f94f-114">文件夹复制操作，较低的 level 对象是正在将复制的文件夹中的子文件夹之一。</span><span class="sxs-lookup"><span data-stu-id="0f94f-114">In the folder copy operation, a lower level object is one of the subfolders in the folder that is being copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0f94f-115">返回值</span><span class="sxs-lookup"><span data-stu-id="0f94f-115">Return value</span></span>

<span data-ttu-id="0f94f-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f94f-116">S_OK</span></span> 
  
> <span data-ttu-id="0f94f-117">已成功返回的标志值。</span><span class="sxs-lookup"><span data-stu-id="0f94f-117">The flags value was returned successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0f94f-118">说明</span><span class="sxs-lookup"><span data-stu-id="0f94f-118">Remarks</span></span>

<span data-ttu-id="0f94f-119">MAPI 启用服务提供商要区分顶级对象，并与 MAPI_TOP_LEVEL 标志的子对象，以便在操作中涉及的所有对象可以使用相同的[IMAPIProgress](imapiprogressiunknown.md)实现以显示进度。</span><span class="sxs-lookup"><span data-stu-id="0f94f-119">MAPI enables service providers to differentiate between top-level objects and subobjects with the MAPI_TOP_LEVEL flag so that all objects involved in an operation can use the same [IMAPIProgress](imapiprogressiunknown.md) implementation to show progress.</span></span> <span data-ttu-id="0f94f-120">这会导致标记显示的一个正数方向顺利。</span><span class="sxs-lookup"><span data-stu-id="0f94f-120">This causes the indicator display to proceed smoothly in a single positive direction.</span></span> <span data-ttu-id="0f94f-121">是否设置 MAPI_TOP_LEVEL 标志确定服务提供程序如何设置对进度对象的后续呼叫中的其他参数。</span><span class="sxs-lookup"><span data-stu-id="0f94f-121">Whether the MAPI_TOP_LEVEL flag is set determines how service providers set the other parameters in subsequent calls to the progress object.</span></span> 
  
<span data-ttu-id="0f94f-122">通过实施并随后服务提供程序通过对[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法的调用最初设置**GetFlags**返回的值。</span><span class="sxs-lookup"><span data-stu-id="0f94f-122">The value returned by **GetFlags** is set initially by the implementer and subsequently by the service provider through a call to the [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="0f94f-123">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="0f94f-123">Notes to implementers</span></span>

<span data-ttu-id="0f94f-124">始终初始化 MAPI_TOP_LEVEL 标志，然后依赖服务提供商，以将其适当时清除。</span><span class="sxs-lookup"><span data-stu-id="0f94f-124">Always initialize the flag to MAPI_TOP_LEVEL and then rely on service providers to clear it when appropriate.</span></span> <span data-ttu-id="0f94f-125">服务提供商可以清除，并重置通过调用**IMAPIProgress::SetLimits**方法的标志。</span><span class="sxs-lookup"><span data-stu-id="0f94f-125">Service providers can clear and reset the flag by calling the **IMAPIProgress::SetLimits** method.</span></span> <span data-ttu-id="0f94f-126">有关如何实施**GetFlags**和其他**IMAPIProgress**方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="0f94f-126">For more information about how to implement **GetFlags** and the other **IMAPIProgress** methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="0f94f-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0f94f-127">Notes to callers</span></span>

<span data-ttu-id="0f94f-128">显示进度指示器，使您第一次调用**IMAPIProgress::GetFlags**调用。</span><span class="sxs-lookup"><span data-stu-id="0f94f-128">When you display a progress indicator, make your first call a call to **IMAPIProgress::GetFlags**.</span></span> <span data-ttu-id="0f94f-129">返回的值应为 MAPI_TOP_LEVEL，因为所有实现都初始化_lpulFlags_参数为此值的内容。</span><span class="sxs-lookup"><span data-stu-id="0f94f-129">The returned value should be MAPI_TOP_LEVEL, because all implementations initialize the contents of the  _lpulFlags_ parameter to this value.</span></span> <span data-ttu-id="0f94f-130">调用进度对象的顺序的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="0f94f-130">For more information about the sequence of calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="0f94f-131">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="0f94f-131">MFCMAPI reference</span></span>

<span data-ttu-id="0f94f-132">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="0f94f-132">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="0f94f-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="0f94f-133">**File**</span></span>|<span data-ttu-id="0f94f-134">**函数**</span><span class="sxs-lookup"><span data-stu-id="0f94f-134">**Function**</span></span>|<span data-ttu-id="0f94f-135">**Comment**</span><span class="sxs-lookup"><span data-stu-id="0f94f-135">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f94f-136">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="0f94f-136">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="0f94f-137">CMAPIProgress::GetFlags</span><span class="sxs-lookup"><span data-stu-id="0f94f-137">CMAPIProgress::GetFlags</span></span>  <br/> |<span data-ttu-id="0f94f-138">MFCMAPI 使用**IMAPIProgress::GetFlags**方法来确定哪些标志设置。</span><span class="sxs-lookup"><span data-stu-id="0f94f-138">MFCMAPI uses the **IMAPIProgress::GetFlags** method to determine which flags are set.</span></span> <span data-ttu-id="0f94f-139">返回 MAPI_TOP_LEVEL，除非已设置使用**IMAPIProgress::SetLimits**方法的标志。</span><span class="sxs-lookup"><span data-stu-id="0f94f-139">Returns MAPI_TOP_LEVEL unless flags have been set by using the **IMAPIProgress::SetLimits** method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0f94f-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f94f-140">See also</span></span>



[<span data-ttu-id="0f94f-141">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="0f94f-141">IMAPIProgress::SetLimits</span></span>](imapiprogress-setlimits.md)
  
[<span data-ttu-id="0f94f-142">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0f94f-142">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="0f94f-143">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="0f94f-143">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="0f94f-144">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="0f94f-144">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="0f94f-145">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="0f94f-145">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

