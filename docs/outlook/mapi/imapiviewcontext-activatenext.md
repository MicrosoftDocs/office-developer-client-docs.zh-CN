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
ms.openlocfilehash: 5b10f744e3033aab63820e4cd5e414f4c01c27cf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410614"
---
# <a name="imapiviewcontextactivatenext"></a><span data-ttu-id="0bd24-103">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="0bd24-103">IMAPIViewContext::ActivateNext</span></span>

<span data-ttu-id="0bd24-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0bd24-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0bd24-105">按查看顺序激活下一条或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd24-105">Activates the next or previous message in the view order.</span></span> 
  
```cpp
HRESULT ActivateNext(
ULONG ulDir,
LPCRECT prcPosRect
);
```

## <a name="parameters"></a><span data-ttu-id="0bd24-106">参数</span><span class="sxs-lookup"><span data-stu-id="0bd24-106">Parameters</span></span>

<span data-ttu-id="0bd24-107">_ulDir_</span><span class="sxs-lookup"><span data-stu-id="0bd24-107">_ulDir_</span></span>
  
> <span data-ttu-id="0bd24-108">实时状态标志, 提供要激活的邮件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="0bd24-108">[in] Status flags giving information about the message to be activated.</span></span> <span data-ttu-id="0bd24-109">有效的标志设置为:</span><span class="sxs-lookup"><span data-stu-id="0bd24-109">Valid flag settings are:</span></span>
    
  - <span data-ttu-id="0bd24-110">VCDIR_CATEGORY: 查看器应激活视图的另一个类别中的邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd24-110">VCDIR_CATEGORY: The viewer should activate a message in another category of the view.</span></span> <span data-ttu-id="0bd24-111">要激活的邮件为:</span><span class="sxs-lookup"><span data-stu-id="0bd24-111">The message to be activated is:</span></span> 
        
    - <span data-ttu-id="0bd24-112">下一个视图类别中的第一条消息 (如果\*\*\*\* 此标志为 VCDIR_NEXT, 则为 ed)。</span><span class="sxs-lookup"><span data-stu-id="0bd24-112">The first message in the next view category if this flag is **OR**ed with VCDIR_NEXT.</span></span> 
        
    - <span data-ttu-id="0bd24-113">在上一视图类别中的最后一封邮件 ( \*\*\*\* 如果此标志为 VCDIR_PREV, 并且已展开上一个类别)。</span><span class="sxs-lookup"><span data-stu-id="0bd24-113">The last message in the previous view category if this flag is **OR**ed with VCDIR_PREV and the previous category is expanded.</span></span> 
        
    - <span data-ttu-id="0bd24-114">在上一视图类别中的第一封邮件 ( \*\*\*\* 如果此标志为 VCDIR_PREV, 而以前的类别未展开)。</span><span class="sxs-lookup"><span data-stu-id="0bd24-114">The first message in the previous view category if this flag is **OR**ed with VCDIR_PREV and the previous category is not expanded.</span></span> <span data-ttu-id="0bd24-115">在这种情况下, 上一个类别会经历自动扩展。</span><span class="sxs-lookup"><span data-stu-id="0bd24-115">In this case the previous category undergoes automatic expansion.</span></span> 
        
  - <span data-ttu-id="0bd24-116">VCDIR_DELETE: 查看器应激活下一条或上一条消息, 因为当前邮件已被删除。</span><span class="sxs-lookup"><span data-stu-id="0bd24-116">VCDIR_DELETE: The viewer should activate the next or previous message because the current message has been deleted.</span></span> 
        
  - <span data-ttu-id="0bd24-117">VCDIR_MOVE: 查看器应激活下一条或上一条消息, 因为当前邮件已被移动。</span><span class="sxs-lookup"><span data-stu-id="0bd24-117">VCDIR_MOVE: The viewer should activate the next or previous message because the current message has been moved.</span></span> 
        
  - <span data-ttu-id="0bd24-118">VCDIR_NEXT: 查看器应激活查看顺序中的下一封邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd24-118">VCDIR_NEXT: The viewer should activate the next message in the view order.</span></span> 
        
  - <span data-ttu-id="0bd24-119">VCDIR_PREV: 查看器应按查看顺序激活上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd24-119">VCDIR_PREV: The viewer should activate the previous message in the view order.</span></span> 
        
  - <span data-ttu-id="0bd24-120">VCDIR_UNREAD: 查看器应激活查看顺序中的下一个或上一个未读邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd24-120">VCDIR_UNREAD: The viewer should activate the next or previous unread message in the view order.</span></span> 
    
