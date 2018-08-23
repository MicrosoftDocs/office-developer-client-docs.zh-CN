---
title: IMAPISessionShowForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.ShowForm
api_type:
- COM
ms.assetid: 233cf936-34db-42d4-b5e3-17a93acb2009
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e9e0ad958acc40dd28f3d9aab9996c1b7a36f38a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591483"
---
# <a name="imapisessionshowform"></a><span data-ttu-id="31cb9-103">IMAPISession::ShowForm</span><span class="sxs-lookup"><span data-stu-id="31cb9-103">IMAPISession::ShowForm</span></span>

  
  
<span data-ttu-id="31cb9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="31cb9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="31cb9-105">显示窗体。</span><span class="sxs-lookup"><span data-stu-id="31cb9-105">Displays a form.</span></span>
  
```cpp
HRESULT ShowForm(
  ULONG_PTR ulUIParam,
  LPMDB lpMsgStore,
  LPMAPIFOLDER lpParentFolder,
  LPCIID lpInterface,
  ULONG ulMessageToken,
  LPMESSAGE lpMessageSent,
  ULONG ulFlags,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags,
  ULONG ulAccess,
  LPSTR lpszMessageClass
);
```

## <a name="parameters"></a><span data-ttu-id="31cb9-106">参数</span><span class="sxs-lookup"><span data-stu-id="31cb9-106">Parameters</span></span>

 <span data-ttu-id="31cb9-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="31cb9-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="31cb9-108">[in]窗体的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="31cb9-108">[in] A handle to the parent window of the form.</span></span>
    
 <span data-ttu-id="31cb9-109">_lpMsgStore_</span><span class="sxs-lookup"><span data-stu-id="31cb9-109">_lpMsgStore_</span></span>
  
> <span data-ttu-id="31cb9-110">[in]消息存储库包含文件夹指向的指针指向_lpParentFolder_参数。</span><span class="sxs-lookup"><span data-stu-id="31cb9-110">[in] A pointer to the message store that contains the folder pointed to by the  _lpParentFolder_ parameter.</span></span> 
    
 <span data-ttu-id="31cb9-111">_lpParentFolder_</span><span class="sxs-lookup"><span data-stu-id="31cb9-111">_lpParentFolder_</span></span>
  
> <span data-ttu-id="31cb9-112">[in]指向在其中创建_ulMessageToken_参数与关联的邮件文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="31cb9-112">[in] A pointer to the folder in which the message associated with the  _ulMessageToken_ parameter was created.</span></span> 
    
 <span data-ttu-id="31cb9-113">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="31cb9-113">_lpInterface_</span></span>
  
> <span data-ttu-id="31cb9-114">[in]指向接口标识 (IID) 值，该值代表要用于访问表单中显示的消息的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="31cb9-114">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the message that is displayed in the form.</span></span> <span data-ttu-id="31cb9-115">_LpInterface_参数必须为空或 IID_IMessage。</span><span class="sxs-lookup"><span data-stu-id="31cb9-115">The  _lpInterface_ parameter must be NULL or IID_IMessage.</span></span> <span data-ttu-id="31cb9-116">传递空导致标准， [IMessage](imessageimapiprop.md)，正在使用的接口。</span><span class="sxs-lookup"><span data-stu-id="31cb9-116">Passing NULL results in the standard interface, [IMessage](imessageimapiprop.md), being used.</span></span> 
    
 <span data-ttu-id="31cb9-117">_ulMessageToken_</span><span class="sxs-lookup"><span data-stu-id="31cb9-117">_ulMessageToken_</span></span>
  
