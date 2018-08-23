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
ms.openlocfilehash: c5f136a0d26b7519bc1b7b3d8f448f5f382767ad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591252"
---
# <a name="outgoing-queue-tables"></a><span data-ttu-id="ed930-103">传出队列表</span><span class="sxs-lookup"><span data-stu-id="ed930-103">Outgoing Queue Tables</span></span>

  
  
<span data-ttu-id="ed930-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed930-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ed930-105">传出的队列表包含有关邮件存储区的所有传出邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="ed930-105">An outgoing queue table contains information about all the outgoing messages for a message store.</span></span> <span data-ttu-id="ed930-106">消息存储提供程序实现 MAPI 后台处理程序使用的传出队列的表。</span><span class="sxs-lookup"><span data-stu-id="ed930-106">Message store providers implement outgoing queue tables for the MAPI spooler to use.</span></span> <span data-ttu-id="ed930-107">存储区不支持发送或接收的消息不需要实现此表。</span><span class="sxs-lookup"><span data-stu-id="ed930-107">Stores that do not support the sending or receiving of messages need not implement this table.</span></span> 
  
<span data-ttu-id="ed930-108">若要访问传出队列表，MAPI 后台处理程序调用[IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ed930-108">To access an outgoing queue table, the MAPI spooler calls the [IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md) method.</span></span> 
  
<span data-ttu-id="ed930-109">没有邮件预处理，如它们发送的客户端应用程序提交到传输提供程序的顺序的要求。</span><span class="sxs-lookup"><span data-stu-id="ed930-109">There is a requirement that messages be preprocessed and submitted to the transport provider in the same order as they were sent by the client application.</span></span> <span data-ttu-id="ed930-110">MAPI 后台处理程序旨在接受来自提交时间的升序顺序的消息存储的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed930-110">The MAPI spooler is designed to accept messages from the message store in ascending order of submission time.</span></span> <span data-ttu-id="ed930-111">由于此要求，可能会有一些延迟之前传出队列表中显示的某些消息。</span><span class="sxs-lookup"><span data-stu-id="ed930-111">Because of this requirement, there can be some delay before some messages appear in the outgoing queue table.</span></span> 
  
<span data-ttu-id="ed930-112">消息存储也应允许传出队列表进行排序，以便 MAPI 后台处理程序可以由提交时间排序邮件或默认的排序顺序应为按升序排序提交时间。</span><span class="sxs-lookup"><span data-stu-id="ed930-112">Message stores should either allow sorting on the outgoing queue table so that the MAPI spooler can sort the messages by submission time, or the default sort order should be by ascending submission time.</span></span> 
  
<span data-ttu-id="ed930-113">队列的内容更改时，必须将传出队列表发送通知。</span><span class="sxs-lookup"><span data-stu-id="ed930-113">The outgoing queue table must send notifications when the contents of the queue changes.</span></span>
  
<span data-ttu-id="ed930-114">以下属性构成传出队列表中所需的列：</span><span class="sxs-lookup"><span data-stu-id="ed930-114">The following properties make up the required column set in outgoing queue tables:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ed930-115">**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-115">**PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ed930-116">**PR_DISPLAY_BCC**([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-116">**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="ed930-117">**PR_DISPLAY_CC**([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-117">**PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ed930-118">**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-118">**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="ed930-119">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-119">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ed930-120">**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-120">**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="ed930-121">**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-121">**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ed930-122">**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-122">**PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="ed930-123">**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-123">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ed930-124">**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-124">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="ed930-125">**PR_SUBMIT_FLAGS**([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ed930-125">**PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md))</span></span>  <br/> | <br/> |
   
<span data-ttu-id="ed930-126">有关如何使用传出队列表的详细信息，请参阅[通过使用消息存储提供程序发送的邮件](sending-messages-by-using-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="ed930-126">For more information about how the outgoing queue table is used, see [Sending Messages by Using Message Store Providers](sending-messages-by-using-message-store-providers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ed930-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed930-127">See also</span></span>



[<span data-ttu-id="ed930-128">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="ed930-128">MAPI Tables</span></span>](mapi-tables.md)

