---
title: IMAPIFormSetViewContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.SetViewContext
api_type:
- COM
ms.assetid: a7b10007-42d8-4755-8362-f8ad9a8dad68
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 81d99b2bbe6ef7914a4b7d253a3472026872260d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350944"
---
# <a name="imapiformsetviewcontext"></a><span data-ttu-id="45d6a-103">IMAPIForm::SetViewContext</span><span class="sxs-lookup"><span data-stu-id="45d6a-103">IMAPIForm::SetViewContext</span></span>

  
  
<span data-ttu-id="45d6a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="45d6a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="45d6a-105">建立表单的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="45d6a-105">Establishes a view context for the form.</span></span> 
  
```cpp
HRESULT SetViewContext(
  LPMAPIVIEWCONTEXT pViewContext
);
```

## <a name="parameters"></a><span data-ttu-id="45d6a-106">参数</span><span class="sxs-lookup"><span data-stu-id="45d6a-106">Parameters</span></span>

 <span data-ttu-id="45d6a-107">_pViewContext_</span><span class="sxs-lookup"><span data-stu-id="45d6a-107">_pViewContext_</span></span>
  
> <span data-ttu-id="45d6a-108">[in]指向表单的新视图上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="45d6a-108">[in] A pointer to the new view context for the form.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="45d6a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="45d6a-109">Return value</span></span>

<span data-ttu-id="45d6a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="45d6a-110">S_OK</span></span> 
  
> <span data-ttu-id="45d6a-111">已成功设置视图上下文。</span><span class="sxs-lookup"><span data-stu-id="45d6a-111">The view context was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="45d6a-112">备注</span><span class="sxs-lookup"><span data-stu-id="45d6a-112">Remarks</span></span>

<span data-ttu-id="45d6a-113">表单查看器调用 **IMAPIForm：：SetViewContext** 方法以将特定的表单视图上下文建立为当前上下文。</span><span class="sxs-lookup"><span data-stu-id="45d6a-113">Form viewers call the **IMAPIForm::SetViewContext** method to establish a particular form view context as current.</span></span> <span data-ttu-id="45d6a-114">表单一次只能有一个视图上下文。</span><span class="sxs-lookup"><span data-stu-id="45d6a-114">A form can have only one view context at a time.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="45d6a-115">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="45d6a-115">Notes to implementers</span></span>

<span data-ttu-id="45d6a-116">大多数表单服务器通过以下算法实现 **SetViewContext：**</span><span class="sxs-lookup"><span data-stu-id="45d6a-116">Most form servers implement **SetViewContext** by using the following algorithm:</span></span> 
  
- <span data-ttu-id="45d6a-117">如果表单已存在视图上下文，则通过调用 _pmnvs_ 参数中为 **null** 的 [IMAPIViewContext：：SetAdviseSink](imapiviewcontext-setadvisesink.md)方法取消表单的注册，然后调用视图上下文的 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法来缩小其引用计数。</span><span class="sxs-lookup"><span data-stu-id="45d6a-117">If a view context already exists for the form, cancel the form's registration by calling the [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md) method with **null** in the  _pmnvs_ parameter, and then call the view context's [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method to decrement its reference count.</span></span> 
    
- <span data-ttu-id="45d6a-118">如果新视图上下文不 **为空**，则使用 _pViewContext_ 参数设置新视图建议接收器来调用 **IMAPIViewContext：：SetAdviseSink。**</span><span class="sxs-lookup"><span data-stu-id="45d6a-118">If the new view context is not **null**, call **IMAPIViewContext::SetAdviseSink** by using the  _pViewContext_ parameter to set up a new view advise sink.</span></span> 
    
- <span data-ttu-id="45d6a-119">如果新视图上下文不 **为空**，请调用 [IMAPIViewContext：：GetViewStatus](imapiviewcontext-getviewstatus.md) 方法以确定已设置的状态标志。</span><span class="sxs-lookup"><span data-stu-id="45d6a-119">If the new view context is not **null**, call the [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md) method to determine which status flags have been set.</span></span> 
    
- <span data-ttu-id="45d6a-120">如果新视图上下文不 **为空**，请存储它并调用其 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) 方法来增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="45d6a-120">If the new view context is not **null**, store it and call its [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) method to increment its reference count.</span></span> 
    
- <span data-ttu-id="45d6a-121">更新依赖于视图上下文的任何用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="45d6a-121">Update any user interface elements that depend on the view context.</span></span> 
    
<span data-ttu-id="45d6a-122">根据从 **IMAPIViewContext：：GetViewStatus** 返回的状态标志 **，SetViewContext** 还可以执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="45d6a-122">Depending on the status flags returned from **IMAPIViewContext::GetViewStatus**, **SetViewContext** can also perform other actions.</span></span> <span data-ttu-id="45d6a-123">例如，如果返回 VCSTATUS_NEXT 和 VCSTATUS_PREV 标志，**则 SetViewContext** 可以启用新视图上下文的"下一步"和"上一步"按钮。</span><span class="sxs-lookup"><span data-stu-id="45d6a-123">For example, if the VCSTATUS_NEXT and VCSTATUS_PREV flags are returned, **SetViewContext** can enable the **Next** and **Previous** buttons for the new view context.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="45d6a-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="45d6a-124">MFCMAPI reference</span></span>

<span data-ttu-id="45d6a-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="45d6a-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="45d6a-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="45d6a-126">**File**</span></span>|<span data-ttu-id="45d6a-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="45d6a-127">**Function**</span></span>|<span data-ttu-id="45d6a-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="45d6a-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="45d6a-129">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="45d6a-129">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="45d6a-130">CreateAndDisplayNewMailInFolder</span><span class="sxs-lookup"><span data-stu-id="45d6a-130">CreateAndDisplayNewMailInFolder</span></span>  <br/> |<span data-ttu-id="45d6a-131">MFCMAPI 在显示表单之前，使用 **IMAPIForm：：SetViewContext** 方法在表单上设置 MFCMAPI 的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="45d6a-131">MFCMAPI uses the **IMAPIForm::SetViewContext** method to set MFCMAPI's view context on the form before the form is displayed.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="45d6a-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45d6a-132">See also</span></span>



[<span data-ttu-id="45d6a-133">IMAPIViewContext::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="45d6a-133">IMAPIViewContext::GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md)
  
[<span data-ttu-id="45d6a-134">IMAPIViewContext::SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="45d6a-134">IMAPIViewContext::SetAdviseSink</span></span>](imapiviewcontext-setadvisesink.md)
  
[<span data-ttu-id="45d6a-135">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="45d6a-135">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)


[<span data-ttu-id="45d6a-136">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="45d6a-136">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

