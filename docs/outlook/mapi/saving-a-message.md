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
# <a name="saving-a-message"></a><span data-ttu-id="74ab9-103">保存邮件</span><span class="sxs-lookup"><span data-stu-id="74ab9-103">Saving a Message</span></span>

  
  
<span data-ttu-id="74ab9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="74ab9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="74ab9-105">在保存邮件之前, 客户端通常会调用邮件的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法, 以设置除邮件文本属性、附件属性、 **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 和属性之外的一些属性。与收件人列表相关联。</span><span class="sxs-lookup"><span data-stu-id="74ab9-105">Before a message is saved, clients typically call the message's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set a few properties in addition to the message text properties, attachment properties, **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)), and properties associated with the recipient list.</span></span>
  
<span data-ttu-id="74ab9-106">将**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性设置为字符串 (如 IPM.)。请注意, 说明传出邮件的类。</span><span class="sxs-lookup"><span data-stu-id="74ab9-106">Set the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property to a character string such as IPM.Note that describes the class of the outgoing message.</span></span> <span data-ttu-id="74ab9-107">虽然客户端应在所有传出邮件上设置**PR_MESSAGE_CLASS** , 但如果您不设置它, 则邮件存储提供程序将提供默认值。</span><span class="sxs-lookup"><span data-stu-id="74ab9-107">Although clients should set **PR_MESSAGE_CLASS** on all outgoing messages, a default value is supplied by the message store provider if you do not set it.</span></span> <span data-ttu-id="74ab9-108">待发邮件的默认邮件类为 IPM。</span><span class="sxs-lookup"><span data-stu-id="74ab9-108">The default message class for outgoing messages is IPM.</span></span> 
  
<span data-ttu-id="74ab9-109">在**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_UNSENT 标志。</span><span class="sxs-lookup"><span data-stu-id="74ab9-109">Set the MSGFLAG_UNSENT flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="74ab9-110">如果需要, 还可以设置 MSGFLAG_READ 和 MSGFLAG_UNMODIFIED 标志。</span><span class="sxs-lookup"><span data-stu-id="74ab9-110">If desired, also set the MSGFLAG_READ and MSGFLAG_UNMODIFIED flags.</span></span> <span data-ttu-id="74ab9-111">设置 MSGFLAG_UNMODIFIED 允许撰写一封邮件, 以模拟已传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="74ab9-111">Setting the MSGFLAG_UNMODIFIED allows a message under composition to simulate a delivered message.</span></span> <span data-ttu-id="74ab9-112">仅在首次保存邮件之前, 客户端才能设置 MSGFLAG_UNMODIFIED。</span><span class="sxs-lookup"><span data-stu-id="74ab9-112">MSGFLAG_UNMODIFIED can only be set by clients before a message has been saved for the first time.</span></span> 
  
<span data-ttu-id="74ab9-113">当您准备好为未发送的邮件创建永久副本时, 请在邮件及其所有附件上调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md) 。</span><span class="sxs-lookup"><span data-stu-id="74ab9-113">When you are ready to make a permanent copy of an unsent message, call [IMAPIProp::SaveChanges](imapiprop-savechanges.md) on the message and all of its attachments.</span></span> <span data-ttu-id="74ab9-114">如果要立即发送邮件, 则无需调用**SaveChanges**。</span><span class="sxs-lookup"><span data-stu-id="74ab9-114">If you intend to send the message right away, you do not need to call **SaveChanges**.</span></span> <span data-ttu-id="74ab9-115">对**SubmitMessage**的调用会在其处理过程中保存邮件。</span><span class="sxs-lookup"><span data-stu-id="74ab9-115">The call to **SubmitMessage** internally saves the message as part of its processing.</span></span> 
  
<span data-ttu-id="74ab9-116">调用**SaveChanges**时, 最好指定 KEEP_OPEN_READWRITE 标志, 这将允许在以后修改该邮件。</span><span class="sxs-lookup"><span data-stu-id="74ab9-116">When calling **SaveChanges**, it is a good idea to specify the KEEP_OPEN_READWRITE flag, which allows the message to be modified at a later time.</span></span> <span data-ttu-id="74ab9-117">其他可设置的标志包括 FORCE_SAVE, 这表示在提交更改后应关闭邮件或附件, KEEP_OPEN_READONLY (指示不会进行进一步的更改) 以及允许邮件存储提供程序的标志批处理客户端请求, MAPI_DEFERRED_ERRORS。</span><span class="sxs-lookup"><span data-stu-id="74ab9-117">Other settable flags include FORCE_SAVE, which indicates that the message or attachment should be closed after changes are committed, KEEP_OPEN_READONLY, which indicates that no further changes will be made, and the flag to allow the message store provider to batch client requests, MAPI_DEFERRED_ERRORS.</span></span>
  
