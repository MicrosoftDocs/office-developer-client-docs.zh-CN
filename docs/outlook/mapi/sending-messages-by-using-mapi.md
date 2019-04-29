---
title: 使用 MAPI 发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3edfbfff-ea15-4926-bf0f-47137251d921
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf6324b89f06ef7f0553d3de1eaa24ae31a329ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438720"
---
# <a name="sending-messages-by-using-mapi"></a><span data-ttu-id="be492-103">使用 MAPI 发送邮件</span><span class="sxs-lookup"><span data-stu-id="be492-103">Sending Messages by Using MAPI</span></span>

  
  
<span data-ttu-id="be492-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="be492-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="be492-105">客户端应用程序调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法以发送邮件。</span><span class="sxs-lookup"><span data-stu-id="be492-105">Client applications call the [IMessage::SubmitMessage](imessage-submitmessage.md) method to send a message.</span></span> <span data-ttu-id="be492-106">**SubmitMessage**调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)以在将控制转移到 MAPI 后台处理程序或直接转到传输提供程序之前保存邮件。</span><span class="sxs-lookup"><span data-stu-id="be492-106">**SubmitMessage** calls [IMAPIProp::SaveChanges](imapiprop-savechanges.md) to save the message before transferring control to either the MAPI spooler or directly to a transport provider.</span></span> 
  
<span data-ttu-id="be492-107">如果发生以下任一情况, MAPI 后台处理程序将收到邮件:</span><span class="sxs-lookup"><span data-stu-id="be492-107">The MAPI spooler receives the message if any of the following occur:</span></span>
  
- <span data-ttu-id="be492-108">邮件存储区提供程序和传输提供程序未紧密结合。</span><span class="sxs-lookup"><span data-stu-id="be492-108">The message store provider and transport provider are not tightly coupled.</span></span>
    
- <span data-ttu-id="be492-109">邮件需要进行预处理。</span><span class="sxs-lookup"><span data-stu-id="be492-109">The message requires preprocessing.</span></span>
    
- <span data-ttu-id="be492-110">紧密耦合邮件存储和传输无法处理邮件所针对的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="be492-110">The tightly coupled message store and transport cannot handle all of the recipients to whom the message is addressed.</span></span>
    
<span data-ttu-id="be492-111">紧密耦合邮件存储必须先考虑邮件的状态, 然后才能将其显示到要下载到传输提供程序的 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="be492-111">A tightly coupled message store must take into account a message's status before it presents it to the MAPI spooler to be downloaded to a transport provider.</span></span> <span data-ttu-id="be492-112">在某些情况下, 可能会出现需要 mapi 后台处理程序的邮件, 但实际上不会涉及 mapi 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="be492-112">There are situations where a message may appear to require the MAPI spooler, but the MAPI spooler should really not be involved.</span></span>
  
<span data-ttu-id="be492-113">例如, 考虑用户从收件箱提交邮件的情况。</span><span class="sxs-lookup"><span data-stu-id="be492-113">For example, consider the situation where a user submits a message from the Inbox.</span></span> <span data-ttu-id="be492-114">客户端使用紧密耦合的存储和传输。</span><span class="sxs-lookup"><span data-stu-id="be492-114">The client is using a tightly coupled store and transport.</span></span> <span data-ttu-id="be492-115">如果紧耦合邮件存储区使用邮件的位置作为确定是否允许 mapi 后台处理程序处理邮件的唯一条件, MAPI 后台处理程序将始终接收邮件。</span><span class="sxs-lookup"><span data-stu-id="be492-115">If the tightly coupled message store uses the message's location as the sole criteria for deciding about whether or not to allow the MAPI spooler to handle the message, the MAPI spooler will always receive the message.</span></span> <span data-ttu-id="be492-116">若要避免这种问题, 紧耦合邮件存储区必须先检查邮件状态以及邮件位置。</span><span class="sxs-lookup"><span data-stu-id="be492-116">To avoid this kind of problem, a tightly coupled message store must check the message status in addition to message location.</span></span> <span data-ttu-id="be492-117">特别是, 传输提供程序不应请求 MAPI 后台处理程序下载任何主动提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="be492-117">Specifically, the transport provider should not request that the MAPI spooler download any message that is actively submitted.</span></span>
  
<span data-ttu-id="be492-118">邮件传输过程涉及邮件存储提供程序、一个或多个传输提供程序和 MAPI。</span><span class="sxs-lookup"><span data-stu-id="be492-118">The message transmission process involves the message store provider, one or more transport providers, and MAPI.</span></span> <span data-ttu-id="be492-119">本节中的主题提供有关邮件传输过程中特定角色的详细信息。</span><span class="sxs-lookup"><span data-stu-id="be492-119">The topics in this section provide detailed information about specific roles in the message transmission process.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="be492-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be492-120">See also</span></span>



[<span data-ttu-id="be492-121">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="be492-121">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="be492-122">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="be492-122">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)

