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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429012"
---
# <a name="imapiviewcontextgetviewstatus"></a><span data-ttu-id="fe3a8-103">IMAPIViewContext::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="fe3a8-103">IMAPIViewContext::GetViewStatus</span></span>

  
  
<span data-ttu-id="fe3a8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fe3a8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fe3a8-105">检索当前查看器状态。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-105">Retrieves the current viewer status.</span></span> 
  
```cpp
HRESULT GetViewStatus(
ULONG FAR * lpulStatus
);
```

## <a name="parameters"></a><span data-ttu-id="fe3a8-106">参数</span><span class="sxs-lookup"><span data-stu-id="fe3a8-106">Parameters</span></span>

 <span data-ttu-id="fe3a8-107">_lpulStatus_</span><span class="sxs-lookup"><span data-stu-id="fe3a8-107">_lpulStatus_</span></span>
  
> <span data-ttu-id="fe3a8-108">[out]指向提供查看器状态的标记的位掩码的指针。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-108">[out] Pointer to a bitmask of flags providing the status of the viewer.</span></span> <span data-ttu-id="fe3a8-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="fe3a8-109">The following flags can be set:</span></span>
    
<span data-ttu-id="fe3a8-110">VCSTATUS_CATEGORY</span><span class="sxs-lookup"><span data-stu-id="fe3a8-110">VCSTATUS_CATEGORY</span></span> 
  
> <span data-ttu-id="fe3a8-111">存在另一个类别中的下一封邮件或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-111">There is a next or previous message in another category.</span></span> 
    
<span data-ttu-id="fe3a8-112">VCSTATUS_DELETE</span><span class="sxs-lookup"><span data-stu-id="fe3a8-112">VCSTATUS_DELETE</span></span> 
  
> <span data-ttu-id="fe3a8-113">窗体允许删除邮件。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-113">The form allows messages to be removed.</span></span> 
    
<span data-ttu-id="fe3a8-114">VCSTATUS_INTERACTIVE</span><span class="sxs-lookup"><span data-stu-id="fe3a8-114">VCSTATUS_INTERACTIVE</span></span> 
  
> <span data-ttu-id="fe3a8-115">表单应显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-115">The form should display a user interface.</span></span> <span data-ttu-id="fe3a8-116">如果未设置此标志，则表单应该禁止显示用户界面，即使该动作通常会导致显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-116">If this flag is not set, the form should suppress displaying a user interface even in response to a verb that usually causes a user interface to be displayed.</span></span> 
    
<span data-ttu-id="fe3a8-117">VCSTATUS_MODAL</span><span class="sxs-lookup"><span data-stu-id="fe3a8-117">VCSTATUS_MODAL</span></span> 
  
> <span data-ttu-id="fe3a8-118">窗体对查看器是模式窗体。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-118">The form is modal to the viewer.</span></span> 
    
<span data-ttu-id="fe3a8-119">VCSTATUS_NEXT</span><span class="sxs-lookup"><span data-stu-id="fe3a8-119">VCSTATUS_NEXT</span></span> 
  
> <span data-ttu-id="fe3a8-120">视图中有下一条消息。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-120">There is a next message in the view.</span></span> 
    
<span data-ttu-id="fe3a8-121">VCSTATUS_PREV</span><span class="sxs-lookup"><span data-stu-id="fe3a8-121">VCSTATUS_PREV</span></span> 
  
> <span data-ttu-id="fe3a8-122">视图中有一条以前的消息。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-122">There is a previous message in the view.</span></span> 
    
<span data-ttu-id="fe3a8-123">VCSTATUS_READONLY</span><span class="sxs-lookup"><span data-stu-id="fe3a8-123">VCSTATUS_READONLY</span></span> 
  
> <span data-ttu-id="fe3a8-124">邮件将在只读模式下打开。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-124">The message is to be opened in read-only mode.</span></span> <span data-ttu-id="fe3a8-125">应禁用删除、提交和移动操作。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-125">Delete, submit, and move operations should be disabled.</span></span> 
    
<span data-ttu-id="fe3a8-126">VCSTATUS_UNREAD</span><span class="sxs-lookup"><span data-stu-id="fe3a8-126">VCSTATUS_UNREAD</span></span> 
  
> <span data-ttu-id="fe3a8-127">视图中存在下一条或上一条未读邮件。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-127">There is a next or previous unread message in the view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fe3a8-128">返回值</span><span class="sxs-lookup"><span data-stu-id="fe3a8-128">Return value</span></span>

<span data-ttu-id="fe3a8-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe3a8-129">S_OK</span></span> 
  
