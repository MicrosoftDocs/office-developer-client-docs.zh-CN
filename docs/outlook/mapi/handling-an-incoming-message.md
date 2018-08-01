---
title: 处理传入消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d45d5ed9-41cd-4aaf-91d2-1e4a27bb16d4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5705af6c8efaf42ae27d1b39bb28d162971ebf9b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775044"
---
# <a name="handling-an-incoming-message"></a><span data-ttu-id="76905-103">处理传入消息</span><span class="sxs-lookup"><span data-stu-id="76905-103">Handling an incoming message</span></span>

<span data-ttu-id="76905-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="76905-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="76905-105">对传入邮件是已跨一个或多个邮件系统发送的消息。</span><span class="sxs-lookup"><span data-stu-id="76905-105">An incoming message is a message that has been sent across one or more messaging systems.</span></span> <span data-ttu-id="76905-106">它可能已发送只对您或其他很多个收件人。</span><span class="sxs-lookup"><span data-stu-id="76905-106">It may have been sent only to you or to many other recipients.</span></span> <span data-ttu-id="76905-107">传入消息被置于指定用于保存的特定类的邮件的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="76905-107">Incoming messages are placed in a receive folder designated to hold messages of a particular class.</span></span> <span data-ttu-id="76905-108">您可以设置另一个接收您处理，或使用的所有类的一个文件夹每个邮件类的文件夹。</span><span class="sxs-lookup"><span data-stu-id="76905-108">You can set up a different receive folder for each message class that you handle or use one folder for all of the classes.</span></span>
  
<span data-ttu-id="76905-109">如果您已注册的与邮件存储的新邮件通知，将一条消息置于接收文件夹时通知您。</span><span class="sxs-lookup"><span data-stu-id="76905-109">If you have registered for new mail notifications with the message store, you will be notified whenever a message is placed in a receive folder.</span></span> <span data-ttu-id="76905-110">如果您未注册新邮件通知，则必须打开相应接收定期来手动检查新邮件的到达的文件夹。</span><span class="sxs-lookup"><span data-stu-id="76905-110">If you have not registered for new mail notifications, you must open the appropriate receive folder periodically to manually check for the arrival of new messages.</span></span>
  
<span data-ttu-id="76905-111">客户端注册新邮件通知通过将参数设置为[IMsgStore::Advise](imsgstore-advise.md) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="76905-111">Clients register for new mail notifications by setting the parameters to [IMsgStore::Advise](imsgstore-advise.md) as follows:</span></span> 
  
- <span data-ttu-id="76905-112">设置为 0 _cbEntryID_ 。</span><span class="sxs-lookup"><span data-stu-id="76905-112">Set  _cbEntryID_ to 0.</span></span> 
    
- <span data-ttu-id="76905-113">_LpEntryID_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="76905-113">Set  _lpEntryID_ to NULL.</span></span> 
    
- <span data-ttu-id="76905-114">设置为 fnevNewMail _ulEventMask_ 。</span><span class="sxs-lookup"><span data-stu-id="76905-114">Set  _ulEventMask_ to fnevNewMail.</span></span> 
    