> <span data-ttu-id="31cb9-118">[in]与窗体中显示的消息相关联的令牌。</span><span class="sxs-lookup"><span data-stu-id="31cb9-118">[in] The token that is associated with the message to be displayed in the form.</span></span> <span data-ttu-id="31cb9-119">从[IMAPISession::PrepareForm](imapisession-prepareform.md)到以前的呼叫， _ulMessageToken_参数必须设置为_lpulMessageToken_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="31cb9-119">The  _ulMessageToken_ parameter must be set to the contents of the  _lpulMessageToken_ parameter from the previous call to [IMAPISession::PrepareForm](imapisession-prepareform.md).</span></span>
    
 <span data-ttu-id="31cb9-120">_lpMessageSent_</span><span class="sxs-lookup"><span data-stu-id="31cb9-120">_lpMessageSent_</span></span>
  
> <span data-ttu-id="31cb9-121">[in]保留;必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="31cb9-121">[in] Reserved; must be NULL.</span></span> 
    
 <span data-ttu-id="31cb9-122">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="31cb9-122">_ulFlags_</span></span>
  
> <span data-ttu-id="31cb9-123">[in]位掩码的标志，控制如何和是否保存邮件。</span><span class="sxs-lookup"><span data-stu-id="31cb9-123">[in] A bitmask of flags that controls how and whether the message is saved.</span></span> <span data-ttu-id="31cb9-124">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="31cb9-124">The following flags can be set:</span></span>
    
<span data-ttu-id="31cb9-125">MAPI_NEW_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="31cb9-125">MAPI_NEW_MESSAGE</span></span> 
  
