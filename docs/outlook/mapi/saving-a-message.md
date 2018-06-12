---
title: 保存一条消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 97bff16b-dc7c-4eed-8834-d0c076d83ca3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e61a72691309b2ac632b764c0607f5b1e36b291b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778669"
---
# <a name="saving-a-message"></a><span data-ttu-id="29704-103">保存一条消息</span><span class="sxs-lookup"><span data-stu-id="29704-103">Saving a Message</span></span>

  
  
<span data-ttu-id="29704-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="29704-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="29704-105">保存一条消息之前，客户端通常呼叫消息的[IMAPIProp::SetProps](imapiprop-setprops.md)方法，以便设置除了消息文本属性、 附件属性、 **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))，和属性的几个属性收件人列表相关联。</span><span class="sxs-lookup"><span data-stu-id="29704-105">Before a message is saved, clients typically call the message's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set a few properties in addition to the message text properties, attachment properties, **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)), and properties associated with the recipient list.</span></span>
  
<span data-ttu-id="29704-106">设置为字符的字符串，如 IPM **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。请注意，介绍传出消息的类。</span><span class="sxs-lookup"><span data-stu-id="29704-106">Set the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property to a character string such as IPM.Note that describes the class of the outgoing message.</span></span> <span data-ttu-id="29704-107">尽管客户端应该对所有传出邮件设置**PR_MESSAGE_CLASS** ，但如果未设置消息存储提供程序提供默认值。</span><span class="sxs-lookup"><span data-stu-id="29704-107">Although clients should set **PR_MESSAGE_CLASS** on all outgoing messages, a default value is supplied by the message store provider if you do not set it.</span></span> <span data-ttu-id="29704-108">待发邮件的默认邮件类 IPM。</span><span class="sxs-lookup"><span data-stu-id="29704-108">The default message class for outgoing messages is IPM.</span></span> 
  
<span data-ttu-id="29704-109">**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_UNSENT 标志。</span><span class="sxs-lookup"><span data-stu-id="29704-109">Set the MSGFLAG_UNSENT flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="29704-110">如果需要，还要设置 MSGFLAG_READ 和 MSGFLAG_UNMODIFIED 标志。</span><span class="sxs-lookup"><span data-stu-id="29704-110">If desired, also set the MSGFLAG_READ and MSGFLAG_UNMODIFIED flags.</span></span> <span data-ttu-id="29704-111">设置 MSGFLAG_UNMODIFIED 允许在组合下的一条消息以模拟邮件已送达。</span><span class="sxs-lookup"><span data-stu-id="29704-111">Setting the MSGFLAG_UNMODIFIED allows a message under composition to simulate a delivered message.</span></span> <span data-ttu-id="29704-112">之前已首次保存一条消息，则仅可以通过客户端设置 MSGFLAG_UNMODIFIED。</span><span class="sxs-lookup"><span data-stu-id="29704-112">MSGFLAG_UNMODIFIED can only be set by clients before a message has been saved for the first time.</span></span> 
  
<span data-ttu-id="29704-113">当您准备好使永久未发送的邮件的副本时，邮件和附件的所有呼叫[IMAPIProp::SaveChanges](imapiprop-savechanges.md) 。</span><span class="sxs-lookup"><span data-stu-id="29704-113">When you are ready to make a permanent copy of an unsent message, call [IMAPIProp::SaveChanges](imapiprop-savechanges.md) on the message and all of its attachments.</span></span> <span data-ttu-id="29704-114">如果要立即发送消息，您不需要调用**SaveChanges**。</span><span class="sxs-lookup"><span data-stu-id="29704-114">If you intend to send the message right away, you do not need to call **SaveChanges**.</span></span> <span data-ttu-id="29704-115">调用**SubmitMessage**内部将邮件作为其处理的一部分。</span><span class="sxs-lookup"><span data-stu-id="29704-115">The call to **SubmitMessage** internally saves the message as part of its processing.</span></span> 
  
<span data-ttu-id="29704-116">调用**SaveChanges**时, 最好指定 KEEP_OPEN_READWRITE 标志，从而要修改在以后的消息。</span><span class="sxs-lookup"><span data-stu-id="29704-116">When calling **SaveChanges**, it is a good idea to specify the KEEP_OPEN_READWRITE flag, which allows the message to be modified at a later time.</span></span> <span data-ttu-id="29704-117">其他可设置标志包括 FORCE_SAVE，指示提交更改后，应关闭消息或附件、 KEEP_OPEN_READONLY，指示将进行任何进一步的更改，和标志若要允许到的消息存储提供程序批处理客户端请求，MAPI_DEFERRED_ERRORS。</span><span class="sxs-lookup"><span data-stu-id="29704-117">Other settable flags include FORCE_SAVE, which indicates that the message or attachment should be closed after changes are committed, KEEP_OPEN_READONLY, which indicates that no further changes will be made, and the flag to allow the message store provider to batch client requests, MAPI_DEFERRED_ERRORS.</span></span>
  
