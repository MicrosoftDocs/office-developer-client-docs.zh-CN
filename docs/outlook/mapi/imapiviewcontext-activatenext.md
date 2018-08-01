---
title: IMAPIViewContextActivateNext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.ActivateNext
api_type:
- COM
ms.assetid: 25ce90ac-526e-48a0-9edb-bd266375d4f4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 150a0c6eb7efa83f5ff1d12d915351bf5ca9d45a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775757"
---
# <a name="imapiviewcontextactivatenext"></a><span data-ttu-id="1fbea-103">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="1fbea-103">IMAPIViewContext::ActivateNext</span></span>

<span data-ttu-id="1fbea-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1fbea-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1fbea-105">激活查看订单中的下一页或上一页消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-105">Activates the next or previous message in the view order.</span></span> 
  
```cpp
HRESULT ActivateNext(
ULONG ulDir,
LPCRECT prcPosRect
);
```

## <a name="parameters"></a><span data-ttu-id="1fbea-106">参数</span><span class="sxs-lookup"><span data-stu-id="1fbea-106">Parameters</span></span>

<span data-ttu-id="1fbea-107">_ulDir_</span><span class="sxs-lookup"><span data-stu-id="1fbea-107">_ulDir_</span></span>
  
> <span data-ttu-id="1fbea-108">[in]提供有关邮件要激活的信息的状态标志。</span><span class="sxs-lookup"><span data-stu-id="1fbea-108">[in] Status flags giving information about the message to be activated.</span></span> <span data-ttu-id="1fbea-109">有效的标志设置为：</span><span class="sxs-lookup"><span data-stu-id="1fbea-109">Valid flag settings are:</span></span>
    
  - <span data-ttu-id="1fbea-110">VCDIR_CATEGORY： 查看器应激活另一个视图的类别中的邮件。</span><span class="sxs-lookup"><span data-stu-id="1fbea-110">VCDIR_CATEGORY: The viewer should activate a message in another category of the view.</span></span> <span data-ttu-id="1fbea-111">是要激活的消息：</span><span class="sxs-lookup"><span data-stu-id="1fbea-111">The message to be activated is:</span></span> 
        
    - <span data-ttu-id="1fbea-112">如果此标志为与 VCDIR_NEXT**或**ed 的下一个视图类别中第一条消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-112">The first message in the next view category if this flag is **OR**ed with VCDIR_NEXT.</span></span> 
        
    - <span data-ttu-id="1fbea-113">展开以前的视图类别此标志是否与 VCDIR_PREV **OR**ed 和上一个类别中的最后一条消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-113">The last message in the previous view category if this flag is **OR**ed with VCDIR_PREV and the previous category is expanded.</span></span> 
        
    - <span data-ttu-id="1fbea-114">不扩展此标志是否与 VCDIR_PREV **OR**ed 的上一视图类别和上一个类别中第一条消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-114">The first message in the previous view category if this flag is **OR**ed with VCDIR_PREV and the previous category is not expanded.</span></span> <span data-ttu-id="1fbea-115">在这种情况下上一个类别经历自动扩展。</span><span class="sxs-lookup"><span data-stu-id="1fbea-115">In this case the previous category undergoes automatic expansion.</span></span> 
        
  - <span data-ttu-id="1fbea-116">VCDIR_DELETE： 因为当前邮件已被删除，查看器应激活下一个或上一条消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-116">VCDIR_DELETE: The viewer should activate the next or previous message because the current message has been deleted.</span></span> 
        
  - <span data-ttu-id="1fbea-117">VCDIR_MOVE： 因为当前邮件已被移动，查看器应激活下一个或上一条消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-117">VCDIR_MOVE: The viewer should activate the next or previous message because the current message has been moved.</span></span> 
        
  - <span data-ttu-id="1fbea-118">VCDIR_NEXT： 查看器应激活视图顺序下一条消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-118">VCDIR_NEXT: The viewer should activate the next message in the view order.</span></span> 
        
  - <span data-ttu-id="1fbea-119">VCDIR_PREV： 查看器应激活顺序查看以前的消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-119">VCDIR_PREV: The viewer should activate the previous message in the view order.</span></span> 
        
  - <span data-ttu-id="1fbea-120">VCDIR_UNREAD： 查看器应激活下一个或上一个未读的邮件视图顺序。</span><span class="sxs-lookup"><span data-stu-id="1fbea-120">VCDIR_UNREAD: The viewer should activate the next or previous unread message in the view order.</span></span> 
    
<span data-ttu-id="1fbea-121">_prcPosRect_</span><span class="sxs-lookup"><span data-stu-id="1fbea-121">_prcPosRect_</span></span>
  
> <span data-ttu-id="1fbea-122">[in]指向 Windows**矩形**结构包含的大小和位置用于显示已激活的邮件窗口。</span><span class="sxs-lookup"><span data-stu-id="1fbea-122">[in] Pointer to a Windows **RECT** structure containing the size and position of the window to be used to display the activated message.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1fbea-123">返回值</span><span class="sxs-lookup"><span data-stu-id="1fbea-123">Return value</span></span>

<span data-ttu-id="1fbea-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="1fbea-124">S_OK</span></span> 
  
> <span data-ttu-id="1fbea-125">邮件已成功激活。</span><span class="sxs-lookup"><span data-stu-id="1fbea-125">The message was activated successfully.</span></span> 
    
<span data-ttu-id="1fbea-126">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1fbea-126">S_FALSE</span></span> 
  
> <span data-ttu-id="1fbea-127">邮件已成功激活，但过程中打开窗体的不同类型。</span><span class="sxs-lookup"><span data-stu-id="1fbea-127">The message was activated successfully, but a different type of form was opened in the process.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1fbea-128">说明</span><span class="sxs-lookup"><span data-stu-id="1fbea-128">Remarks</span></span>

