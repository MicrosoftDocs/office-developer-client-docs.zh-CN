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
# <a name="ipersistmessageinitnew"></a><span data-ttu-id="3299f-103">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="3299f-103">IPersistMessage::InitNew</span></span>

  
  
<span data-ttu-id="3299f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3299f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3299f-105">初始化新邮件。</span><span class="sxs-lookup"><span data-stu-id="3299f-105">Initializes a new message.</span></span>
  
```cpp
HRESULT InitNew(
  LPMAPIMESSAGESITE pMessageSite,
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a><span data-ttu-id="3299f-106">参数</span><span class="sxs-lookup"><span data-stu-id="3299f-106">Parameters</span></span>

 <span data-ttu-id="3299f-107">_pMessageSite_</span><span class="sxs-lookup"><span data-stu-id="3299f-107">_pMessageSite_</span></span>
  
> <span data-ttu-id="3299f-108">实时一个指针, 指向表单将用于处理查看器中的邮件的邮件网站。</span><span class="sxs-lookup"><span data-stu-id="3299f-108">[in] A pointer to the message site that the form will use to work with the message in the viewer.</span></span>
    
 <span data-ttu-id="3299f-109">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="3299f-109">_pMessage_</span></span>
  
> <span data-ttu-id="3299f-110">实时指向新邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="3299f-110">[in] A pointer to the new message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3299f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="3299f-111">Return value</span></span>

<span data-ttu-id="3299f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3299f-112">S_OK</span></span> 
  
> <span data-ttu-id="3299f-113">已成功初始化新邮件。</span><span class="sxs-lookup"><span data-stu-id="3299f-113">The new message was successfully initialized.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3299f-114">注解</span><span class="sxs-lookup"><span data-stu-id="3299f-114">Remarks</span></span>

<span data-ttu-id="3299f-115">表单查看者在用户写入属于表单所处理的邮件类的新邮件时, 调用**IPersistMessage:: InitNew**方法。</span><span class="sxs-lookup"><span data-stu-id="3299f-115">Form viewers call the **IPersistMessage::InitNew** method when the user writes a new message that belongs to a message class that the form handles.</span></span> <span data-ttu-id="3299f-116">如果 form 对象具有有效的用户界面指针, 则应显示 message 对象的用户界面。</span><span class="sxs-lookup"><span data-stu-id="3299f-116">If the form object has a valid user interface pointer, the user interface for the message object should be displayed.</span></span> 
  
 <span data-ttu-id="3299f-117">当窗体处于[未初始化](uninitialized-state.md)状态之外的任何状态时, 不应调用**InitNew** 。</span><span class="sxs-lookup"><span data-stu-id="3299f-117">**InitNew** should not be called when your form is in any state except the [Uninitialized](uninitialized-state.md) state.</span></span> <span data-ttu-id="3299f-118">如果在调用**InitNew**时窗体处于其他状态之一, 则返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="3299f-118">If the form is in one of the other states when **InitNew** is called, return E_UNEXPECTED.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="3299f-119">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="3299f-119">Notes to implementers</span></span>

<span data-ttu-id="3299f-120">通常情况下, 具有未保存属性的邮件将被标记为已修改, 以便客户端可以显示一个对话框, 提示用户是否应保存这些属性。</span><span class="sxs-lookup"><span data-stu-id="3299f-120">Typically, messages that have unsaved properties are marked as modified so that the client can display a dialog box that prompts the user whether these properties should be saved.</span></span> <span data-ttu-id="3299f-121">如果用户指示应保存某封邮件, 请保存数据, 将邮件标记为 "干净", 并正常退出。</span><span class="sxs-lookup"><span data-stu-id="3299f-121">If the user indicates that a message should be saved, save the data, mark the message as clean, and exit normally.</span></span>
  
<span data-ttu-id="3299f-122">但是, 如果处理新初始化的邮件包括设置一个或多个计算属性, 并且要保存这些属性, 请不要将邮件标记为 "已修改"。</span><span class="sxs-lookup"><span data-stu-id="3299f-122">However, if processing for your newly initialized messages includes setting one or more computed properties, and it is important for those properties to be saved, do not mark the messages as modified.</span></span> <span data-ttu-id="3299f-123">由于计算属性对用户是不可见的, 因此不应显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="3299f-123">Because computed properties should be invisible to users, no dialog box should be displayed.</span></span>
  
<span data-ttu-id="3299f-124">如果您的表单具有对传递到**InitNew**中的活动邮件网站的引用, 请释放原始网站, 因为它将不再使用。</span><span class="sxs-lookup"><span data-stu-id="3299f-124">If your form has a reference to an active message site other than the one that is passed into **InitNew**, release the original site because it will no longer be used.</span></span> <span data-ttu-id="3299f-125">将指针存储到邮件网站和来自_pMessageSite_和_pMessage_参数的消息, 并调用两个对象的[IUnknown:: AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法以增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="3299f-125">Store the pointers to the message site and message from the  _pMessageSite_ and  _pMessage_ parameters and call both objects' [IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) methods to increment their reference counts.</span></span> 
  
<span data-ttu-id="3299f-126">将新邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性设置为适合您的邮件类的内容。</span><span class="sxs-lookup"><span data-stu-id="3299f-126">Set the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) and **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) properties for the new message to something appropriate for your message class.</span></span> <span data-ttu-id="3299f-127">例如, 许多邮件类将**PR_MESSAGE_FLAGS**设置为 MSGFLAG_UNSENT, 以查找新邮件。</span><span class="sxs-lookup"><span data-stu-id="3299f-127">Many message classes, for example, set **PR_MESSAGE_FLAGS** to MSGFLAG_UNSENT for new messages.</span></span> 
  
<span data-ttu-id="3299f-128">返回之前, 如果没有出现任何错误, 则将窗体转换为[正常](normal-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="3299f-128">Before returning, transition the form to the [Normal](normal-state.md) state if no errors have occurred.</span></span> <span data-ttu-id="3299f-129">通过调用[IMAPIViewAdviseSink:: OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法并返回 S_OK, 向所有注册的查看器发送新的邮件通知。</span><span class="sxs-lookup"><span data-stu-id="3299f-129">Send a new message notification to all registered viewers by calling their [IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md) methods and return S_OK.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3299f-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3299f-130">Notes to callers</span></span>

<span data-ttu-id="3299f-131">成功调用**InitNew**后, 可以假定已为表单设置了以下必需属性, 而不是其他属性:</span><span class="sxs-lookup"><span data-stu-id="3299f-131">After you have made a successful call to **InitNew**, you can assume that the following required properties, and no others, have been set for the form:</span></span>
  
 <span data-ttu-id="3299f-132">**PR_DELETE_AFTER_SUBMIT**([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3299f-132">**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))</span></span>
  
 <span data-ttu-id="3299f-133">**PR_IMPORTANCE**([PidTagImportance](pidtagimportance-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3299f-133">**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md))</span></span>
  
 <span data-ttu-id="3299f-134">**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3299f-134">**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))</span></span>
  
 <span data-ttu-id="3299f-135">**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3299f-135">**PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md))</span></span>
  
 <span data-ttu-id="3299f-136">**PR_READ_RECEIPT_REQUESTED**([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3299f-136">**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))</span></span>
  
 <span data-ttu-id="3299f-137">**PR_SENSITIVITY**([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3299f-137">**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span></span>
  
 <span data-ttu-id="3299f-138">**PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3299f-138">**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span></span>
  
<span data-ttu-id="3299f-139">有关窗体状态的详细信息, 请参阅[表单状态](form-states.md)。</span><span class="sxs-lookup"><span data-stu-id="3299f-139">For more information about the states of forms, see [Form States](form-states.md).</span></span> <span data-ttu-id="3299f-140">有关如何初始化存储对象的详细信息, 请参阅[IPersistStorage:: InitNew](https://msdn.microsoft.com/library/79caf1f6-d974-4aee-8563-eda4876a0a90%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="3299f-140">For more information about how storage objects are initialized, see the [IPersistStorage::InitNew](https://msdn.microsoft.com/library/79caf1f6-d974-4aee-8563-eda4876a0a90%28Office.15%29.aspx) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3299f-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3299f-141">See also</span></span>



[<span data-ttu-id="3299f-142">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3299f-142">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

