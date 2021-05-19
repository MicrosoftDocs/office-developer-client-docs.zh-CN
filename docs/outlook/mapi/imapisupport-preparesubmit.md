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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 738eb346ec5388cbd94b32598236ef2ca05740f3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425734"
---
# <a name="imapisupportpreparesubmit"></a><span data-ttu-id="5600d-103">IMAPISupport::PrepareSubmit</span><span class="sxs-lookup"><span data-stu-id="5600d-103">IMAPISupport::PrepareSubmit</span></span>

  
  
<span data-ttu-id="5600d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5600d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5600d-105">准备消息以提交到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="5600d-105">Prepares a message for submission to the MAPI spooler.</span></span>
  
```cpp
HRESULT PrepareSubmit(
LPMESSAGE lpMessage,
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="5600d-106">参数</span><span class="sxs-lookup"><span data-stu-id="5600d-106">Parameters</span></span>

 <span data-ttu-id="5600d-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="5600d-107">_lpMessage_</span></span>
  
> <span data-ttu-id="5600d-108">[in]指向要准备的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="5600d-108">[in] A pointer to the message to prepare.</span></span>
    
 <span data-ttu-id="5600d-109">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="5600d-109">_lpulFlags_</span></span>
  
> <span data-ttu-id="5600d-110">[in， out]输入时  _，保留 lpulFlags_ 参数，并且必须为零。</span><span class="sxs-lookup"><span data-stu-id="5600d-110">[in, out] On input, the  _lpulFlags_ parameter is reserved and must be zero.</span></span> <span data-ttu-id="5600d-111">在输出时  _，lpulFlags_ 必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5600d-111">On output,  _lpulFlags_ must be NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5600d-112">返回值</span><span class="sxs-lookup"><span data-stu-id="5600d-112">Return value</span></span>

<span data-ttu-id="5600d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5600d-113">S_OK</span></span> 
  
> <span data-ttu-id="5600d-114">邮件已成功准备。</span><span class="sxs-lookup"><span data-stu-id="5600d-114">The message was successfully prepared.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5600d-115">备注</span><span class="sxs-lookup"><span data-stu-id="5600d-115">Remarks</span></span>

<span data-ttu-id="5600d-116">**IMAPISupport：:P repareSubmit** 方法为邮件存储提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="5600d-116">The **IMAPISupport::PrepareSubmit** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="5600d-117">邮件存储提供程序在 [IMessage：：SubmitMessage](imessage-submitmessage.md)方法的实现中调用 **PrepareSubmit，** 以准备邮件以提交到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="5600d-117">Message store providers call **PrepareSubmit** in their implementation of the [IMessage::SubmitMessage](imessage-submitmessage.md) method to prepare a message for submission to the MAPI spooler.</span></span> 
  
 <span data-ttu-id="5600d-118">**PrepareSubmit** 用于处理在 [PidTagMessageFlags](pidtagmessageflags-canonical-property.md) PR_MESSAGE_FLAGS (属性中设置了 **MSGFLAG_RESEND** 标志) 的邮件。</span><span class="sxs-lookup"><span data-stu-id="5600d-118">**PrepareSubmit** is used to handle messages that have the MSGFLAG_RESEND flag set in their **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="5600d-119">MSGFLAG_RESEND包括初始传输失败时要重新发送的请求的邮件，则设置此设置。</span><span class="sxs-lookup"><span data-stu-id="5600d-119">MSGFLAG_RESEND is set for messages that include a request to be resent when an initial transmission fails.</span></span> <span data-ttu-id="5600d-120">**PrepareSubmit** 确定收件人列表中的哪些收件人已成功收到邮件，哪些收件人未收到邮件。</span><span class="sxs-lookup"><span data-stu-id="5600d-120">**PrepareSubmit** determines which of the recipients in the recipient list successfully received the message and which did not.</span></span> 
  
<span data-ttu-id="5600d-121">若要访问收件人列表 **，PrepareSubmit** 将调用邮件的 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="5600d-121">To access the recipient list, **PrepareSubmit** calls the message's [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method.</span></span> <span data-ttu-id="5600d-122">若要检索收件人数据 **，PrepareSubmit** 将调用收件人表的 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="5600d-122">To retrieve the recipient data, **PrepareSubmit** calls the recipient table's [IMAPITable::QueryRows](imapitable-queryrows.md) method.</span></span> <span data-ttu-id="5600d-123">对于表中的每一行 **，PrepareSubmit** 将检查PR_RECIPIENT_TYPE ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性，并执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="5600d-123">For each row in the table, **PrepareSubmit** checks the **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property and takes one of the following actions:</span></span>
  
- <span data-ttu-id="5600d-124">如果 **MAPI_SUBMITTED，PrepareSubmit** 将清除该标志，PR_RESPONSIBILITY ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 设置为 FALSE。 </span><span class="sxs-lookup"><span data-stu-id="5600d-124">If the MAPI_SUBMITTED flag is set, **PrepareSubmit** clears the flag and sets the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property to FALSE.</span></span>
    
- <span data-ttu-id="5600d-125">如果未设置MAPI_SUBMITTED，**则 PrepareSubmit\*\*\*\*更改PR_RECIPIENT_TYPE** 设置为 **MAPI_P1，PR_RESPONSIBILITY** 设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="5600d-125">If the MAPI_SUBMITTED flag is not set, **PrepareSubmit** changes **PR_RECIPIENT_TYPE** to MAPI_P1 and sets **PR_RESPONSIBILITY** to TRUE.</span></span> 
    
## <a name="notes-to-callers"></a><span data-ttu-id="5600d-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5600d-126">Notes to callers</span></span>

<span data-ttu-id="5600d-127">在调用 **PrepareSubmit** 之前，请确保已调用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法，并设置  _ulFlags_ 参数中的 NOTIFY_READYTOSEND 标志。</span><span class="sxs-lookup"><span data-stu-id="5600d-127">Before you call **PrepareSubmit**, be sure you have called the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method and set the NOTIFY_READYTOSEND flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="5600d-128">在调用 **PrepareSubmit** 之前，必须每个会话进行一次 **SpoolerNotify** 调用。</span><span class="sxs-lookup"><span data-stu-id="5600d-128">The **SpoolerNotify** call must be made once per session before the call to **PrepareSubmit**.</span></span> <span data-ttu-id="5600d-129">**SpoolerNotify** 同步 MAPI 后台处理程序，并确保已登录所有所需的传输提供程序并注册其地址类型。</span><span class="sxs-lookup"><span data-stu-id="5600d-129">**SpoolerNotify** synchronizes the MAPI spooler and ensures that all needed transport providers are logged on and their address types are registered.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5600d-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5600d-130">See also</span></span>



[<span data-ttu-id="5600d-131">IMAPIFolder::GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="5600d-131">IMAPIFolder::GetMessageStatus</span></span>](imapifolder-getmessagestatus.md)
  
[<span data-ttu-id="5600d-132">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="5600d-132">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="5600d-133">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5600d-133">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

