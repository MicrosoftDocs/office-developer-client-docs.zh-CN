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
ms.openlocfilehash: 7062e0b73d2d70be12fb9cead6813ef9c36fdd43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775470"
---
# <a name="imapimessagesitenewmessage"></a><span data-ttu-id="98d2a-103">IMAPIMessageSite::NewMessage</span><span class="sxs-lookup"><span data-stu-id="98d2a-103">IMAPIMessageSite::NewMessage</span></span>

  
  
<span data-ttu-id="98d2a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="98d2a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="98d2a-105">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="98d2a-105">Creates a new message.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="98d2a-106">参数</span><span class="sxs-lookup"><span data-stu-id="98d2a-106">Parameters</span></span>

 <span data-ttu-id="98d2a-107">_fComposeInFolder_</span><span class="sxs-lookup"><span data-stu-id="98d2a-107">_fComposeInFolder_</span></span>
  
> <span data-ttu-id="98d2a-108">[in]指示哪些文件夹中邮件应组成。</span><span class="sxs-lookup"><span data-stu-id="98d2a-108">[in] Indicates in which folder the message should be composed.</span></span> <span data-ttu-id="98d2a-109">如果该变量为 FALSE，将忽略该_pFolderFocus_参数和表单查看器可以撰写任何文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="98d2a-109">If the variable is FALSE, the  _pFolderFocus_ parameter is ignored and the form viewer can compose the message in any folder.</span></span> <span data-ttu-id="98d2a-110">如果该变量值为 TRUE 和_pFolderFocus_参数中传递 NULL，则邮件由当前文件夹中。</span><span class="sxs-lookup"><span data-stu-id="98d2a-110">If the variable is TRUE and NULL is passed in the  _pFolderFocus_ parameter, the message is composed in the current folder.</span></span> <span data-ttu-id="98d2a-111">如果该变量为 TRUE 且非 NULL 值_pFolderFocus_中传递，邮件由由_pFolderFocus_指向的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="98d2a-111">If the variable is TRUE and a non-NULL value is passed in  _pFolderFocus_, the message is composed in the folder pointed to by  _pFolderFocus_.</span></span>
    
 <span data-ttu-id="98d2a-112">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="98d2a-112">_pFolderFocus_</span></span>
  
> <span data-ttu-id="98d2a-113">[in]指向在其中创建新邮件文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="98d2a-113">[in] A pointer to the folder where the new message is created.</span></span>
    
 <span data-ttu-id="98d2a-114">_pPersistMessage_</span><span class="sxs-lookup"><span data-stu-id="98d2a-114">_pPersistMessage_</span></span>
  
> <span data-ttu-id="98d2a-115">[in]指向新窗体的窗体对象的指针。</span><span class="sxs-lookup"><span data-stu-id="98d2a-115">[in] A pointer to the form object for the new form.</span></span>
    
 <span data-ttu-id="98d2a-116">_ppMessage_</span><span class="sxs-lookup"><span data-stu-id="98d2a-116">_ppMessage_</span></span>
  
> <span data-ttu-id="98d2a-117">[输出]为指向新邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="98d2a-117">[out] A pointer to a pointer to the new message.</span></span>
    
 <span data-ttu-id="98d2a-118">_ppMessageSite_</span><span class="sxs-lookup"><span data-stu-id="98d2a-118">_ppMessageSite_</span></span>
  
> <span data-ttu-id="98d2a-119">[输出]指向新邮件的邮件网站对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="98d2a-119">[out] A pointer to a pointer to a message site object for the new message.</span></span>
    
 <span data-ttu-id="98d2a-120">_ppViewContext_</span><span class="sxs-lookup"><span data-stu-id="98d2a-120">_ppViewContext_</span></span>
  
