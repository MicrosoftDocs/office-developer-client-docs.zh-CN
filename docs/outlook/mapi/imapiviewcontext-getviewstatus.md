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
ms.openlocfilehash: fb543f4188578483333614cb5768f903c9f243d2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775770"
---
# <a name="imapiviewcontextgetviewstatus"></a><span data-ttu-id="5efe3-103">IMAPIViewContext::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="5efe3-103">IMAPIViewContext::GetViewStatus</span></span>

  
  
<span data-ttu-id="5efe3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5efe3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5efe3-105">检索当前的查看器状态。</span><span class="sxs-lookup"><span data-stu-id="5efe3-105">Retrieves the current viewer status.</span></span> 
  
```cpp
HRESULT GetViewStatus(
ULONG FAR * lpulStatus
);
```

## <a name="parameters"></a><span data-ttu-id="5efe3-106">参数</span><span class="sxs-lookup"><span data-stu-id="5efe3-106">Parameters</span></span>

 <span data-ttu-id="5efe3-107">_lpulStatus_</span><span class="sxs-lookup"><span data-stu-id="5efe3-107">_lpulStatus_</span></span>
  
> <span data-ttu-id="5efe3-108">[输出]指向提供查看器的状态标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5efe3-108">[out] Pointer to a bitmask of flags providing the status of the viewer.</span></span> <span data-ttu-id="5efe3-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5efe3-109">The following flags can be set:</span></span>
    
<span data-ttu-id="5efe3-110">VCSTATUS_CATEGORY</span><span class="sxs-lookup"><span data-stu-id="5efe3-110">VCSTATUS_CATEGORY</span></span> 
  
> <span data-ttu-id="5efe3-111">在其他类别没有下一个或上一条消息。</span><span class="sxs-lookup"><span data-stu-id="5efe3-111">There is a next or previous message in another category.</span></span> 
    
<span data-ttu-id="5efe3-112">VCSTATUS_DELETE</span><span class="sxs-lookup"><span data-stu-id="5efe3-112">VCSTATUS_DELETE</span></span> 
  
> <span data-ttu-id="5efe3-113">窗体允许要移除的消息。</span><span class="sxs-lookup"><span data-stu-id="5efe3-113">The form allows messages to be removed.</span></span> 
    
<span data-ttu-id="5efe3-114">VCSTATUS_INTERACTIVE</span><span class="sxs-lookup"><span data-stu-id="5efe3-114">VCSTATUS_INTERACTIVE</span></span> 
  
> <span data-ttu-id="5efe3-115">表单应显示的用户界面。</span><span class="sxs-lookup"><span data-stu-id="5efe3-115">The form should display a user interface.</span></span> <span data-ttu-id="5efe3-116">如果未设置此标志，表单应禁止显示用户界面，即使在响应通常会导致用户界面将显示动词。</span><span class="sxs-lookup"><span data-stu-id="5efe3-116">If this flag is not set, the form should suppress displaying a user interface even in response to a verb that usually causes a user interface to be displayed.</span></span> 
    
<span data-ttu-id="5efe3-117">VCSTATUS_MODAL</span><span class="sxs-lookup"><span data-stu-id="5efe3-117">VCSTATUS_MODAL</span></span> 
  
> <span data-ttu-id="5efe3-118">窗体是模式到查看器。</span><span class="sxs-lookup"><span data-stu-id="5efe3-118">The form is modal to the viewer.</span></span> 
    
<span data-ttu-id="5efe3-119">VCSTATUS_NEXT</span><span class="sxs-lookup"><span data-stu-id="5efe3-119">VCSTATUS_NEXT</span></span> 
  
> <span data-ttu-id="5efe3-120">在视图中没有下一条消息。</span><span class="sxs-lookup"><span data-stu-id="5efe3-120">There is a next message in the view.</span></span> 
    
<span data-ttu-id="5efe3-121">VCSTATUS_PREV</span><span class="sxs-lookup"><span data-stu-id="5efe3-121">VCSTATUS_PREV</span></span> 
  
> <span data-ttu-id="5efe3-122">在视图中没有上一条消息。</span><span class="sxs-lookup"><span data-stu-id="5efe3-122">There is a previous message in the view.</span></span> 
    
<span data-ttu-id="5efe3-123">VCSTATUS_READONLY</span><span class="sxs-lookup"><span data-stu-id="5efe3-123">VCSTATUS_READONLY</span></span> 
  
> <span data-ttu-id="5efe3-124">邮件是以只读模式打开。</span><span class="sxs-lookup"><span data-stu-id="5efe3-124">The message is to be opened in read-only mode.</span></span> <span data-ttu-id="5efe3-125">删除、 提交，和移动操作应被禁用。</span><span class="sxs-lookup"><span data-stu-id="5efe3-125">Delete, submit, and move operations should be disabled.</span></span> 
    
<span data-ttu-id="5efe3-126">VCSTATUS_UNREAD</span><span class="sxs-lookup"><span data-stu-id="5efe3-126">VCSTATUS_UNREAD</span></span> 
  
> <span data-ttu-id="5efe3-127">在视图中没有下一页或上一页未读的邮件。</span><span class="sxs-lookup"><span data-stu-id="5efe3-127">There is a next or previous unread message in the view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5efe3-128">返回值</span><span class="sxs-lookup"><span data-stu-id="5efe3-128">Return value</span></span>