<span data-ttu-id="0bd24-121">_prcPosRect_</span><span class="sxs-lookup"><span data-stu-id="0bd24-121">_prcPosRect_</span></span>
  
> <span data-ttu-id="0bd24-122">实时指向 Windows **RECT**结构的指针, 该结构包含要用于显示激活的消息的窗口的大小和位置。</span><span class="sxs-lookup"><span data-stu-id="0bd24-122">[in] Pointer to a Windows **RECT** structure containing the size and position of the window to be used to display the activated message.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0bd24-123">返回值</span><span class="sxs-lookup"><span data-stu-id="0bd24-123">Return value</span></span>

<span data-ttu-id="0bd24-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="0bd24-124">S_OK</span></span> 
  
> <span data-ttu-id="0bd24-125">邮件已成功激活。</span><span class="sxs-lookup"><span data-stu-id="0bd24-125">The message was activated successfully.</span></span> 
    
<span data-ttu-id="0bd24-126">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0bd24-126">S_FALSE</span></span> 
  
> <span data-ttu-id="0bd24-127">邮件已成功激活, 但在进程中打开了另一种类型的窗体。</span><span class="sxs-lookup"><span data-stu-id="0bd24-127">The message was activated successfully, but a different type of form was opened in the process.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0bd24-128">说明</span><span class="sxs-lookup"><span data-stu-id="0bd24-128">Remarks</span></span>

<span data-ttu-id="0bd24-129">表单对象调用**IMAPIViewContext:: ActivateNext**方法以更改向用户显示的消息。</span><span class="sxs-lookup"><span data-stu-id="0bd24-129">Form objects call the **IMAPIViewContext::ActivateNext** method to change what message is displayed to the user.</span></span> <span data-ttu-id="0bd24-130">在_ulDir_参数中传递的值指示应激活的邮件, 在某些情况下, 这是为什么。</span><span class="sxs-lookup"><span data-stu-id="0bd24-130">The value passed in the  _ulDir_ parameter indicates which message should be activated and, in some cases, why.</span></span> <span data-ttu-id="0bd24-131">VCDIR_NEXT 和 VCDIR_PREVIOUS 标志分别对应于在视图中选择**下一个**或**上**一个命令的用户。</span><span class="sxs-lookup"><span data-stu-id="0bd24-131">The VCDIR_NEXT and VCDIR_PREVIOUS flags correspond to users choosing the **Next** or **Previous** command in a view, respectively.</span></span> <span data-ttu-id="0bd24-132">这些操作通常对应于在表单查看器的邮件列表中上移或下移一封邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd24-132">These operations usually correspond to moving up or down one message in the form viewer's list of messages.</span></span> 
  
