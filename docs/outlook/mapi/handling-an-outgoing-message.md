---
title: 处理待发邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f40c2e0b-1a35-4901-868f-af6c191c921e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 07785ac82c41108b4333b3c370e3d2f5bfd1426a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407625"
---
# <a name="handling-an-outgoing-message"></a><span data-ttu-id="82a51-103">处理待发邮件</span><span class="sxs-lookup"><span data-stu-id="82a51-103">Handling an outgoing message</span></span>

<span data-ttu-id="82a51-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82a51-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82a51-105">传出邮件是一种可以跨一个或多个邮件系统发送给一个或多个收件人或发送到邮件存储中的文件夹的邮件。</span><span class="sxs-lookup"><span data-stu-id="82a51-105">An outgoing message is a message that can be sent to one or more recipients across one or more messaging systems or be posted to a folder in a message store.</span></span>
  
## <a name="create-and-send-an-outgoing-message"></a><span data-ttu-id="82a51-106">创建和发送传出邮件</span><span class="sxs-lookup"><span data-stu-id="82a51-106">Create and send an outgoing message</span></span>
  
1. <span data-ttu-id="82a51-107">打开默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="82a51-107">Open the default message store.</span></span> <span data-ttu-id="82a51-108">有关详细信息，请参阅打开[邮件存储和](opening-a-message-store.md)[打开默认邮件存储](opening-the-default-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-108">For more information, see [Opening a Message Store](opening-a-message-store.md) and [Opening the Default Message Store](opening-the-default-message-store.md).</span></span>
    
2. <span data-ttu-id="82a51-109">打开发件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="82a51-109">Open the Outbox folder.</span></span> <span data-ttu-id="82a51-110">有关详细信息，请参阅打开 [邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-110">For more information, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
    
3. <span data-ttu-id="82a51-111">调用发件箱文件夹的 **IMAPIFolder：：CreateMessage** 方法来创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="82a51-111">Call the Outbox folder's **IMAPIFolder::CreateMessage** method to create the new message.</span></span> <span data-ttu-id="82a51-112">有关详细信息，请参阅 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md)、</span><span class="sxs-lookup"><span data-stu-id="82a51-112">For more information, see [IMAPIFolder::CreateMessage](imapifolder-createmessage.md),</span></span>
    
4. <span data-ttu-id="82a51-113">创建包含一个或多个已解析收件人的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="82a51-113">Create a recipient list with one or more resolved recipients.</span></span> <span data-ttu-id="82a51-114">有关详细信息，请参阅创建 [收件人列表](creating-a-recipient-list.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-114">For more information, see [Creating a Recipient List](creating-a-recipient-list.md).</span></span>
    
5. <span data-ttu-id="82a51-115">（可选）添加主题。</span><span class="sxs-lookup"><span data-stu-id="82a51-115">Optionally, add a subject.</span></span> <span data-ttu-id="82a51-116">有关详细信息，请参阅 [创建邮件主题](creating-a-message-subject.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-116">For more information, see [Creating a Message Subject](creating-a-message-subject.md).</span></span>
    
6. <span data-ttu-id="82a51-117">添加邮件文本。</span><span class="sxs-lookup"><span data-stu-id="82a51-117">Add the message text.</span></span> <span data-ttu-id="82a51-118">有关详细信息，请参阅创建 [消息文本](creating-message-text.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-118">For more information, see [Creating Message Text](creating-message-text.md).</span></span>
    
7. <span data-ttu-id="82a51-119">如果邮件文本已设置格式，请添加呈现信息。</span><span class="sxs-lookup"><span data-stu-id="82a51-119">If the message text is formatted, add rendering information.</span></span> <span data-ttu-id="82a51-120">有关详细信息，请参阅向 [格式化文本添加呈现信息](adding-rendering-information-to-formatted-text.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-120">For more information, see [Adding Rendering Information to Formatted Text](adding-rendering-information-to-formatted-text.md).</span></span>
    
8. <span data-ttu-id="82a51-121">（可选）添加一个或多个附件。</span><span class="sxs-lookup"><span data-stu-id="82a51-121">Optionally, add one or more attachments.</span></span> <span data-ttu-id="82a51-122">有关详细信息，请参阅创建 [邮件附件](creating-a-message-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-122">For more information, see [Creating a Message Attachment](creating-a-message-attachment.md).</span></span>
    
9. <span data-ttu-id="82a51-123">设置其他邮件属性，然后通过调用 **IMessage：：SubmitMessage 保存并发送邮件**。</span><span class="sxs-lookup"><span data-stu-id="82a51-123">Set other message properties as desired and then save and send the message by calling **IMessage::SubmitMessage**.</span></span> <span data-ttu-id="82a51-124">有关详细信息，请参阅 [IMessage：：SubmitMessage](imessage-submitmessage.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-124">For more information, see [IMessage::SubmitMessage](imessage-submitmessage.md).</span></span>
    
10. <span data-ttu-id="82a51-125">如果 **PR \_ DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性设置为 TRUE 或将其移动到 **由 PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性标识的文件夹，则删除已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="82a51-125">Delete the sent message if the **PR\_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property is set to TRUE or move it to the folder identified by the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="82a51-126">有关详细信息，请参阅处理 [已发送的邮件](processing-a-sent-message.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-126">For more information, see [Processing a Sent Message](processing-a-sent-message.md).</span></span>
    
<span data-ttu-id="82a51-127">如果要在发送邮件之前进行互操作保存，请调用邮件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="82a51-127">If you want to intermittantly save the message before sending it, call the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="82a51-128">有关详细信息，请参阅保存 [邮件](saving-a-message.md) 或 [发送邮件](sending-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="82a51-128">For more information, see, [Saving a Message](saving-a-message.md) or [Sending a Message](sending-a-message.md).</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="82a51-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="82a51-129">In this section</span></span>

- <span data-ttu-id="82a51-130">[创建收件人列表](creating-a-recipient-list.md)：介绍如何创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="82a51-130">[Creating a Recipient List](creating-a-recipient-list.md): Describes how to create a recipient list.</span></span>
    
- <span data-ttu-id="82a51-131">[创建邮件主题](creating-a-message-subject.md)：介绍如何为邮件创建可选主题。</span><span class="sxs-lookup"><span data-stu-id="82a51-131">[Creating a Message Subject](creating-a-message-subject.md): Describes how to create an optional subject for a message.</span></span>
    
- <span data-ttu-id="82a51-132">[创建消息文本](creating-message-text.md)：介绍如何创建邮件文本。</span><span class="sxs-lookup"><span data-stu-id="82a51-132">[Creating Message Text](creating-message-text.md): Describes how to create message text.</span></span>
    
- <span data-ttu-id="82a51-133">[向格式化文本添加呈现信息](adding-rendering-information-to-formatted-text.md)：描述附件在格式化文本中的呈现位置。</span><span class="sxs-lookup"><span data-stu-id="82a51-133">[Adding Rendering Information to Formatted Text](adding-rendering-information-to-formatted-text.md): Describes where in formatted text an attachment is to be rendered.</span></span>
    
- <span data-ttu-id="82a51-134">[创建邮件附件](creating-a-message-attachment.md)：介绍如何创建附件。</span><span class="sxs-lookup"><span data-stu-id="82a51-134">[Creating a Message Attachment](creating-a-message-attachment.md): Describes how to create attachments.</span></span>
    
- <span data-ttu-id="82a51-135">[保存邮件](saving-a-message.md)：描述客户端如何保存邮件。</span><span class="sxs-lookup"><span data-stu-id="82a51-135">[Saving a Message](saving-a-message.md): Describes how clients save messages.</span></span>
    
- <span data-ttu-id="82a51-136">[发送邮件 ：](sending-a-message.md)介绍如何发送邮件。</span><span class="sxs-lookup"><span data-stu-id="82a51-136">[Sending a Message](sending-a-message.md): Describes how to send a message.</span></span>
    
- <span data-ttu-id="82a51-137">[处理已发送的邮件](processing-a-sent-message.md)：介绍如何处理已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="82a51-137">[Processing a Sent Message](processing-a-sent-message.md): Describes how to sent messages can be processed.</span></span>
    

