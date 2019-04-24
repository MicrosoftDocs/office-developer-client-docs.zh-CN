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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 073a76766a296d86e7a23809921b832d494a8f1b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329475"
---
# <a name="imapiformshutdownform"></a><span data-ttu-id="c0d77-103">IMAPIForm::ShutdownForm</span><span class="sxs-lookup"><span data-stu-id="c0d77-103">IMAPIForm::ShutdownForm</span></span>

  
  
<span data-ttu-id="c0d77-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c0d77-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c0d77-105">关闭表单。</span><span class="sxs-lookup"><span data-stu-id="c0d77-105">Closes the form.</span></span>
  
```cpp
HRESULT ShutdownForm(
  ULONG ulSaveOptions
);
```

## <a name="parameters"></a><span data-ttu-id="c0d77-106">参数</span><span class="sxs-lookup"><span data-stu-id="c0d77-106">Parameters</span></span>

 <span data-ttu-id="c0d77-107">_ulSaveOptions_</span><span class="sxs-lookup"><span data-stu-id="c0d77-107">_ulSaveOptions_</span></span>
  
> <span data-ttu-id="c0d77-108">实时用于控制表单中的数据在窗体关闭之前的保存方式或是否保存的值。</span><span class="sxs-lookup"><span data-stu-id="c0d77-108">[in] A value that controls how or whether data in the form is saved before the form is closed.</span></span> <span data-ttu-id="c0d77-109">可以设置下列标志之一:</span><span class="sxs-lookup"><span data-stu-id="c0d77-109">One of the following flags can be set:</span></span>
    
<span data-ttu-id="c0d77-110">SAVEOPTS_NOSAVE</span><span class="sxs-lookup"><span data-stu-id="c0d77-110">SAVEOPTS_NOSAVE</span></span> 
  
> <span data-ttu-id="c0d77-111">不应保存窗体数据。</span><span class="sxs-lookup"><span data-stu-id="c0d77-111">Form data should not be saved.</span></span>
    
<span data-ttu-id="c0d77-112">SAVEOPTS_PROMPTSAVE</span><span class="sxs-lookup"><span data-stu-id="c0d77-112">SAVEOPTS_PROMPTSAVE</span></span> 
  
> <span data-ttu-id="c0d77-113">应提示用户在表单中保存任何已更改的数据。</span><span class="sxs-lookup"><span data-stu-id="c0d77-113">The user should be prompted to save any changed data in the form.</span></span>
    
<span data-ttu-id="c0d77-114">SAVEOPTS_SAVEIFDIRTY</span><span class="sxs-lookup"><span data-stu-id="c0d77-114">SAVEOPTS_SAVEIFDIRTY</span></span> 
  
> <span data-ttu-id="c0d77-115">如果表单数据自上次保存后进行了更改, 则应将其保存。</span><span class="sxs-lookup"><span data-stu-id="c0d77-115">Form data should be saved if it has changed since the last save.</span></span> <span data-ttu-id="c0d77-116">如果未显示用户界面, 则表单可以选择切换为使用 SAVEOPTS_NOSAVE 选项的功能。</span><span class="sxs-lookup"><span data-stu-id="c0d77-116">If no user interface is being displayed, the form can optionally switch to using the functionality for the SAVEOPTS_NOSAVE option.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c0d77-117">返回值</span><span class="sxs-lookup"><span data-stu-id="c0d77-117">Return value</span></span>

<span data-ttu-id="c0d77-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0d77-118">S_OK</span></span> 
  
> <span data-ttu-id="c0d77-119">表单已关闭。</span><span class="sxs-lookup"><span data-stu-id="c0d77-119">The form was closed.</span></span>
    
<span data-ttu-id="c0d77-120">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="c0d77-120">E_UNEXPECTED</span></span> 
  
> <span data-ttu-id="c0d77-121">表单已被以前调用**ShutdownForm**关闭。</span><span class="sxs-lookup"><span data-stu-id="c0d77-121">The form was already closed by a prior call to **ShutdownForm**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c0d77-122">注解</span><span class="sxs-lookup"><span data-stu-id="c0d77-122">Remarks</span></span>

<span data-ttu-id="c0d77-123">表单查看者调用**IMAPIForm:: ShutdownForm**方法以关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="c0d77-123">Form viewers call the **IMAPIForm::ShutdownForm** method to close a form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="c0d77-124">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="c0d77-124">Notes to implementers</span></span>

<span data-ttu-id="c0d77-125">在您的**ShutdownForm**实现中执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="c0d77-125">Perform the following tasks in your implementation of **ShutdownForm**:</span></span>
  
1. <span data-ttu-id="c0d77-126">检查查看器是否尚未调用**ShutdownForm**, 如果有, 则返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="c0d77-126">Check that a viewer has not already called **ShutdownForm**, and return E_UNEXPECTED if it has.</span></span> <span data-ttu-id="c0d77-127">尽管这不太可能, 但应该进行检查。</span><span class="sxs-lookup"><span data-stu-id="c0d77-127">Although this is unlikely, you should check.</span></span>
    
