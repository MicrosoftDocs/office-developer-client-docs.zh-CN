---
title: 发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4fa47824-b4ef-41e1-9096-c1b1cdacd7ac
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6845c3d86fb3d34119a296ebbae76a7322d7d8c1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590909"
---
# <a name="sending-a-message"></a><span data-ttu-id="fa9b2-103">发送邮件</span><span class="sxs-lookup"><span data-stu-id="fa9b2-103">Sending a Message</span></span>

  
  
<span data-ttu-id="fa9b2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fa9b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fa9b2-105">当您准备要发送消息时，调用其[IMessage::SubmitMessage](imessage-submitmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-105">When you are ready to send a message, call its [IMessage::SubmitMessage](imessage-submitmessage.md) method.</span></span> <span data-ttu-id="fa9b2-106">**SubmitMessage**传出队列中放置邮件和消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_SUBMIT 标志。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-106">**SubmitMessage** places the message in the outgoing queue and sets the MSGFLAG_SUBMIT flag in the message's **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="fa9b2-107">消息存储提供程序，如果紧密耦合到传输提供程序，则将直接向其传递到邮件系统的传输邮件。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-107">The message store provider, if tightly coupled to a transport provider, gives the message directly to the transport which delivers it to the messaging system.</span></span> <span data-ttu-id="fa9b2-108">如果不紧密耦合的消息存储提供程序通知传出队列已更改 MAPI 后台处理程序和 MAPI 后台处理程序将邮件传输到适当的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-108">If not tightly coupled, the message store provider informs the MAPI spooler that the outgoing queue has changed and the MAPI spooler transfers the message to an appropriate transport provider.</span></span>
  
<span data-ttu-id="fa9b2-109">如果允许用户取消发送操作，请调用[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-109">If you allow users to cancel a send operation, call [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) to implement this feature.</span></span> <span data-ttu-id="fa9b2-110">**AbortSubmit**传出队列中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-110">**AbortSubmit** removes the message from the outgoing queue.</span></span> <span data-ttu-id="fa9b2-111">可以允许用户停止从最新动态直到消息提供给基础邮件系统发送。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-111">Users can be allowed to stop a send from happening until the message is given to the underlying messaging system.</span></span> 
  
<span data-ttu-id="fa9b2-112">如果**SubmitMessage**返回 MAPI_E_CORRUPT_DATA，假定正在发送的数据是否立即丢失。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-112">If **SubmitMessage** returns MAPI_E_CORRUPT_DATA, assume that the data being sent is now lost.</span></span> <span data-ttu-id="fa9b2-113">尝试发送第二次之前, 重新通过调用[IMAPIProp::SetProps](imapiprop-setprops.md)和[IMAPIProp::SaveChanges](imapiprop-savechanges.md)编写邮件。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-113">Before attempting to send a second time, re-write the message by calling [IMAPIProp::SetProps](imapiprop-setprops.md) and [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span> <span data-ttu-id="fa9b2-114">如果这些**IMAPIProp**呼叫失败或**SubmitMessage**失败第二次向用户显示错误。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-114">Display an error to the user if these **IMAPIProp** calls fail or if **SubmitMessage** fails a second time.</span></span> 
  
<span data-ttu-id="fa9b2-115">成功调用**SubmitMessage**之后, 释放已分配给的收件人列表的任何内存和释放邮件及其附件。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-115">After a successful call to **SubmitMessage**, free any memory that was allocated for the recipient list and release the message and its attachments.</span></span> <span data-ttu-id="fa9b2-116">已发送一条消息，一旦 MAPI 不允许这些对象的指针上任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-116">Once a message has been sent, MAPI does not permit any further operations on the pointers for these objects.</span></span> <span data-ttu-id="fa9b2-117">一个例外调用**IUnknown::Release**。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-117">The one exception is calling **IUnknown::Release**.</span></span> <span data-ttu-id="fa9b2-118">允许没有任何其他呼叫，因为许多消息存储提供程序使失效的已发送邮件的项标识符。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-118">No other calls are allowed because many message store providers invalidate entry identifiers for messages that have been sent.</span></span>
  

