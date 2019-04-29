---
title: 处理传入的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d45d5ed9-41cd-4aaf-91d2-1e4a27bb16d4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f3fbe34793e3520b26b984f4bd6b14fbcab7a951
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438979"
---
# <a name="handling-an-incoming-message"></a><span data-ttu-id="ca31a-103">处理传入的邮件</span><span class="sxs-lookup"><span data-stu-id="ca31a-103">Handling an incoming message</span></span>

<span data-ttu-id="ca31a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca31a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca31a-105">传入邮件是已在一个或多个邮件系统中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-105">An incoming message is a message that has been sent across one or more messaging systems.</span></span> <span data-ttu-id="ca31a-106">它可能已仅发送给您或其他许多收件人。</span><span class="sxs-lookup"><span data-stu-id="ca31a-106">It may have been sent only to you or to many other recipients.</span></span> <span data-ttu-id="ca31a-107">传入邮件放在接收文件夹中, 指定用于保存特定类的邮件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-107">Incoming messages are placed in a receive folder designated to hold messages of a particular class.</span></span> <span data-ttu-id="ca31a-108">您可以为每个要处理的邮件类别设置不同的接收文件夹, 或为所有类使用一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca31a-108">You can set up a different receive folder for each message class that you handle or use one folder for all of the classes.</span></span>
  
<span data-ttu-id="ca31a-109">如果已使用邮件存储区注册了新邮件通知, 则每当邮件放在接收文件夹中时, 都会收到通知。</span><span class="sxs-lookup"><span data-stu-id="ca31a-109">If you have registered for new mail notifications with the message store, you will be notified whenever a message is placed in a receive folder.</span></span> <span data-ttu-id="ca31a-110">如果尚未注册新邮件通知, 则必须定期打开相应的接收文件夹, 以手动检查是否到达新邮件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-110">If you have not registered for new mail notifications, you must open the appropriate receive folder periodically to manually check for the arrival of new messages.</span></span>
  
<span data-ttu-id="ca31a-111">客户端通过将参数设置为[IMsgStore:: 建议](imsgstore-advise.md)来注册新邮件通知, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="ca31a-111">Clients register for new mail notifications by setting the parameters to [IMsgStore::Advise](imsgstore-advise.md) as follows:</span></span> 
  
- <span data-ttu-id="ca31a-112">将_cbEntryID_设置为0。</span><span class="sxs-lookup"><span data-stu-id="ca31a-112">Set  _cbEntryID_ to 0.</span></span> 
    
- <span data-ttu-id="ca31a-113">将_lpEntryID_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ca31a-113">Set  _lpEntryID_ to NULL.</span></span> 
    
- <span data-ttu-id="ca31a-114">将_ulEventMask_设置为 fnevNewMail。</span><span class="sxs-lookup"><span data-stu-id="ca31a-114">Set  _ulEventMask_ to fnevNewMail.</span></span> 
    
