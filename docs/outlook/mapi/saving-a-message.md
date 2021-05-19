---
title: 保存邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 97bff16b-dc7c-4eed-8834-d0c076d83ca3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d5ceeb46bded101700aec696a17d690bde80ce6d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420928"
---
# <a name="saving-a-message"></a><span data-ttu-id="c0fd0-103">保存邮件</span><span class="sxs-lookup"><span data-stu-id="c0fd0-103">Saving a Message</span></span>

  
  
<span data-ttu-id="c0fd0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c0fd0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c0fd0-105">在保存邮件之前，客户端通常调用邮件的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来设置邮件文本属性、附件属性 **、PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 以及与收件人列表关联的属性。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-105">Before a message is saved, clients typically call the message's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set a few properties in addition to the message text properties, attachment properties, **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)), and properties associated with the recipient list.</span></span>
  
<span data-ttu-id="c0fd0-106">将 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性设置为字符串（如 IPM）。请注意，描述传出邮件的类。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-106">Set the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property to a character string such as IPM.Note that describes the class of the outgoing message.</span></span> <span data-ttu-id="c0fd0-107">尽管客户端应 **PR_MESSAGE_CLASS** 所有传出邮件设置默认值，但是如果未设置，则由邮件存储提供程序提供默认值。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-107">Although clients should set **PR_MESSAGE_CLASS** on all outgoing messages, a default value is supplied by the message store provider if you do not set it.</span></span> <span data-ttu-id="c0fd0-108">传出邮件的默认邮件类别为 IPM。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-108">The default message class for outgoing messages is IPM.</span></span> 
  
<span data-ttu-id="c0fd0-109">设置 MSGFLAG_UNSENT [PidTagMessageFlags](pidtagmessageflags-canonical-property.md) PR_MESSAGE_FLAGS (标记) 标记。 </span><span class="sxs-lookup"><span data-stu-id="c0fd0-109">Set the MSGFLAG_UNSENT flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="c0fd0-110">如果需要，还要设置MSGFLAG_READ和MSGFLAG_UNMODIFIED标志。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-110">If desired, also set the MSGFLAG_READ and MSGFLAG_UNMODIFIED flags.</span></span> <span data-ttu-id="c0fd0-111">设置MSGFLAG_UNMODIFIED允许组合下的邮件模拟传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-111">Setting the MSGFLAG_UNMODIFIED allows a message under composition to simulate a delivered message.</span></span> <span data-ttu-id="c0fd0-112">MSGFLAG_UNMODIFIED第一次保存邮件之前，客户端才能设置该设置。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-112">MSGFLAG_UNMODIFIED can only be set by clients before a message has been saved for the first time.</span></span> 
  
<span data-ttu-id="c0fd0-113">准备好制作未发送邮件的永久副本时，请对邮件及其所有附件调用[IMAPIProp：：SaveChanges。](imapiprop-savechanges.md)</span><span class="sxs-lookup"><span data-stu-id="c0fd0-113">When you are ready to make a permanent copy of an unsent message, call [IMAPIProp::SaveChanges](imapiprop-savechanges.md) on the message and all of its attachments.</span></span> <span data-ttu-id="c0fd0-114">如果打算立即发送邮件，则无需调用 **SaveChanges**。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-114">If you intend to send the message right away, you do not need to call **SaveChanges**.</span></span> <span data-ttu-id="c0fd0-115">调用 **SubmitMessage** 会将邮件保存为邮件处理的一部分。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-115">The call to **SubmitMessage** internally saves the message as part of its processing.</span></span> 
  
<span data-ttu-id="c0fd0-116">调用 **SaveChanges** 时，建议指定 KEEP_OPEN_READWRITE 标记，以允许在以后修改邮件。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-116">When calling **SaveChanges**, it is a good idea to specify the KEEP_OPEN_READWRITE flag, which allows the message to be modified at a later time.</span></span> <span data-ttu-id="c0fd0-117">其他可设置的标志包括 FORCE_SAVE（指示提交更改后应关闭邮件或附件）和 KEEP_OPEN_READONLY（指示不会进行进一步更改）和用于允许邮件存储提供程序批处理客户端请求的标志 MAPI_DEFERRED_ERRORS。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-117">Other settable flags include FORCE_SAVE, which indicates that the message or attachment should be closed after changes are committed, KEEP_OPEN_READONLY, which indicates that no further changes will be made, and the flag to allow the message store provider to batch client requests, MAPI_DEFERRED_ERRORS.</span></span>
  
<span data-ttu-id="c0fd0-118">为邮件调用 **SaveChanges** 之前，必须针对邮件中每个附件调用 **SaveChanges。**</span><span class="sxs-lookup"><span data-stu-id="c0fd0-118">It is essential that you call **SaveChanges** for every attachment in the message before you call **SaveChanges** for the message.</span></span> <span data-ttu-id="c0fd0-119">如果无法保存附件，则邮件发送时不会包含附件，并且附件不会显示在邮件的附件表中。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-119">If you fail to save an attachment, the attachment will not be included with the message when it is sent and it will not appear in the message's attachment table.</span></span> <span data-ttu-id="c0fd0-120">如果在保存所有附件后无法保存邮件，邮件和附件都将丢失。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-120">If you fail to save the message after saving all of the attachments, both the message and the attachments will be lost.</span></span> 
  
