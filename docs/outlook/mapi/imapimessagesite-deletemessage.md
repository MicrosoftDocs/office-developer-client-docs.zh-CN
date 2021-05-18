---
title: IMAPIMessageSiteDeleteMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.DeleteMessage
api_type:
- COM
ms.assetid: 09955996-b904-4c0d-8ba5-954a8875c055
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7b2761e20444c51d08380aee01c41eee797733eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321411"
---
# <a name="imapimessagesitedeletemessage"></a><span data-ttu-id="c4d05-103">IMAPIMessageSite::DeleteMessage</span><span class="sxs-lookup"><span data-stu-id="c4d05-103">IMAPIMessageSite::DeleteMessage</span></span>

  
  
<span data-ttu-id="c4d05-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c4d05-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c4d05-105">删除当前邮件。</span><span class="sxs-lookup"><span data-stu-id="c4d05-105">Deletes the current message.</span></span>
  
```cpp
HRESULT DeleteMessage(
  LPMAPIVIEWCONTEXT pViewContext,
  LPCRECT prcPosRect
);
```

## <a name="parameters"></a><span data-ttu-id="c4d05-106">参数</span><span class="sxs-lookup"><span data-stu-id="c4d05-106">Parameters</span></span>

 <span data-ttu-id="c4d05-107">_pViewContext_</span><span class="sxs-lookup"><span data-stu-id="c4d05-107">_pViewContext_</span></span>
  
> <span data-ttu-id="c4d05-108">[in]指向视图上下文对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c4d05-108">[in] A pointer to a view context object.</span></span>
    
 <span data-ttu-id="c4d05-109">_prcPosRect_</span><span class="sxs-lookup"><span data-stu-id="c4d05-109">_prcPosRect_</span></span>
  
