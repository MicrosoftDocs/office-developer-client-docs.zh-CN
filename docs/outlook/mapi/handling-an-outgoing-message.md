---
title: 处理的传出邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f40c2e0b-1a35-4901-868f-af6c191c921e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ab293ee3813d77c3a954e8364736a89bc2330feb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775040"
---
# <a name="handling-an-outgoing-message"></a><span data-ttu-id="00e96-103">处理的传出邮件</span><span class="sxs-lookup"><span data-stu-id="00e96-103">Handling an outgoing message</span></span>

<span data-ttu-id="00e96-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="00e96-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="00e96-105">传出 message 是一条消息，可以跨一个或多个邮件系统发送到一个或多个收件人或发送到的文件夹中的消息存储。</span><span class="sxs-lookup"><span data-stu-id="00e96-105">An outgoing message is a message that can be sent to one or more recipients across one or more messaging systems or be posted to a folder in a message store.</span></span>
  
## <a name="create-and-send-an-outgoing-message"></a><span data-ttu-id="00e96-106">创建并发送传出邮件</span><span class="sxs-lookup"><span data-stu-id="00e96-106">Create and send an outgoing message</span></span>
  
1. <span data-ttu-id="00e96-107">打开默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="00e96-107">Open the default message store.</span></span> <span data-ttu-id="00e96-108">有关详细信息，请参阅[打开消息存储](opening-a-message-store.md)并[打开默认的邮件存储](opening-the-default-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-108">For more information, see [Opening a Message Store](opening-a-message-store.md) and [Opening the Default Message Store](opening-the-default-message-store.md).</span></span>
    
2. <span data-ttu-id="00e96-109">打开发件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="00e96-109">Open the Outbox folder.</span></span> <span data-ttu-id="00e96-110">有关详细信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-110">For more information, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
    
3. <span data-ttu-id="00e96-111">调用发件箱文件夹的**IMAPIFolder::CreateMessage**方法，以创建新的邮件。</span><span class="sxs-lookup"><span data-stu-id="00e96-111">Call the Outbox folder's **IMAPIFolder::CreateMessage** method to create the new message.</span></span> <span data-ttu-id="00e96-112">有关详细信息，请参阅[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)，</span><span class="sxs-lookup"><span data-stu-id="00e96-112">For more information, see [IMAPIFolder::CreateMessage](imapifolder-createmessage.md),</span></span>
    
4. <span data-ttu-id="00e96-113">创建具有一个或多个解析的收件人的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="00e96-113">Create a recipient list with one or more resolved recipients.</span></span> <span data-ttu-id="00e96-114">有关详细信息，请参阅[创建收件人列表](creating-a-recipient-list.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-114">For more information, see [Creating a Recipient List](creating-a-recipient-list.md).</span></span>
    
5. <span data-ttu-id="00e96-115">（可选） 添加主题。</span><span class="sxs-lookup"><span data-stu-id="00e96-115">Optionally, add a subject.</span></span> <span data-ttu-id="00e96-116">有关详细信息，请参阅[创建邮件主题](creating-a-message-subject.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-116">For more information, see [Creating a Message Subject](creating-a-message-subject.md).</span></span>
    
6. <span data-ttu-id="00e96-117">添加的消息文本。</span><span class="sxs-lookup"><span data-stu-id="00e96-117">Add the message text.</span></span> <span data-ttu-id="00e96-118">有关详细信息，请参阅[创建消息文本](creating-message-text.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-118">For more information, see [Creating Message Text](creating-message-text.md).</span></span>
    
7. <span data-ttu-id="00e96-119">如果消息文本的格式，添加呈现的信息。</span><span class="sxs-lookup"><span data-stu-id="00e96-119">If the message text is formatted, add rendering information.</span></span> <span data-ttu-id="00e96-120">有关详细信息，请参阅[为格式文本添加呈现信息](adding-rendering-information-to-formatted-text.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-120">For more information, see [Adding Rendering Information to Formatted Text](adding-rendering-information-to-formatted-text.md).</span></span>
    
8. <span data-ttu-id="00e96-121">（可选） 中添加一个或多个附件。</span><span class="sxs-lookup"><span data-stu-id="00e96-121">Optionally, add one or more attachments.</span></span> <span data-ttu-id="00e96-122">有关详细信息，请参阅[创建邮件附件](creating-a-message-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-122">For more information, see [Creating a Message Attachment](creating-a-message-attachment.md).</span></span>
    
9. <span data-ttu-id="00e96-123">将其他邮件属性设置为所需然后保存并通过调用**IMessage::SubmitMessage**发送消息。</span><span class="sxs-lookup"><span data-stu-id="00e96-123">Set other message properties as desired and then save and send the message by calling **IMessage::SubmitMessage**.</span></span> <span data-ttu-id="00e96-124">有关详细信息，请参阅[IMessage::SubmitMessage](imessage-submitmessage.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-124">For more information, see [IMessage::SubmitMessage](imessage-submitmessage.md).</span></span>
    
10. <span data-ttu-id="00e96-125">删除已发送的邮件如果**PR\_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性设置为 TRUE 或移动到文件夹它标识**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="00e96-125">Delete the sent message if the **PR\_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property is set to TRUE or move it to the folder identified by the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="00e96-126">有关详细信息，请参阅[处理发送消息](processing-a-sent-message.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-126">For more information, see [Processing a Sent Message](processing-a-sent-message.md).</span></span>
    
<span data-ttu-id="00e96-127">如果您希望 intermittantly 发送之前保存邮件、 呼叫消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="00e96-127">If you want to intermittantly save the message before sending it, call the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="00e96-128">有关详细信息，请参阅，[保存邮件](saving-a-message.md)或[发送一条消息](sending-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="00e96-128">For more information, see, [Saving a Message](saving-a-message.md) or [Sending a Message](sending-a-message.md).</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="00e96-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="00e96-129">In this section</span></span>

- <span data-ttu-id="00e96-130">[创建收件人列表](creating-a-recipient-list.md)： 介绍如何创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="00e96-130">[Creating a Recipient List](creating-a-recipient-list.md): Describes how to create a recipient list.</span></span>
    
- <span data-ttu-id="00e96-131">[创建邮件主题](creating-a-message-subject.md)： 介绍如何创建一条消息，可选主题。</span><span class="sxs-lookup"><span data-stu-id="00e96-131">[Creating a Message Subject](creating-a-message-subject.md): Describes how to create an optional subject for a message.</span></span>
    
- <span data-ttu-id="00e96-132">[创建消息文本](creating-message-text.md)： 介绍如何创建消息文本。</span><span class="sxs-lookup"><span data-stu-id="00e96-132">[Creating Message Text](creating-message-text.md): Describes how to create message text.</span></span>
    
- <span data-ttu-id="00e96-133">[为格式文本添加呈现信息](adding-rendering-information-to-formatted-text.md)： 介绍在带格式的文本附件与要在其中呈现。</span><span class="sxs-lookup"><span data-stu-id="00e96-133">[Adding Rendering Information to Formatted Text](adding-rendering-information-to-formatted-text.md): Describes where in formatted text an attachment is to be rendered.</span></span>
    
- <span data-ttu-id="00e96-134">[创建邮件附件](creating-a-message-attachment.md)： 介绍如何创建附件。</span><span class="sxs-lookup"><span data-stu-id="00e96-134">[Creating a Message Attachment](creating-a-message-attachment.md): Describes how to create attachments.</span></span>
    
- <span data-ttu-id="00e96-135">[保存消息](saving-a-message.md)： 介绍了客户端如何保存邮件。</span><span class="sxs-lookup"><span data-stu-id="00e96-135">[Saving a Message](saving-a-message.md): Describes how clients save messages.</span></span>
    
- <span data-ttu-id="00e96-136">[发送一条消息](sending-a-message.md)： 介绍如何发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="00e96-136">[Sending a Message](sending-a-message.md): Describes how to send a message.</span></span>
    
- <span data-ttu-id="00e96-137">[发送邮件的处理](processing-a-sent-message.md)： 介绍如何发送可以处理邮件。</span><span class="sxs-lookup"><span data-stu-id="00e96-137">[Processing a Sent Message](processing-a-sent-message.md): Describes how to sent messages can be processed.</span></span>
    

