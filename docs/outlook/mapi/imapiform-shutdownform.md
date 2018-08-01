---
title: IMAPIFormShutdownForm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.ShutdownForm
api_type:
- COM
ms.assetid: f1e2a526-40ad-4a93-908f-8ab9a65928a8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9a6ab96a70bce622f44de6576e7b77861302de4f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775374"
---
# <a name="imapiformshutdownform"></a><span data-ttu-id="733a1-103">IMAPIForm::ShutdownForm</span><span class="sxs-lookup"><span data-stu-id="733a1-103">IMAPIForm::ShutdownForm</span></span>

  
  
<span data-ttu-id="733a1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="733a1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="733a1-105">关闭表单。</span><span class="sxs-lookup"><span data-stu-id="733a1-105">Closes the form.</span></span>
  
```cpp
HRESULT ShutdownForm(
  ULONG ulSaveOptions
);
```

## <a name="parameters"></a><span data-ttu-id="733a1-106">参数</span><span class="sxs-lookup"><span data-stu-id="733a1-106">Parameters</span></span>

 <span data-ttu-id="733a1-107">_ulSaveOptions_</span><span class="sxs-lookup"><span data-stu-id="733a1-107">_ulSaveOptions_</span></span>
  
> <span data-ttu-id="733a1-108">[in]一个控件之前关闭窗体如何或是否保存表单中的数据的值。</span><span class="sxs-lookup"><span data-stu-id="733a1-108">[in] A value that controls how or whether data in the form is saved before the form is closed.</span></span> <span data-ttu-id="733a1-109">可以设置以下标志之一：</span><span class="sxs-lookup"><span data-stu-id="733a1-109">One of the following flags can be set:</span></span>
    
<span data-ttu-id="733a1-110">SAVEOPTS_NOSAVE</span><span class="sxs-lookup"><span data-stu-id="733a1-110">SAVEOPTS_NOSAVE</span></span> 
  
> <span data-ttu-id="733a1-111">应不会保存表单数据。</span><span class="sxs-lookup"><span data-stu-id="733a1-111">Form data should not be saved.</span></span>
    
<span data-ttu-id="733a1-112">SAVEOPTS_PROMPTSAVE</span><span class="sxs-lookup"><span data-stu-id="733a1-112">SAVEOPTS_PROMPTSAVE</span></span> 
  
> <span data-ttu-id="733a1-113">应提示用户保存表单中的任何更改的数据。</span><span class="sxs-lookup"><span data-stu-id="733a1-113">The user should be prompted to save any changed data in the form.</span></span>
    
<span data-ttu-id="733a1-114">SAVEOPTS_SAVEIFDIRTY</span><span class="sxs-lookup"><span data-stu-id="733a1-114">SAVEOPTS_SAVEIFDIRTY</span></span> 
  
> <span data-ttu-id="733a1-115">如果上次保存后进行了更改，则应保存表单数据。</span><span class="sxs-lookup"><span data-stu-id="733a1-115">Form data should be saved if it has changed since the last save.</span></span> <span data-ttu-id="733a1-116">如果显示没有用户界面时，窗体可以 （可选） 切换到使用 SAVEOPTS_NOSAVE 选项的功能。</span><span class="sxs-lookup"><span data-stu-id="733a1-116">If no user interface is being displayed, the form can optionally switch to using the functionality for the SAVEOPTS_NOSAVE option.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="733a1-117">返回值</span><span class="sxs-lookup"><span data-stu-id="733a1-117">Return value</span></span>

<span data-ttu-id="733a1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="733a1-118">S_OK</span></span> 
  
> <span data-ttu-id="733a1-119">关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="733a1-119">The form was closed.</span></span>
    
<span data-ttu-id="733a1-120">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="733a1-120">E_UNEXPECTED</span></span> 
  
> <span data-ttu-id="733a1-121">以前调用**ShutdownForm**已被关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="733a1-121">The form was already closed by a prior call to **ShutdownForm**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="733a1-122">说明</span><span class="sxs-lookup"><span data-stu-id="733a1-122">Remarks</span></span>

<span data-ttu-id="733a1-123">表单查看器调用**IMAPIForm::ShutdownForm**方法关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="733a1-123">Form viewers call the **IMAPIForm::ShutdownForm** method to close a form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="733a1-124">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="733a1-124">Notes to implementers</span></span>

<span data-ttu-id="733a1-125">**ShutdownForm**在实现中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="733a1-125">Perform the following tasks in your implementation of **ShutdownForm**:</span></span>
  
1. <span data-ttu-id="733a1-126">检查的一个查看器不已调用**ShutdownForm**，并返回 E_UNEXPECTED，如果它具有。</span><span class="sxs-lookup"><span data-stu-id="733a1-126">Check that a viewer has not already called **ShutdownForm**, and return E_UNEXPECTED if it has.</span></span> <span data-ttu-id="733a1-127">尽管这是不可能，应检查。</span><span class="sxs-lookup"><span data-stu-id="733a1-127">Although this is unlikely, you should check.</span></span>
    
