---
title: 发送信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4fa47824-b4ef-41e1-9096-c1b1cdacd7ac
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 01fd66033da0f24948913f47a752d555eca655fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423620"
---
# <a name="sending-a-message"></a><span data-ttu-id="83282-103">发送信息</span><span class="sxs-lookup"><span data-stu-id="83282-103">Sending a Message</span></span>

  
  
<span data-ttu-id="83282-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="83282-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="83282-105">当您准备好发送邮件时, 请调用其[IMessage:: SubmitMessage](imessage-submitmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="83282-105">When you are ready to send a message, call its [IMessage::SubmitMessage](imessage-submitmessage.md) method.</span></span> <span data-ttu-id="83282-106">**SubmitMessage**将邮件放入传出队列, 并在邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_SUBMIT 标志。</span><span class="sxs-lookup"><span data-stu-id="83282-106">**SubmitMessage** places the message in the outgoing queue and sets the MSGFLAG_SUBMIT flag in the message's **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="83282-107">邮件存储提供程序 (如果与传输提供程序紧密结合) 将直接向传输提供邮件, 并将邮件传递到邮件系统。</span><span class="sxs-lookup"><span data-stu-id="83282-107">The message store provider, if tightly coupled to a transport provider, gives the message directly to the transport which delivers it to the messaging system.</span></span> <span data-ttu-id="83282-108">如果未紧密结合, 邮件存储提供程序将通知 mapi 后台处理程序传出队列已更改, mapi 后台处理程序将邮件传输到适当的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="83282-108">If not tightly coupled, the message store provider informs the MAPI spooler that the outgoing queue has changed and the MAPI spooler transfers the message to an appropriate transport provider.</span></span>
  
<span data-ttu-id="83282-109">如果允许用户取消发送操作, 请调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)以实现此功能。</span><span class="sxs-lookup"><span data-stu-id="83282-109">If you allow users to cancel a send operation, call [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) to implement this feature.</span></span> <span data-ttu-id="83282-110">**AbortSubmit**从传出队列中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="83282-110">**AbortSubmit** removes the message from the outgoing queue.</span></span> <span data-ttu-id="83282-111">在向基础邮件系统提供邮件之前, 可以允许用户停止发送。</span><span class="sxs-lookup"><span data-stu-id="83282-111">Users can be allowed to stop a send from happening until the message is given to the underlying messaging system.</span></span> 
  
<span data-ttu-id="83282-112">如果**SubmitMessage**返回 MAPI_E_CORRUPT_DATA, 则假定正在发送的数据现在已丢失。</span><span class="sxs-lookup"><span data-stu-id="83282-112">If **SubmitMessage** returns MAPI_E_CORRUPT_DATA, assume that the data being sent is now lost.</span></span> <span data-ttu-id="83282-113">在尝试发送第二次之前, 请通过调用[IMAPIProp:: SetProps](imapiprop-setprops.md)和[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)来重新编写邮件。</span><span class="sxs-lookup"><span data-stu-id="83282-113">Before attempting to send a second time, re-write the message by calling [IMAPIProp::SetProps](imapiprop-setprops.md) and [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span> <span data-ttu-id="83282-114">如果这些**IMAPIProp**调用失败, 或者**SubmitMessage**第二次失败, 则向用户显示一个错误。</span><span class="sxs-lookup"><span data-stu-id="83282-114">Display an error to the user if these **IMAPIProp** calls fail or if **SubmitMessage** fails a second time.</span></span> 
  
<span data-ttu-id="83282-115">成功调用**SubmitMessage**后, 释放为收件人列表分配的所有内存并释放邮件及其附件。</span><span class="sxs-lookup"><span data-stu-id="83282-115">After a successful call to **SubmitMessage**, free any memory that was allocated for the recipient list and release the message and its attachments.</span></span> <span data-ttu-id="83282-116">一旦发送了邮件, MAPI 就不允许对这些对象的指针进行任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="83282-116">Once a message has been sent, MAPI does not permit any further operations on the pointers for these objects.</span></span> <span data-ttu-id="83282-117">一个例外是调用**IUnknown:: Release**。</span><span class="sxs-lookup"><span data-stu-id="83282-117">The one exception is calling **IUnknown::Release**.</span></span> <span data-ttu-id="83282-118">由于许多邮件存储提供程序对已发送邮件的条目标识符无效, 因此不允许任何其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="83282-118">No other calls are allowed because many message store providers invalidate entry identifiers for messages that have been sent.</span></span>
  