<span data-ttu-id="5efe3-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="5efe3-129">S_OK</span></span> 
  
> <span data-ttu-id="5efe3-130">成功返回将查看器的状态。</span><span class="sxs-lookup"><span data-stu-id="5efe3-130">The viewer's status was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5efe3-131">说明</span><span class="sxs-lookup"><span data-stu-id="5efe3-131">Remarks</span></span>

<span data-ttu-id="5efe3-132">表单对象调用**IMAPIViewContext::GetViewStatus**方法以确定是否在窗体视图中要激活的更多邮件或两个方向，即方向**下一步**命令在其中激活消息，请在方向**上一个**命令中激活邮件，或在两个方向。</span><span class="sxs-lookup"><span data-stu-id="5efe3-132">Form objects call the **IMAPIViewContext::GetViewStatus** method to determine whether there are more messages to be activated in a form view in either or both directions that is, in the direction in which a **Next** command activates messages, in the direction in which a **Previous** command activates messages, or in both directions.</span></span> <span data-ttu-id="5efe3-133">指向_lpulStatus_参数的值用于确定是否有效的[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)VCSTATUS_NEXT 和 VCSTATUS_PREV 标志。</span><span class="sxs-lookup"><span data-stu-id="5efe3-133">The value pointed to by the  _lpulStatus_ parameter is used to determine whether the VCSTATUS_NEXT and VCSTATUS_PREV flags are valid for [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md).</span></span> <span data-ttu-id="5efe3-134">如果设置，但不是 VCSTATUS_READONLY 标志 VCSTATUS_DELETE 标志，然后可以使用[IMAPIMessageSite::DeleteMessage](imapimessagesite-deletemessage.md)方法删除邮件。</span><span class="sxs-lookup"><span data-stu-id="5efe3-134">If the VCSTATUS_DELETE flag is set, but not the VCSTATUS_READONLY flag, then the message can be deleted using the [IMAPIMessageSite::DeleteMessage](imapimessagesite-deletemessage.md) method.</span></span> 
  
<span data-ttu-id="5efe3-135">通常情况下，窗体禁用菜单命令和按钮如果不是有效的查看者的上下文。</span><span class="sxs-lookup"><span data-stu-id="5efe3-135">Typically, forms disable menu commands and buttons if they are not valid for the viewer's context.</span></span> <span data-ttu-id="5efe3-136">查看器可以通过调用其[IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md)方法通知状态更改的表单。</span><span class="sxs-lookup"><span data-stu-id="5efe3-136">A viewer can alert a form to a change in status by calling its [IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md) method.</span></span> 
  
<span data-ttu-id="5efe3-137">如果该窗体必须模式窗口的句柄传递设置 VCSTATUS_MODAL 标志早期[IMAPIForm::DoVerb](imapiform-doverb.md)呼叫中。</span><span class="sxs-lookup"><span data-stu-id="5efe3-137">The VCSTATUS_MODAL flag is set if the form must be modal to the window whose handle is passed in the earlier [IMAPIForm::DoVerb](imapiform-doverb.md) call.</span></span> <span data-ttu-id="5efe3-138">如果设置 VCSTATUS_MODAL，表单可以使用窗体关闭之前在其进行**DoVerb**通话的线程。</span><span class="sxs-lookup"><span data-stu-id="5efe3-138">If VCSTATUS_MODAL is set, the form can use the thread on which the **DoVerb** call was made until the form closes.</span></span> <span data-ttu-id="5efe3-139">如果未设置 VCSTATUS_MODAL，窗体不应在此窗口模式，并不得使用线程。</span><span class="sxs-lookup"><span data-stu-id="5efe3-139">If VCSTATUS_MODAL is not set, the form should not be modal to this window and must not use the thread.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="5efe3-140">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="5efe3-140">MFCMAPI reference</span></span>

<span data-ttu-id="5efe3-141">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5efe3-141">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="5efe3-142">**文件**</span><span class="sxs-lookup"><span data-stu-id="5efe3-142">**File**</span></span>|<span data-ttu-id="5efe3-143">**函数**</span><span class="sxs-lookup"><span data-stu-id="5efe3-143">**Function**</span></span>|<span data-ttu-id="5efe3-144">**Comment**</span><span class="sxs-lookup"><span data-stu-id="5efe3-144">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5efe3-145">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="5efe3-145">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="5efe3-146">CMyMAPIFormViewer::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="5efe3-146">CMyMAPIFormViewer::GetViewStatus</span></span>  <br/> |<span data-ttu-id="5efe3-147">MFCMAPI 此函数中实现**IMAPIViewContext::GetViewStatus**方法。</span><span class="sxs-lookup"><span data-stu-id="5efe3-147">MFCMAPI implements the **IMAPIViewContext::GetViewStatus** method in this function.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5efe3-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5efe3-148">See also</span></span>



[<span data-ttu-id="5efe3-149">IMAPIMessageSite::GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="5efe3-149">IMAPIMessageSite::GetSiteStatus</span></span>](imapimessagesite-getsitestatus.md)
  
[<span data-ttu-id="5efe3-150">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5efe3-150">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)


[<span data-ttu-id="5efe3-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="5efe3-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

