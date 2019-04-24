---
title: IMAPIViewContextGetViewStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.GetViewStatus
api_type:
- COM
ms.assetid: 2e5ec914-7171-41ce-a6fe-78dd80ac32ff
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bb8699746b3f4207ee70edd4e56d0ec6041beac2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351175"
---
# <a name="imapiviewcontextgetviewstatus"></a><span data-ttu-id="8d5cc-103">IMAPIViewContext::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="8d5cc-103">IMAPIViewContext::GetViewStatus</span></span>

  
  
<span data-ttu-id="8d5cc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8d5cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8d5cc-105">检索当前查看器状态。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-105">Retrieves the current viewer status.</span></span> 
  
```cpp
HRESULT GetViewStatus(
ULONG FAR * lpulStatus
);
```

## <a name="parameters"></a><span data-ttu-id="8d5cc-106">参数</span><span class="sxs-lookup"><span data-stu-id="8d5cc-106">Parameters</span></span>

 <span data-ttu-id="8d5cc-107">_lpulStatus_</span><span class="sxs-lookup"><span data-stu-id="8d5cc-107">_lpulStatus_</span></span>
  
> <span data-ttu-id="8d5cc-108">排除指向提供查看器状态的标志的位掩码的指针。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-108">[out] Pointer to a bitmask of flags providing the status of the viewer.</span></span> <span data-ttu-id="8d5cc-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="8d5cc-109">The following flags can be set:</span></span>
    
<span data-ttu-id="8d5cc-110">VCSTATUS_CATEGORY</span><span class="sxs-lookup"><span data-stu-id="8d5cc-110">VCSTATUS_CATEGORY</span></span> 
  
> <span data-ttu-id="8d5cc-111">另一个类别中有下一个或上一个邮件。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-111">There is a next or previous message in another category.</span></span> 
    
<span data-ttu-id="8d5cc-112">VCSTATUS_DELETE</span><span class="sxs-lookup"><span data-stu-id="8d5cc-112">VCSTATUS_DELETE</span></span> 
  
> <span data-ttu-id="8d5cc-113">该窗体允许删除邮件。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-113">The form allows messages to be removed.</span></span> 
    
<span data-ttu-id="8d5cc-114">VCSTATUS_INTERACTIVE</span><span class="sxs-lookup"><span data-stu-id="8d5cc-114">VCSTATUS_INTERACTIVE</span></span> 
  
> <span data-ttu-id="8d5cc-115">表单应显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-115">The form should display a user interface.</span></span> <span data-ttu-id="8d5cc-116">如果未设置此标志, 则表单应禁止显示用户界面, 即使是响应通常会导致显示用户界面的动作也是如此。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-116">If this flag is not set, the form should suppress displaying a user interface even in response to a verb that usually causes a user interface to be displayed.</span></span> 
    
<span data-ttu-id="8d5cc-117">VCSTATUS_MODAL</span><span class="sxs-lookup"><span data-stu-id="8d5cc-117">VCSTATUS_MODAL</span></span> 
  
> <span data-ttu-id="8d5cc-118">窗体是查看器的模式。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-118">The form is modal to the viewer.</span></span> 
    
<span data-ttu-id="8d5cc-119">VCSTATUS_NEXT</span><span class="sxs-lookup"><span data-stu-id="8d5cc-119">VCSTATUS_NEXT</span></span> 
  
> <span data-ttu-id="8d5cc-120">视图中存在下一条消息。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-120">There is a next message in the view.</span></span> 
    
<span data-ttu-id="8d5cc-121">VCSTATUS_PREV</span><span class="sxs-lookup"><span data-stu-id="8d5cc-121">VCSTATUS_PREV</span></span> 
  
> <span data-ttu-id="8d5cc-122">视图中有上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-122">There is a previous message in the view.</span></span> 
    
<span data-ttu-id="8d5cc-123">VCSTATUS_READONLY</span><span class="sxs-lookup"><span data-stu-id="8d5cc-123">VCSTATUS_READONLY</span></span> 
  
> <span data-ttu-id="8d5cc-124">将在只读模式下打开邮件。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-124">The message is to be opened in read-only mode.</span></span> <span data-ttu-id="8d5cc-125">应禁用删除、提交和移动操作。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-125">Delete, submit, and move operations should be disabled.</span></span> 
    
<span data-ttu-id="8d5cc-126">VCSTATUS_UNREAD</span><span class="sxs-lookup"><span data-stu-id="8d5cc-126">VCSTATUS_UNREAD</span></span> 
  
> <span data-ttu-id="8d5cc-127">视图中存在下一个或上一个未读邮件。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-127">There is a next or previous unread message in the view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8d5cc-128">返回值</span><span class="sxs-lookup"><span data-stu-id="8d5cc-128">Return value</span></span>

<span data-ttu-id="8d5cc-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d5cc-129">S_OK</span></span> 
  
