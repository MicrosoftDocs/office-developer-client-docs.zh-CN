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
ms.openlocfilehash: 7e445646477ad1fc56b41141b541358d9b9f9616
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418783"
---
# <a name="imapiformmgrloadform"></a><span data-ttu-id="52a08-103">IMAPIFormMgr::LoadForm</span><span class="sxs-lookup"><span data-stu-id="52a08-103">IMAPIFormMgr::LoadForm</span></span>

  
  
<span data-ttu-id="52a08-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="52a08-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="52a08-105">启动窗体以打开现有邮件。</span><span class="sxs-lookup"><span data-stu-id="52a08-105">Starts a form to open an existing message.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="52a08-106">参数</span><span class="sxs-lookup"><span data-stu-id="52a08-106">Parameters</span></span>

 <span data-ttu-id="52a08-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="52a08-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="52a08-108">实时进度指示器的父窗口的句柄, 在打开窗体时显示。</span><span class="sxs-lookup"><span data-stu-id="52a08-108">[in] A handle to the parent window of the progress indicator that is displayed while the form is opened.</span></span> <span data-ttu-id="52a08-109">除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="52a08-109">The  _ulUIParam_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="52a08-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="52a08-110">_ulFlags_</span></span>
  
> <span data-ttu-id="52a08-111">实时用于控制表单打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="52a08-111">[in] A bitmask of flags that controls how the form is opened.</span></span> <span data-ttu-id="52a08-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="52a08-112">The following flags can be set:</span></span>
    
<span data-ttu-id="52a08-113">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="52a08-113">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="52a08-114">显示一个用户界面, 以提供状态或提示用户详细信息。</span><span class="sxs-lookup"><span data-stu-id="52a08-114">Displays a user interface to provide status or prompt the user for more information.</span></span> <span data-ttu-id="52a08-115">如果未设置此标志, 则不会显示任何用户界面。</span><span class="sxs-lookup"><span data-stu-id="52a08-115">If this flag is not set, no user interface is displayed.</span></span>
    
<span data-ttu-id="52a08-116">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="52a08-116">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="52a08-117">应解析完全匹配的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="52a08-117">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="52a08-118">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="52a08-118">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="52a08-119">实时指向一个字符串的指针, 该字符串命名要加载的邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="52a08-119">[in] A pointer to a string that names the message class of the message to be loaded.</span></span> <span data-ttu-id="52a08-120">如果在_lpszMessageClass_参数中传递 NULL, 则邮件类由_pmsg_参数所指向的邮件确定。</span><span class="sxs-lookup"><span data-stu-id="52a08-120">If NULL is passed in the  _lpszMessageClass_ parameter, the message class is determined from the message pointed to by the  _pmsg_ parameter.</span></span> 
    
 <span data-ttu-id="52a08-121">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="52a08-121">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="52a08-122">实时从邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中复制的客户端定义或提供程序定义的标志的位掩码, 它提供有关邮件状态的信息。</span><span class="sxs-lookup"><span data-stu-id="52a08-122">[in] A bitmask of client-defined or provider-defined flags copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of the message that provides information about the state of the message.</span></span> <span data-ttu-id="52a08-123">如果_lpszMessageClass_为非 NULL, 则必须设置_ulMessageStatus_参数;否则, _ulMessageStatus_将被忽略。</span><span class="sxs-lookup"><span data-stu-id="52a08-123">The  _ulMessageStatus_ parameter must be set if  _lpszMessageClass_ is non-NULL; otherwise,  _ulMessageStatus_ is ignored.</span></span> 
    
 <span data-ttu-id="52a08-124">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="52a08-124">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="52a08-125">实时指向从消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志位掩码的指针, 该消息指示邮件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="52a08-125">[in] A pointer to a bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message that indicates the current state of the message.</span></span> <span data-ttu-id="52a08-126">如果_lpszMessageClass_为非 NULL, 则必须设置_ulMessageFlags_参数;否则, _ulMessageFlags_将被忽略。</span><span class="sxs-lookup"><span data-stu-id="52a08-126">The  _ulMessageFlags_ parameter must be set if  _lpszMessageClass_ is non-NULL; otherwise,  _ulMessageFlags_ is ignored.</span></span> 
    
 <span data-ttu-id="52a08-127">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="52a08-127">_pFolderFocus_</span></span>
  
> <span data-ttu-id="52a08-128">实时指向直接包含邮件的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="52a08-128">[in] A pointer to the folder that directly contains the message.</span></span> <span data-ttu-id="52a08-129">如果不存在这样的文件夹 (例如, 如果邮件嵌入在另一封邮件中), _pFolderFocus_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="52a08-129">The  _pFolderFocus_ parameter can be NULL if such a folder does not exist (for example, if the message is embedded in another message).</span></span> 
    
 <span data-ttu-id="52a08-130">_pMessageSite_</span><span class="sxs-lookup"><span data-stu-id="52a08-130">_pMessageSite_</span></span>
  
> <span data-ttu-id="52a08-131">实时指向邮件的邮件网站的指针。</span><span class="sxs-lookup"><span data-stu-id="52a08-131">[in] A pointer to the message site of the message.</span></span>
    
 <span data-ttu-id="52a08-132">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="52a08-132">_pmsg_</span></span>
  
> <span data-ttu-id="52a08-133">实时指向邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="52a08-133">[in] A pointer to the message.</span></span>
    
 <span data-ttu-id="52a08-134">_pViewContext_</span><span class="sxs-lookup"><span data-stu-id="52a08-134">_pViewContext_</span></span>
  
