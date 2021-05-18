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
ms.openlocfilehash: 8b90dee3958a20994f9a60d104ae714ad95307d3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412525"
---
# <a name="imapisessionshowform"></a><span data-ttu-id="a0b96-103">IMAPISession::ShowForm</span><span class="sxs-lookup"><span data-stu-id="a0b96-103">IMAPISession::ShowForm</span></span>

  
  
<span data-ttu-id="a0b96-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a0b96-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a0b96-105">显示窗体。</span><span class="sxs-lookup"><span data-stu-id="a0b96-105">Displays a form.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="a0b96-106">参数</span><span class="sxs-lookup"><span data-stu-id="a0b96-106">Parameters</span></span>

 <span data-ttu-id="a0b96-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="a0b96-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="a0b96-108">[in]窗体父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="a0b96-108">[in] A handle to the parent window of the form.</span></span>
    
 <span data-ttu-id="a0b96-109">_lpMsgStore_</span><span class="sxs-lookup"><span data-stu-id="a0b96-109">_lpMsgStore_</span></span>
  
> <span data-ttu-id="a0b96-110">[in]指向包含  _lpParentFolder_ 参数指向的文件夹的邮件存储的指针。</span><span class="sxs-lookup"><span data-stu-id="a0b96-110">[in] A pointer to the message store that contains the folder pointed to by the  _lpParentFolder_ parameter.</span></span> 
    
 <span data-ttu-id="a0b96-111">_lpParentFolder_</span><span class="sxs-lookup"><span data-stu-id="a0b96-111">_lpParentFolder_</span></span>
  
> <span data-ttu-id="a0b96-112">[in]指向创建与  _ulMessageToken_ 参数关联的邮件的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="a0b96-112">[in] A pointer to the folder in which the message associated with the  _ulMessageToken_ parameter was created.</span></span> 
    
 <span data-ttu-id="a0b96-113">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="a0b96-113">_lpInterface_</span></span>
  
> <span data-ttu-id="a0b96-114">[in]指向接口标识符 (IID) 表示用于访问窗体中显示的消息的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="a0b96-114">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the message that is displayed in the form.</span></span> <span data-ttu-id="a0b96-115">_lpInterface_ 参数必须为 NULL 或 IID_IMessage。</span><span class="sxs-lookup"><span data-stu-id="a0b96-115">The  _lpInterface_ parameter must be NULL or IID_IMessage.</span></span> <span data-ttu-id="a0b96-116">传递 NULL 会导致使用标准接口[IMessage。](imessageimapiprop.md)</span><span class="sxs-lookup"><span data-stu-id="a0b96-116">Passing NULL results in the standard interface, [IMessage](imessageimapiprop.md), being used.</span></span> 
    
 <span data-ttu-id="a0b96-117">_ulMessageToken_</span><span class="sxs-lookup"><span data-stu-id="a0b96-117">_ulMessageToken_</span></span>
  
> <span data-ttu-id="a0b96-118">[in]与要显示在表单中的邮件关联的令牌。</span><span class="sxs-lookup"><span data-stu-id="a0b96-118">[in] The token that is associated with the message to be displayed in the form.</span></span> <span data-ttu-id="a0b96-119">必须将 _ulMessageToken_ 参数设置为上一次对 [IMAPISession：:P repareForm](imapisession-prepareform.md)的调用中 _lpulMessageToken_ 参数的内容。</span><span class="sxs-lookup"><span data-stu-id="a0b96-119">The  _ulMessageToken_ parameter must be set to the contents of the  _lpulMessageToken_ parameter from the previous call to [IMAPISession::PrepareForm](imapisession-prepareform.md).</span></span>
    
 <span data-ttu-id="a0b96-120">_lpMessageSent_</span><span class="sxs-lookup"><span data-stu-id="a0b96-120">_lpMessageSent_</span></span>
  
> <span data-ttu-id="a0b96-121">[in]保留;必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a0b96-121">[in] Reserved; must be NULL.</span></span> 
    
 <span data-ttu-id="a0b96-122">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a0b96-122">_ulFlags_</span></span>
  
> <span data-ttu-id="a0b96-123">[in]控制邮件保存方式和保存方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a0b96-123">[in] A bitmask of flags that controls how and whether the message is saved.</span></span> <span data-ttu-id="a0b96-124">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a0b96-124">The following flags can be set:</span></span>
    
<span data-ttu-id="a0b96-125">MAPI_NEW_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="a0b96-125">MAPI_NEW_MESSAGE</span></span> 
  
