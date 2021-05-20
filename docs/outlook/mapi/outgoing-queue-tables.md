---
title: 传出队列表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 070377ca-ba9e-42ef-ac6b-ff7548b5ccf5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4bf935f58fb20460bbf6baf4b1434be1f3ab8156
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437572"
---
# <a name="outgoing-queue-tables"></a><span data-ttu-id="fb0d9-103">传出队列表</span><span class="sxs-lookup"><span data-stu-id="fb0d9-103">Outgoing Queue Tables</span></span>

  
  
<span data-ttu-id="fb0d9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb0d9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fb0d9-105">传出队列表包含有关邮件存储的所有传出邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-105">An outgoing queue table contains information about all the outgoing messages for a message store.</span></span> <span data-ttu-id="fb0d9-106">邮件存储提供程序实现传出队列表，供 MAPI 后台处理程序使用。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-106">Message store providers implement outgoing queue tables for the MAPI spooler to use.</span></span> <span data-ttu-id="fb0d9-107">不支持发送或接收邮件的存储区不需要实现此表。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-107">Stores that do not support the sending or receiving of messages need not implement this table.</span></span> 
  
<span data-ttu-id="fb0d9-108">为了访问传出队列表，MAPI 后台处理程序调用 [IMsgStore：：GetOutgoingQueue](imsgstore-getoutgoingqueue.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-108">To access an outgoing queue table, the MAPI spooler calls the [IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md) method.</span></span> 
  
<span data-ttu-id="fb0d9-109">要求对邮件进行预处理，并按客户端应用程序发送的邮件顺序提交给传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-109">There is a requirement that messages be preprocessed and submitted to the transport provider in the same order as they were sent by the client application.</span></span> <span data-ttu-id="fb0d9-110">MAPI 后台处理程序旨在按提交时间升序接受来自邮件存储的邮件。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-110">The MAPI spooler is designed to accept messages from the message store in ascending order of submission time.</span></span> <span data-ttu-id="fb0d9-111">由于此要求，在一些邮件出现在传出队列表中之前，可能会出现一些延迟。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-111">Because of this requirement, there can be some delay before some messages appear in the outgoing queue table.</span></span> 
  
<span data-ttu-id="fb0d9-112">邮件存储应允许对传出队列表进行排序，以便 MAPI 后台处理程序可以按提交时间对邮件进行排序，或者默认排序顺序应为按升序提交时间。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-112">Message stores should either allow sorting on the outgoing queue table so that the MAPI spooler can sort the messages by submission time, or the default sort order should be by ascending submission time.</span></span> 
  
<span data-ttu-id="fb0d9-113">传出队列表必须在队列内容更改时发送通知。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-113">The outgoing queue table must send notifications when the contents of the queue changes.</span></span>
  
<span data-ttu-id="fb0d9-114">以下属性将包含传出队列表中所需的列集：</span><span class="sxs-lookup"><span data-stu-id="fb0d9-114">The following properties make up the required column set in outgoing queue tables:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fb0d9-115">**PR_CLIENT_SUBMIT_TIME (** [PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-115">**PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="fb0d9-116">**PR_DISPLAY_BCC (** [PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-116">**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="fb0d9-117">**PR_DISPLAY_CC (** [PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-117">**PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="fb0d9-118">**PR_DISPLAY_TO (** [PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-118">**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="fb0d9-119">**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-119">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="fb0d9-120">**PR_MESSAGE_FLAGS (** [PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-120">**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="fb0d9-121">**PR_MESSAGE_SIZE (** [PidTagMessageSize](pidtagmessagesize-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-121">**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="fb0d9-122">**PR_PRIORITY (** [PidTagPriority)](pidtagpriority-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="fb0d9-122">**PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="fb0d9-123">**PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-123">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="fb0d9-124">**PR_SUBJECT (** [PidTagSubject)](pidtagsubject-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="fb0d9-124">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="fb0d9-125">**PR_SUBMIT_FLAGS (** [PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-125">**PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md))</span></span>  <br/> | <br/> |
   
<span data-ttu-id="fb0d9-126">有关如何使用传出队列表的信息，请参阅使用邮件存储提供程序 [发送邮件](sending-messages-by-using-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-126">For more information about how the outgoing queue table is used, see [Sending Messages by Using Message Store Providers](sending-messages-by-using-message-store-providers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fb0d9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb0d9-127">See also</span></span>



[<span data-ttu-id="fb0d9-128">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="fb0d9-128">MAPI Tables</span></span>](mapi-tables.md)

