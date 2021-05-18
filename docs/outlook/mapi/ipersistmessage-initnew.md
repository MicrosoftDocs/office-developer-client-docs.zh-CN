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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9f70b178e7c30e1cdf94b485c77f80374113211c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317148"
---
# <a name="ipersistmessageinitnew"></a><span data-ttu-id="3712d-103">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="3712d-103">IPersistMessage::InitNew</span></span>

  
  
<span data-ttu-id="3712d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3712d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3712d-105">初始化新邮件。</span><span class="sxs-lookup"><span data-stu-id="3712d-105">Initializes a new message.</span></span>
  
```cpp
HRESULT InitNew(
  LPMAPIMESSAGESITE pMessageSite,
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a><span data-ttu-id="3712d-106">参数</span><span class="sxs-lookup"><span data-stu-id="3712d-106">Parameters</span></span>

 <span data-ttu-id="3712d-107">_pMessageSite_</span><span class="sxs-lookup"><span data-stu-id="3712d-107">_pMessageSite_</span></span>
  
> <span data-ttu-id="3712d-108">[in]指向表单用于处理查看器中邮件的消息网站的指针。</span><span class="sxs-lookup"><span data-stu-id="3712d-108">[in] A pointer to the message site that the form will use to work with the message in the viewer.</span></span>
    
 <span data-ttu-id="3712d-109">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="3712d-109">_pMessage_</span></span>
  
> <span data-ttu-id="3712d-110">[in]指向新邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="3712d-110">[in] A pointer to the new message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3712d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="3712d-111">Return value</span></span>

<span data-ttu-id="3712d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3712d-112">S_OK</span></span> 
  
> <span data-ttu-id="3712d-113">已成功初始化新邮件。</span><span class="sxs-lookup"><span data-stu-id="3712d-113">The new message was successfully initialized.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3712d-114">备注</span><span class="sxs-lookup"><span data-stu-id="3712d-114">Remarks</span></span>

<span data-ttu-id="3712d-115">当用户写入属于表单处理的邮件类的新邮件时，表单查看者将调用 **IPersistMessage：：InitNew** 方法。</span><span class="sxs-lookup"><span data-stu-id="3712d-115">Form viewers call the **IPersistMessage::InitNew** method when the user writes a new message that belongs to a message class that the form handles.</span></span> <span data-ttu-id="3712d-116">如果窗体对象具有有效的用户界面指针，应显示消息对象的用户界面。</span><span class="sxs-lookup"><span data-stu-id="3712d-116">If the form object has a valid user interface pointer, the user interface for the message object should be displayed.</span></span> 
  
 <span data-ttu-id="3712d-117">当表单除未初始化状态之外的任何状态时，不应调用 **InitNew。** [](uninitialized-state.md)</span><span class="sxs-lookup"><span data-stu-id="3712d-117">**InitNew** should not be called when your form is in any state except the [Uninitialized](uninitialized-state.md) state.</span></span> <span data-ttu-id="3712d-118">如果调用 **InitNew** 时窗体位于其他状态之一，则返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="3712d-118">If the form is in one of the other states when **InitNew** is called, return E_UNEXPECTED.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="3712d-119">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="3712d-119">Notes to implementers</span></span>

<span data-ttu-id="3712d-120">通常，将具有未保存属性的邮件标记为已修改，以便客户端可以显示一个对话框，提示用户是否应该保存这些属性。</span><span class="sxs-lookup"><span data-stu-id="3712d-120">Typically, messages that have unsaved properties are marked as modified so that the client can display a dialog box that prompts the user whether these properties should be saved.</span></span> <span data-ttu-id="3712d-121">如果用户指示应保存邮件，请保存数据，将邮件标记为干净并正常退出。</span><span class="sxs-lookup"><span data-stu-id="3712d-121">If the user indicates that a message should be saved, save the data, mark the message as clean, and exit normally.</span></span>
  
<span data-ttu-id="3712d-122">但是，如果对新初始化的邮件的处理包括设置一个或多个计算属性，并且保存这些属性非常重要，请不要将邮件标记为已修改。</span><span class="sxs-lookup"><span data-stu-id="3712d-122">However, if processing for your newly initialized messages includes setting one or more computed properties, and it is important for those properties to be saved, do not mark the messages as modified.</span></span> <span data-ttu-id="3712d-123">由于计算的属性应该对用户不可见，因此不应显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="3712d-123">Because computed properties should be invisible to users, no dialog box should be displayed.</span></span>
  
<span data-ttu-id="3712d-124">如果您的表单具有对传入 **InitNew** 的活动邮件网站的引用，请释放原始网站，因为它将不再使用。</span><span class="sxs-lookup"><span data-stu-id="3712d-124">If your form has a reference to an active message site other than the one that is passed into **InitNew**, release the original site because it will no longer be used.</span></span> <span data-ttu-id="3712d-125">从  _pMessageSite_ 和  _pMessage_ 参数存储指向邮件网站和邮件的指针，并调用这两个对象的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) 方法来增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="3712d-125">Store the pointers to the message site and message from the  _pMessageSite_ and  _pMessage_ parameters and call both objects' [IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) methods to increment their reference counts.</span></span> 
  
<span data-ttu-id="3712d-126">将 **新邮件** 的 PR_MESSAGE_FLAGS ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性设置为适用于邮件类的信息。</span><span class="sxs-lookup"><span data-stu-id="3712d-126">Set the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) and **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) properties for the new message to something appropriate for your message class.</span></span> <span data-ttu-id="3712d-127">例如，许多邮件类 **将PR_MESSAGE_FLAGS设置为** MSGFLAG_UNSENT的新邮件。</span><span class="sxs-lookup"><span data-stu-id="3712d-127">Many message classes, for example, set **PR_MESSAGE_FLAGS** to MSGFLAG_UNSENT for new messages.</span></span> 
  
<span data-ttu-id="3712d-128">在返回之前，如果未发生错误，将窗体转换为 [Normal](normal-state.md) 状态。</span><span class="sxs-lookup"><span data-stu-id="3712d-128">Before returning, transition the form to the [Normal](normal-state.md) state if no errors have occurred.</span></span> <span data-ttu-id="3712d-129">通过调用所有注册的查看者 [IMAPIViewAdviseSink：：OnNewMessage](imapiviewadvisesink-onnewmessage.md) 方法并返回新消息S_OK。</span><span class="sxs-lookup"><span data-stu-id="3712d-129">Send a new message notification to all registered viewers by calling their [IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md) methods and return S_OK.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3712d-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3712d-130">Notes to callers</span></span>

<span data-ttu-id="3712d-131">成功调用 **InitNew** 后，可以假定为表单设置了以下必需属性，而未设置其他属性：</span><span class="sxs-lookup"><span data-stu-id="3712d-131">After you have made a successful call to **InitNew**, you can assume that the following required properties, and no others, have been set for the form:</span></span>
  
 <span data-ttu-id="3712d-132">**PR_DELETE_AFTER_SUBMIT (** [PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="3712d-132">**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))</span></span>
  
 <span data-ttu-id="3712d-133">**PR_IMPORTANCE (** [PidTagImportance)](pidtagimportance-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="3712d-133">**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md))</span></span>
  
 <span data-ttu-id="3712d-134">**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED (** [PidTagOriginatorDeliveryReportRequested)](pidtagoriginatordeliveryreportrequested-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="3712d-134">**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))</span></span>
  
 <span data-ttu-id="3712d-135">**PR_PRIORITY (** [PidTagPriority)](pidtagpriority-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="3712d-135">**PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md))</span></span>
  
 <span data-ttu-id="3712d-136">**PR_READ_RECEIPT_REQUESTED (** [PidTagReadReceiptRequested)](pidtagreadreceiptrequested-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="3712d-136">**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))</span></span>
  
 <span data-ttu-id="3712d-137">**PR_SENSITIVITY (** [PidTagSensitivity)](pidtagsensitivity-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="3712d-137">**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span></span>
  
 <span data-ttu-id="3712d-138">**PR_SENTMAIL_ENTRYID (** [PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="3712d-138">**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span></span>
  
<span data-ttu-id="3712d-139">有关表单状态的信息，请参阅窗体 [状态](form-states.md)。</span><span class="sxs-lookup"><span data-stu-id="3712d-139">For more information about the states of forms, see [Form States](form-states.md).</span></span> <span data-ttu-id="3712d-140">有关存储对象的初始化方式详细信息，请参阅 [IPersistStorage：：InitNew](https://msdn.microsoft.com/library/79caf1f6-d974-4aee-8563-eda4876a0a90%28Office.15%29.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="3712d-140">For more information about how storage objects are initialized, see the [IPersistStorage::InitNew](https://msdn.microsoft.com/library/79caf1f6-d974-4aee-8563-eda4876a0a90%28Office.15%29.aspx) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3712d-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3712d-141">See also</span></span>



[<span data-ttu-id="3712d-142">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3712d-142">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

