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
# <a name="imapisupportpreparesubmit"></a><span data-ttu-id="8bfbd-103">IMAPISupport::PrepareSubmit</span><span class="sxs-lookup"><span data-stu-id="8bfbd-103">IMAPISupport::PrepareSubmit</span></span>

  
  
<span data-ttu-id="8bfbd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8bfbd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8bfbd-105">准备邮件以提交到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-105">Prepares a message for submission to the MAPI spooler.</span></span>
  
```cpp
HRESULT PrepareSubmit(
LPMESSAGE lpMessage,
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="8bfbd-106">参数</span><span class="sxs-lookup"><span data-stu-id="8bfbd-106">Parameters</span></span>

 <span data-ttu-id="8bfbd-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="8bfbd-107">_lpMessage_</span></span>
  
> <span data-ttu-id="8bfbd-108">实时指向要准备的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-108">[in] A pointer to the message to prepare.</span></span>
    
 <span data-ttu-id="8bfbd-109">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="8bfbd-109">_lpulFlags_</span></span>
  
> <span data-ttu-id="8bfbd-110">[in, out]在输入时, _lpulFlags_参数是保留参数, 并且必须为零。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-110">[in, out] On input, the  _lpulFlags_ parameter is reserved and must be zero.</span></span> <span data-ttu-id="8bfbd-111">在输出时, _lpulFlags_必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-111">On output,  _lpulFlags_ must be NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="8bfbd-112">返回值</span><span class="sxs-lookup"><span data-stu-id="8bfbd-112">Return value</span></span>

<span data-ttu-id="8bfbd-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8bfbd-113">S_OK</span></span> 
  
> <span data-ttu-id="8bfbd-114">邮件已成功准备就绪。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-114">The message was successfully prepared.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8bfbd-115">说明</span><span class="sxs-lookup"><span data-stu-id="8bfbd-115">Remarks</span></span>

<span data-ttu-id="8bfbd-116">**IMAPISupport::P reparesubmit**方法是为邮件存储提供程序支持对象而实现的。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-116">The **IMAPISupport::PrepareSubmit** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="8bfbd-117">邮件存储提供程序在其[IMessage:: SubmitMessage](imessage-submitmessage.md)方法的实现中调用**PrepareSubmit** , 以准备要提交到 MAPI 后台处理程序的邮件。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-117">Message store providers call **PrepareSubmit** in their implementation of the [IMessage::SubmitMessage](imessage-submitmessage.md) method to prepare a message for submission to the MAPI spooler.</span></span> 
  
 <span data-ttu-id="8bfbd-118">**PrepareSubmit**用于处理在其**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置了 MSGFLAG_RESEND 标志的邮件。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-118">**PrepareSubmit** is used to handle messages that have the MSGFLAG_RESEND flag set in their **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="8bfbd-119">MSGFLAG_RESEND 是为包含在初始传输失败时发送的请求的邮件而设置的。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-119">MSGFLAG_RESEND is set for messages that include a request to be resent when an initial transmission fails.</span></span> <span data-ttu-id="8bfbd-120">**PrepareSubmit**确定收件人列表中的哪些收件人已成功接收邮件, 但没有。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-120">**PrepareSubmit** determines which of the recipients in the recipient list successfully received the message and which did not.</span></span> 
  
<span data-ttu-id="8bfbd-121">若要访问收件人列表, **PrepareSubmit**调用邮件的[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-121">To access the recipient list, **PrepareSubmit** calls the message's [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method.</span></span> <span data-ttu-id="8bfbd-122">若要检索收件人数据, **PrepareSubmit**调用收件人表的[IMAPITable:: QueryRows](imapitable-queryrows.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-122">To retrieve the recipient data, **PrepareSubmit** calls the recipient table's [IMAPITable::QueryRows](imapitable-queryrows.md) method.</span></span> <span data-ttu-id="8bfbd-123">对于表中的每一行, **PrepareSubmit**检查**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性并执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="8bfbd-123">For each row in the table, **PrepareSubmit** checks the **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property and takes one of the following actions:</span></span>
  
- <span data-ttu-id="8bfbd-124">如果设置了 MAPI_SUBMITTED 标志, 则**PrepareSubmit**将清除该标志, 并将**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-124">If the MAPI_SUBMITTED flag is set, **PrepareSubmit** clears the flag and sets the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property to FALSE.</span></span>
    
- <span data-ttu-id="8bfbd-125">如果未设置 MAPI_SUBMITTED 标志, 则**PrepareSubmit**会将**PR_RECIPIENT_TYPE**更改为 MAPI_P1 并将**PR_RESPONSIBILITY**设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-125">If the MAPI_SUBMITTED flag is not set, **PrepareSubmit** changes **PR_RECIPIENT_TYPE** to MAPI_P1 and sets **PR_RESPONSIBILITY** to TRUE.</span></span> 
    
## <a name="notes-to-callers"></a><span data-ttu-id="8bfbd-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8bfbd-126">Notes to callers</span></span>

<span data-ttu-id="8bfbd-127">在调用**PrepareSubmit**之前, 请确保您已调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法, 并在_ulFlags_参数中设置 NOTIFY_READYTOSEND 标志。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-127">Before you call **PrepareSubmit**, be sure you have called the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method and set the NOTIFY_READYTOSEND flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="8bfbd-128">在对**PrepareSubmit**的调用之前, 必须为每个会话发出**SpoolerNotify**调用一次。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-128">The **SpoolerNotify** call must be made once per session before the call to **PrepareSubmit**.</span></span> <span data-ttu-id="8bfbd-129">**SpoolerNotify**将同步 MAPI 后台处理程序, 并确保所有需要的传输提供程序均已登录并注册其地址类型。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-129">**SpoolerNotify** synchronizes the MAPI spooler and ensures that all needed transport providers are logged on and their address types are registered.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8bfbd-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bfbd-130">See also</span></span>



[<span data-ttu-id="8bfbd-131">IMAPIFolder::GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="8bfbd-131">IMAPIFolder::GetMessageStatus</span></span>](imapifolder-getmessagestatus.md)
  
[<span data-ttu-id="8bfbd-132">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="8bfbd-132">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="8bfbd-133">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8bfbd-133">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