> <span data-ttu-id="31cb9-126">从未保存过邮件 （即，其[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法调用过）。</span><span class="sxs-lookup"><span data-stu-id="31cb9-126">The message has never been saved (that is, its [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method has never been called).</span></span> 
    
<span data-ttu-id="31cb9-127">MAPI_POST_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="31cb9-127">MAPI_POST_MESSAGE</span></span> 
  
> <span data-ttu-id="31cb9-128">邮件应将保存到其父文件夹中。</span><span class="sxs-lookup"><span data-stu-id="31cb9-128">The message should be saved to its parent folder.</span></span> <span data-ttu-id="31cb9-129">消息未发送的处理，但投递到文件夹改为。</span><span class="sxs-lookup"><span data-stu-id="31cb9-129">The message is not processed for sending but is posted to the folder instead.</span></span> <span data-ttu-id="31cb9-130">如果未设置此标志，邮件复制到发件箱并处理发送。</span><span class="sxs-lookup"><span data-stu-id="31cb9-130">If this flag is not set, the message is copied to the Outbox and is processed for sending.</span></span> 
    
 <span data-ttu-id="31cb9-131">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="31cb9-131">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="31cb9-132">[in]复制从与_ulMessageToken_参数中的令牌关联的消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="31cb9-132">[in] A bitmask of flags copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> <span data-ttu-id="31cb9-133">标志提供有关邮件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="31cb9-133">The flags provide information about the state of the message.</span></span> 
    
 <span data-ttu-id="31cb9-134">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="31cb9-134">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="31cb9-135">[in]复制从与_ulMessageToken_参数中的令牌关联的消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="31cb9-135">[in] A bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> <span data-ttu-id="31cb9-136">这些标志进一步提供有关邮件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="31cb9-136">These flags provide further information about the state of the message.</span></span> 
    
 <span data-ttu-id="31cb9-137">_ulAccess_</span><span class="sxs-lookup"><span data-stu-id="31cb9-137">_ulAccess_</span></span>
  
> <span data-ttu-id="31cb9-138">[in]一个标志，指示表单中显示的消息的权限级别。</span><span class="sxs-lookup"><span data-stu-id="31cb9-138">[in] A flag that indicates the permission level for the message that is displayed in the form.</span></span> <span data-ttu-id="31cb9-139">从与_ulMessageToken_参数中的令牌关联的消息的**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性复制此信息。</span><span class="sxs-lookup"><span data-stu-id="31cb9-139">This information is copied from the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> 
    
 <span data-ttu-id="31cb9-140">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="31cb9-140">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="31cb9-141">[in]指向要显示在表单中，复制**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性与_ulMessageToken_参数中标记相关联的消息中的邮件的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="31cb9-141">[in] A pointer to the message class of the message being displayed in the form, copied from the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="31cb9-142">返回值</span><span class="sxs-lookup"><span data-stu-id="31cb9-142">Return value</span></span>

<span data-ttu-id="31cb9-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="31cb9-143">S_OK</span></span> 
  
> <span data-ttu-id="31cb9-144">成功显示窗体。</span><span class="sxs-lookup"><span data-stu-id="31cb9-144">The form was successfully displayed.</span></span>
    
<span data-ttu-id="31cb9-145">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="31cb9-145">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="31cb9-146">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="31cb9-146">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="31cb9-147">注解</span><span class="sxs-lookup"><span data-stu-id="31cb9-147">Remarks</span></span>

<span data-ttu-id="31cb9-148">**IMAPISession::ShowForm**方法显示已准备好**IMAPISession::PrepareForm**方法的邮件窗体。</span><span class="sxs-lookup"><span data-stu-id="31cb9-148">The **IMAPISession::ShowForm** method displays a message form that has been prepared by the **IMAPISession::PrepareForm** method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="31cb9-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="31cb9-149">Notes to callers</span></span>

<span data-ttu-id="31cb9-150">您应该仅对**PrepareForm**方法的_lpMessage_参数中传递的消息的单个引用。</span><span class="sxs-lookup"><span data-stu-id="31cb9-150">You should have only a single reference to the message passed in the **PrepareForm** method's  _lpMessage_ parameter.</span></span> 
  
<span data-ttu-id="31cb9-151">注意窗体实现可以返回错误值以外的记录的 MAPI 的值。</span><span class="sxs-lookup"><span data-stu-id="31cb9-151">Be aware that form implementations can return error values other than the ones documented by MAPI.</span></span> <span data-ttu-id="31cb9-152">如果您可以使用这些错误值要更精确地确定错误条件的这样做。</span><span class="sxs-lookup"><span data-stu-id="31cb9-152">If you can use these error values to make a more accurate determination of the error condition, do so.</span></span> <span data-ttu-id="31cb9-153">与您处理 MAPI_E_CALL_FAILED，否则，处理这些错误。</span><span class="sxs-lookup"><span data-stu-id="31cb9-153">Otherwise, handle these errors as you would handle MAPI_E_CALL_FAILED.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="31cb9-154">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="31cb9-154">MFCMAPI reference</span></span>

<span data-ttu-id="31cb9-155">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="31cb9-155">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="31cb9-156">**文件**</span><span class="sxs-lookup"><span data-stu-id="31cb9-156">**File**</span></span>|<span data-ttu-id="31cb9-157">**函数**</span><span class="sxs-lookup"><span data-stu-id="31cb9-157">**Function**</span></span>|<span data-ttu-id="31cb9-158">**Comment**</span><span class="sxs-lookup"><span data-stu-id="31cb9-158">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="31cb9-159">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="31cb9-159">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="31cb9-160">OpenMessageModal</span><span class="sxs-lookup"><span data-stu-id="31cb9-160">OpenMessageModal</span></span>  <br/> |<span data-ttu-id="31cb9-161">MFCMAPI 使用**IMAPISession::ShowForm**方法，以及**PrepareForm**方法中，窗体模式中显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="31cb9-161">MFCMAPI uses the **IMAPISession::ShowForm** method, together with the **PrepareForm** method, to display a message in a modal form.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="31cb9-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31cb9-162">See also</span></span>



[<span data-ttu-id="31cb9-163">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="31cb9-163">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="31cb9-164">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="31cb9-164">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)
  
[<span data-ttu-id="31cb9-165">IMAPISession::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="31cb9-165">IMAPISession::PrepareForm</span></span>](imapisession-prepareform.md)
  
[<span data-ttu-id="31cb9-166">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="31cb9-166">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="31cb9-167">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="31cb9-167">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