<span data-ttu-id="1fbea-129">表单对象调用**IMAPIViewContext::ActivateNext**方法更改向用户显示什么消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-129">Form objects call the **IMAPIViewContext::ActivateNext** method to change what message is displayed to the user.</span></span> <span data-ttu-id="1fbea-130">_UlDir_参数中传递的值表示哪些消息应该激活的并在某些情况下，原因。</span><span class="sxs-lookup"><span data-stu-id="1fbea-130">The value passed in the  _ulDir_ parameter indicates which message should be activated and, in some cases, why.</span></span> <span data-ttu-id="1fbea-131">VCDIR_NEXT 和 VCDIR_PREVIOUS 标志对应于用户分别在视图中，选择**下一步**或**上一步**命令。</span><span class="sxs-lookup"><span data-stu-id="1fbea-131">The VCDIR_NEXT and VCDIR_PREVIOUS flags correspond to users choosing the **Next** or **Previous** command in a view, respectively.</span></span> <span data-ttu-id="1fbea-132">这些操作通常对应于上移或下移一条消息中的邮件将表单查看器的列表。</span><span class="sxs-lookup"><span data-stu-id="1fbea-132">These operations usually correspond to moving up or down one message in the form viewer's list of messages.</span></span> 
  
<span data-ttu-id="1fbea-133">分别由[IMAPIMessageSite::DeleteMessage](imapimessagesite-deletemessage.md)和[IMAPIMessageSite::MoveMessage](imapimessagesite-movemessage.md)方法设置了 VCDIR_DELETE 和 VCDIR_MOVE 标志。</span><span class="sxs-lookup"><span data-stu-id="1fbea-133">The VCDIR_DELETE and VCDIR_MOVE flags are set by the [IMAPIMessageSite::DeleteMessage](imapimessagesite-deletemessage.md) and [IMAPIMessageSite::MoveMessage](imapimessagesite-movemessage.md) methods, respectively.</span></span> <span data-ttu-id="1fbea-134">实现这些方法的调用**ActivateNext**相应方向，然后执行邮件上请求的操作，如果**ActivateNext**呼叫没有进行故障。</span><span class="sxs-lookup"><span data-stu-id="1fbea-134">Implementations of these methods call **ActivateNext** with the appropriate direction and then perform the requested operation on the message if the **ActivateNext** call did not fail.</span></span> <span data-ttu-id="1fbea-135">窗体查看者通常会使用户能够指定要在消息列表中移动的方向。</span><span class="sxs-lookup"><span data-stu-id="1fbea-135">Form viewers typically enable users to specify the direction to move in the message list.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="1fbea-136">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="1fbea-136">Notes to implementers</span></span>

<span data-ttu-id="1fbea-137">在文件夹中，根据_ulDir_，当前消息的值的[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)实现使下一页或上一页消息。</span><span class="sxs-lookup"><span data-stu-id="1fbea-137">Your implementation of [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) makes the next or previous message in the folder, depending on the value of  _ulDir_, the current message.</span></span> <span data-ttu-id="1fbea-138">**ActivateNext**返回后，调用[IMAPIMessageSite::GetMessage](imapimessagesite-getmessage.md)获取新激活的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="1fbea-138">After **ActivateNext** returns, call [IMAPIMessageSite::GetMessage](imapimessagesite-getmessage.md) to get a pointer to the newly activated message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1fbea-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1fbea-139">Notes to callers</span></span>

<span data-ttu-id="1fbea-140">如果**ActivateNext**返回 S_FALSE，或者当前消息不存在，请执行正常关闭过程应包括调用窗体的[IMAPIForm::ShutdownForm](imapiform-shutdownform.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1fbea-140">If **ActivateNext** returns S_FALSE, or if a current message is not present, perform your normal shutdown procedure which should include calling your form's [IMAPIForm::ShutdownForm](imapiform-shutdownform.md) method.</span></span> <span data-ttu-id="1fbea-141">如果显示下一个或上一条消息，则使用_prcPosRect_参数中传递的窗口矩形来显示它。</span><span class="sxs-lookup"><span data-stu-id="1fbea-141">If a next or previous message is displayed, use the window rectangle passed in the  _prcPosRect_ parameter to display it.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1fbea-142">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1fbea-142">MFCMAPI reference</span></span>

<span data-ttu-id="1fbea-143">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1fbea-143">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1fbea-144">**文件**</span><span class="sxs-lookup"><span data-stu-id="1fbea-144">**File**</span></span>|<span data-ttu-id="1fbea-145">**函数**</span><span class="sxs-lookup"><span data-stu-id="1fbea-145">**Function**</span></span>|<span data-ttu-id="1fbea-146">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1fbea-146">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1fbea-147">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="1fbea-147">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="1fbea-148">CMyMAPIFormViewer::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="1fbea-148">CMyMAPIFormViewer::ActivateNext</span></span>  <br/> |<span data-ttu-id="1fbea-149">MFCMAPI 此函数中实现**IMAPIViewContext::ActivateNext**方法。</span><span class="sxs-lookup"><span data-stu-id="1fbea-149">MFCMAPI implements the **IMAPIViewContext::ActivateNext** method in this function.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1fbea-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fbea-150">See also</span></span>

- [<span data-ttu-id="1fbea-151">IMAPIViewContext::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="1fbea-151">IMAPIViewContext::GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md)
- [<span data-ttu-id="1fbea-152">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1fbea-152">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)
- [<span data-ttu-id="1fbea-153">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1fbea-153">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