<span data-ttu-id="74ab9-118">在调用消息的**savechanges**之前, 对邮件中的每个附件调用**savechanges**是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="74ab9-118">It is essential that you call **SaveChanges** for every attachment in the message before you call **SaveChanges** for the message.</span></span> <span data-ttu-id="74ab9-119">如果无法保存附件, 则邮件在发送时不会包含在邮件中, 并且不会显示在邮件的附件表中。</span><span class="sxs-lookup"><span data-stu-id="74ab9-119">If you fail to save an attachment, the attachment will not be included with the message when it is sent and it will not appear in the message's attachment table.</span></span> <span data-ttu-id="74ab9-120">如果保存所有附件后无法保存邮件, 则邮件和附件都将丢失。</span><span class="sxs-lookup"><span data-stu-id="74ab9-120">If you fail to save the message after saving all of the attachments, both the message and the attachments will be lost.</span></span> 
  
<span data-ttu-id="74ab9-121">调用**SaveChanges**时, 邮件存储提供程序将更新以下属性:</span><span class="sxs-lookup"><span data-stu-id="74ab9-121">When **SaveChanges** is called, the message store provider updates the following properties:</span></span> 
  
- <span data-ttu-id="74ab9-122">**PR_DISPLAY_TO**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 列出所有主要收件人。</span><span class="sxs-lookup"><span data-stu-id="74ab9-122">**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) lists all primary recipients.</span></span>
    
- <span data-ttu-id="74ab9-123">**PR_DISPLAY_TO**列出所有抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="74ab9-123">**PR_DISPLAY_TO** lists all carbon copy recipients.</span></span> 
    
- <span data-ttu-id="74ab9-124">**PR_DISPLAY_BCC**([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 列出所有密件抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="74ab9-124">**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) lists all blind carbon copy recipients.</span></span>
    
- <span data-ttu-id="74ab9-125">**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="74ab9-125">**PR_LAST_MODIFICATION_TIME** ([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="74ab9-126">如果保存了一个或多个附件并清除 MSGFLAG_UNMODIFIED 以显示邮件已更改, 则**PR_MESSAGE_FLAGS**将设置 MSGFLAG_HASATTACH。</span><span class="sxs-lookup"><span data-stu-id="74ab9-126">**PR_MESSAGE_FLAGS** sets MSGFLAG_HASATTACH if one or more attachments have been saved and clears MSGFLAG_UNMODIFIED to show the message has changed.</span></span> 
    
- <span data-ttu-id="74ab9-127">**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 包含最新的邮件大小。</span><span class="sxs-lookup"><span data-stu-id="74ab9-127">**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) contains the most current size of the message.</span></span>
    
- <span data-ttu-id="74ab9-128">**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 提供对附件表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="74ab9-128">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) provides access to the attachment table.</span></span>
    
- <span data-ttu-id="74ab9-129">**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 提供对收件人表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="74ab9-129">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) provides access to the recipient table.</span></span>
    
<span data-ttu-id="74ab9-130">某些邮件属性通常由客户端或服务提供商在创建邮件时提供。</span><span class="sxs-lookup"><span data-stu-id="74ab9-130">Some message properties are typically supplied by clients or service providers when a message is created.</span></span> <span data-ttu-id="74ab9-131">如果客户端在对其进行设置, 则在调用**SaveChanges**时, 将由邮件存储提供程序对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="74ab9-131">If a client neglects to set them, it is up to the message store provider to update them at the time **SaveChanges** is called.</span></span> <span data-ttu-id="74ab9-132">例如, 如果在创建邮件时设置了邮件的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性, 则无需在保存时对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="74ab9-132">For example, if a message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) and **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) properties were set when the message was created, they need not be modified at save time.</span></span> <span data-ttu-id="74ab9-133">但是, 在邮件创建过程中忘记设置它们的邮件存储提供程序必须在第一次调用**SaveChanges**时设置它们。</span><span class="sxs-lookup"><span data-stu-id="74ab9-133">However, message store providers that neglect to set them at message creation must set them the first time that **SaveChanges** is called.</span></span> 
  
<span data-ttu-id="74ab9-134">如果**SaveChanges**返回 MAPI_E_CORRUPT_DATA, 则假定要保存的数据现在已丢失。</span><span class="sxs-lookup"><span data-stu-id="74ab9-134">If **SaveChanges** returns MAPI_E_CORRUPT_DATA, assume that the data being saved is now lost.</span></span> <span data-ttu-id="74ab9-135">将客户端-服务器模型用于实施的邮件存储提供程序可能会在网络连接丢失或服务器未运行时返回此值。</span><span class="sxs-lookup"><span data-stu-id="74ab9-135">Message store providers that use a client-server model for their implementation might return this value when a network connection is lost or the server is not running.</span></span> <span data-ttu-id="74ab9-136">在向用户返回错误之前, 请先调用**SetProps**并再次调用**SaveChanges**, 以再次写入并保存数据。</span><span class="sxs-lookup"><span data-stu-id="74ab9-136">Before returning an error to the user, try to write and save the data a second time by making a call to **SetProps** followed by another call to **SaveChanges**.</span></span> <span data-ttu-id="74ab9-137">如果数据在本地缓存, 则不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="74ab9-137">If the data is cached locally, this should not be a problem.</span></span> <span data-ttu-id="74ab9-138">但是, 如果没有本地缓存或第二个**SaveChanges**调用失败, 则显示一个错误, 提醒用户出现该问题。</span><span class="sxs-lookup"><span data-stu-id="74ab9-138">However, if there is no local cache or the second **SaveChanges** call fails, display an error to alert the user to the problem.</span></span> 
  

