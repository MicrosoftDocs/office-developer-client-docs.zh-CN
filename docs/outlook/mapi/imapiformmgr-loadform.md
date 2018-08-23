---
title: IMAPIFormMgrLoadForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.LoadForm
api_type:
- COM
ms.assetid: 5ca500c3-c737-45a5-b0fc-473b75c1d68d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3e758acfa1cf0c11be666dd730d9bf589d2e9d77
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586212"
---
# <a name="imapiformmgrloadform"></a><span data-ttu-id="3f0a6-103">IMAPIFormMgr::LoadForm</span><span class="sxs-lookup"><span data-stu-id="3f0a6-103">IMAPIFormMgr::LoadForm</span></span>

  
  
<span data-ttu-id="3f0a6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3f0a6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3f0a6-105">启动打开现有邮件窗体。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-105">Starts a form to open an existing message.</span></span>
  
```cpp
HRESULT LoadForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR lpszMessageClass,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags,
  LPMAPIFOLDER pFolderFocus,
  LPMAPIMESSAGESITE pMessageSite,
  LPMESSAGE pmsg,
  LPMAPIVIEWCONTEXT pViewContext,
  REFIID riid,
  LPVOID FAR * ppvObj
);
```

## <a name="parameters"></a><span data-ttu-id="3f0a6-106">参数</span><span class="sxs-lookup"><span data-stu-id="3f0a6-106">Parameters</span></span>

 <span data-ttu-id="3f0a6-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="3f0a6-108">[in]打开表单时显示进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-108">[in] A handle to the parent window of the progress indicator that is displayed while the form is opened.</span></span> <span data-ttu-id="3f0a6-109">除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-109">The  _ulUIParam_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="3f0a6-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-110">_ulFlags_</span></span>
  
> <span data-ttu-id="3f0a6-111">[in]位掩码的标志，控制如何打开表单。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-111">[in] A bitmask of flags that controls how the form is opened.</span></span> <span data-ttu-id="3f0a6-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="3f0a6-112">The following flags can be set:</span></span>
    
<span data-ttu-id="3f0a6-113">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="3f0a6-113">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="3f0a6-114">显示用户界面，以提供状态或提示用户输入的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-114">Displays a user interface to provide status or prompt the user for more information.</span></span> <span data-ttu-id="3f0a6-115">如果未设置此标志，将显示没有用户界面。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-115">If this flag is not set, no user interface is displayed.</span></span>
    
<span data-ttu-id="3f0a6-116">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="3f0a6-116">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="3f0a6-117">应解决仅邮件类的字符串完全匹配。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-117">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="3f0a6-118">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-118">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="3f0a6-119">[in]一个指向命名要加载的邮件的邮件类的字符串。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-119">[in] A pointer to a string that names the message class of the message to be loaded.</span></span> <span data-ttu-id="3f0a6-120">如果_lpszMessageClass_参数中传递 NULL，则邮件类由_pmsg_参数指向的邮件。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-120">If NULL is passed in the  _lpszMessageClass_ parameter, the message class is determined from the message pointed to by the  _pmsg_ parameter.</span></span> 
    
 <span data-ttu-id="3f0a6-121">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-121">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="3f0a6-122">[in]复制邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中的客户端或提供程序定义标志的位掩码，提供有关状态的消息的信息。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-122">[in] A bitmask of client-defined or provider-defined flags copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of the message that provides information about the state of the message.</span></span> <span data-ttu-id="3f0a6-123">如果_lpszMessageClass_为非空; 必须设置_ulMessageStatus_参数否则，将忽略_ulMessageStatus_ 。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-123">The  _ulMessageStatus_ parameter must be set if  _lpszMessageClass_ is non-NULL; otherwise,  _ulMessageStatus_ is ignored.</span></span> 
    
 <span data-ttu-id="3f0a6-124">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-124">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="3f0a6-125">[in]一个指向标志指示邮件的当前状态的消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性从复制的位掩码。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-125">[in] A pointer to a bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message that indicates the current state of the message.</span></span> <span data-ttu-id="3f0a6-126">如果_lpszMessageClass_为非空; 必须设置_ulMessageFlags_参数否则，将忽略_ulMessageFlags_ 。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-126">The  _ulMessageFlags_ parameter must be set if  _lpszMessageClass_ is non-NULL; otherwise,  _ulMessageFlags_ is ignored.</span></span> 
    
 <span data-ttu-id="3f0a6-127">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-127">_pFolderFocus_</span></span>
  
> <span data-ttu-id="3f0a6-128">[in]一个指向直接包含邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-128">[in] A pointer to the folder that directly contains the message.</span></span> <span data-ttu-id="3f0a6-129">_PFolderFocus_参数可以是 NULL，如果这样的文件夹不存在 （例如，如果邮件嵌入到另一条消息）。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-129">The  _pFolderFocus_ parameter can be NULL if such a folder does not exist (for example, if the message is embedded in another message).</span></span> 
    
 <span data-ttu-id="3f0a6-130">_pMessageSite_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-130">_pMessageSite_</span></span>
  
> <span data-ttu-id="3f0a6-131">[in]一个指向邮件的邮件网站。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-131">[in] A pointer to the message site of the message.</span></span>
    
 <span data-ttu-id="3f0a6-132">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-132">_pmsg_</span></span>
  
> <span data-ttu-id="3f0a6-133">[in]指向邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-133">[in] A pointer to the message.</span></span>
    
 <span data-ttu-id="3f0a6-134">_pViewContext_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-134">_pViewContext_</span></span>
  