> <span data-ttu-id="a0b96-126">邮件从未保存过 (，即 [从未调用过其 IMAPIProp：：SaveChanges](imapiprop-savechanges.md)) 。</span><span class="sxs-lookup"><span data-stu-id="a0b96-126">The message has never been saved (that is, its [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method has never been called).</span></span> 
    
<span data-ttu-id="a0b96-127">MAPI_POST_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="a0b96-127">MAPI_POST_MESSAGE</span></span> 
  
> <span data-ttu-id="a0b96-128">邮件应保存到其父文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0b96-128">The message should be saved to its parent folder.</span></span> <span data-ttu-id="a0b96-129">邮件不会处理发送，而是发送到文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0b96-129">The message is not processed for sending but is posted to the folder instead.</span></span> <span data-ttu-id="a0b96-130">如果未设置此标志，邮件将复制到发件箱并进行处理以发送。</span><span class="sxs-lookup"><span data-stu-id="a0b96-130">If this flag is not set, the message is copied to the Outbox and is processed for sending.</span></span> 
    
 <span data-ttu-id="a0b96-131">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="a0b96-131">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="a0b96-132">[in]从 _与 ulMessageToken_ 参数中的令牌关联的邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a0b96-132">[in] A bitmask of flags copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> <span data-ttu-id="a0b96-133">标志提供有关邮件状态的信息。</span><span class="sxs-lookup"><span data-stu-id="a0b96-133">The flags provide information about the state of the message.</span></span> 
    
 <span data-ttu-id="a0b96-134">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="a0b96-134">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="a0b96-135">[in]从 _与 ulMessageToken_ 参数 **中的令牌** 关联的邮件的 PR_MESSAGE_FLAGS ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a0b96-135">[in] A bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> <span data-ttu-id="a0b96-136">这些标志提供有关邮件状态的进一步信息。</span><span class="sxs-lookup"><span data-stu-id="a0b96-136">These flags provide further information about the state of the message.</span></span> 
    
 <span data-ttu-id="a0b96-137">_ulAccess_</span><span class="sxs-lookup"><span data-stu-id="a0b96-137">_ulAccess_</span></span>
  
> <span data-ttu-id="a0b96-138">[in]一个标志，指示窗体中显示的邮件的权限级别。</span><span class="sxs-lookup"><span data-stu-id="a0b96-138">[in] A flag that indicates the permission level for the message that is displayed in the form.</span></span> <span data-ttu-id="a0b96-139">此信息从与 _ulMessageToken_ 参数 **中的** 令牌PR_ACCESS ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性中复制。</span><span class="sxs-lookup"><span data-stu-id="a0b96-139">This information is copied from the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> 
    
 <span data-ttu-id="a0b96-140">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="a0b96-140">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="a0b96-141">[in]指向表单中显示的邮件的邮件类的指针，从与 _ulMessageToken_ 参数中的令牌关联的邮件的 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性复制。</span><span class="sxs-lookup"><span data-stu-id="a0b96-141">[in] A pointer to the message class of the message being displayed in the form, copied from the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a0b96-142">返回值</span><span class="sxs-lookup"><span data-stu-id="a0b96-142">Return value</span></span>

<span data-ttu-id="a0b96-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0b96-143">S_OK</span></span> 
  
> <span data-ttu-id="a0b96-144">已成功显示表单。</span><span class="sxs-lookup"><span data-stu-id="a0b96-144">The form was successfully displayed.</span></span>
    
<span data-ttu-id="a0b96-145">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="a0b96-145">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="a0b96-146">用户通常通过单击对话框中的"取消" **按钮来取消** 操作。</span><span class="sxs-lookup"><span data-stu-id="a0b96-146">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a0b96-147">备注</span><span class="sxs-lookup"><span data-stu-id="a0b96-147">Remarks</span></span>

<span data-ttu-id="a0b96-148">**IMAPISession：：ShowForm** 方法显示 **由 IMAPISession：:P repareForm 方法准备的消息** 表单。</span><span class="sxs-lookup"><span data-stu-id="a0b96-148">The **IMAPISession::ShowForm** method displays a message form that has been prepared by the **IMAPISession::PrepareForm** method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="a0b96-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a0b96-149">Notes to callers</span></span>

<span data-ttu-id="a0b96-150">应只对在 **PrepareForm** 方法的  _lpMessage_ 参数中传递的邮件进行一次引用。</span><span class="sxs-lookup"><span data-stu-id="a0b96-150">You should have only a single reference to the message passed in the **PrepareForm** method's  _lpMessage_ parameter.</span></span> 
  
<span data-ttu-id="a0b96-151">请注意，表单实现可能会返回 MAPI 记录的错误值。</span><span class="sxs-lookup"><span data-stu-id="a0b96-151">Be aware that form implementations can return error values other than the ones documented by MAPI.</span></span> <span data-ttu-id="a0b96-152">如果可以使用这些错误值更精确地确定错误条件，则执行上述操作。</span><span class="sxs-lookup"><span data-stu-id="a0b96-152">If you can use these error values to make a more accurate determination of the error condition, do so.</span></span> <span data-ttu-id="a0b96-153">否则，请像处理这些错误一样处理MAPI_E_CALL_FAILED。</span><span class="sxs-lookup"><span data-stu-id="a0b96-153">Otherwise, handle these errors as you would handle MAPI_E_CALL_FAILED.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a0b96-154">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a0b96-154">MFCMAPI reference</span></span>

<span data-ttu-id="a0b96-155">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a0b96-155">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a0b96-156">**文件**</span><span class="sxs-lookup"><span data-stu-id="a0b96-156">**File**</span></span>|<span data-ttu-id="a0b96-157">**函数**</span><span class="sxs-lookup"><span data-stu-id="a0b96-157">**Function**</span></span>|<span data-ttu-id="a0b96-158">**备注**</span><span class="sxs-lookup"><span data-stu-id="a0b96-158">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a0b96-159">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="a0b96-159">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="a0b96-160">OpenMessageModal</span><span class="sxs-lookup"><span data-stu-id="a0b96-160">OpenMessageModal</span></span>  <br/> |<span data-ttu-id="a0b96-161">MFCMAPI 使用 **IMAPISession：：ShowForm** 方法以及 **PrepareForm** 方法在模式窗体中显示消息。</span><span class="sxs-lookup"><span data-stu-id="a0b96-161">MFCMAPI uses the **IMAPISession::ShowForm** method, together with the **PrepareForm** method, to display a message in a modal form.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a0b96-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0b96-162">See also</span></span>



[<span data-ttu-id="a0b96-163">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="a0b96-163">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="a0b96-164">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a0b96-164">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)
  
[<span data-ttu-id="a0b96-165">IMAPISession::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="a0b96-165">IMAPISession::PrepareForm</span></span>](imapisession-prepareform.md)
  
[<span data-ttu-id="a0b96-166">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a0b96-166">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="a0b96-167">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a0b96-167">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