> <span data-ttu-id="8d5cc-130">已成功返回查看器的状态。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-130">The viewer's status was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8d5cc-131">注解</span><span class="sxs-lookup"><span data-stu-id="8d5cc-131">Remarks</span></span>

<span data-ttu-id="8d5cc-132">表单对象调用**IMAPIViewContext:: GetViewStatus**方法, 以确定在一种或两种方向的 "窗体" 视图中是否有更多的要激活的邮件, 这些方向是在 "**下一步**" 命令激活邮件的方向, 在上一个命令激活邮件的方向, 或在两个方向**上**激活邮件的方向。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-132">Form objects call the **IMAPIViewContext::GetViewStatus** method to determine whether there are more messages to be activated in a form view in either or both directions that is, in the direction in which a **Next** command activates messages, in the direction in which a **Previous** command activates messages, or in both directions.</span></span> <span data-ttu-id="8d5cc-133">_lpulStatus_参数所指向的值用于确定 VCSTATUS_NEXT 和 VCSTATUS_PREV 标志对[IMAPIViewContext:: ActivateNext](imapiviewcontext-activatenext.md)是否有效。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-133">The value pointed to by the  _lpulStatus_ parameter is used to determine whether the VCSTATUS_NEXT and VCSTATUS_PREV flags are valid for [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md).</span></span> <span data-ttu-id="8d5cc-134">如果设置了 VCSTATUS_DELETE 标志, 而不是 VCSTATUS_READONLY 标志, 则可以使用[IMAPIMessageSite::D eletemessage](imapimessagesite-deletemessage.md)方法删除邮件。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-134">If the VCSTATUS_DELETE flag is set, but not the VCSTATUS_READONLY flag, then the message can be deleted using the [IMAPIMessageSite::DeleteMessage](imapimessagesite-deletemessage.md) method.</span></span> 
  
<span data-ttu-id="8d5cc-135">通常, 如果窗体对查看者的上下文无效, 则会禁用菜单命令和按钮。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-135">Typically, forms disable menu commands and buttons if they are not valid for the viewer's context.</span></span> <span data-ttu-id="8d5cc-136">查看者可以通过调用其[IMAPIFormAdviseSink:: OnChange](imapiformadvisesink-onchange.md)方法, 将窗体的状态更改警告到状态更改。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-136">A viewer can alert a form to a change in status by calling its [IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md) method.</span></span> 
  
<span data-ttu-id="8d5cc-137">如果窗体必须是在之前的 IMAPIForm 中传递的句柄所在窗口的模式, 则设置 VCSTATUS_MODAL 标志[::D overb](imapiform-doverb.md)调用。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-137">The VCSTATUS_MODAL flag is set if the form must be modal to the window whose handle is passed in the earlier [IMAPIForm::DoVerb](imapiform-doverb.md) call.</span></span> <span data-ttu-id="8d5cc-138">如果设置了 VCSTATUS_MODAL, 则表单可以使用在其上进行**DoVerb**调用的线程, 直到窗体关闭。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-138">If VCSTATUS_MODAL is set, the form can use the thread on which the **DoVerb** call was made until the form closes.</span></span> <span data-ttu-id="8d5cc-139">如果未设置 VCSTATUS_MODAL, 则该窗体不应为此窗口的模式, 并且不得使用该线程。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-139">If VCSTATUS_MODAL is not set, the form should not be modal to this window and must not use the thread.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="8d5cc-140">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="8d5cc-140">MFCMAPI reference</span></span>

<span data-ttu-id="8d5cc-141">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-141">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="8d5cc-142">**文件**</span><span class="sxs-lookup"><span data-stu-id="8d5cc-142">**File**</span></span>|<span data-ttu-id="8d5cc-143">**函数**</span><span class="sxs-lookup"><span data-stu-id="8d5cc-143">**Function**</span></span>|<span data-ttu-id="8d5cc-144">**备注**</span><span class="sxs-lookup"><span data-stu-id="8d5cc-144">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8d5cc-145">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="8d5cc-145">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="8d5cc-146">CMyMAPIFormViewer:: GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="8d5cc-146">CMyMAPIFormViewer::GetViewStatus</span></span>  <br/> |<span data-ttu-id="8d5cc-147">MFCMAPI 实现此函数中的**IMAPIViewContext:: GetViewStatus**方法。</span><span class="sxs-lookup"><span data-stu-id="8d5cc-147">MFCMAPI implements the **IMAPIViewContext::GetViewStatus** method in this function.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8d5cc-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d5cc-148">See also</span></span>



[<span data-ttu-id="8d5cc-149">IMAPIMessageSite::GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="8d5cc-149">IMAPIMessageSite::GetSiteStatus</span></span>](imapimessagesite-getsitestatus.md)
  
[<span data-ttu-id="8d5cc-150">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8d5cc-150">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)


[<span data-ttu-id="8d5cc-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="8d5cc-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

