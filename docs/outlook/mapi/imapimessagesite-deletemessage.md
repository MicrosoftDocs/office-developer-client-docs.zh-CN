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
ms.openlocfilehash: da6de94342c8d8bbd378a3cde2fb065c97632291
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775451"
---
# <a name="imapimessagesitedeletemessage"></a><span data-ttu-id="e22a5-103">IMAPIMessageSite::DeleteMessage</span><span class="sxs-lookup"><span data-stu-id="e22a5-103">IMAPIMessageSite::DeleteMessage</span></span>

  
  
<span data-ttu-id="e22a5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e22a5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e22a5-105">删除当前邮件。</span><span class="sxs-lookup"><span data-stu-id="e22a5-105">Deletes the current message.</span></span>
  
```cpp
HRESULT DeleteMessage(
  LPMAPIVIEWCONTEXT pViewContext,
  LPCRECT prcPosRect
);
```

## <a name="parameters"></a><span data-ttu-id="e22a5-106">参数</span><span class="sxs-lookup"><span data-stu-id="e22a5-106">Parameters</span></span>

 <span data-ttu-id="e22a5-107">_pViewContext_</span><span class="sxs-lookup"><span data-stu-id="e22a5-107">_pViewContext_</span></span>
  
> <span data-ttu-id="e22a5-108">[in]指向视图上下文对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e22a5-108">[in] A pointer to a view context object.</span></span>
    
 <span data-ttu-id="e22a5-109">_prcPosRect_</span><span class="sxs-lookup"><span data-stu-id="e22a5-109">_prcPosRect_</span></span>
  