> <span data-ttu-id="52a08-135">实时指向邮件的视图上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="52a08-135">[in] A pointer to the view context for the message.</span></span> <span data-ttu-id="52a08-136">_pViewContext_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="52a08-136">The  _pViewContext_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="52a08-137">_riid_</span><span class="sxs-lookup"><span data-stu-id="52a08-137">_riid_</span></span>
  
> <span data-ttu-id="52a08-138">实时要用于返回的 form 对象的接口的接口标识符 (IID)。</span><span class="sxs-lookup"><span data-stu-id="52a08-138">[in] The interface identifier (IID) of the interface to be used for the returned form object.</span></span> <span data-ttu-id="52a08-139">_riid_参数不得为 NULL。</span><span class="sxs-lookup"><span data-stu-id="52a08-139">The  _riid_ parameter must not be NULL.</span></span> 
    
 <span data-ttu-id="52a08-140">_ppvObj_</span><span class="sxs-lookup"><span data-stu-id="52a08-140">_ppvObj_</span></span>
  
> <span data-ttu-id="52a08-141">排除指向指向返回的接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="52a08-141">[out] A pointer to a pointer to the returned interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="52a08-142">返回值</span><span class="sxs-lookup"><span data-stu-id="52a08-142">Return value</span></span>

<span data-ttu-id="52a08-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="52a08-143">S_OK</span></span> 
  
> <span data-ttu-id="52a08-144">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="52a08-144">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="52a08-145">MAPI_E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="52a08-145">MAPI_E_NO_INTERFACE</span></span> 
  
> <span data-ttu-id="52a08-146">表单不支持所请求的界面。</span><span class="sxs-lookup"><span data-stu-id="52a08-146">The form does not support the requested interface.</span></span>
    
<span data-ttu-id="52a08-147">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="52a08-147">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="52a08-148">_lpszMessageClass_中传递的邮件类与表单库中任何表单的邮件类都不匹配。</span><span class="sxs-lookup"><span data-stu-id="52a08-148">The message class passed in  _lpszMessageClass_ does not match the message class for any form in the form library.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="52a08-149">说明</span><span class="sxs-lookup"><span data-stu-id="52a08-149">Remarks</span></span>

<span data-ttu-id="52a08-150">表单查看者调用**IMAPIFormMgr:: LoadForm**方法打开现有邮件的表单。</span><span class="sxs-lookup"><span data-stu-id="52a08-150">Form viewers call the **IMAPIFormMgr::LoadForm** method to open a form for an existing message.</span></span> <span data-ttu-id="52a08-151">**LoadForm**打开 form 对象, 将邮件加载到 form 对象中, 并设置适当的视图上下文 (如有必要), 并返回窗体对象所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="52a08-151">**LoadForm** opens the form object, loads the message into the form object, sets up the appropriate view context, if necessary, and returns the requested interface for the form object.</span></span> 
  
<span data-ttu-id="52a08-152">_pFolderFocus_参数指向包含邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="52a08-152">The  _pFolderFocus_ parameter points to the folder that contains the message.</span></span> <span data-ttu-id="52a08-153">如果邮件嵌入在另一封邮件中, 则_pFolderFocus_应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="52a08-153">If the message is embedded in another message,  _pFolderFocus_ should be NULL.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="52a08-154">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="52a08-154">Notes to implementers</span></span>

<span data-ttu-id="52a08-155">如果在_lpszMessageClass_中传递 NULL, 则实现将从邮件的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))、 **PR_MSG_STATUS**和 PR_MESSAGE_FLAGS 中获取邮件的邮件类、状态和标志。 \*\*\*\* 属性。</span><span class="sxs-lookup"><span data-stu-id="52a08-155">If NULL is passed in  _lpszMessageClass_, the implementation obtains the message's message class, status, and flags from the message's **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)), **PR_MSG_STATUS** and **PR_MESSAGE_FLAGS** properties.</span></span> <span data-ttu-id="52a08-156">如果在_lpszMessageClass_中提供了邮件类字符串, 则该实现必须使用_ulMessageStatus_和_ulMessageFlags_中的值。</span><span class="sxs-lookup"><span data-stu-id="52a08-156">If a message class string is provided in  _lpszMessageClass_, the implementation must use the values in  _ulMessageStatus_ and  _ulMessageFlags_.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="52a08-157">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="52a08-157">MFCMAPI reference</span></span>

<span data-ttu-id="52a08-158">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="52a08-158">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="52a08-159">**文件**</span><span class="sxs-lookup"><span data-stu-id="52a08-159">**File**</span></span>|<span data-ttu-id="52a08-160">**函数**</span><span class="sxs-lookup"><span data-stu-id="52a08-160">**Function**</span></span>|<span data-ttu-id="52a08-161">**备注**</span><span class="sxs-lookup"><span data-stu-id="52a08-161">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="52a08-162">MAPIFormFunctions</span><span class="sxs-lookup"><span data-stu-id="52a08-162">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="52a08-163">OpenMessageNonModal</span><span class="sxs-lookup"><span data-stu-id="52a08-163">OpenMessageNonModal</span></span>  <br/> |<span data-ttu-id="52a08-164">MFCMAPI 使用**IMAPIFormMgr:: LoadForm**方法在显示窗体之前加载它。</span><span class="sxs-lookup"><span data-stu-id="52a08-164">MFCMAPI uses the **IMAPIFormMgr::LoadForm** method to load a form before displaying it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="52a08-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52a08-165">See also</span></span>



[<span data-ttu-id="52a08-166">PidTagMessageClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="52a08-166">PidTagMessageClass Canonical Property</span></span>](pidtagmessageclass-canonical-property.md)
  
[<span data-ttu-id="52a08-167">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="52a08-167">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="52a08-168">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="52a08-168">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="52a08-169">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="52a08-169">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="52a08-170">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="52a08-170">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