<span data-ttu-id="0bd24-133">VCDIR_DELETE 和 VCDIR_MOVE 标志分别由[IMAPIMessageSite::D eletemessage](imapimessagesite-deletemessage.md)和[IMAPIMessageSite:: MoveMessage](imapimessagesite-movemessage.md)方法设置。</span><span class="sxs-lookup"><span data-stu-id="0bd24-133">The VCDIR_DELETE and VCDIR_MOVE flags are set by the [IMAPIMessageSite::DeleteMessage](imapimessagesite-deletemessage.md) and [IMAPIMessageSite::MoveMessage](imapimessagesite-movemessage.md) methods, respectively.</span></span> <span data-ttu-id="0bd24-134">这些方法的实现将以适当的方向调用**ActivateNext** , 然后在**ActivateNext**调用未失败时对邮件执行请求的操作。</span><span class="sxs-lookup"><span data-stu-id="0bd24-134">Implementations of these methods call **ActivateNext** with the appropriate direction and then perform the requested operation on the message if the **ActivateNext** call did not fail.</span></span> <span data-ttu-id="0bd24-135">表单查看器通常使用户能够在邮件列表中指定移动的方向。</span><span class="sxs-lookup"><span data-stu-id="0bd24-135">Form viewers typically enable users to specify the direction to move in the message list.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="0bd24-136">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="0bd24-136">Notes to implementers</span></span>

<span data-ttu-id="0bd24-137">您对[IMAPIViewContext:: ActivateNext](imapiviewcontext-activatenext.md)的实现将根据当前邮件的_ulDir_值, 在文件夹中生成下一条或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd24-137">Your implementation of [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) makes the next or previous message in the folder, depending on the value of  _ulDir_, the current message.</span></span> <span data-ttu-id="0bd24-138">在**ActivateNext**返回后, 调用[IMAPIMessageSite:: GetMessage](imapimessagesite-getmessage.md)以获取指向新激活邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="0bd24-138">After **ActivateNext** returns, call [IMAPIMessageSite::GetMessage](imapimessagesite-getmessage.md) to get a pointer to the newly activated message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0bd24-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0bd24-139">Notes to callers</span></span>

<span data-ttu-id="0bd24-140">如果**ActivateNext**返回 S_FALSE, 或者当前邮件不存在, 请执行正常关机过程, 该过程应包括调用表单的[IMAPIForm:: ShutdownForm](imapiform-shutdownform.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0bd24-140">If **ActivateNext** returns S_FALSE, or if a current message is not present, perform your normal shutdown procedure which should include calling your form's [IMAPIForm::ShutdownForm](imapiform-shutdownform.md) method.</span></span> <span data-ttu-id="0bd24-141">如果显示的是下一条或上一条消息, 请使用_prcPosRect_参数中传递的窗口矩形来显示它。</span><span class="sxs-lookup"><span data-stu-id="0bd24-141">If a next or previous message is displayed, use the window rectangle passed in the  _prcPosRect_ parameter to display it.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="0bd24-142">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="0bd24-142">MFCMAPI reference</span></span>

<span data-ttu-id="0bd24-143">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="0bd24-143">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="0bd24-144">**文件**</span><span class="sxs-lookup"><span data-stu-id="0bd24-144">**File**</span></span>|<span data-ttu-id="0bd24-145">**函数**</span><span class="sxs-lookup"><span data-stu-id="0bd24-145">**Function**</span></span>|<span data-ttu-id="0bd24-146">**备注**</span><span class="sxs-lookup"><span data-stu-id="0bd24-146">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0bd24-147">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="0bd24-147">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="0bd24-148">CMyMAPIFormViewer:: ActivateNext</span><span class="sxs-lookup"><span data-stu-id="0bd24-148">CMyMAPIFormViewer::ActivateNext</span></span>  <br/> |<span data-ttu-id="0bd24-149">MFCMAPI 实现此函数中的**IMAPIViewContext:: ActivateNext**方法。</span><span class="sxs-lookup"><span data-stu-id="0bd24-149">MFCMAPI implements the **IMAPIViewContext::ActivateNext** method in this function.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0bd24-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bd24-150">See also</span></span>

- [<span data-ttu-id="0bd24-151">IMAPIViewContext::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="0bd24-151">IMAPIViewContext::GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md)
- [<span data-ttu-id="0bd24-152">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0bd24-152">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)
- [<span data-ttu-id="0bd24-153">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="0bd24-153">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

