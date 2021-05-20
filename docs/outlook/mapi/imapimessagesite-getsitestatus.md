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
ms.openlocfilehash: ab4a06a20c71943f9b649d8f22377f59223e9717
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430124"
---
# <a name="imapimessagesitegetsitestatus"></a><span data-ttu-id="2793e-103">IMAPIMessageSite::GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="2793e-103">IMAPIMessageSite::GetSiteStatus</span></span>

  
  
<span data-ttu-id="2793e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2793e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2793e-105">从邮件网站对象返回有关当前邮件的邮件网站功能的信息。</span><span class="sxs-lookup"><span data-stu-id="2793e-105">Returns information from a message site object about the message site's capabilities for the current message.</span></span>
  
```cpp
HRESULT GetSiteStatus(
  ULONG FAR * lpulStatus
);
```

## <a name="parameters"></a><span data-ttu-id="2793e-106">参数</span><span class="sxs-lookup"><span data-stu-id="2793e-106">Parameters</span></span>

 <span data-ttu-id="2793e-107">_lpulStatus_</span><span class="sxs-lookup"><span data-stu-id="2793e-107">_lpulStatus_</span></span>
  
> <span data-ttu-id="2793e-108">[out]指向标志的位掩码的指针，该标记提供有关邮件状态的信息。</span><span class="sxs-lookup"><span data-stu-id="2793e-108">[out] A pointer to a bitmask of flags that provides information about message status.</span></span> <span data-ttu-id="2793e-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="2793e-109">The following flags can be set:</span></span>
    
<span data-ttu-id="2793e-110">VCSTATUS_COPY</span><span class="sxs-lookup"><span data-stu-id="2793e-110">VCSTATUS_COPY</span></span> 
  
> <span data-ttu-id="2793e-111">可以复制邮件。</span><span class="sxs-lookup"><span data-stu-id="2793e-111">The message can be copied.</span></span> 
    
<span data-ttu-id="2793e-112">VCSTATUS_DELETE</span><span class="sxs-lookup"><span data-stu-id="2793e-112">VCSTATUS_DELETE</span></span> 
  
> <span data-ttu-id="2793e-113">可以删除该邮件。</span><span class="sxs-lookup"><span data-stu-id="2793e-113">The message can be deleted.</span></span>
    
<span data-ttu-id="2793e-114">VCSTATUS_DELETE_IS_MOVE</span><span class="sxs-lookup"><span data-stu-id="2793e-114">VCSTATUS_DELETE_IS_MOVE</span></span> 
  
> <span data-ttu-id="2793e-115">删除邮件时，邮件将移动到其邮件存储中的"已删除邮件"文件夹，而不是立即从邮件存储中删除。</span><span class="sxs-lookup"><span data-stu-id="2793e-115">When deleted, a message is moved to a **Deleted Items** folder in its message store instead of being immediately removed from its message store.</span></span> 
    
<span data-ttu-id="2793e-116">VCSTATUS_MOVE</span><span class="sxs-lookup"><span data-stu-id="2793e-116">VCSTATUS_MOVE</span></span> 
  
> <span data-ttu-id="2793e-117">可以移动邮件。</span><span class="sxs-lookup"><span data-stu-id="2793e-117">The message can be moved.</span></span>
    
<span data-ttu-id="2793e-118">VCSTATUS_NEW_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="2793e-118">VCSTATUS_NEW_MESSAGE</span></span> 
  
> <span data-ttu-id="2793e-119">可以新建邮件。</span><span class="sxs-lookup"><span data-stu-id="2793e-119">A new message can be created.</span></span>
    
<span data-ttu-id="2793e-120">VCSTATUS_SAVE</span><span class="sxs-lookup"><span data-stu-id="2793e-120">VCSTATUS_SAVE</span></span> 
  
> <span data-ttu-id="2793e-121">可以保存邮件。</span><span class="sxs-lookup"><span data-stu-id="2793e-121">The message can be saved.</span></span>
    
<span data-ttu-id="2793e-122">VCSTATUS_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="2793e-122">VCSTATUS_SUBMIT</span></span> 
  
> <span data-ttu-id="2793e-123">可以提交邮件。</span><span class="sxs-lookup"><span data-stu-id="2793e-123">The message can be submitted.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2793e-124">返回值</span><span class="sxs-lookup"><span data-stu-id="2793e-124">Return value</span></span>

<span data-ttu-id="2793e-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="2793e-125">S_OK</span></span> 
  
> <span data-ttu-id="2793e-126">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="2793e-126">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2793e-127">备注</span><span class="sxs-lookup"><span data-stu-id="2793e-127">Remarks</span></span>