2. <span data-ttu-id="733a1-128">调用窗体的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx)方法，以便完成处理之前，仍可存储窗体和任何内部数据结构。</span><span class="sxs-lookup"><span data-stu-id="733a1-128">Call your form's [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx) method so that storage for the form and any internal data structures remain available until processing is finished.</span></span> 
    
3. <span data-ttu-id="733a1-129">确定是否有任何未保存的更改窗体的数据。</span><span class="sxs-lookup"><span data-stu-id="733a1-129">Determine whether there are any unsaved changes to the form's data.</span></span> <span data-ttu-id="733a1-130">保存未保存的数据，根据如何_ulSaveOptions_参数设置通过调用查看器的[IMAPIMessageSite::SaveMessage](imapimessagesite-savemessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="733a1-130">Save unsaved data according to how the  _ulSaveOptions_ parameter is set by calling your viewer's [IMAPIMessageSite::SaveMessage](imapimessagesite-savemessage.md) method.</span></span> 
    
4. <span data-ttu-id="733a1-131">销毁窗体的用户界面窗口。</span><span class="sxs-lookup"><span data-stu-id="733a1-131">Destroy your form's user interface window.</span></span>
    
5. <span data-ttu-id="733a1-132">通过调用其[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法释放窗体的邮件和消息网站对象。</span><span class="sxs-lookup"><span data-stu-id="733a1-132">Release your form's message and message site objects by calling their [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) methods.</span></span> 
    
6. <span data-ttu-id="733a1-133">通过调用其[IMAPIViewAdviseSink::OnShutdown](imapiviewadvisesink-onshutdown.md)方法通知所有已注册查看器的挂起关闭。</span><span class="sxs-lookup"><span data-stu-id="733a1-133">Notify all registered viewers of the pending shutdown by calling their [IMAPIViewAdviseSink::OnShutdown](imapiviewadvisesink-onshutdown.md) methods.</span></span> 
    
7. <span data-ttu-id="733a1-134">调用[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)方法取消由 advise 接收器指针设置为**null**的通知的窗体的注册。</span><span class="sxs-lookup"><span data-stu-id="733a1-134">Call the [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md) method to cancel your form's registration for notification by setting the advise sink pointer to **null**.</span></span>
    
8. <span data-ttu-id="733a1-135">调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放内存的窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="733a1-135">Call the [MAPIFreeBuffer](mapifreebuffer.md) function to free the memory for your form's properties.</span></span> 
    
9. <span data-ttu-id="733a1-136">调用匹配**AddRef**呼叫在步骤 2 中所做的窗体的**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="733a1-136">Call your form's **IUnknown::Release** method, matching the **AddRef** call made in step 2.</span></span> 
    
10. <span data-ttu-id="733a1-137">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="733a1-137">Return S_OK.</span></span>
    
> [!NOTE]
> <span data-ttu-id="733a1-138">这些操作完成后，可能会调用的窗体对象上的唯一有效方法是从[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="733a1-138">After these actions have been completed, the only valid methods on the form object that may be called are those from the [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) interface.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="733a1-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="733a1-139">Notes to callers</span></span>

<span data-ttu-id="733a1-140">当**ShutdownForm**返回，而不管是否返回错误，通过调用其**IUnknown::Release**方法释放窗体。</span><span class="sxs-lookup"><span data-stu-id="733a1-140">When **ShutdownForm** returns, regardless of whether it returns an error, release the form by calling its **IUnknown::Release** method.</span></span> <span data-ttu-id="733a1-141">您可以忽略**ShutdownForm**返回任何错误。</span><span class="sxs-lookup"><span data-stu-id="733a1-141">You can safely ignore any errors returned by **ShutdownForm**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="733a1-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="733a1-142">See also</span></span>



[<span data-ttu-id="733a1-143">IMAPIMessageSite::SaveMessage</span><span class="sxs-lookup"><span data-stu-id="733a1-143">IMAPIMessageSite::SaveMessage</span></span>](imapimessagesite-savemessage.md)
  
[<span data-ttu-id="733a1-144">IMAPIViewAdviseSink::OnShutdown</span><span class="sxs-lookup"><span data-stu-id="733a1-144">IMAPIViewAdviseSink::OnShutdown</span></span>](imapiviewadvisesink-onshutdown.md)
  
[<span data-ttu-id="733a1-145">IMAPIViewContext::SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="733a1-145">IMAPIViewContext::SetAdviseSink</span></span>](imapiviewcontext-setadvisesink.md)
  
[<span data-ttu-id="733a1-146">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="733a1-146">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="733a1-147">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="733a1-147">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)