<span data-ttu-id="ca31a-115">对**IMAPIAdviseSink:: OnNotify**方法的调用中的_lpNotifications_参数指向一个**\_NEWMAIL 通知**结构, 其中包含有关传入邮件的信息, 例如其邮件类别、其条目标识符、其父文件夹的条目标识符以及它的**PR_MESSAGE_FLAGS**属性的内容。</span><span class="sxs-lookup"><span data-stu-id="ca31a-115">The  _lpNotifications_ parameter in the call to your **IMAPIAdviseSink::OnNotify** method points to a **NEWMAIL\_NOTIFICATION** structure that contains information about the incoming message, such as its message class, its entry identifier, the entry identifier of its parent folder, and the contents of its **PR_MESSAGE_FLAGS** property.</span></span> <span data-ttu-id="ca31a-116">有关注册和处理通知的详细信息, 请参阅[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)、 [NEWMAIL_NOTIFICATION](newmail_notification.md)、 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和[处理通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-116">For more information about registering for and handling notifications, see [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md), [NEWMAIL_NOTIFICATION](newmail_notification.md), **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)), and [Handling Notifications](handling-notifications.md).</span></span> 
  
<span data-ttu-id="ca31a-117">在向用户显示传入邮件之前, 请确定其邮件类别是否为您的客户端支持的类。</span><span class="sxs-lookup"><span data-stu-id="ca31a-117">Before displaying an incoming message to a user, determine if its message class is a class that your client supports.</span></span> <span data-ttu-id="ca31a-118">如果不是, 则忽略该消息。</span><span class="sxs-lookup"><span data-stu-id="ca31a-118">If not, ignore the message.</span></span> <span data-ttu-id="ca31a-119">如果类是您支持的类, 则可以使用适合于邮件的邮件类的窗体打开和显示邮件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-119">If the class is one that you support, you can open and display the message with a form that is appropriate for the message class of the message.</span></span> <span data-ttu-id="ca31a-120">窗体的选择基于邮件类。</span><span class="sxs-lookup"><span data-stu-id="ca31a-120">The choice of forms is based on message class.</span></span> <span data-ttu-id="ca31a-121">属于 IPM 类的邮件使用由 MAPI 实现的默认表单。</span><span class="sxs-lookup"><span data-stu-id="ca31a-121">Messages that belong to the IPM class use a default form implemented by MAPI.</span></span> <span data-ttu-id="ca31a-122">属于由客户端定义的自定义类的邮件可以使用客户端定义的专用表单或 MAPI 默认表单。</span><span class="sxs-lookup"><span data-stu-id="ca31a-122">Messages that belong to custom classes defined by clients can use either client-defined specialized forms or the MAPI default form.</span></span>
  
## <a name="open-and-display-an-incoming-message"></a><span data-ttu-id="ca31a-123">打开并显示传入的邮件</span><span class="sxs-lookup"><span data-stu-id="ca31a-123">Open and display an incoming message</span></span>
  
1. <span data-ttu-id="ca31a-124">调用**IMsgStore:: GetReceiveFolder**以检索邮件的邮件类的接收文件夹的条目标识符, 并将此条目标识符传递到**IMsgStore:: OpenEntry**以打开该文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca31a-124">Call **IMsgStore::GetReceiveFolder** to retrieve the entry identifier of the receive folder for the message class of the message and pass this entry identifier to **IMsgStore::OpenEntry** to open the folder.</span></span> <span data-ttu-id="ca31a-125">有关详细信息, 请参阅[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md), [IMsgStore:: OpenEntry](imsgstore-openentry.md), 并[打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-125">For more information, see [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md), [IMsgStore::OpenEntry](imsgstore-openentry.md), and [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
    
2. <span data-ttu-id="ca31a-126">调用接收文件夹的**IMAPIContainer:: GetContentsTable**方法以检索其内容表。</span><span class="sxs-lookup"><span data-stu-id="ca31a-126">Call the receive folder's **IMAPIContainer::GetContentsTable** method to retrieve its contents table.</span></span> <span data-ttu-id="ca31a-127">有关详细信息, 请参阅[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-127">For more information, see [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md).</span></span> <span data-ttu-id="ca31a-128">调用表的**IMAPITable:: QueryRows**方法以检索表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="ca31a-128">Call the table's **IMAPITable::QueryRows** method to retrieve all the rows in the table.</span></span> <span data-ttu-id="ca31a-129">有关详细信息, 请参阅[IMAPITable:: QueryRows](imapitable-queryrows.md)和[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-129">For more information see [IMAPITable::QueryRows](imapitable-queryrows.md) and [Contents Tables](contents-tables.md).</span></span> <span data-ttu-id="ca31a-130">有关显示内容表的详细信息, 请参阅[显示文件夹内容表](displaying-a-folder-contents-table.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-130">For more information about displaying a contents table, see [Displaying a Folder Contents Table](displaying-a-folder-contents-table.md).</span></span>
    
3. <span data-ttu-id="ca31a-131">如果您的客户端是交互式的, 则允许用户从表中选择一封邮件, 并确定要用于显示该邮件的窗体。</span><span class="sxs-lookup"><span data-stu-id="ca31a-131">If your client is interactive, allow the user to select a message from the table and determine the form to be used to display that message.</span></span> <span data-ttu-id="ca31a-132">客户端可以使用 MAPI 或自定义窗体提供的默认窗体。</span><span class="sxs-lookup"><span data-stu-id="ca31a-132">Clients can use the default form provided by MAPI or a custom form.</span></span> <span data-ttu-id="ca31a-133">有关详细信息, 请参阅[处理 MAPI 表单](handling-mapi-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-133">For more information, see [Handling MAPI Forms](handling-mapi-forms.md).</span></span>
    
4. <span data-ttu-id="ca31a-134">调用**IMsgStore:: OpenEntry**以打开邮件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-134">Call **IMsgStore::OpenEntry** to open the message.</span></span> <span data-ttu-id="ca31a-135">有关详细信息, 请参阅[打开邮件](opening-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-135">For more information, see [Opening a Message](opening-a-message.md).</span></span>
    
5. <span data-ttu-id="ca31a-136">处理消息文本。</span><span class="sxs-lookup"><span data-stu-id="ca31a-136">Process the message text.</span></span> <span data-ttu-id="ca31a-137">有关详细信息, 请参阅[打开消息文本](opening-message-text.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-137">For more information, see [Opening Message Text](opening-message-text.md).</span></span>
    
6. <span data-ttu-id="ca31a-138">呈现每个邮件附件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-138">Render each of the message attachments.</span></span> <span data-ttu-id="ca31a-139">有关详细信息, 请参阅[以纯文本呈现附件](rendering-an-attachment-in-plain-text.md)或[在 RTF 文本中呈现附件](rendering-an-attachment-in-rtf-text.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-139">For more information, see [Rendering an Attachment in Plain Text](rendering-an-attachment-in-plain-text.md) or [Rendering an Attachment in RTF Text](rendering-an-attachment-in-rtf-text.md).</span></span>
    
7. <span data-ttu-id="ca31a-140">如果需要, 打开一个附件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-140">Open an attachment if desired.</span></span> <span data-ttu-id="ca31a-141">有关详细信息, 请参阅[打开附件](opening-an-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="ca31a-141">For more information see [Opening an Attachment](opening-an-attachment.md).</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="ca31a-142">本节内容</span><span class="sxs-lookup"><span data-stu-id="ca31a-142">In this section</span></span>

- <span data-ttu-id="ca31a-143">[打开消息文本](opening-message-text.md): 介绍如何打开消息文本。</span><span class="sxs-lookup"><span data-stu-id="ca31a-143">[Opening Message Text](opening-message-text.md): Describes how to open the message text.</span></span>
    
- <span data-ttu-id="ca31a-144">[以纯文本格式呈现附件](rendering-an-attachment-in-plain-text.md): 介绍如何以纯文本形式呈现附件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-144">[Rendering an Attachment in Plain Text](rendering-an-attachment-in-plain-text.md): Describes how to render an attachment in plain text.</span></span>
    
- <span data-ttu-id="ca31a-145">[在 RTF 文本中呈现附件](rendering-an-attachment-in-rtf-text.md): 介绍如何在格式化文本中呈现附件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-145">[Rendering an Attachment in RTF Text](rendering-an-attachment-in-rtf-text.md): Describes how to render an attachment in formatted text.</span></span>
    
- <span data-ttu-id="ca31a-146">[打开附件](opening-an-attachment.md): 介绍如何打开附件。</span><span class="sxs-lookup"><span data-stu-id="ca31a-146">[Opening an Attachment](opening-an-attachment.md): Describes how to open an attachment.</span></span>
    