> <span data-ttu-id="e22a5-110">[in]指向[矩形](http://msdn.microsoft.com/en-us/library/dd162897%28VS.85%29.aspx)结构，其中包含当前表单的窗口的大小和位置的指针。</span><span class="sxs-lookup"><span data-stu-id="e22a5-110">[in] A pointer to a [RECT](http://msdn.microsoft.com/en-us/library/dd162897%28VS.85%29.aspx) structure that contains the current form's window size and position.</span></span> <span data-ttu-id="e22a5-111">显示的下一个窗体也使用此窗口矩形。</span><span class="sxs-lookup"><span data-stu-id="e22a5-111">The next form displayed also uses this window rectangle.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e22a5-112">返回值</span><span class="sxs-lookup"><span data-stu-id="e22a5-112">Return value</span></span>

<span data-ttu-id="e22a5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e22a5-113">S_OK</span></span> 
  
> <span data-ttu-id="e22a5-114">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="e22a5-114">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="e22a5-115">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="e22a5-115">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="e22a5-116">该操作不受此消息网站。</span><span class="sxs-lookup"><span data-stu-id="e22a5-116">The operation is not supported by this message site.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e22a5-117">说明</span><span class="sxs-lookup"><span data-stu-id="e22a5-117">Remarks</span></span>

<span data-ttu-id="e22a5-118">Form 对象调用**IMAPIMessageSite::DeleteMessage**方法删除当前显示窗体的邮件。</span><span class="sxs-lookup"><span data-stu-id="e22a5-118">A form object calls the **IMAPIMessageSite::DeleteMessage** method to delete the message that the form is currently displaying.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e22a5-119">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e22a5-119">Notes to callers</span></span>

<span data-ttu-id="e22a5-120">**DeleteMessage**返回时，以下表单对象必须检查新邮件，然后关闭本身，如果不存在。</span><span class="sxs-lookup"><span data-stu-id="e22a5-120">Following the return of **DeleteMessage**, form objects must check for a new message and then dismiss themselves if none exists.</span></span> <span data-ttu-id="e22a5-121">若要确定是否**DeleteMessage**作用于邮件已被删除或移动到**已删除邮件**文件夹，form 对象可以调用[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)方法以确定是否返回 DELETE_IS_MOVE 标志。</span><span class="sxs-lookup"><span data-stu-id="e22a5-121">To determine whether the message **DeleteMessage** acted on was deleted or moved to a **Deleted Items** folder, a form object can call the [IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md) method to determine whether the DELETE_IS_MOVE flag was returned.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e22a5-122">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="e22a5-122">Notes to implementers</span></span>

<span data-ttu-id="e22a5-123">如果后将删除在一条消息， **DeleteMessage**方法的表单查看器的实现将移至下一条消息，实现应调用[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)方法，并将 VCDIR_DELETE 标志传递执行之前实际删除。</span><span class="sxs-lookup"><span data-stu-id="e22a5-123">If a form viewer's implementation of the **DeleteMessage** method moves to the next message after it deletes a message, the implementation should call the [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) method and pass the VCDIR_DELETE flag before performing the actual deletion.</span></span> <span data-ttu-id="e22a5-124">如果**DeleteMessage**表单查看器的实现移动 （例如，到**已删除邮件**文件夹中） 的已删除的消息，实现必须到邮件保存更改，如果邮件的修改。</span><span class="sxs-lookup"><span data-stu-id="e22a5-124">If a form viewer's implementation of **DeleteMessage** moves the deleted message (for example, to a **Deleted Items** folder), the implementation must save changes to the message if the message was modified.</span></span> 
  
<span data-ttu-id="e22a5-125">**DeleteMessage**的典型实现执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e22a5-125">A typical implementation of **DeleteMessage** performs the following tasks:</span></span> 
  
1. <span data-ttu-id="e22a5-126">如果实现在移动邮件，它会调用[IPersistMessage::Save](ipersistmessage-save.md)方法，传递**null** _pMessage_参数中和**true** _fSameAsLoad_参数。</span><span class="sxs-lookup"><span data-stu-id="e22a5-126">If the implementation is moving the message, it calls the [IPersistMessage::Save](ipersistmessage-save.md) method, passing **null** in the  _pMessage_ parameter and **true** in the  _fSameAsLoad_ parameter.</span></span> 
    
2. <span data-ttu-id="e22a5-127">它调用**IMAPIViewContext::ActivateNext**方法， _ulDir_参数中传递 VCDIR_DELETE 标志。</span><span class="sxs-lookup"><span data-stu-id="e22a5-127">It calls the **IMAPIViewContext::ActivateNext** method, passing the VCDIR_DELETE flag in the  _ulDir_ parameter.</span></span> 
    
3. <span data-ttu-id="e22a5-128">如果**ActivateNext**调用将失败，则返回。</span><span class="sxs-lookup"><span data-stu-id="e22a5-128">If the **ActivateNext** call fails, it returns.</span></span> <span data-ttu-id="e22a5-129">如果**ActivateNext**返回 S_FALSE，它会调用[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e22a5-129">If **ActivateNext** returns S_FALSE, it calls the [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) method.</span></span> 
    
4. <span data-ttu-id="e22a5-130">它删除，或将邮件移动。</span><span class="sxs-lookup"><span data-stu-id="e22a5-130">It deletes or moves the message.</span></span>
    
<span data-ttu-id="e22a5-131">若要获取使用窗体的窗口的**矩形**结构，请调用 Windows [GetWindowRect](http://msdn.microsoft.com/en-us/library/ms633519)函数。</span><span class="sxs-lookup"><span data-stu-id="e22a5-131">To obtain the **RECT** structure used by a form's window, call the Windows [GetWindowRect](http://msdn.microsoft.com/en-us/library/ms633519) function.</span></span> 
  
<span data-ttu-id="e22a5-132">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="e22a5-132">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e22a5-133">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="e22a5-133">MFCMAPI reference</span></span>

<span data-ttu-id="e22a5-134">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e22a5-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e22a5-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="e22a5-135">**File**</span></span>|<span data-ttu-id="e22a5-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="e22a5-136">**Function**</span></span>|<span data-ttu-id="e22a5-137">**Comment**</span><span class="sxs-lookup"><span data-stu-id="e22a5-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e22a5-138">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="e22a5-138">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="e22a5-139">CMyMAPIFormViewer::DeleteMessage</span><span class="sxs-lookup"><span data-stu-id="e22a5-139">CMyMAPIFormViewer::DeleteMessage</span></span>  <br/> |<span data-ttu-id="e22a5-140">未实现。</span><span class="sxs-lookup"><span data-stu-id="e22a5-140">Not implemented.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e22a5-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e22a5-141">See also</span></span>



[<span data-ttu-id="e22a5-142">IMAPIMessageSite::GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="e22a5-142">IMAPIMessageSite::GetSiteStatus</span></span>](imapimessagesite-getsitestatus.md)
  
[<span data-ttu-id="e22a5-143">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="e22a5-143">IMAPIViewContext::ActivateNext</span></span>](imapiviewcontext-activatenext.md)
  
[<span data-ttu-id="e22a5-144">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="e22a5-144">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md)
  
[<span data-ttu-id="e22a5-145">IPersistMessage::Save</span><span class="sxs-lookup"><span data-stu-id="e22a5-145">IPersistMessage::Save</span></span>](ipersistmessage-save.md)
  
[<span data-ttu-id="e22a5-146">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e22a5-146">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="e22a5-147">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e22a5-147">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="e22a5-148">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="e22a5-148">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

