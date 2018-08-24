---
title: IPersistMessageInitNew
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.InitNew
api_type:
- COM
ms.assetid: 4bf37c35-4f72-438a-912c-402f3711a5ea
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: efeac5a54c576d8b76d94ea7af8949e64dbccab6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588508"
---
# <a name="ipersistmessageinitnew"></a><span data-ttu-id="f3119-103">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="f3119-103">IPersistMessage::InitNew</span></span>

  
  
<span data-ttu-id="f3119-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3119-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3119-105">初始化新邮件。</span><span class="sxs-lookup"><span data-stu-id="f3119-105">Initializes a new message.</span></span>
  
```cpp
HRESULT InitNew(
  LPMAPIMESSAGESITE pMessageSite,
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a><span data-ttu-id="f3119-106">参数</span><span class="sxs-lookup"><span data-stu-id="f3119-106">Parameters</span></span>

 <span data-ttu-id="f3119-107">_pMessageSite_</span><span class="sxs-lookup"><span data-stu-id="f3119-107">_pMessageSite_</span></span>
  
> <span data-ttu-id="f3119-108">[in]表单将用于处理查看器中邮件消息站点链接。</span><span class="sxs-lookup"><span data-stu-id="f3119-108">[in] A pointer to the message site that the form will use to work with the message in the viewer.</span></span>
    
 <span data-ttu-id="f3119-109">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="f3119-109">_pMessage_</span></span>
  
> <span data-ttu-id="f3119-110">[in]一个指向新邮件。</span><span class="sxs-lookup"><span data-stu-id="f3119-110">[in] A pointer to the new message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f3119-111">返回值</span><span class="sxs-lookup"><span data-stu-id="f3119-111">Return value</span></span>

<span data-ttu-id="f3119-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3119-112">S_OK</span></span> 
  
> <span data-ttu-id="f3119-113">已成功初始化新邮件。</span><span class="sxs-lookup"><span data-stu-id="f3119-113">The new message was successfully initialized.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f3119-114">注解</span><span class="sxs-lookup"><span data-stu-id="f3119-114">Remarks</span></span>

<span data-ttu-id="f3119-115">当用户写入属于窗体处理邮件类的新消息时，表单查看器调用**IPersistMessage::InitNew**方法。</span><span class="sxs-lookup"><span data-stu-id="f3119-115">Form viewers call the **IPersistMessage::InitNew** method when the user writes a new message that belongs to a message class that the form handles.</span></span> <span data-ttu-id="f3119-116">如果窗体对象具有一个有效的用户界面指针，应显示的消息对象的用户界面。</span><span class="sxs-lookup"><span data-stu-id="f3119-116">If the form object has a valid user interface pointer, the user interface for the message object should be displayed.</span></span> 
  
 <span data-ttu-id="f3119-117">仅当表单处于[未初始化](uninitialized-state.md)状态以外的所有状态时，不应调用**丢失**。</span><span class="sxs-lookup"><span data-stu-id="f3119-117">**InitNew** should not be called when your form is in any state except the [Uninitialized](uninitialized-state.md) state.</span></span> <span data-ttu-id="f3119-118">如果表单没有其他状态之一，调用**丢失**时，返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="f3119-118">If the form is in one of the other states when **InitNew** is called, return E_UNEXPECTED.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="f3119-119">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="f3119-119">Notes to implementers</span></span>

<span data-ttu-id="f3119-120">通常情况下，有未保存的属性的邮件被标记为修改，以便客户端可以显示一个对话框，提示用户是否应该保存这些属性。</span><span class="sxs-lookup"><span data-stu-id="f3119-120">Typically, messages that have unsaved properties are marked as modified so that the client can display a dialog box that prompts the user whether these properties should be saved.</span></span> <span data-ttu-id="f3119-121">如果用户指示应保存一条消息，保存数据、 邮件标记为干净，并正常退出。</span><span class="sxs-lookup"><span data-stu-id="f3119-121">If the user indicates that a message should be saved, save the data, mark the message as clean, and exit normally.</span></span>
  
<span data-ttu-id="f3119-122">但是，如果新初始化邮件处理包括设置其中一个或多计算属性，并且一点很重要保存这些属性，不要将邮件标记为已修改。</span><span class="sxs-lookup"><span data-stu-id="f3119-122">However, if processing for your newly initialized messages includes setting one or more computed properties, and it is important for those properties to be saved, do not mark the messages as modified.</span></span> <span data-ttu-id="f3119-123">因为计算属性应为对用户不可见，应不显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="f3119-123">Because computed properties should be invisible to users, no dialog box should be displayed.</span></span>
  
<span data-ttu-id="f3119-124">如果窗体有一个引用传递到**丢失**以外的活动邮件网站，释放原始网站，因为不再使用它。</span><span class="sxs-lookup"><span data-stu-id="f3119-124">If your form has a reference to an active message site other than the one that is passed into **InitNew**, release the original site because it will no longer be used.</span></span> <span data-ttu-id="f3119-125">存储从_pMessageSite_和_pMessage_参数的消息网站和消息的指针和调用这两个对象的[IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法，以增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="f3119-125">Store the pointers to the message site and message from the  _pMessageSite_ and  _pMessage_ parameters and call both objects' [IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) methods to increment their reference counts.</span></span> 
  
<span data-ttu-id="f3119-126">设置为适合于您的邮件类的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和新邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="f3119-126">Set the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) and **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) properties for the new message to something appropriate for your message class.</span></span> <span data-ttu-id="f3119-127">多个邮件类别，例如，设置**PR_MESSAGE_FLAGS**为 MSGFLAG_UNSENT 新邮件。</span><span class="sxs-lookup"><span data-stu-id="f3119-127">Many message classes, for example, set **PR_MESSAGE_FLAGS** to MSGFLAG_UNSENT for new messages.</span></span> 
  
<span data-ttu-id="f3119-128">返回之前, 出现转换为[普通](normal-state.md)状态，如果没有错误窗体。</span><span class="sxs-lookup"><span data-stu-id="f3119-128">Before returning, transition the form to the [Normal](normal-state.md) state if no errors have occurred.</span></span> <span data-ttu-id="f3119-129">通过调用其[IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法向所有已注册的查看者发送新邮件通知，并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f3119-129">Send a new message notification to all registered viewers by calling their [IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md) methods and return S_OK.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f3119-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f3119-130">Notes to callers</span></span>

<span data-ttu-id="f3119-131">所做的**丢失**成功调用后，可以假定以下必需的属性，或任何其他已设置的表单：</span><span class="sxs-lookup"><span data-stu-id="f3119-131">After you have made a successful call to **InitNew**, you can assume that the following required properties, and no others, have been set for the form:</span></span>
  
 <span data-ttu-id="f3119-132">**PR_DELETE_AFTER_SUBMIT**([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f3119-132">**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))</span></span>
  
 <span data-ttu-id="f3119-133">**PR_IMPORTANCE**([PidTagImportance](pidtagimportance-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f3119-133">**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md))</span></span>
  
 <span data-ttu-id="f3119-134">**邮件已被阅读**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f3119-134">**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))</span></span>
  
 <span data-ttu-id="f3119-135">**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f3119-135">**PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md))</span></span>
  
 <span data-ttu-id="f3119-136">**PR_READ_RECEIPT_REQUESTED**([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f3119-136">**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))</span></span>
  
 <span data-ttu-id="f3119-137">**PR_SENSITIVITY**([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f3119-137">**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span></span>
  
 <span data-ttu-id="f3119-138">**PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f3119-138">**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span></span>
  
<span data-ttu-id="f3119-139">有关窗体的状态的详细信息，请参阅[窗体状态](form-states.md)。</span><span class="sxs-lookup"><span data-stu-id="f3119-139">For more information about the states of forms, see [Form States](form-states.md).</span></span> <span data-ttu-id="f3119-140">有关如何初始化存储对象的详细信息，请参阅[IPersistStorage::InitNew](http://msdn.microsoft.com/library/79caf1f6-d974-4aee-8563-eda4876a0a90%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="f3119-140">For more information about how storage objects are initialized, see the [IPersistStorage::InitNew](http://msdn.microsoft.com/library/79caf1f6-d974-4aee-8563-eda4876a0a90%28Office.15%29.aspx) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f3119-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3119-141">See also</span></span>



[<span data-ttu-id="f3119-142">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f3119-142">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