> <span data-ttu-id="98d2a-121">[输出]指向适用于向新窗体与新邮件的传递了视图上下文的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="98d2a-121">[out] A pointer to a pointer to a view context that is appropriate for passing to a new form with the new message.</span></span> <span data-ttu-id="98d2a-122">如果窗体实现自己视图上下文，则可以_ppViewContext_参数中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="98d2a-122">If the form implements its own view context, NULL can be passed in the  _ppViewContext_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="98d2a-123">返回值</span><span class="sxs-lookup"><span data-stu-id="98d2a-123">Return value</span></span>

<span data-ttu-id="98d2a-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="98d2a-124">S_OK</span></span> 
  
> <span data-ttu-id="98d2a-125">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="98d2a-125">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="98d2a-126">说明</span><span class="sxs-lookup"><span data-stu-id="98d2a-126">Remarks</span></span>

<span data-ttu-id="98d2a-127">表单对象调用**IMAPIMessageSite::NewMessage**方法创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="98d2a-127">Form objects call the **IMAPIMessageSite::NewMessage** method to create a new message.</span></span> <span data-ttu-id="98d2a-128">窗体使用**NewMessage**获得其视图的新邮件和关联的邮件网站。</span><span class="sxs-lookup"><span data-stu-id="98d2a-128">The form uses **NewMessage** to get a new message and the associated message site from its view.</span></span> <span data-ttu-id="98d2a-129">然后，它可以修改新邮件。</span><span class="sxs-lookup"><span data-stu-id="98d2a-129">It can then modify the new message.</span></span> 
  
<span data-ttu-id="98d2a-130">您还可以通过传入非 NULL 值_ppViewContext_参数中获取的关联的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="98d2a-130">You can also obtain an associated view context by passing in a non-NULL value in the  _ppViewContext_ parameter.</span></span> <span data-ttu-id="98d2a-131">此视图上下文可直接，也可以聚合和传递给新邮件。</span><span class="sxs-lookup"><span data-stu-id="98d2a-131">This view context can be used directly, or it can be aggregated and passed to the new message.</span></span> <span data-ttu-id="98d2a-132">如果需要完整的实现，则在_ppViewContext_传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="98d2a-132">If a complete implementation is required, pass NULL in  _ppViewContext_.</span></span>
  
<span data-ttu-id="98d2a-133">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="98d2a-133">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="98d2a-134">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="98d2a-134">MFCMAPI reference</span></span>

<span data-ttu-id="98d2a-135">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="98d2a-135">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="98d2a-136">**文件**</span><span class="sxs-lookup"><span data-stu-id="98d2a-136">**File**</span></span>|<span data-ttu-id="98d2a-137">**函数**</span><span class="sxs-lookup"><span data-stu-id="98d2a-137">**Function**</span></span>|<span data-ttu-id="98d2a-138">**Comment**</span><span class="sxs-lookup"><span data-stu-id="98d2a-138">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="98d2a-139">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="98d2a-139">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="98d2a-140">CMyMAPIFormViewer::NewMessage</span><span class="sxs-lookup"><span data-stu-id="98d2a-140">CMyMAPIFormViewer::NewMessage</span></span>  <br/> |<span data-ttu-id="98d2a-141">MFCMAPI 使用**IMAPIMessageSite::NewMessage**方法创建一个新的邮件、 实例化新的表单查看器中，并调用**SetPersist**对表单查看器中设置邮件。</span><span class="sxs-lookup"><span data-stu-id="98d2a-141">MFCMAPI uses the **IMAPIMessageSite::NewMessage** method to create a new message, instantiate a new form viewer, and call **SetPersist** to set the message on the form viewer.</span></span> <span data-ttu-id="98d2a-142">最后，该消息网站返回表单查看器。</span><span class="sxs-lookup"><span data-stu-id="98d2a-142">Finally, it returns the form viewer as the message site.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="98d2a-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98d2a-143">See also</span></span>



[<span data-ttu-id="98d2a-144">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="98d2a-144">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)
  
[<span data-ttu-id="98d2a-145">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="98d2a-145">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="98d2a-146">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="98d2a-146">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="98d2a-147">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="98d2a-147">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

