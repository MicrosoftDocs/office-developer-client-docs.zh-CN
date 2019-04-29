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
# <a name="imapisessionshowform"></a><span data-ttu-id="30a46-103">IMAPISession::ShowForm</span><span class="sxs-lookup"><span data-stu-id="30a46-103">IMAPISession::ShowForm</span></span>

  
  
<span data-ttu-id="30a46-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="30a46-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="30a46-105">显示窗体。</span><span class="sxs-lookup"><span data-stu-id="30a46-105">Displays a form.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="30a46-106">参数</span><span class="sxs-lookup"><span data-stu-id="30a46-106">Parameters</span></span>

 <span data-ttu-id="30a46-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="30a46-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="30a46-108">实时表单的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="30a46-108">[in] A handle to the parent window of the form.</span></span>
    
 <span data-ttu-id="30a46-109">_lpMsgStore_</span><span class="sxs-lookup"><span data-stu-id="30a46-109">_lpMsgStore_</span></span>
  
> <span data-ttu-id="30a46-110">实时指向邮件存储区的指针, 该邮件存储区包含由_lpParentFolder_参数指向的文件夹。</span><span class="sxs-lookup"><span data-stu-id="30a46-110">[in] A pointer to the message store that contains the folder pointed to by the  _lpParentFolder_ parameter.</span></span> 
    
 <span data-ttu-id="30a46-111">_lpParentFolder_</span><span class="sxs-lookup"><span data-stu-id="30a46-111">_lpParentFolder_</span></span>
  
> <span data-ttu-id="30a46-112">实时一个指针, 指向在其中创建与_ulMessageToken_参数相关联的邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="30a46-112">[in] A pointer to the folder in which the message associated with the  _ulMessageToken_ parameter was created.</span></span> 
    
 <span data-ttu-id="30a46-113">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="30a46-113">_lpInterface_</span></span>
  
> <span data-ttu-id="30a46-114">实时指向接口标识符 (IID) 的指针, 该接口标识符代表要用于访问表单中显示的邮件的接口。</span><span class="sxs-lookup"><span data-stu-id="30a46-114">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the message that is displayed in the form.</span></span> <span data-ttu-id="30a46-115">_lpInterface_参数必须为 NULL 或 IID_IMessage。</span><span class="sxs-lookup"><span data-stu-id="30a46-115">The  _lpInterface_ parameter must be NULL or IID_IMessage.</span></span> <span data-ttu-id="30a46-116">在使用的标准接口[IMessage](imessageimapiprop.md)中传递 NULL 结果。</span><span class="sxs-lookup"><span data-stu-id="30a46-116">Passing NULL results in the standard interface, [IMessage](imessageimapiprop.md), being used.</span></span> 
    
 <span data-ttu-id="30a46-117">_ulMessageToken_</span><span class="sxs-lookup"><span data-stu-id="30a46-117">_ulMessageToken_</span></span>
  
> <span data-ttu-id="30a46-118">实时与要在表单中显示的邮件相关联的标记。</span><span class="sxs-lookup"><span data-stu-id="30a46-118">[in] The token that is associated with the message to be displayed in the form.</span></span> <span data-ttu-id="30a46-119">必须将_ulMessageToken_参数设置为以前对[IMAPISession::P repareform](imapisession-prepareform.md)的调用中的_lpulMessageToken_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="30a46-119">The  _ulMessageToken_ parameter must be set to the contents of the  _lpulMessageToken_ parameter from the previous call to [IMAPISession::PrepareForm](imapisession-prepareform.md).</span></span>
    
 <span data-ttu-id="30a46-120">_lpMessageSent_</span><span class="sxs-lookup"><span data-stu-id="30a46-120">_lpMessageSent_</span></span>
  
> <span data-ttu-id="30a46-121">实时保留必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="30a46-121">[in] Reserved; must be NULL.</span></span> 
    
 <span data-ttu-id="30a46-122">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="30a46-122">_ulFlags_</span></span>
  
> <span data-ttu-id="30a46-123">实时用于控制是否保存邮件以及是否保存邮件的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="30a46-123">[in] A bitmask of flags that controls how and whether the message is saved.</span></span> <span data-ttu-id="30a46-124">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="30a46-124">The following flags can be set:</span></span>
    
<span data-ttu-id="30a46-125">MAPI_NEW_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="30a46-125">MAPI_NEW_MESSAGE</span></span> 
  
