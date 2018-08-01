---
title: IMAPIMessageSiteGetSiteStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetSiteStatus
api_type:
- COM
ms.assetid: 02718898-7857-4e43-8f46-622269f812e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7d81533b13f4f44a0644215e009dc3477717e9a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775461"
---
# <a name="imapimessagesitegetsitestatus"></a><span data-ttu-id="eb9d9-103">IMAPIMessageSite::GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="eb9d9-103">IMAPIMessageSite::GetSiteStatus</span></span>

  
  
<span data-ttu-id="eb9d9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="eb9d9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="eb9d9-105">返回信息有关邮件消息网站对象中为当前消息的网站的功能。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-105">Returns information from a message site object about the message site's capabilities for the current message.</span></span>
  
```cpp
HRESULT GetSiteStatus(
  ULONG FAR * lpulStatus
);
```

## <a name="parameters"></a><span data-ttu-id="eb9d9-106">参数</span><span class="sxs-lookup"><span data-stu-id="eb9d9-106">Parameters</span></span>

 <span data-ttu-id="eb9d9-107">_lpulStatus_</span><span class="sxs-lookup"><span data-stu-id="eb9d9-107">_lpulStatus_</span></span>
  
> <span data-ttu-id="eb9d9-108">[输出]一个指向提供有关邮件状态信息的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-108">[out] A pointer to a bitmask of flags that provides information about message status.</span></span> <span data-ttu-id="eb9d9-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="eb9d9-109">The following flags can be set:</span></span>
    
<span data-ttu-id="eb9d9-110">VCSTATUS_COPY</span><span class="sxs-lookup"><span data-stu-id="eb9d9-110">VCSTATUS_COPY</span></span> 
  
> <span data-ttu-id="eb9d9-111">可以复制邮件。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-111">The message can be copied.</span></span> 
    
<span data-ttu-id="eb9d9-112">VCSTATUS_DELETE</span><span class="sxs-lookup"><span data-stu-id="eb9d9-112">VCSTATUS_DELETE</span></span> 
  
> <span data-ttu-id="eb9d9-113">可以删除邮件。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-113">The message can be deleted.</span></span>
    
<span data-ttu-id="eb9d9-114">VCSTATUS_DELETE_IS_MOVE</span><span class="sxs-lookup"><span data-stu-id="eb9d9-114">VCSTATUS_DELETE_IS_MOVE</span></span> 
  
> <span data-ttu-id="eb9d9-115">删除时，邮件移动到而不是从其消息存储库立即删除其消息存储库中的**已删除邮件**文件夹。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-115">When deleted, a message is moved to a **Deleted Items** folder in its message store instead of being immediately removed from its message store.</span></span> 
    
<span data-ttu-id="eb9d9-116">VCSTATUS_MOVE</span><span class="sxs-lookup"><span data-stu-id="eb9d9-116">VCSTATUS_MOVE</span></span> 
  
> <span data-ttu-id="eb9d9-117">邮件可被移动。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-117">The message can be moved.</span></span>
    
<span data-ttu-id="eb9d9-118">VCSTATUS_NEW_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="eb9d9-118">VCSTATUS_NEW_MESSAGE</span></span> 
  
> <span data-ttu-id="eb9d9-119">可以创建一个新的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-119">A new message can be created.</span></span>
    
<span data-ttu-id="eb9d9-120">VCSTATUS_SAVE</span><span class="sxs-lookup"><span data-stu-id="eb9d9-120">VCSTATUS_SAVE</span></span> 
  
> <span data-ttu-id="eb9d9-121">可以保存该邮件。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-121">The message can be saved.</span></span>
    
<span data-ttu-id="eb9d9-122">VCSTATUS_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="eb9d9-122">VCSTATUS_SUBMIT</span></span> 
  
> <span data-ttu-id="eb9d9-123">可以提交邮件。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-123">The message can be submitted.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="eb9d9-124">返回值</span><span class="sxs-lookup"><span data-stu-id="eb9d9-124">Return value</span></span>

<span data-ttu-id="eb9d9-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb9d9-125">S_OK</span></span> 
  
> <span data-ttu-id="eb9d9-126">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-126">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="eb9d9-127">说明</span><span class="sxs-lookup"><span data-stu-id="eb9d9-127">Remarks</span></span>