> <span data-ttu-id="fe3a8-130">已成功返回查看者的状态。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-130">The viewer's status was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fe3a8-131">备注</span><span class="sxs-lookup"><span data-stu-id="fe3a8-131">Remarks</span></span>

<span data-ttu-id="fe3a8-132">Form 对象调用 **IMAPIViewContext：：GetViewStatus** 方法，以确定表单视图中是否还有更多消息需要激活，方向为：或两个方向，即 **Next** 命令激活消息的方向 **、Previous** 命令激活消息的方向或两个方向。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-132">Form objects call the **IMAPIViewContext::GetViewStatus** method to determine whether there are more messages to be activated in a form view in either or both directions that is, in the direction in which a **Next** command activates messages, in the direction in which a **Previous** command activates messages, or in both directions.</span></span> <span data-ttu-id="fe3a8-133">_lpulStatus_ 参数指向的值用于确定 VCSTATUS_NEXT 和 VCSTATUS_PREV 标志是否对 [IMAPIViewContext：：ActivateNext 有效](imapiviewcontext-activatenext.md)。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-133">The value pointed to by the  _lpulStatus_ parameter is used to determine whether the VCSTATUS_NEXT and VCSTATUS_PREV flags are valid for [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md).</span></span> <span data-ttu-id="fe3a8-134">如果设置了 VCSTATUS_DELETE 标志，但没有设置 VCSTATUS_READONLY 标志，可以使用 [IMAPIMessageSite：:D eleteMessage 方法删除该](imapimessagesite-deletemessage.md) 邮件。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-134">If the VCSTATUS_DELETE flag is set, but not the VCSTATUS_READONLY flag, then the message can be deleted using the [IMAPIMessageSite::DeleteMessage](imapimessagesite-deletemessage.md) method.</span></span> 
  
<span data-ttu-id="fe3a8-135">通常，如果菜单命令和按钮与查看器的上下文无效，则表单会禁用它们。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-135">Typically, forms disable menu commands and buttons if they are not valid for the viewer's context.</span></span> <span data-ttu-id="fe3a8-136">查看者可以通过调用表单的 [IMAPIFormAdviseSink：：OnChange](imapiformadvisesink-onchange.md) 方法来提醒表单状态更改。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-136">A viewer can alert a form to a change in status by calling its [IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md) method.</span></span> 
  
<span data-ttu-id="fe3a8-137">如果VCSTATUS_MODAL必须模式化到其句柄在早期 [IMAPIForm：:D oVerb 调用中](imapiform-doverb.md) 传递的窗口，则设置该标志。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-137">The VCSTATUS_MODAL flag is set if the form must be modal to the window whose handle is passed in the earlier [IMAPIForm::DoVerb](imapiform-doverb.md) call.</span></span> <span data-ttu-id="fe3a8-138">如果VCSTATUS_MODAL，窗体可以使用 **DoVerb** 调用所基于的线程，直到窗体关闭。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-138">If VCSTATUS_MODAL is set, the form can use the thread on which the **DoVerb** call was made until the form closes.</span></span> <span data-ttu-id="fe3a8-139">如果未VCSTATUS_MODAL，则表单不应是此窗口的模式，并且不得使用线程。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-139">If VCSTATUS_MODAL is not set, the form should not be modal to this window and must not use the thread.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="fe3a8-140">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="fe3a8-140">MFCMAPI reference</span></span>

<span data-ttu-id="fe3a8-141">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-141">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="fe3a8-142">**文件**</span><span class="sxs-lookup"><span data-stu-id="fe3a8-142">**File**</span></span>|<span data-ttu-id="fe3a8-143">**函数**</span><span class="sxs-lookup"><span data-stu-id="fe3a8-143">**Function**</span></span>|<span data-ttu-id="fe3a8-144">**备注**</span><span class="sxs-lookup"><span data-stu-id="fe3a8-144">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fe3a8-145">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="fe3a8-145">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="fe3a8-146">CMyMAPIFormViewer：：GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="fe3a8-146">CMyMAPIFormViewer::GetViewStatus</span></span>  <br/> |<span data-ttu-id="fe3a8-147">MFCMAPI 在此函数中实现 **IMAPIViewContext：：GetViewStatus** 方法。</span><span class="sxs-lookup"><span data-stu-id="fe3a8-147">MFCMAPI implements the **IMAPIViewContext::GetViewStatus** method in this function.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fe3a8-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe3a8-148">See also</span></span>



[<span data-ttu-id="fe3a8-149">IMAPIMessageSite::GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="fe3a8-149">IMAPIMessageSite::GetSiteStatus</span></span>](imapimessagesite-getsitestatus.md)
  
[<span data-ttu-id="fe3a8-150">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fe3a8-150">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)


[<span data-ttu-id="fe3a8-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="fe3a8-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

