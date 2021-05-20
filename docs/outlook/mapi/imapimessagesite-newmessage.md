---
title: IMAPIMessageSiteNewMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.NewMessage
api_type:
- COM
ms.assetid: ce6b6e6c-7f22-43c2-8182-90cf6db93844
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f51dd1fe533d0577996e6e1be185302f2dc972fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438769"
---
# <a name="imapimessagesitenewmessage"></a><span data-ttu-id="6f544-103">IMAPIMessageSite::NewMessage</span><span class="sxs-lookup"><span data-stu-id="6f544-103">IMAPIMessageSite::NewMessage</span></span>

  
  
<span data-ttu-id="6f544-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f544-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6f544-105">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="6f544-105">Creates a new message.</span></span>
  
```cpp
HRESULT NewMessage(
  ULONG fComposeInFolder,
  LPMAPIFOLDER pFolderFocus,
  LPPERSISTMESSAGE pPersistMessage,
  LPMESSAGE FAR * ppMessage,
  LPMAPIMESSAGESITE FAR * ppMessageSite,
  LPMAPIVIEWCONTEXT FAR * ppViewContext
);
```

## <a name="parameters"></a><span data-ttu-id="6f544-106">参数</span><span class="sxs-lookup"><span data-stu-id="6f544-106">Parameters</span></span>

 <span data-ttu-id="6f544-107">_fComposeInFolder_</span><span class="sxs-lookup"><span data-stu-id="6f544-107">_fComposeInFolder_</span></span>
  
> <span data-ttu-id="6f544-108">[in]指示应在哪个文件夹中撰写邮件。</span><span class="sxs-lookup"><span data-stu-id="6f544-108">[in] Indicates in which folder the message should be composed.</span></span> <span data-ttu-id="6f544-109">如果变量为 FALSE，  _则忽略 pFolderFocus_ 参数，并且窗体查看器可以在任何文件夹中撰写邮件。</span><span class="sxs-lookup"><span data-stu-id="6f544-109">If the variable is FALSE, the  _pFolderFocus_ parameter is ignored and the form viewer can compose the message in any folder.</span></span> <span data-ttu-id="6f544-110">如果变量为 TRUE，并且 NULL 在  _pFolderFocus_ 参数中传递，则邮件将在当前文件夹中撰写。</span><span class="sxs-lookup"><span data-stu-id="6f544-110">If the variable is TRUE and NULL is passed in the  _pFolderFocus_ parameter, the message is composed in the current folder.</span></span> <span data-ttu-id="6f544-111">如果变量为 TRUE，且  _pFolderFocus_ 中传递了非 NULL 值，则邮件将组合在  _pFolderFocus 指向的文件夹中_。</span><span class="sxs-lookup"><span data-stu-id="6f544-111">If the variable is TRUE and a non-NULL value is passed in  _pFolderFocus_, the message is composed in the folder pointed to by  _pFolderFocus_.</span></span>
    
 <span data-ttu-id="6f544-112">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="6f544-112">_pFolderFocus_</span></span>
  
> <span data-ttu-id="6f544-113">[in]指向新建邮件的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="6f544-113">[in] A pointer to the folder where the new message is created.</span></span>
    
 <span data-ttu-id="6f544-114">_pPersistMessage_</span><span class="sxs-lookup"><span data-stu-id="6f544-114">_pPersistMessage_</span></span>
  
> <span data-ttu-id="6f544-115">[in]指向新窗体的 form 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="6f544-115">[in] A pointer to the form object for the new form.</span></span>
    
 <span data-ttu-id="6f544-116">_ppMessage_</span><span class="sxs-lookup"><span data-stu-id="6f544-116">_ppMessage_</span></span>
  
> <span data-ttu-id="6f544-117">[out]指向指向新邮件的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6f544-117">[out] A pointer to a pointer to the new message.</span></span>
    
 <span data-ttu-id="6f544-118">_ppMessageSite_</span><span class="sxs-lookup"><span data-stu-id="6f544-118">_ppMessageSite_</span></span>
  
> <span data-ttu-id="6f544-119">[out]指向指向新邮件的消息网站对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6f544-119">[out] A pointer to a pointer to a message site object for the new message.</span></span>
    
 <span data-ttu-id="6f544-120">_ppViewContext_</span><span class="sxs-lookup"><span data-stu-id="6f544-120">_ppViewContext_</span></span>
  