<span data-ttu-id="2793e-128">Form 对象调用 **IMAPIMessageSite：：GetSiteStatus** 方法以获取邮件网站对象对当前邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="2793e-128">Form objects call the **IMAPIMessageSite::GetSiteStatus** method to obtain the message site object's capabilities for the current message.</span></span> <span data-ttu-id="2793e-129">_lpulStatus_ 参数中返回的标志提供有关邮件站点的信息。</span><span class="sxs-lookup"><span data-stu-id="2793e-129">The flags returned in the  _lpulStatus_ parameter provide information about the message site.</span></span> <span data-ttu-id="2793e-130">通常，窗体启用或禁用菜单命令，具体取决于标志提供的有关邮件网站实现功能的信息。</span><span class="sxs-lookup"><span data-stu-id="2793e-130">Typically, a form enables or disables menu commands, depending on information the flags provide about the capabilities of the message site implementation.</span></span> <span data-ttu-id="2793e-131">如果 [IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) 方法或 [IPersistMessage：：Load](ipersistmessage-load.md) 方法将新邮件加载到表单中，则必须检查状态标志。</span><span class="sxs-lookup"><span data-stu-id="2793e-131">If a new message is loaded into a form by the [IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md) method or the [IPersistMessage::Load](ipersistmessage-load.md) method, the status flags must be checked.</span></span> <span data-ttu-id="2793e-132">某些邮件网站对象（尤其是只读对象）不允许保存或删除邮件。</span><span class="sxs-lookup"><span data-stu-id="2793e-132">Some message site objects, especially read-only objects, do not allow messages to be saved or deleted.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2793e-133">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="2793e-133">Notes to implementers</span></span>

<span data-ttu-id="2793e-134">**IMAPIMessageSite：：GetSiteStatus** 方法可能要求客户端应用程序执行一些计算，以确定可以或不能对当前消息执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2793e-134">The **IMAPIMessageSite::GetSiteStatus** method may require the client application to do some calculation to determine what operations can or cannot be performed on the current message.</span></span> <span data-ttu-id="2793e-135">通常，这涉及到查看当前邮件的邮件存储提供程序的状态行，或查询存储提供程序以确定客户端应用程序可以使用邮件存储执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2793e-135">Typically, that involves looking at the status row for the current message's message store provider, or querying the store provider to determine which actions the client application can perform by using the message store.</span></span> <span data-ttu-id="2793e-136">例如，若要确定是否返回 MAPI_DELETE_IS_MOVE 标志，请检查邮件存储对象的 **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 属性以查看邮件存储中是否有"已删除邮件"文件夹。 </span><span class="sxs-lookup"><span data-stu-id="2793e-136">For example, to determine whether to return the MAPI_DELETE_IS_MOVE flag, check the message store object's **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) property to see whether there is a **Deleted Items** folder in the message store.</span></span> 
  
<span data-ttu-id="2793e-137">有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="2793e-137">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2793e-138">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="2793e-138">MFCMAPI reference</span></span>

<span data-ttu-id="2793e-139">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2793e-139">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2793e-140">**文件**</span><span class="sxs-lookup"><span data-stu-id="2793e-140">**File**</span></span>|<span data-ttu-id="2793e-141">**函数**</span><span class="sxs-lookup"><span data-stu-id="2793e-141">**Function**</span></span>|<span data-ttu-id="2793e-142">**备注**</span><span class="sxs-lookup"><span data-stu-id="2793e-142">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2793e-143">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="2793e-143">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="2793e-144">CMyMAPIFormViewer：：GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="2793e-144">CMyMAPIFormViewer::GetSiteStatus</span></span>  <br/> |<span data-ttu-id="2793e-145">MFCMAPI 使用 **IMAPIMessageSite：：GetSiteStatus** 方法获取指定站点的状态。</span><span class="sxs-lookup"><span data-stu-id="2793e-145">MFCMAPI uses the **IMAPIMessageSite::GetSiteStatus** method to get the status of the specified site.</span></span> <span data-ttu-id="2793e-146">它可以返回VCSTATUS_NEW_MESSAGE、VCSTATUS_SAVE或VCSTATUS_SUBMIT。</span><span class="sxs-lookup"><span data-stu-id="2793e-146">It can return VCSTATUS_NEW_MESSAGE, VCSTATUS_SAVE, or VCSTATUS_SUBMIT.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2793e-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2793e-147">See also</span></span>



[<span data-ttu-id="2793e-148">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="2793e-148">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="2793e-149">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="2793e-149">IPersistMessage::SaveCompleted</span></span>](ipersistmessage-savecompleted.md)
  
[<span data-ttu-id="2793e-150">PidTagIpmWastebasketEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="2793e-150">PidTagIpmWastebasketEntryId Canonical Property</span></span>](pidtagipmwastebasketentryid-canonical-property.md)
  
[<span data-ttu-id="2793e-151">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2793e-151">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="2793e-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="2793e-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="2793e-153">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="2793e-153">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

