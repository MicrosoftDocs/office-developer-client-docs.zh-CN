---
title: 使用邮件存储区提供程序接收邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4763951e-ccfd-453e-b99c-5c7d5efb90c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8a5df2e8f50d8de05ec43b03ae5b56887e76d505
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590188"
---
# <a name="receiving-messages-by-using-message-store-providers"></a><span data-ttu-id="20238-103">使用邮件存储区提供程序接收邮件</span><span class="sxs-lookup"><span data-stu-id="20238-103">Receiving Messages by Using Message Store Providers</span></span>

  
  
<span data-ttu-id="20238-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20238-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20238-105">消息存储提供程序无需支持传入的邮件提交 （即，为支持的功能的传输提供商和 MAPI 后台处理程序使用消息存储提供程序的邮件的传递点）。</span><span class="sxs-lookup"><span data-stu-id="20238-105">Message store providers do not have to support incoming message submissions (that is, support the ability for transport providers and the MAPI spooler to use the message store provider as a delivery point for messages).</span></span> <span data-ttu-id="20238-106">但是，如果您的消息存储提供程序不支持传入的邮件提交，它不能用作默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="20238-106">However, if your message store provider does not support incoming message submissions, it cannot be used as the default message store.</span></span>
  
<span data-ttu-id="20238-107">若要支持传入的邮件提交，消息存储提供程序必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20238-107">To support incoming message submissions, your message store provider must do the following:</span></span>
  
- <span data-ttu-id="20238-108">支持的[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)和[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)方法，以便客户端应用程序可以找到传入消息。</span><span class="sxs-lookup"><span data-stu-id="20238-108">Support the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) and [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) methods so client applications can find incoming messages.</span></span> 
    
- <span data-ttu-id="20238-109">支持的[IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)方法，以便 MAPI 后台处理程序可通知新消息已到达的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="20238-109">Support the [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md) method so that the MAPI spooler can inform the message store provider that a new message has arrived.</span></span> 
    
- <span data-ttu-id="20238-110">实现通知，以便客户端可以注册新邮件通知。</span><span class="sxs-lookup"><span data-stu-id="20238-110">Implement notifications so that clients can register for new message notification.</span></span> <span data-ttu-id="20238-111">通知是可选的但您的提供商应实现它们。</span><span class="sxs-lookup"><span data-stu-id="20238-111">Notifications are optional, but your provider should implement them.</span></span>
    
<span data-ttu-id="20238-112">传入消息传递到的消息存储时，发生此事件的方法调用顺序如下所示：</span><span class="sxs-lookup"><span data-stu-id="20238-112">The sequence of method calls that occurs when an incoming message is delivered to a message store is as follows:</span></span>
  
1. <span data-ttu-id="20238-113">MAPI 后台处理程序调用[IMsgStore::OpenEntry](imsgstore-openentry.md)与收件箱[EntryID](entryid.md)获取[IMAPIFolder](imapifolderimapicontainer.md)接口。</span><span class="sxs-lookup"><span data-stu-id="20238-113">The MAPI spooler calls [IMsgStore::OpenEntry](imsgstore-openentry.md) with the Inbox [EntryID](entryid.md) to get an [IMAPIFolder](imapifolderimapicontainer.md) interface.</span></span> 
    
2. <span data-ttu-id="20238-114">MAPI 后台处理程序调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)获取新消息对象。</span><span class="sxs-lookup"><span data-stu-id="20238-114">The MAPI spooler calls [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) to get a new message object.</span></span> 
    
3. <span data-ttu-id="20238-115">MAPI 后台处理程序将 message 对象传递到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="20238-115">The MAPI spooler passes the message object to the transport provider.</span></span>
    
4. <span data-ttu-id="20238-116">传输提供程序填入基础邮件系统中的数据消息的属性，并调用 message 对象的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="20238-116">The transport provider fills in the message's properties with data from the underlying messaging system and calls the message object's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
    
5. <span data-ttu-id="20238-117">消息存储提供程序使用其通知方法通知注册的客户端，已到达一个新的邮件。</span><span class="sxs-lookup"><span data-stu-id="20238-117">The message store provider uses its notification method to inform registered clients that a new message has arrived.</span></span>
    
6. <span data-ttu-id="20238-118">MAPI 后台处理程序调用的消息存储[IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)方法。</span><span class="sxs-lookup"><span data-stu-id="20238-118">The MAPI spooler calls the message store's [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md) method.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="20238-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20238-119">See also</span></span>



[<span data-ttu-id="20238-120">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="20238-120">Message Store Features</span></span>](message-store-features.md)