> <span data-ttu-id="6f544-121">[out]指向适用于通过新消息传递到新表单的视图上下文的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6f544-121">[out] A pointer to a pointer to a view context that is appropriate for passing to a new form with the new message.</span></span> <span data-ttu-id="6f544-122">如果表单实现自己的视图上下文，可以在  _ppViewContext_ 参数中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="6f544-122">If the form implements its own view context, NULL can be passed in the  _ppViewContext_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="6f544-123">返回值</span><span class="sxs-lookup"><span data-stu-id="6f544-123">Return value</span></span>

<span data-ttu-id="6f544-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f544-124">S_OK</span></span> 
  
> <span data-ttu-id="6f544-125">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="6f544-125">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6f544-126">备注</span><span class="sxs-lookup"><span data-stu-id="6f544-126">Remarks</span></span>

<span data-ttu-id="6f544-127">Form 对象调用 **IMAPIMessageSite：：NewMessage** 方法来创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="6f544-127">Form objects call the **IMAPIMessageSite::NewMessage** method to create a new message.</span></span> <span data-ttu-id="6f544-128">表单使用 **NewMessage** 从其视图中获取新邮件和关联邮件网站。</span><span class="sxs-lookup"><span data-stu-id="6f544-128">The form uses **NewMessage** to get a new message and the associated message site from its view.</span></span> <span data-ttu-id="6f544-129">然后，它可以修改新邮件。</span><span class="sxs-lookup"><span data-stu-id="6f544-129">It can then modify the new message.</span></span> 
  
<span data-ttu-id="6f544-130">您还可以通过传递  _ppViewContext_ 参数中的非 NULL 值来获取关联的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="6f544-130">You can also obtain an associated view context by passing in a non-NULL value in the  _ppViewContext_ parameter.</span></span> <span data-ttu-id="6f544-131">此视图上下文可以直接使用，也可以聚合并传递到新邮件。</span><span class="sxs-lookup"><span data-stu-id="6f544-131">This view context can be used directly, or it can be aggregated and passed to the new message.</span></span> <span data-ttu-id="6f544-132">如果需要完整实现，在  _ppViewContext_ 中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="6f544-132">If a complete implementation is required, pass NULL in  _ppViewContext_.</span></span>
  
<span data-ttu-id="6f544-133">有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="6f544-133">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6f544-134">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="6f544-134">MFCMAPI reference</span></span>

<span data-ttu-id="6f544-135">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6f544-135">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6f544-136">**文件**</span><span class="sxs-lookup"><span data-stu-id="6f544-136">**File**</span></span>|<span data-ttu-id="6f544-137">**函数**</span><span class="sxs-lookup"><span data-stu-id="6f544-137">**Function**</span></span>|<span data-ttu-id="6f544-138">**备注**</span><span class="sxs-lookup"><span data-stu-id="6f544-138">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6f544-139">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="6f544-139">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="6f544-140">CMyMAPIFormViewer：：NewMessage</span><span class="sxs-lookup"><span data-stu-id="6f544-140">CMyMAPIFormViewer::NewMessage</span></span>  <br/> |<span data-ttu-id="6f544-141">MFCMAPI 使用 **IMAPIMessageSite：：NewMessage** 方法创建新邮件、实例化新的表单查看器，并调用 **SetPersist** 在表单查看器上设置邮件。</span><span class="sxs-lookup"><span data-stu-id="6f544-141">MFCMAPI uses the **IMAPIMessageSite::NewMessage** method to create a new message, instantiate a new form viewer, and call **SetPersist** to set the message on the form viewer.</span></span> <span data-ttu-id="6f544-142">最后，它将窗体查看器作为消息网站返回。</span><span class="sxs-lookup"><span data-stu-id="6f544-142">Finally, it returns the form viewer as the message site.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6f544-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f544-143">See also</span></span>



[<span data-ttu-id="6f544-144">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6f544-144">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)
  
[<span data-ttu-id="6f544-145">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6f544-145">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="6f544-146">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6f544-146">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="6f544-147">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="6f544-147">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

