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
ms.openlocfilehash: 074a806a710ce8c11adba815951c93c25d8cae7c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579254"
---
# <a name="imapimessagesitecopymessage"></a><span data-ttu-id="0d1f8-103">IMAPIMessageSite::CopyMessage</span><span class="sxs-lookup"><span data-stu-id="0d1f8-103">IMAPIMessageSite::CopyMessage</span></span>

  
  
<span data-ttu-id="0d1f8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d1f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d1f8-105">将当前的邮件复制到一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-105">Copies the current message to a folder.</span></span>
  
```cpp
HRESULT CopyMessage(
  LPMAPIFOLDER pFolderDestination
);
```

## <a name="parameters"></a><span data-ttu-id="0d1f8-106">参数</span><span class="sxs-lookup"><span data-stu-id="0d1f8-106">Parameters</span></span>

 <span data-ttu-id="0d1f8-107">_pFolderDestination_</span><span class="sxs-lookup"><span data-stu-id="0d1f8-107">_pFolderDestination_</span></span>
  
> <span data-ttu-id="0d1f8-108">[in]一个指向邮件后要复制的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-108">[in] A pointer to the folder where the message is to be copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0d1f8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0d1f8-109">Return value</span></span>

<span data-ttu-id="0d1f8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d1f8-110">S_OK</span></span> 
  
> <span data-ttu-id="0d1f8-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-111">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="0d1f8-112">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="0d1f8-112">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="0d1f8-113">该操作不受此消息网站。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-113">The operation is not supported by this message site.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0d1f8-114">注解</span><span class="sxs-lookup"><span data-stu-id="0d1f8-114">Remarks</span></span>

<span data-ttu-id="0d1f8-115">表单对象调用**IMAPIMessageSite::CopyMessage**方法将当前的邮件复制到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-115">Form objects call the **IMAPIMessageSite::CopyMessage** method to copy the current message to a new folder.</span></span> <span data-ttu-id="0d1f8-116">**CopyMessage**不会更改当前正在显示给用户的邮件和新创建的邮件没有接口返回到表单。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-116">**CopyMessage** does not change the message currently being displayed to the user, and no interface for the newly created message is returned to the form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="0d1f8-117">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="0d1f8-117">Notes to implementers</span></span>

<span data-ttu-id="0d1f8-118">**CopyMessage**方法的典型实现执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0d1f8-118">A typical implementation of the **CopyMessage** method performs the following tasks:</span></span> 
  
1. <span data-ttu-id="0d1f8-119">创建一个新邮件以复制到的当前消息。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-119">Creates a new message for the current message to be copied to.</span></span>
    
2. <span data-ttu-id="0d1f8-120">调用[IPersistMessage::Save](ipersistmessage-save.md)方法与指向_pMessage_参数和 FALSE _fSameAsLoad_参数中的新消息的指针。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-120">Calls the [IPersistMessage::Save](ipersistmessage-save.md) method with a pointer to the new message in the  _pMessage_ parameter and FALSE in the  _fSameAsLoad_ parameter.</span></span> 
    
3. <span data-ttu-id="0d1f8-121">调用[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)方法， _pMessage_参数中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-121">Calls the [IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md) method, passing NULL in the  _pMessage_ parameter.</span></span> 
    
4. <span data-ttu-id="0d1f8-122">在新邮件上调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-122">Calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the new message.</span></span> 
    
<span data-ttu-id="0d1f8-123">向窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-123">For a list of interfaces that are related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="0d1f8-124">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="0d1f8-124">MFCMAPI reference</span></span>

<span data-ttu-id="0d1f8-125">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="0d1f8-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="0d1f8-126">**File**</span></span>|<span data-ttu-id="0d1f8-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="0d1f8-127">**Function**</span></span>|<span data-ttu-id="0d1f8-128">**Comment**</span><span class="sxs-lookup"><span data-stu-id="0d1f8-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0d1f8-129">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="0d1f8-129">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="0d1f8-130">CMyMAPIFormViewer::CopyMessage</span><span class="sxs-lookup"><span data-stu-id="0d1f8-130">CMyMAPIFormViewer::CopyMessage</span></span>  <br/> |<span data-ttu-id="0d1f8-131">未实现。</span><span class="sxs-lookup"><span data-stu-id="0d1f8-131">Not implemented.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0d1f8-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d1f8-132">See also</span></span>



[<span data-ttu-id="0d1f8-133">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="0d1f8-133">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="0d1f8-134">IPersistMessage::Save</span><span class="sxs-lookup"><span data-stu-id="0d1f8-134">IPersistMessage::Save</span></span>](ipersistmessage-save.md)
  
[<span data-ttu-id="0d1f8-135">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="0d1f8-135">IPersistMessage::SaveCompleted</span></span>](ipersistmessage-savecompleted.md)
  
[<span data-ttu-id="0d1f8-136">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0d1f8-136">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="0d1f8-137">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="0d1f8-137">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="0d1f8-138">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="0d1f8-138">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

