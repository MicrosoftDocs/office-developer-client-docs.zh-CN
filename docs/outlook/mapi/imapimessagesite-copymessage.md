---
title: IMAPIMessageSiteCopyMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.CopyMessage
api_type:
- COM
ms.assetid: d4e18483-409a-4d81-91dc-f4aec29a82bb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aeb8b090997bd0c4f51f872b36d6520547846f7f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429998"
---
# <a name="imapimessagesitecopymessage"></a><span data-ttu-id="4499a-103">IMAPIMessageSite::CopyMessage</span><span class="sxs-lookup"><span data-stu-id="4499a-103">IMAPIMessageSite::CopyMessage</span></span>

  
  
<span data-ttu-id="4499a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4499a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4499a-105">将当前邮件复制到文件夹。</span><span class="sxs-lookup"><span data-stu-id="4499a-105">Copies the current message to a folder.</span></span>
  
```cpp
HRESULT CopyMessage(
  LPMAPIFOLDER pFolderDestination
);
```

## <a name="parameters"></a><span data-ttu-id="4499a-106">参数</span><span class="sxs-lookup"><span data-stu-id="4499a-106">Parameters</span></span>

 <span data-ttu-id="4499a-107">_pFolderDestination_</span><span class="sxs-lookup"><span data-stu-id="4499a-107">_pFolderDestination_</span></span>
  
> <span data-ttu-id="4499a-108">[in]指向要复制邮件的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="4499a-108">[in] A pointer to the folder where the message is to be copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4499a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4499a-109">Return value</span></span>

<span data-ttu-id="4499a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4499a-110">S_OK</span></span> 
  
> <span data-ttu-id="4499a-111">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="4499a-111">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="4499a-112">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="4499a-112">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="4499a-113">此消息网站不支持该操作。</span><span class="sxs-lookup"><span data-stu-id="4499a-113">The operation is not supported by this message site.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4499a-114">备注</span><span class="sxs-lookup"><span data-stu-id="4499a-114">Remarks</span></span>

<span data-ttu-id="4499a-115">Form 对象调用 **IMAPIMessageSite：：CopyMessage** 方法将当前邮件复制到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="4499a-115">Form objects call the **IMAPIMessageSite::CopyMessage** method to copy the current message to a new folder.</span></span> <span data-ttu-id="4499a-116">**CopyMessage** 不会更改当前向用户显示的消息，并且不会向表单返回新创建的邮件的界面。</span><span class="sxs-lookup"><span data-stu-id="4499a-116">**CopyMessage** does not change the message currently being displayed to the user, and no interface for the newly created message is returned to the form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="4499a-117">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="4499a-117">Notes to implementers</span></span>

<span data-ttu-id="4499a-118">**CopyMessage** 方法的典型实现将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4499a-118">A typical implementation of the **CopyMessage** method performs the following tasks:</span></span> 
  
1. <span data-ttu-id="4499a-119">为要复制到的当前邮件创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="4499a-119">Creates a new message for the current message to be copied to.</span></span>
    
2. <span data-ttu-id="4499a-120">使用指向 _pMessage_ 参数中新邮件的指针和 _fSameAsLoad_ 参数中的 FALSE 调用 [IPersistMessage：：Save](ipersistmessage-save.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4499a-120">Calls the [IPersistMessage::Save](ipersistmessage-save.md) method with a pointer to the new message in the  _pMessage_ parameter and FALSE in the  _fSameAsLoad_ parameter.</span></span> 
    
3. <span data-ttu-id="4499a-121">调用 [IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) 方法，在  _pMessage_ 参数中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="4499a-121">Calls the [IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md) method, passing NULL in the  _pMessage_ parameter.</span></span> 
    
4. <span data-ttu-id="4499a-122">对新 [邮件调用 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="4499a-122">Calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the new message.</span></span> 
    
<span data-ttu-id="4499a-123">有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="4499a-123">For a list of interfaces that are related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="4499a-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="4499a-124">MFCMAPI reference</span></span>

<span data-ttu-id="4499a-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="4499a-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="4499a-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="4499a-126">**File**</span></span>|<span data-ttu-id="4499a-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="4499a-127">**Function**</span></span>|<span data-ttu-id="4499a-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="4499a-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4499a-129">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="4499a-129">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="4499a-130">CMyMAPIFormViewer：：CopyMessage</span><span class="sxs-lookup"><span data-stu-id="4499a-130">CMyMAPIFormViewer::CopyMessage</span></span>  <br/> |<span data-ttu-id="4499a-131">未实现。</span><span class="sxs-lookup"><span data-stu-id="4499a-131">Not implemented.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4499a-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4499a-132">See also</span></span>



[<span data-ttu-id="4499a-133">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="4499a-133">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="4499a-134">IPersistMessage::Save</span><span class="sxs-lookup"><span data-stu-id="4499a-134">IPersistMessage::Save</span></span>](ipersistmessage-save.md)
  
[<span data-ttu-id="4499a-135">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="4499a-135">IPersistMessage::SaveCompleted</span></span>](ipersistmessage-savecompleted.md)
  
[<span data-ttu-id="4499a-136">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4499a-136">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="4499a-137">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="4499a-137">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="4499a-138">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="4499a-138">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