> <span data-ttu-id="3f0a6-135">[in]一个指向视图上下文的邮件。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-135">[in] A pointer to the view context for the message.</span></span> <span data-ttu-id="3f0a6-136">_PViewContext_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-136">The  _pViewContext_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="3f0a6-137">_riid_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-137">_riid_</span></span>
  
> <span data-ttu-id="3f0a6-138">[in]用于返回的 form 对象的接口接口标识符 (IID)。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-138">[in] The interface identifier (IID) of the interface to be used for the returned form object.</span></span> <span data-ttu-id="3f0a6-139">_Riid_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-139">The  _riid_ parameter must not be NULL.</span></span> 
    
 <span data-ttu-id="3f0a6-140">_ppvObj_</span><span class="sxs-lookup"><span data-stu-id="3f0a6-140">_ppvObj_</span></span>
  
> <span data-ttu-id="3f0a6-141">[输出]指向返回的接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-141">[out] A pointer to a pointer to the returned interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3f0a6-142">返回值</span><span class="sxs-lookup"><span data-stu-id="3f0a6-142">Return value</span></span>

<span data-ttu-id="3f0a6-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f0a6-143">S_OK</span></span> 
  
> <span data-ttu-id="3f0a6-144">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-144">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="3f0a6-145">MAPI_E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="3f0a6-145">MAPI_E_NO_INTERFACE</span></span> 
  
> <span data-ttu-id="3f0a6-146">窗体不支持所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-146">The form does not support the requested interface.</span></span>
    
<span data-ttu-id="3f0a6-147">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="3f0a6-147">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="3f0a6-148">_LpszMessageClass_中传递的邮件类不匹配的邮件类的窗体库中的任何表单。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-148">The message class passed in  _lpszMessageClass_ does not match the message class for any form in the form library.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="3f0a6-149">注解</span><span class="sxs-lookup"><span data-stu-id="3f0a6-149">Remarks</span></span>

<span data-ttu-id="3f0a6-150">表单查看器调用**IMAPIFormMgr::LoadForm**方法打开现有邮件窗体。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-150">Form viewers call the **IMAPIFormMgr::LoadForm** method to open a form for an existing message.</span></span> <span data-ttu-id="3f0a6-151">**LoadForm**打开 form 对象，将邮件加载到窗体对象、 设置适当的视图上下文，如有必要，并返回窗体对象的请求的接口。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-151">**LoadForm** opens the form object, loads the message into the form object, sets up the appropriate view context, if necessary, and returns the requested interface for the form object.</span></span> 
  
<span data-ttu-id="3f0a6-152">_PFolderFocus_参数指向包含邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-152">The  _pFolderFocus_ parameter points to the folder that contains the message.</span></span> <span data-ttu-id="3f0a6-153">邮件嵌入到另一条消息中，如果_pFolderFocus_应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-153">If the message is embedded in another message,  _pFolderFocus_ should be NULL.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="3f0a6-154">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="3f0a6-154">Notes to implementers</span></span>

<span data-ttu-id="3f0a6-155">实现消息的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))、 **PR_MSG_STATUS**和**PR_MESSAGE_FLAGS 如果_lpszMessageClass_中传递 NULL，则获取消息的邮件类、 状态和标志**属性。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-155">If NULL is passed in  _lpszMessageClass_, the implementation obtains the message's message class, status, and flags from the message's **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)), **PR_MSG_STATUS** and **PR_MESSAGE_FLAGS** properties.</span></span> <span data-ttu-id="3f0a6-156">如果_lpszMessageClass_中提供的邮件类字符串，则实现必须使用_ulMessageStatus_和_ulMessageFlags_中的值。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-156">If a message class string is provided in  _lpszMessageClass_, the implementation must use the values in  _ulMessageStatus_ and  _ulMessageFlags_.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3f0a6-157">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="3f0a6-157">MFCMAPI reference</span></span>

<span data-ttu-id="3f0a6-158">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-158">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3f0a6-159">**文件**</span><span class="sxs-lookup"><span data-stu-id="3f0a6-159">**File**</span></span>|<span data-ttu-id="3f0a6-160">**函数**</span><span class="sxs-lookup"><span data-stu-id="3f0a6-160">**Function**</span></span>|<span data-ttu-id="3f0a6-161">**Comment**</span><span class="sxs-lookup"><span data-stu-id="3f0a6-161">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f0a6-162">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="3f0a6-162">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="3f0a6-163">OpenMessageNonModal</span><span class="sxs-lookup"><span data-stu-id="3f0a6-163">OpenMessageNonModal</span></span>  <br/> |<span data-ttu-id="3f0a6-164">MFCMAPI 使用**IMAPIFormMgr::LoadForm**方法显示之前加载窗体。</span><span class="sxs-lookup"><span data-stu-id="3f0a6-164">MFCMAPI uses the **IMAPIFormMgr::LoadForm** method to load a form before displaying it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3f0a6-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0a6-165">See also</span></span>



[<span data-ttu-id="3f0a6-166">PidTagMessageClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f0a6-166">PidTagMessageClass Canonical Property</span></span>](pidtagmessageclass-canonical-property.md)
  
[<span data-ttu-id="3f0a6-167">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f0a6-167">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="3f0a6-168">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f0a6-168">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="3f0a6-169">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3f0a6-169">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="3f0a6-170">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="3f0a6-170">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