<span data-ttu-id="29704-118">呼叫**SaveChanges**邮件中的每个附件的邮件的呼叫**SaveChanges**之前至关重要。</span><span class="sxs-lookup"><span data-stu-id="29704-118">It is essential that you call **SaveChanges** for every attachment in the message before you call **SaveChanges** for the message.</span></span> <span data-ttu-id="29704-119">如果您不能将附件保存，附件将不可包含在邮件时，它发送并不会出现在邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="29704-119">If you fail to save an attachment, the attachment will not be included with the message when it is sent and it will not appear in the message's attachment table.</span></span> <span data-ttu-id="29704-120">如果您不能保存邮件的所有附件保存后，邮件及其附件将丢失。</span><span class="sxs-lookup"><span data-stu-id="29704-120">If you fail to save the message after saving all of the attachments, both the message and the attachments will be lost.</span></span> 
  
<span data-ttu-id="29704-121">当调用**SaveChanges**时，消息存储提供程序将更新以下属性：</span><span class="sxs-lookup"><span data-stu-id="29704-121">When **SaveChanges** is called, the message store provider updates the following properties:</span></span> 
  
- <span data-ttu-id="29704-122">**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 列出了所有主收件人。</span><span class="sxs-lookup"><span data-stu-id="29704-122">**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) lists all primary recipients.</span></span>
    
- <span data-ttu-id="29704-123">**仅包含显示名称**列出所有抄送副本收件人。</span><span class="sxs-lookup"><span data-stu-id="29704-123">**PR_DISPLAY_TO** lists all carbon copy recipients.</span></span> 
    
- <span data-ttu-id="29704-124">**PR_DISPLAY_BCC**([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 列出了所有密件抄送副本收件人。</span><span class="sxs-lookup"><span data-stu-id="29704-124">**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) lists all blind carbon copy recipients.</span></span>
    
- <span data-ttu-id="29704-125">**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="29704-125">**PR_LAST_MODIFICATION_TIME** ([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="29704-126">**PR_MESSAGE_FLAGS**设置 MSGFLAG_HASATTACH，如果一个或多个附件已保存，并清除 MSGFLAG_UNMODIFIED 显示消息已经更改。</span><span class="sxs-lookup"><span data-stu-id="29704-126">**PR_MESSAGE_FLAGS** sets MSGFLAG_HASATTACH if one or more attachments have been saved and clears MSGFLAG_UNMODIFIED to show the message has changed.</span></span> 
    
- <span data-ttu-id="29704-127">**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 包含邮件的最新的大小。</span><span class="sxs-lookup"><span data-stu-id="29704-127">**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) contains the most current size of the message.</span></span>
    
- <span data-ttu-id="29704-128">**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 提供对附件表访问。</span><span class="sxs-lookup"><span data-stu-id="29704-128">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) provides access to the attachment table.</span></span>
    
- <span data-ttu-id="29704-129">**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 提供对收件人表访问。</span><span class="sxs-lookup"><span data-stu-id="29704-129">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) provides access to the recipient table.</span></span>
    
<span data-ttu-id="29704-130">创建一条消息时，某些消息属性通常由客户端或服务提供程序中提供。</span><span class="sxs-lookup"><span data-stu-id="29704-130">Some message properties are typically supplied by clients or service providers when a message is created.</span></span> <span data-ttu-id="29704-131">如果客户端在将它们设置，则由**SaveChanges**称为次更新它们的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="29704-131">If a client neglects to set them, it is up to the message store provider to update them at the time **SaveChanges** is called.</span></span> <span data-ttu-id="29704-132">例如，如果设置了一条消息**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性创建邮件时，他们无需修改在节省时间。</span><span class="sxs-lookup"><span data-stu-id="29704-132">For example, if a message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) and **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) properties were set when the message was created, they need not be modified at save time.</span></span> <span data-ttu-id="29704-133">但是，忽略这些设置创建消息的消息存储提供程序必须将它们设置第一次调用**SaveChanges** 。</span><span class="sxs-lookup"><span data-stu-id="29704-133">However, message store providers that neglect to set them at message creation must set them the first time that **SaveChanges** is called.</span></span> 
  
<span data-ttu-id="29704-134">如果**SaveChanges**返回 MAPI_E_CORRUPT_DATA，假定正在保存的数据现在丢失。</span><span class="sxs-lookup"><span data-stu-id="29704-134">If **SaveChanges** returns MAPI_E_CORRUPT_DATA, assume that the data being saved is now lost.</span></span> <span data-ttu-id="29704-135">丢失网络连接时或服务器未运行时，其实现中使用客户端-服务器模型的消息存储提供程序可能会返回此值。</span><span class="sxs-lookup"><span data-stu-id="29704-135">Message store providers that use a client-server model for their implementation might return this value when a network connection is lost or the server is not running.</span></span> <span data-ttu-id="29704-136">向用户返回错误之前, 尝试写入并通过调用**SetProps**跟**SaveChanges**到另一个呼叫到第二次保存的数据。</span><span class="sxs-lookup"><span data-stu-id="29704-136">Before returning an error to the user, try to write and save the data a second time by making a call to **SetProps** followed by another call to **SaveChanges**.</span></span> <span data-ttu-id="29704-137">如果数据缓存在本地，这不应出现问题。</span><span class="sxs-lookup"><span data-stu-id="29704-137">If the data is cached locally, this should not be a problem.</span></span> <span data-ttu-id="29704-138">但是，如果没有本地高速缓存或第二个**SaveChanges**呼叫失败，则显示错误警告的问题的用户。</span><span class="sxs-lookup"><span data-stu-id="29704-138">However, if there is no local cache or the second **SaveChanges** call fails, display an error to alert the user to the problem.</span></span> 
  