<span data-ttu-id="eb9d9-128">表单对象调用**IMAPIMessageSite::GetSiteStatus**方法获取当前消息的消息网站对象的功能。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-128">Form objects call the **IMAPIMessageSite::GetSiteStatus** method to obtain the message site object's capabilities for the current message.</span></span> <span data-ttu-id="eb9d9-129">_LpulStatus_参数中返回的标志提供有关邮件网站的信息。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-129">The flags returned in the  _lpulStatus_ parameter provide information about the message site.</span></span> <span data-ttu-id="eb9d9-130">通常情况下，窗体启用或禁用菜单命令，具体取决于标志提供有关功能的信息的邮件网站实现。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-130">Typically, a form enables or disables menu commands, depending on information the flags provide about the capabilities of the message site implementation.</span></span> <span data-ttu-id="eb9d9-131">如果新邮件[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)方法或[IPersistMessage::Load](ipersistmessage-load.md)方法加载到窗体时，必须检查状态标志。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-131">If a new message is loaded into a form by the [IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md) method or the [IPersistMessage::Load](ipersistmessage-load.md) method, the status flags must be checked.</span></span> <span data-ttu-id="eb9d9-132">某些消息网站对象，尤其是只读的对象，不允许保存或删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-132">Some message site objects, especially read-only objects, do not allow messages to be saved or deleted.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="eb9d9-133">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="eb9d9-133">Notes to implementers</span></span>

<span data-ttu-id="eb9d9-134">**IMAPIMessageSite::GetSiteStatus**方法可能需要进行一些计算，以确定操作可以或不能对当前邮件执行客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-134">The **IMAPIMessageSite::GetSiteStatus** method may require the client application to do some calculation to determine what operations can or cannot be performed on the current message.</span></span> <span data-ttu-id="eb9d9-135">通常情况下，涉及的当前消息的消息存储提供程序，看的状态行或查询的存储提供程序，以确定哪些操作的客户端应用程序可以执行使用的消息存储。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-135">Typically, that involves looking at the status row for the current message's message store provider, or querying the store provider to determine which actions the client application can perform by using the message store.</span></span> <span data-ttu-id="eb9d9-136">例如，若要确定是否返回 MAPI_DELETE_IS_MOVE 标志，检查消息存储对象**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 属性以查看是否存在中的**已删除邮件**文件夹邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-136">For example, to determine whether to return the MAPI_DELETE_IS_MOVE flag, check the message store object's **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) property to see whether there is a **Deleted Items** folder in the message store.</span></span> 
  
<span data-ttu-id="eb9d9-137">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-137">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="eb9d9-138">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="eb9d9-138">MFCMAPI reference</span></span>

<span data-ttu-id="eb9d9-139">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-139">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="eb9d9-140">**文件**</span><span class="sxs-lookup"><span data-stu-id="eb9d9-140">**File**</span></span>|<span data-ttu-id="eb9d9-141">**函数**</span><span class="sxs-lookup"><span data-stu-id="eb9d9-141">**Function**</span></span>|<span data-ttu-id="eb9d9-142">**Comment**</span><span class="sxs-lookup"><span data-stu-id="eb9d9-142">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eb9d9-143">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="eb9d9-143">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="eb9d9-144">CMyMAPIFormViewer::GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="eb9d9-144">CMyMAPIFormViewer::GetSiteStatus</span></span>  <br/> |<span data-ttu-id="eb9d9-145">MFCMAPI 使用**IMAPIMessageSite::GetSiteStatus**方法获取指定网站的状态。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-145">MFCMAPI uses the **IMAPIMessageSite::GetSiteStatus** method to get the status of the specified site.</span></span> <span data-ttu-id="eb9d9-146">它可以返回 VCSTATUS_NEW_MESSAGE、 VCSTATUS_SAVE 或 VCSTATUS_SUBMIT。</span><span class="sxs-lookup"><span data-stu-id="eb9d9-146">It can return VCSTATUS_NEW_MESSAGE, VCSTATUS_SAVE, or VCSTATUS_SUBMIT.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="eb9d9-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb9d9-147">See also</span></span>



[<span data-ttu-id="eb9d9-148">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="eb9d9-148">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="eb9d9-149">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="eb9d9-149">IPersistMessage::SaveCompleted</span></span>](ipersistmessage-savecompleted.md)
  
[<span data-ttu-id="eb9d9-150">PidTagIpmWastebasketEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="eb9d9-150">PidTagIpmWastebasketEntryId Canonical Property</span></span>](pidtagipmwastebasketentryid-canonical-property.md)
  
[<span data-ttu-id="eb9d9-151">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="eb9d9-151">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="eb9d9-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="eb9d9-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="eb9d9-153">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="eb9d9-153">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

