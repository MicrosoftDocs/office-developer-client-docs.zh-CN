---
title: IMAPIControlGetState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIControl.GetState
api_type:
- COM
ms.assetid: fb321b48-3e5f-4b99-9af0-a57b66f26a2e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a6ae89bf9b2b16439cc06f0e106859dda10ea22c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775320"
---
# <a name="imapicontrolgetstate"></a><span data-ttu-id="4252c-103">IMAPIControl::GetState</span><span class="sxs-lookup"><span data-stu-id="4252c-103">IMAPIControl::GetState</span></span>

  
  
<span data-ttu-id="4252c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4252c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4252c-105">检索值，该值指示是否启用或禁用按钮控件。</span><span class="sxs-lookup"><span data-stu-id="4252c-105">Retrieves a value that indicates whether the button control is enabled or disabled.</span></span>
  
```cpp
HRESULT GetState(
  ULONG ulFlags,
  ULONG FAR * lpulState
);
```

## <a name="parameters"></a><span data-ttu-id="4252c-106">参数</span><span class="sxs-lookup"><span data-stu-id="4252c-106">Parameters</span></span>

 <span data-ttu-id="4252c-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="4252c-107">_ulFlags_</span></span>
  
> <span data-ttu-id="4252c-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="4252c-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="4252c-109">_lpulState_</span><span class="sxs-lookup"><span data-stu-id="4252c-109">_lpulState_</span></span>
  
> <span data-ttu-id="4252c-110">[输出]指向一个值，指示的状态按钮控件的指针。</span><span class="sxs-lookup"><span data-stu-id="4252c-110">[out] A pointer to a value that indicates the state of the button control.</span></span> <span data-ttu-id="4252c-111">可以返回下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4252c-111">One of the following values can be returned:</span></span>
    
<span data-ttu-id="4252c-112">MAPI_DISABLED</span><span class="sxs-lookup"><span data-stu-id="4252c-112">MAPI_DISABLED</span></span> 
  
> <span data-ttu-id="4252c-113">按钮控件将禁用，并且不能单击。</span><span class="sxs-lookup"><span data-stu-id="4252c-113">The button control is disabled and cannot be clicked.</span></span> 
    
<span data-ttu-id="4252c-114">MAPI_ENABLED</span><span class="sxs-lookup"><span data-stu-id="4252c-114">MAPI_ENABLED</span></span> 
  
> <span data-ttu-id="4252c-115">按钮控件启用，并且可以单击。</span><span class="sxs-lookup"><span data-stu-id="4252c-115">The button control is enabled and can be clicked.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4252c-116">返回值</span><span class="sxs-lookup"><span data-stu-id="4252c-116">Return value</span></span>

<span data-ttu-id="4252c-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="4252c-117">S_OK</span></span> 
  
> <span data-ttu-id="4252c-118">已成功检索按钮控件的状态。</span><span class="sxs-lookup"><span data-stu-id="4252c-118">The state of the button control was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4252c-119">说明</span><span class="sxs-lookup"><span data-stu-id="4252c-119">Remarks</span></span>

<span data-ttu-id="4252c-120">服务提供商实现**IMAPIControl::GetState**方法使 MAPI 按钮控件的状态。</span><span class="sxs-lookup"><span data-stu-id="4252c-120">Service providers implement the **IMAPIControl::GetState** method to provide MAPI with the state of a button control.</span></span> <span data-ttu-id="4252c-121">如果启用按钮，则它可以响应鼠标单击或击键。</span><span class="sxs-lookup"><span data-stu-id="4252c-121">If the button is enabled, it can respond to a mouse click or key press.</span></span> <span data-ttu-id="4252c-122">如果它被禁用，该按钮变暗，并对鼠标单击或击键没有响应。</span><span class="sxs-lookup"><span data-stu-id="4252c-122">If it is disabled, the button appears dimmed and does not respond to a mouse click or key press.</span></span> 
  
<span data-ttu-id="4252c-123">有关如何实施**GetState**和其他详细信息[IMAPIControl: IUnknown](imapicontroliunknown.md)方法，请参阅[控件对象实现](control-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="4252c-123">For more information about how to implement **GetState** and the other [IMAPIControl : IUnknown](imapicontroliunknown.md) methods, see [Control Object Implementation](control-object-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4252c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4252c-124">See also</span></span>



[<span data-ttu-id="4252c-125">IMAPIControl::Activate</span><span class="sxs-lookup"><span data-stu-id="4252c-125">IMAPIControl::Activate</span></span>](imapicontrol-activate.md)
  
[<span data-ttu-id="4252c-126">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4252c-126">IMAPIControl : IUnknown</span></span>](imapicontroliunknown.md)

