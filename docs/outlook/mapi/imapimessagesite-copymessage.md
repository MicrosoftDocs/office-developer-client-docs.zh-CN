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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5bf2ff74f6cda01608efd4b372aa4b03468c820f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775450"
---
# <a name="imapimessagesitecopymessage"></a><span data-ttu-id="92043-103">IMAPIMessageSite::CopyMessage</span><span class="sxs-lookup"><span data-stu-id="92043-103">IMAPIMessageSite::CopyMessage</span></span>

  
  
<span data-ttu-id="92043-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="92043-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="92043-105">将当前的邮件复制到一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="92043-105">Copies the current message to a folder.</span></span>
  
```cpp
HRESULT CopyMessage(
  LPMAPIFOLDER pFolderDestination
);
```

## <a name="parameters"></a><span data-ttu-id="92043-106">参数</span><span class="sxs-lookup"><span data-stu-id="92043-106">Parameters</span></span>

 <span data-ttu-id="92043-107">_pFolderDestination_</span><span class="sxs-lookup"><span data-stu-id="92043-107">_pFolderDestination_</span></span>
  
> <span data-ttu-id="92043-108">[in]一个指向邮件后要复制的文件夹。</span><span class="sxs-lookup"><span data-stu-id="92043-108">[in] A pointer to the folder where the message is to be copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="92043-109">返回值</span><span class="sxs-lookup"><span data-stu-id="92043-109">Return value</span></span>

<span data-ttu-id="92043-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="92043-110">S_OK</span></span> 
  
> <span data-ttu-id="92043-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="92043-111">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="92043-112">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="92043-112">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="92043-113">该操作不受此消息网站。</span><span class="sxs-lookup"><span data-stu-id="92043-113">The operation is not supported by this message site.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="92043-114">备注</span><span class="sxs-lookup"><span data-stu-id="92043-114">Remarks</span></span>

<span data-ttu-id="92043-115">表单对象调用**IMAPIMessageSite::CopyMessage**方法将当前的邮件复制到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="92043-115">Form objects call the **IMAPIMessageSite::CopyMessage** method to copy the current message to a new folder.</span></span> <span data-ttu-id="92043-116">**CopyMessage**不会更改当前正在显示给用户的邮件和新创建的邮件没有接口返回到表单。</span><span class="sxs-lookup"><span data-stu-id="92043-116">**CopyMessage** does not change the message currently being displayed to the user, and no interface for the newly created message is returned to the form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="92043-117">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="92043-117">Notes to implementers</span></span>

<span data-ttu-id="92043-118">**CopyMessage**方法的典型实现执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="92043-118">A typical implementation of the **CopyMessage** method performs the following tasks:</span></span> 
  
1. <span data-ttu-id="92043-119">创建一个新邮件以复制到的当前消息。</span><span class="sxs-lookup"><span data-stu-id="92043-119">Creates a new message for the current message to be copied to.</span></span>
    
2. <span data-ttu-id="92043-120">调用[IPersistMessage::Save](ipersistmessage-save.md)方法与指向_pMessage_参数和 FALSE _fSameAsLoad_参数中的新消息的指针。</span><span class="sxs-lookup"><span data-stu-id="92043-120">Calls the [IPersistMessage::Save](ipersistmessage-save.md) method with a pointer to the new message in the  _pMessage_ parameter and FALSE in the  _fSameAsLoad_ parameter.</span></span> 
    
3. <span data-ttu-id="92043-121">调用[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)方法， _pMessage_参数中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="92043-121">Calls the [IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md) method, passing NULL in the  _pMessage_ parameter.</span></span> 
    
4. <span data-ttu-id="92043-122">在新邮件上调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="92043-122">Calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the new message.</span></span> 
    
<span data-ttu-id="92043-123">向窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="92043-123">For a list of interfaces that are related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="92043-124">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="92043-124">MFCMAPI reference</span></span>

<span data-ttu-id="92043-125">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="92043-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="92043-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="92043-126">**File**</span></span>|<span data-ttu-id="92043-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="92043-127">**Function**</span></span>|<span data-ttu-id="92043-128">**Comment**</span><span class="sxs-lookup"><span data-stu-id="92043-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92043-129">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="92043-129">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="92043-130">CMyMAPIFormViewer::CopyMessage</span><span class="sxs-lookup"><span data-stu-id="92043-130">CMyMAPIFormViewer::CopyMessage</span></span>  <br/> |<span data-ttu-id="92043-131">未实现。</span><span class="sxs-lookup"><span data-stu-id="92043-131">Not implemented.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="92043-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92043-132">See also</span></span>



[<span data-ttu-id="92043-133">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="92043-133">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="92043-134">IPersistMessage::Save</span><span class="sxs-lookup"><span data-stu-id="92043-134">IPersistMessage::Save</span></span>](ipersistmessage-save.md)
  
[<span data-ttu-id="92043-135">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="92043-135">IPersistMessage::SaveCompleted</span></span>](ipersistmessage-savecompleted.md)
  
[<span data-ttu-id="92043-136">IMAPIMessageSite: IUnknown</span><span class="sxs-lookup"><span data-stu-id="92043-136">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="92043-137">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="92043-137">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="92043-138">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="92043-138">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

