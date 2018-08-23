---
title: IMAPISupportPrepareSubmit
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.PrepareSubmit
api_type:
- COM
ms.assetid: 467242e3-96c9-4280-9cbc-9ecfe3f279cf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5f45a6457bba738b290d967260bbd34c0f88f93f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595060"
---
# <a name="imapisupportpreparesubmit"></a><span data-ttu-id="9f49f-103">IMAPISupport::PrepareSubmit</span><span class="sxs-lookup"><span data-stu-id="9f49f-103">IMAPISupport::PrepareSubmit</span></span>

  
  
<span data-ttu-id="9f49f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9f49f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9f49f-105">提交到 MAPI 后台处理程序准备一条消息。</span><span class="sxs-lookup"><span data-stu-id="9f49f-105">Prepares a message for submission to the MAPI spooler.</span></span>
  
```cpp
HRESULT PrepareSubmit(
LPMESSAGE lpMessage,
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="9f49f-106">参数</span><span class="sxs-lookup"><span data-stu-id="9f49f-106">Parameters</span></span>

 <span data-ttu-id="9f49f-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="9f49f-107">_lpMessage_</span></span>
  
> <span data-ttu-id="9f49f-108">[in]指向要准备的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="9f49f-108">[in] A pointer to the message to prepare.</span></span>
    
 <span data-ttu-id="9f49f-109">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="9f49f-109">_lpulFlags_</span></span>
  
> <span data-ttu-id="9f49f-110">[传入、 传出]在输入_lpulFlags_参数保留，必须为零。</span><span class="sxs-lookup"><span data-stu-id="9f49f-110">[in, out] On input, the  _lpulFlags_ parameter is reserved and must be zero.</span></span> <span data-ttu-id="9f49f-111">输出， _lpulFlags_必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9f49f-111">On output,  _lpulFlags_ must be NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9f49f-112">返回值</span><span class="sxs-lookup"><span data-stu-id="9f49f-112">Return value</span></span>

<span data-ttu-id="9f49f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f49f-113">S_OK</span></span> 
  
> <span data-ttu-id="9f49f-114">邮件已成功准备好。</span><span class="sxs-lookup"><span data-stu-id="9f49f-114">The message was successfully prepared.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9f49f-115">注解</span><span class="sxs-lookup"><span data-stu-id="9f49f-115">Remarks</span></span>

<span data-ttu-id="9f49f-116">消息存储提供程序支持对象的实现**IMAPISupport::PrepareSubmit**方法。</span><span class="sxs-lookup"><span data-stu-id="9f49f-116">The **IMAPISupport::PrepareSubmit** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="9f49f-117">消息存储提供程序调用**PrepareSubmit**其方法的实现， [IMessage::SubmitMessage](imessage-submitmessage.md) MAPI 后台处理程序提交准备一条消息。</span><span class="sxs-lookup"><span data-stu-id="9f49f-117">Message store providers call **PrepareSubmit** in their implementation of the [IMessage::SubmitMessage](imessage-submitmessage.md) method to prepare a message for submission to the MAPI spooler.</span></span> 
  
 <span data-ttu-id="9f49f-118">**PrepareSubmit**用于处理其**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_RESEND 标志的消息。</span><span class="sxs-lookup"><span data-stu-id="9f49f-118">**PrepareSubmit** is used to handle messages that have the MSGFLAG_RESEND flag set in their **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="9f49f-119">为邮件，其中包括初始传输失败时重新发送的请求设置 MSGFLAG_RESEND。</span><span class="sxs-lookup"><span data-stu-id="9f49f-119">MSGFLAG_RESEND is set for messages that include a request to be resent when an initial transmission fails.</span></span> <span data-ttu-id="9f49f-120">**PrepareSubmit**确定哪些收件人列表中的收件人成功收到邮件，并且其没有。</span><span class="sxs-lookup"><span data-stu-id="9f49f-120">**PrepareSubmit** determines which of the recipients in the recipient list successfully received the message and which did not.</span></span> 
  
<span data-ttu-id="9f49f-121">若要访问的收件人列表， **PrepareSubmit**调用消息的[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9f49f-121">To access the recipient list, **PrepareSubmit** calls the message's [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method.</span></span> <span data-ttu-id="9f49f-122">若要检索的收件人数据， **PrepareSubmit**调用收件人表的[IMAPITable::QueryRows](imapitable-queryrows.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9f49f-122">To retrieve the recipient data, **PrepareSubmit** calls the recipient table's [IMAPITable::QueryRows](imapitable-queryrows.md) method.</span></span> <span data-ttu-id="9f49f-123">对于表中的每一行， **PrepareSubmit**检查**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性，并采用下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="9f49f-123">For each row in the table, **PrepareSubmit** checks the **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property and takes one of the following actions:</span></span>
  
- <span data-ttu-id="9f49f-124">如果设置了 MAPI_SUBMITTED 标志， **PrepareSubmit**清除标志，并将**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="9f49f-124">If the MAPI_SUBMITTED flag is set, **PrepareSubmit** clears the flag and sets the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property to FALSE.</span></span>
    
- <span data-ttu-id="9f49f-125">如果未设置 MAPI_SUBMITTED 标志， **PrepareSubmit** **PR_RECIPIENT_TYPE**变为 MAPI_P1，并将**PR_RESPONSIBILITY**设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9f49f-125">If the MAPI_SUBMITTED flag is not set, **PrepareSubmit** changes **PR_RECIPIENT_TYPE** to MAPI_P1 and sets **PR_RESPONSIBILITY** to TRUE.</span></span> 
    
## <a name="notes-to-callers"></a><span data-ttu-id="9f49f-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9f49f-126">Notes to callers</span></span>

<span data-ttu-id="9f49f-127">在调用**PrepareSubmit**之前，确保您已被调用[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法并将 NOTIFY_READYTOSEND 标志设置_ulFlags_参数中。</span><span class="sxs-lookup"><span data-stu-id="9f49f-127">Before you call **PrepareSubmit**, be sure you have called the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method and set the NOTIFY_READYTOSEND flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="9f49f-128">每次会话**PrepareSubmit**调用之前，必须在进行**SpoolerNotify**呼叫。</span><span class="sxs-lookup"><span data-stu-id="9f49f-128">The **SpoolerNotify** call must be made once per session before the call to **PrepareSubmit**.</span></span> <span data-ttu-id="9f49f-129">**SpoolerNotify**同步 MAPI 后台处理程序，并确保所有所需的传输提供程序的登录和注册其地址类型。</span><span class="sxs-lookup"><span data-stu-id="9f49f-129">**SpoolerNotify** synchronizes the MAPI spooler and ensures that all needed transport providers are logged on and their address types are registered.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9f49f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f49f-130">See also</span></span>



[<span data-ttu-id="9f49f-131">IMAPIFolder::GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="9f49f-131">IMAPIFolder::GetMessageStatus</span></span>](imapifolder-getmessagestatus.md)
  
[<span data-ttu-id="9f49f-132">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="9f49f-132">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="9f49f-133">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9f49f-133">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