> <span data-ttu-id="30a46-126">从未保存过该邮件 (即它的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法从未被调用过)。</span><span class="sxs-lookup"><span data-stu-id="30a46-126">The message has never been saved (that is, its [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method has never been called).</span></span> 
    
<span data-ttu-id="30a46-127">MAPI_POST_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="30a46-127">MAPI_POST_MESSAGE</span></span> 
  
> <span data-ttu-id="30a46-128">应将邮件保存到其父文件夹中。</span><span class="sxs-lookup"><span data-stu-id="30a46-128">The message should be saved to its parent folder.</span></span> <span data-ttu-id="30a46-129">邮件不会被处理为发送, 而是投递到文件夹中。</span><span class="sxs-lookup"><span data-stu-id="30a46-129">The message is not processed for sending but is posted to the folder instead.</span></span> <span data-ttu-id="30a46-130">如果未设置此标志, 则会将邮件复制到 "发件箱", 并将其处理为发送。</span><span class="sxs-lookup"><span data-stu-id="30a46-130">If this flag is not set, the message is copied to the Outbox and is processed for sending.</span></span> 
    
 <span data-ttu-id="30a46-131">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="30a46-131">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="30a46-132">实时从与_ulMessageToken_参数中的标记关联的消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="30a46-132">[in] A bitmask of flags copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> <span data-ttu-id="30a46-133">这些标志提供有关邮件状态的信息。</span><span class="sxs-lookup"><span data-stu-id="30a46-133">The flags provide information about the state of the message.</span></span> 
    
 <span data-ttu-id="30a46-134">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="30a46-134">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="30a46-135">实时从与_ulMessageToken_参数中的标记关联的消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="30a46-135">[in] A bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> <span data-ttu-id="30a46-136">这些标志提供有关邮件状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="30a46-136">These flags provide further information about the state of the message.</span></span> 
    
 <span data-ttu-id="30a46-137">_ulAccess_</span><span class="sxs-lookup"><span data-stu-id="30a46-137">_ulAccess_</span></span>
  
> <span data-ttu-id="30a46-138">实时指示表单中显示的邮件的权限级别的标志。</span><span class="sxs-lookup"><span data-stu-id="30a46-138">[in] A flag that indicates the permission level for the message that is displayed in the form.</span></span> <span data-ttu-id="30a46-139">此信息从与_ulMessageToken_参数中的令牌相关联的邮件的**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性复制。</span><span class="sxs-lookup"><span data-stu-id="30a46-139">This information is copied from the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> 
    
 <span data-ttu-id="30a46-140">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="30a46-140">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="30a46-141">实时指向在表单中显示的邮件的邮件类的指针, 从与_ulMessageToken_参数中的令牌相关联的邮件的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性复制。</span><span class="sxs-lookup"><span data-stu-id="30a46-141">[in] A pointer to the message class of the message being displayed in the form, copied from the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property of the message associated with the token in the  _ulMessageToken_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="30a46-142">返回值</span><span class="sxs-lookup"><span data-stu-id="30a46-142">Return value</span></span>

<span data-ttu-id="30a46-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="30a46-143">S_OK</span></span> 
  
> <span data-ttu-id="30a46-144">表单已成功显示。</span><span class="sxs-lookup"><span data-stu-id="30a46-144">The form was successfully displayed.</span></span>
    
<span data-ttu-id="30a46-145">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="30a46-145">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="30a46-146">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="30a46-146">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="30a46-147">说明</span><span class="sxs-lookup"><span data-stu-id="30a46-147">Remarks</span></span>

<span data-ttu-id="30a46-148">**IMAPISession:: ShowForm**方法显示一个已由**IMAPISession::P repareform**方法准备的邮件窗体。</span><span class="sxs-lookup"><span data-stu-id="30a46-148">The **IMAPISession::ShowForm** method displays a message form that has been prepared by the **IMAPISession::PrepareForm** method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="30a46-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="30a46-149">Notes to callers</span></span>

<span data-ttu-id="30a46-150">您应该只有对在**PrepareForm**方法的_lpMessage_参数中传递的邮件的单个引用。</span><span class="sxs-lookup"><span data-stu-id="30a46-150">You should have only a single reference to the message passed in the **PrepareForm** method's  _lpMessage_ parameter.</span></span> 
  
<span data-ttu-id="30a46-151">请注意, 表单实现可能返回除 MAPI 记录的错误值之外的其他错误值。</span><span class="sxs-lookup"><span data-stu-id="30a46-151">Be aware that form implementations can return error values other than the ones documented by MAPI.</span></span> <span data-ttu-id="30a46-152">如果可以使用这些错误值来更精确地确定错误条件, 请执行此操作。</span><span class="sxs-lookup"><span data-stu-id="30a46-152">If you can use these error values to make a more accurate determination of the error condition, do so.</span></span> <span data-ttu-id="30a46-153">否则, 请处理这些错误, 就像处理 MAPI_E_CALL_FAILED 一样。</span><span class="sxs-lookup"><span data-stu-id="30a46-153">Otherwise, handle these errors as you would handle MAPI_E_CALL_FAILED.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="30a46-154">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="30a46-154">MFCMAPI reference</span></span>

<span data-ttu-id="30a46-155">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="30a46-155">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="30a46-156">**文件**</span><span class="sxs-lookup"><span data-stu-id="30a46-156">**File**</span></span>|<span data-ttu-id="30a46-157">**函数**</span><span class="sxs-lookup"><span data-stu-id="30a46-157">**Function**</span></span>|<span data-ttu-id="30a46-158">**备注**</span><span class="sxs-lookup"><span data-stu-id="30a46-158">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="30a46-159">MAPIFormFunctions</span><span class="sxs-lookup"><span data-stu-id="30a46-159">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="30a46-160">OpenMessageModal</span><span class="sxs-lookup"><span data-stu-id="30a46-160">OpenMessageModal</span></span>  <br/> |<span data-ttu-id="30a46-161">MFCMAPI 将**IMAPISession:: ShowForm**方法与**PrepareForm**方法结合使用, 以在模式窗体中显示消息。</span><span class="sxs-lookup"><span data-stu-id="30a46-161">MFCMAPI uses the **IMAPISession::ShowForm** method, together with the **PrepareForm** method, to display a message in a modal form.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="30a46-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30a46-162">See also</span></span>



[<span data-ttu-id="30a46-163">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="30a46-163">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="30a46-164">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="30a46-164">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)
  
[<span data-ttu-id="30a46-165">IMAPISession::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="30a46-165">IMAPISession::PrepareForm</span></span>](imapisession-prepareform.md)
  
[<span data-ttu-id="30a46-166">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="30a46-166">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="30a46-167">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="30a46-167">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