<span data-ttu-id="76905-115">对**IMAPIAdviseSink::OnNotify**方法的调用中的_lpNotifications_参数指向**NEWMAIL\_通知**结构，其中包含有关传入邮件，例如其邮件类别，它的项的信息标识符，其父文件夹的项标识符和其**PR_MESSAGE_FLAGS**属性的内容。</span><span class="sxs-lookup"><span data-stu-id="76905-115">The  _lpNotifications_ parameter in the call to your **IMAPIAdviseSink::OnNotify** method points to a **NEWMAIL\_NOTIFICATION** structure that contains information about the incoming message, such as its message class, its entry identifier, the entry identifier of its parent folder, and the contents of its **PR_MESSAGE_FLAGS** property.</span></span> <span data-ttu-id="76905-116">有关注册和处理通知的详细信息，请参阅[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)、 [NEWMAIL_NOTIFICATION](newmail_notification.md)、 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和[处理通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-116">For more information about registering for and handling notifications, see [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md), [NEWMAIL_NOTIFICATION](newmail_notification.md), **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)), and [Handling Notifications](handling-notifications.md).</span></span> 
  
<span data-ttu-id="76905-117">向用户显示传入消息之前, 确定其邮件类别是您的客户端支持的类。</span><span class="sxs-lookup"><span data-stu-id="76905-117">Before displaying an incoming message to a user, determine if its message class is a class that your client supports.</span></span> <span data-ttu-id="76905-118">如果没有，则忽略该消息。</span><span class="sxs-lookup"><span data-stu-id="76905-118">If not, ignore the message.</span></span> <span data-ttu-id="76905-119">如果您支持的一个类，您可以打开并显示适用于邮件的邮件类的窗体的邮件。</span><span class="sxs-lookup"><span data-stu-id="76905-119">If the class is one that you support, you can open and display the message with a form that is appropriate for the message class of the message.</span></span> <span data-ttu-id="76905-120">邮件类基于表单的选择。</span><span class="sxs-lookup"><span data-stu-id="76905-120">The choice of forms is based on message class.</span></span> <span data-ttu-id="76905-121">属于 IPM 类的邮件使用由 MAPI 实现默认窗体。</span><span class="sxs-lookup"><span data-stu-id="76905-121">Messages that belong to the IPM class use a default form implemented by MAPI.</span></span> <span data-ttu-id="76905-122">属于自定义类定义由客户端的消息可以使用客户端定义专用窗体或 MAPI 默认窗体。</span><span class="sxs-lookup"><span data-stu-id="76905-122">Messages that belong to custom classes defined by clients can use either client-defined specialized forms or the MAPI default form.</span></span>
  
## <a name="open-and-display-an-incoming-message"></a><span data-ttu-id="76905-123">打开并显示传入消息</span><span class="sxs-lookup"><span data-stu-id="76905-123">Open and display an incoming message</span></span>
  
1. <span data-ttu-id="76905-124">调用**IMsgStore::GetReceiveFolder**检索的接收文件夹的邮件的邮件类的项标识符，并将此条目标识符传递到**IMsgStore::OpenEntry**打开文件夹。</span><span class="sxs-lookup"><span data-stu-id="76905-124">Call **IMsgStore::GetReceiveFolder** to retrieve the entry identifier of the receive folder for the message class of the message and pass this entry identifier to **IMsgStore::OpenEntry** to open the folder.</span></span> <span data-ttu-id="76905-125">有关详细信息，请参阅[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)、 [IMsgStore::OpenEntry](imsgstore-openentry.md)，和[打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-125">For more information, see [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md), [IMsgStore::OpenEntry](imsgstore-openentry.md), and [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
    
2. <span data-ttu-id="76905-126">呼叫的接收文件夹**IMAPIContainer::GetContentsTable**方法来检索其内容表。</span><span class="sxs-lookup"><span data-stu-id="76905-126">Call the receive folder's **IMAPIContainer::GetContentsTable** method to retrieve its contents table.</span></span> <span data-ttu-id="76905-127">有关详细信息，请参阅[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-127">For more information, see [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md).</span></span> <span data-ttu-id="76905-128">调用表的**IMAPITable::QueryRows**方法来检索表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="76905-128">Call the table's **IMAPITable::QueryRows** method to retrieve all the rows in the table.</span></span> <span data-ttu-id="76905-129">有关详细信息，请参阅[IMAPITable::QueryRows](imapitable-queryrows.md)和[内容的表格](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-129">For more information see [IMAPITable::QueryRows](imapitable-queryrows.md) and [Contents Tables](contents-tables.md).</span></span> <span data-ttu-id="76905-130">有关显示内容表的详细信息，请参阅[显示文件夹内容表](displaying-a-folder-contents-table.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-130">For more information about displaying a contents table, see [Displaying a Folder Contents Table](displaying-a-folder-contents-table.md).</span></span>
    
3. <span data-ttu-id="76905-131">如果您的客户端交互，允许用户从表中选择一条消息，并确定要用于显示该邮件的表单。</span><span class="sxs-lookup"><span data-stu-id="76905-131">If your client is interactive, allow the user to select a message from the table and determine the form to be used to display that message.</span></span> <span data-ttu-id="76905-132">客户端可以使用 MAPI 或自定义窗体提供的默认窗体。</span><span class="sxs-lookup"><span data-stu-id="76905-132">Clients can use the default form provided by MAPI or a custom form.</span></span> <span data-ttu-id="76905-133">有关详细信息，请参阅[处理 MAPI 表单](handling-mapi-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-133">For more information, see [Handling MAPI Forms](handling-mapi-forms.md).</span></span>
    
4. <span data-ttu-id="76905-134">调用**IMsgStore::OpenEntry**以打开该邮件。</span><span class="sxs-lookup"><span data-stu-id="76905-134">Call **IMsgStore::OpenEntry** to open the message.</span></span> <span data-ttu-id="76905-135">有关详细信息，请参阅[打开一条消息](opening-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-135">For more information, see [Opening a Message](opening-a-message.md).</span></span>
    
5. <span data-ttu-id="76905-136">处理的消息文本。</span><span class="sxs-lookup"><span data-stu-id="76905-136">Process the message text.</span></span> <span data-ttu-id="76905-137">有关详细信息，请参阅[打开消息文本](opening-message-text.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-137">For more information, see [Opening Message Text](opening-message-text.md).</span></span>
    
6. <span data-ttu-id="76905-138">呈现每个邮件附件。</span><span class="sxs-lookup"><span data-stu-id="76905-138">Render each of the message attachments.</span></span> <span data-ttu-id="76905-139">有关详细信息，请参阅[呈现纯文本中的附件](rendering-an-attachment-in-plain-text.md)或[呈现 RTF 文本中的附件](rendering-an-attachment-in-rtf-text.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-139">For more information, see [Rendering an Attachment in Plain Text](rendering-an-attachment-in-plain-text.md) or [Rendering an Attachment in RTF Text](rendering-an-attachment-in-rtf-text.md).</span></span>
    
7. <span data-ttu-id="76905-140">如果需要，请打开的附件。</span><span class="sxs-lookup"><span data-stu-id="76905-140">Open an attachment if desired.</span></span> <span data-ttu-id="76905-141">有关详细信息，请参阅[打开附件](opening-an-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="76905-141">For more information see [Opening an Attachment](opening-an-attachment.md).</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="76905-142">本节内容</span><span class="sxs-lookup"><span data-stu-id="76905-142">In this section</span></span>

- <span data-ttu-id="76905-143">[打开消息文本](opening-message-text.md)： 介绍如何打开的消息文本。</span><span class="sxs-lookup"><span data-stu-id="76905-143">[Opening Message Text](opening-message-text.md): Describes how to open the message text.</span></span>
    
- <span data-ttu-id="76905-144">[呈现以纯文本附件](rendering-an-attachment-in-plain-text.md)： 介绍如何呈现纯文本中的附件。</span><span class="sxs-lookup"><span data-stu-id="76905-144">[Rendering an Attachment in Plain Text](rendering-an-attachment-in-plain-text.md): Describes how to render an attachment in plain text.</span></span>
    
- <span data-ttu-id="76905-145">[呈现 RTF 文本中的附件](rendering-an-attachment-in-rtf-text.md)： 介绍如何呈现附件中带格式的文本。</span><span class="sxs-lookup"><span data-stu-id="76905-145">[Rendering an Attachment in RTF Text](rendering-an-attachment-in-rtf-text.md): Describes how to render an attachment in formatted text.</span></span>
    
- <span data-ttu-id="76905-146">[打开附件](opening-an-attachment.md)： 介绍如何打开的附件。</span><span class="sxs-lookup"><span data-stu-id="76905-146">[Opening an Attachment](opening-an-attachment.md): Describes how to open an attachment.</span></span>
    