<span data-ttu-id="c0fd0-121">调用 **SaveChanges** 时，邮件存储提供程序将更新以下属性：</span><span class="sxs-lookup"><span data-stu-id="c0fd0-121">When **SaveChanges** is called, the message store provider updates the following properties:</span></span> 
  
- <span data-ttu-id="c0fd0-122">**PR_DISPLAY_TO (** [PidTagDisplayTo)](pidtagdisplayto-canonical-property.md) 列出所有主收件人。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-122">**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) lists all primary recipients.</span></span>
    
- <span data-ttu-id="c0fd0-123">**PR_DISPLAY_TO** 列出所有抄稿收件人。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-123">**PR_DISPLAY_TO** lists all carbon copy recipients.</span></span> 
    
- <span data-ttu-id="c0fd0-124">**PR_DISPLAY_BCC (** [PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 列出所有抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-124">**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) lists all blind carbon copy recipients.</span></span>
    
- <span data-ttu-id="c0fd0-125">**PR_LAST_MODIFICATION_TIME (** [PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c0fd0-125">**PR_LAST_MODIFICATION_TIME** ([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="c0fd0-126">**PR_MESSAGE_FLAGS** 设置MSGFLAG_HASATTACH一个或多个附件，并清除MSGFLAG_UNMODIFIED显示邮件已更改的附件。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-126">**PR_MESSAGE_FLAGS** sets MSGFLAG_HASATTACH if one or more attachments have been saved and clears MSGFLAG_UNMODIFIED to show the message has changed.</span></span> 
    
- <span data-ttu-id="c0fd0-127">**PR_MESSAGE_SIZE (** [PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 包含邮件的当前大小。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-127">**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) contains the most current size of the message.</span></span>
    
- <span data-ttu-id="c0fd0-128">**PR_MESSAGE_ATTACHMENTS (** [PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 提供对附件表的访问。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-128">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) provides access to the attachment table.</span></span>
    
- <span data-ttu-id="c0fd0-129">**PR_MESSAGE_RECIPIENTS (** [PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 提供对收件人表的访问。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-129">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) provides access to the recipient table.</span></span>
    
<span data-ttu-id="c0fd0-130">一些邮件属性通常由客户端或服务提供商在邮件创建时提供。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-130">Some message properties are typically supplied by clients or service providers when a message is created.</span></span> <span data-ttu-id="c0fd0-131">如果客户端没有设置它们，则由消息存储提供程序在调用 **SaveChanges** 时更新它们。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-131">If a client neglects to set them, it is up to the message store provider to update them at the time **SaveChanges** is called.</span></span> <span data-ttu-id="c0fd0-132">例如，如果在创建邮件时设置了邮件的 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性，则无需在保存时修改这些属性。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-132">For example, if a message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) and **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) properties were set when the message was created, they need not be modified at save time.</span></span> <span data-ttu-id="c0fd0-133">但是，在邮件创建时忽略设置它们的邮件存储提供程序必须在首次调用 **SaveChanges 时** 设置它们。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-133">However, message store providers that neglect to set them at message creation must set them the first time that **SaveChanges** is called.</span></span> 
  
<span data-ttu-id="c0fd0-134">如果 **SaveChanges** 返回MAPI_E_CORRUPT_DATA，则假定正在保存的数据现已丢失。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-134">If **SaveChanges** returns MAPI_E_CORRUPT_DATA, assume that the data being saved is now lost.</span></span> <span data-ttu-id="c0fd0-135">当网络连接丢失或服务器未运行时，使用客户端-服务器模型实现的消息存储提供程序可能会返回此值。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-135">Message store providers that use a client-server model for their implementation might return this value when a network connection is lost or the server is not running.</span></span> <span data-ttu-id="c0fd0-136">在向用户返回错误之前，尝试再次写入并保存数据，方法为调用 **SetProps，** 然后再次调用 **SaveChanges**。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-136">Before returning an error to the user, try to write and save the data a second time by making a call to **SetProps** followed by another call to **SaveChanges**.</span></span> <span data-ttu-id="c0fd0-137">如果在本地缓存数据，这应该不会是问题。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-137">If the data is cached locally, this should not be a problem.</span></span> <span data-ttu-id="c0fd0-138">但是，如果没有本地缓存或第二个 **SaveChanges** 调用失败，则显示一个错误以提醒用户该问题。</span><span class="sxs-lookup"><span data-stu-id="c0fd0-138">However, if there is no local cache or the second **SaveChanges** call fails, display an error to alert the user to the problem.</span></span> 
  