2. <span data-ttu-id="c0d77-128">调用表单的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)方法, 以便在处理完成后, 表单和任何内部数据结构的存储仍可用。</span><span class="sxs-lookup"><span data-stu-id="c0d77-128">Call your form's [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) method so that storage for the form and any internal data structures remain available until processing is finished.</span></span> 
    
3. <span data-ttu-id="c0d77-129">确定表单数据是否有任何未保存的更改。</span><span class="sxs-lookup"><span data-stu-id="c0d77-129">Determine whether there are any unsaved changes to the form's data.</span></span> <span data-ttu-id="c0d77-130">根据通过调用您的查看器的[IMAPIMessageSite:: SaveMessage](imapimessagesite-savemessage.md)方法设置_ulSaveOptions_参数的方式, 保存未保存的数据。</span><span class="sxs-lookup"><span data-stu-id="c0d77-130">Save unsaved data according to how the  _ulSaveOptions_ parameter is set by calling your viewer's [IMAPIMessageSite::SaveMessage](imapimessagesite-savemessage.md) method.</span></span> 
    
4. <span data-ttu-id="c0d77-131">销毁表单的用户界面窗口。</span><span class="sxs-lookup"><span data-stu-id="c0d77-131">Destroy your form's user interface window.</span></span>
    
5. <span data-ttu-id="c0d77-132">通过调用其[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法来释放表单的邮件和邮件网站对象。</span><span class="sxs-lookup"><span data-stu-id="c0d77-132">Release your form's message and message site objects by calling their [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) methods.</span></span> 
    
6. <span data-ttu-id="c0d77-133">通过调用[IMAPIViewAdviseSink:: OnShutdown](imapiviewadvisesink-onshutdown.md)方法, 通知所有已注册的查看器是否有挂起的关闭。</span><span class="sxs-lookup"><span data-stu-id="c0d77-133">Notify all registered viewers of the pending shutdown by calling their [IMAPIViewAdviseSink::OnShutdown](imapiviewadvisesink-onshutdown.md) methods.</span></span> 
    
7. <span data-ttu-id="c0d77-134">通过将建议接收器指针设置为**null**, 调用[IMAPIViewContext:: SetAdviseSink](imapiviewcontext-setadvisesink.md)方法以取消表单的注册通知。</span><span class="sxs-lookup"><span data-stu-id="c0d77-134">Call the [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md) method to cancel your form's registration for notification by setting the advise sink pointer to **null**.</span></span>
    
8. <span data-ttu-id="c0d77-135">调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放窗体属性的内存。</span><span class="sxs-lookup"><span data-stu-id="c0d77-135">Call the [MAPIFreeBuffer](mapifreebuffer.md) function to free the memory for your form's properties.</span></span> 
    
9. <span data-ttu-id="c0d77-136">调用表单的**IUnknown:: Release**方法, 匹配在步骤2中进行的**AddRef**呼叫。</span><span class="sxs-lookup"><span data-stu-id="c0d77-136">Call your form's **IUnknown::Release** method, matching the **AddRef** call made in step 2.</span></span> 
    
10. <span data-ttu-id="c0d77-137">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="c0d77-137">Return S_OK.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c0d77-138">完成这些操作后, 可以调用的窗体对象上唯一有效的方法是[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="c0d77-138">After these actions have been completed, the only valid methods on the form object that may be called are those from the [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) interface.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c0d77-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c0d77-139">Notes to callers</span></span>

<span data-ttu-id="c0d77-140">当**ShutdownForm**返回时, 无论是否返回错误, 都通过调用其**IUnknown:: release**方法来释放窗体。</span><span class="sxs-lookup"><span data-stu-id="c0d77-140">When **ShutdownForm** returns, regardless of whether it returns an error, release the form by calling its **IUnknown::Release** method.</span></span> <span data-ttu-id="c0d77-141">您可以安全地忽略由**ShutdownForm**返回的任何错误。</span><span class="sxs-lookup"><span data-stu-id="c0d77-141">You can safely ignore any errors returned by **ShutdownForm**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c0d77-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0d77-142">See also</span></span>



[<span data-ttu-id="c0d77-143">IMAPIMessageSite::SaveMessage</span><span class="sxs-lookup"><span data-stu-id="c0d77-143">IMAPIMessageSite::SaveMessage</span></span>](imapimessagesite-savemessage.md)
  
[<span data-ttu-id="c0d77-144">IMAPIViewAdviseSink::OnShutdown</span><span class="sxs-lookup"><span data-stu-id="c0d77-144">IMAPIViewAdviseSink::OnShutdown</span></span>](imapiviewadvisesink-onshutdown.md)
  
[<span data-ttu-id="c0d77-145">IMAPIViewContext::SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="c0d77-145">IMAPIViewContext::SetAdviseSink</span></span>](imapiviewcontext-setadvisesink.md)
  
[<span data-ttu-id="c0d77-146">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="c0d77-146">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="c0d77-147">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c0d77-147">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)

