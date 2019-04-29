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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f477c617533d66fc129c7192c9f86bb8a46afbb1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419007"
---
# <a name="imapicontrolgetstate"></a><span data-ttu-id="79d90-103">IMAPIControl::GetState</span><span class="sxs-lookup"><span data-stu-id="79d90-103">IMAPIControl::GetState</span></span>

  
  
<span data-ttu-id="79d90-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79d90-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79d90-105">检索一个值, 该值指示按钮控件是否已启用或已禁用。</span><span class="sxs-lookup"><span data-stu-id="79d90-105">Retrieves a value that indicates whether the button control is enabled or disabled.</span></span>
  
```cpp
HRESULT GetState(
  ULONG ulFlags,
  ULONG FAR * lpulState
);
```

## <a name="parameters"></a><span data-ttu-id="79d90-106">参数</span><span class="sxs-lookup"><span data-stu-id="79d90-106">Parameters</span></span>

 <span data-ttu-id="79d90-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="79d90-107">_ulFlags_</span></span>
  
> <span data-ttu-id="79d90-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="79d90-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="79d90-109">_lpulState_</span><span class="sxs-lookup"><span data-stu-id="79d90-109">_lpulState_</span></span>
  
> <span data-ttu-id="79d90-110">排除指向指示按钮控件状态的值的指针。</span><span class="sxs-lookup"><span data-stu-id="79d90-110">[out] A pointer to a value that indicates the state of the button control.</span></span> <span data-ttu-id="79d90-111">可以返回下列值之一:</span><span class="sxs-lookup"><span data-stu-id="79d90-111">One of the following values can be returned:</span></span>
    
<span data-ttu-id="79d90-112">MAPI_DISABLED</span><span class="sxs-lookup"><span data-stu-id="79d90-112">MAPI_DISABLED</span></span> 
  
> <span data-ttu-id="79d90-113">按钮控件已被禁用, 无法单击。</span><span class="sxs-lookup"><span data-stu-id="79d90-113">The button control is disabled and cannot be clicked.</span></span> 
    
<span data-ttu-id="79d90-114">MAPI_ENABLED</span><span class="sxs-lookup"><span data-stu-id="79d90-114">MAPI_ENABLED</span></span> 
  
> <span data-ttu-id="79d90-115">按钮控件已启用, 可以单击。</span><span class="sxs-lookup"><span data-stu-id="79d90-115">The button control is enabled and can be clicked.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="79d90-116">返回值</span><span class="sxs-lookup"><span data-stu-id="79d90-116">Return value</span></span>

<span data-ttu-id="79d90-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="79d90-117">S_OK</span></span> 
  
> <span data-ttu-id="79d90-118">已成功检索按钮控件的状态。</span><span class="sxs-lookup"><span data-stu-id="79d90-118">The state of the button control was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="79d90-119">说明</span><span class="sxs-lookup"><span data-stu-id="79d90-119">Remarks</span></span>

<span data-ttu-id="79d90-120">服务提供程序实现**IMAPIControl:: GetState**方法, 以向 MAPI 提供按钮控件的状态。</span><span class="sxs-lookup"><span data-stu-id="79d90-120">Service providers implement the **IMAPIControl::GetState** method to provide MAPI with the state of a button control.</span></span> <span data-ttu-id="79d90-121">如果按钮已启用, 则它可以响应鼠标单击或按键。</span><span class="sxs-lookup"><span data-stu-id="79d90-121">If the button is enabled, it can respond to a mouse click or key press.</span></span> <span data-ttu-id="79d90-122">如果已禁用, 则按钮显示为灰色, 且不响应鼠标单击或按键。</span><span class="sxs-lookup"><span data-stu-id="79d90-122">If it is disabled, the button appears dimmed and does not respond to a mouse click or key press.</span></span> 
  
<span data-ttu-id="79d90-123">有关如何实现**GetState**和其他[IMAPIControl: IUnknown](imapicontroliunknown.md)方法的详细信息, 请参阅[Control Object 实现](control-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="79d90-123">For more information about how to implement **GetState** and the other [IMAPIControl : IUnknown](imapicontroliunknown.md) methods, see [Control Object Implementation](control-object-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79d90-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79d90-124">See also</span></span>



[<span data-ttu-id="79d90-125">IMAPIControl::Activate</span><span class="sxs-lookup"><span data-stu-id="79d90-125">IMAPIControl::Activate</span></span>](imapicontrol-activate.md)
  
[<span data-ttu-id="79d90-126">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="79d90-126">IMAPIControl : IUnknown</span></span>](imapicontroliunknown.md)