> <span data-ttu-id="c4d05-110">[in]指向包含当前窗体的窗口大小和位置的 [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="c4d05-110">[in] A pointer to a [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) structure that contains the current form's window size and position.</span></span> <span data-ttu-id="c4d05-111">显示的下一个窗体也使用此窗口矩形。</span><span class="sxs-lookup"><span data-stu-id="c4d05-111">The next form displayed also uses this window rectangle.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c4d05-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c4d05-112">Return value</span></span>

<span data-ttu-id="c4d05-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4d05-113">S_OK</span></span> 
  
> <span data-ttu-id="c4d05-114">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="c4d05-114">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="c4d05-115">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="c4d05-115">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="c4d05-116">此消息网站不支持该操作。</span><span class="sxs-lookup"><span data-stu-id="c4d05-116">The operation is not supported by this message site.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c4d05-117">备注</span><span class="sxs-lookup"><span data-stu-id="c4d05-117">Remarks</span></span>

<span data-ttu-id="c4d05-118">表单对象调用 **IMAPIMessageSite：:D eleteMessage** 方法以删除表单当前显示的消息。</span><span class="sxs-lookup"><span data-stu-id="c4d05-118">A form object calls the **IMAPIMessageSite::DeleteMessage** method to delete the message that the form is currently displaying.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c4d05-119">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c4d05-119">Notes to callers</span></span>

<span data-ttu-id="c4d05-120">返回 **DeleteMessage** 之后，form 对象必须检查新邮件，然后在不存在邮件时自行消除。</span><span class="sxs-lookup"><span data-stu-id="c4d05-120">Following the return of **DeleteMessage**, form objects must check for a new message and then dismiss themselves if none exists.</span></span> <span data-ttu-id="c4d05-121">若要确定对 **DeleteMessage** 操作的邮件是已删除还是移动到"已删除邮件"文件夹，表单对象可以调用 [IMAPIMessageSite：：GetSiteStatus](imapimessagesite-getsitestatus.md)方法以确定是否返回 DELETE_IS_MOVE 标志。</span><span class="sxs-lookup"><span data-stu-id="c4d05-121">To determine whether the message **DeleteMessage** acted on was deleted or moved to a **Deleted Items** folder, a form object can call the [IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md) method to determine whether the DELETE_IS_MOVE flag was returned.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="c4d05-122">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="c4d05-122">Notes to implementers</span></span>

<span data-ttu-id="c4d05-123">如果表单查看器的 **DeleteMessage** 方法实现在删除邮件后移至下一条消息，则实现应调用 [IMAPIViewContext：：ActivateNext](imapiviewcontext-activatenext.md) 方法，并传递 VCDIR_DELETE 标志，然后再执行实际删除。</span><span class="sxs-lookup"><span data-stu-id="c4d05-123">If a form viewer's implementation of the **DeleteMessage** method moves to the next message after it deletes a message, the implementation should call the [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) method and pass the VCDIR_DELETE flag before performing the actual deletion.</span></span> <span data-ttu-id="c4d05-124">如果表单查看器的 **DeleteMessage** 实现将已删除的邮件 (例如移动到"已删除邮件"文件夹) ，则实现必须保存对邮件所做的更改（如果邮件已修改）。</span><span class="sxs-lookup"><span data-stu-id="c4d05-124">If a form viewer's implementation of **DeleteMessage** moves the deleted message (for example, to a **Deleted Items** folder), the implementation must save changes to the message if the message was modified.</span></span> 
  
<span data-ttu-id="c4d05-125">**DeleteMessage 的典型** 实现执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c4d05-125">A typical implementation of **DeleteMessage** performs the following tasks:</span></span> 
  
1. <span data-ttu-id="c4d05-126">如果实现移动消息，它将调用 [IPersistMessage：：Save](ipersistmessage-save.md)方法，在 _pMessage_ 参数中传递 **null，** 在 _fSameAsLoad_ 参数中传递 **true。**</span><span class="sxs-lookup"><span data-stu-id="c4d05-126">If the implementation is moving the message, it calls the [IPersistMessage::Save](ipersistmessage-save.md) method, passing **null** in the  _pMessage_ parameter and **true** in the  _fSameAsLoad_ parameter.</span></span> 
    
2. <span data-ttu-id="c4d05-127">它调用 **IMAPIViewContext：：ActivateNext** 方法，在  _ulDir_ VCDIR_DELETE传递该标记。</span><span class="sxs-lookup"><span data-stu-id="c4d05-127">It calls the **IMAPIViewContext::ActivateNext** method, passing the VCDIR_DELETE flag in the  _ulDir_ parameter.</span></span> 
    
3. <span data-ttu-id="c4d05-128">如果 **ActivateNext 调用** 失败，它将返回。</span><span class="sxs-lookup"><span data-stu-id="c4d05-128">If the **ActivateNext** call fails, it returns.</span></span> <span data-ttu-id="c4d05-129">如果 **ActivateNext** 返回 S_FALSE，它将调用 [IPersistMessage：：HandsOffMessage](ipersistmessage-handsoffmessage.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c4d05-129">If **ActivateNext** returns S_FALSE, it calls the [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) method.</span></span> 
    
4. <span data-ttu-id="c4d05-130">它会删除或移动邮件。</span><span class="sxs-lookup"><span data-stu-id="c4d05-130">It deletes or moves the message.</span></span>
    
<span data-ttu-id="c4d05-131">若要获取窗体的窗口使用的 **RECT** 结构，请调用 Windows [GetWindowRect](https://msdn.microsoft.com/library/ms633519)函数。</span><span class="sxs-lookup"><span data-stu-id="c4d05-131">To obtain the **RECT** structure used by a form's window, call the Windows [GetWindowRect](https://msdn.microsoft.com/library/ms633519) function.</span></span> 
  
<span data-ttu-id="c4d05-132">有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="c4d05-132">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c4d05-133">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c4d05-133">MFCMAPI reference</span></span>

<span data-ttu-id="c4d05-134">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c4d05-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c4d05-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="c4d05-135">**File**</span></span>|<span data-ttu-id="c4d05-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="c4d05-136">**Function**</span></span>|<span data-ttu-id="c4d05-137">**备注**</span><span class="sxs-lookup"><span data-stu-id="c4d05-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c4d05-138">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="c4d05-138">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="c4d05-139">CMyMAPIFormViewer：:D eleteMessage</span><span class="sxs-lookup"><span data-stu-id="c4d05-139">CMyMAPIFormViewer::DeleteMessage</span></span>  <br/> |<span data-ttu-id="c4d05-140">未实现。</span><span class="sxs-lookup"><span data-stu-id="c4d05-140">Not implemented.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c4d05-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4d05-141">See also</span></span>



[<span data-ttu-id="c4d05-142">IMAPIMessageSite::GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="c4d05-142">IMAPIMessageSite::GetSiteStatus</span></span>](imapimessagesite-getsitestatus.md)
  
[<span data-ttu-id="c4d05-143">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="c4d05-143">IMAPIViewContext::ActivateNext</span></span>](imapiviewcontext-activatenext.md)
  
[<span data-ttu-id="c4d05-144">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="c4d05-144">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md)
  
[<span data-ttu-id="c4d05-145">IPersistMessage::Save</span><span class="sxs-lookup"><span data-stu-id="c4d05-145">IPersistMessage::Save</span></span>](ipersistmessage-save.md)
  
[<span data-ttu-id="c4d05-146">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c4d05-146">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="c4d05-147">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c4d05-147">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="c4d05-148">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="c4d05-148">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

