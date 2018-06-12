---
title: 通过使用 MAPI 发送消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3edfbfff-ea15-4926-bf0f-47137251d921
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 36de3b70b0ab7b16f8abed85bbd0983224e00568
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778735"
---
# <a name="sending-messages-by-using-mapi"></a><span data-ttu-id="9d52e-103">通过使用 MAPI 发送消息</span><span class="sxs-lookup"><span data-stu-id="9d52e-103">Sending Messages by Using MAPI</span></span>

  
  
<span data-ttu-id="9d52e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9d52e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9d52e-105">客户端应用程序调用[IMessage::SubmitMessage](imessage-submitmessage.md)方法发送消息。</span><span class="sxs-lookup"><span data-stu-id="9d52e-105">Client applications call the [IMessage::SubmitMessage](imessage-submitmessage.md) method to send a message.</span></span> <span data-ttu-id="9d52e-106">**SubmitMessage**调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)保存邮件之前将控制转到以下任意 MAPI 后台处理程序或直接到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="9d52e-106">**SubmitMessage** calls [IMAPIProp::SaveChanges](imapiprop-savechanges.md) to save the message before transferring control to either the MAPI spooler or directly to a transport provider.</span></span> 
  
<span data-ttu-id="9d52e-107">如果发生下列任一情况，MAPI 后台处理程序接收的消息：</span><span class="sxs-lookup"><span data-stu-id="9d52e-107">The MAPI spooler receives the message if any of the following occur:</span></span>
  
- <span data-ttu-id="9d52e-108">未紧密耦合的消息存储提供程序和传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="9d52e-108">The message store provider and transport provider are not tightly coupled.</span></span>
    
- <span data-ttu-id="9d52e-109">邮件需要预处理。</span><span class="sxs-lookup"><span data-stu-id="9d52e-109">The message requires preprocessing.</span></span>
    
- <span data-ttu-id="9d52e-110">紧密耦合的消息存储和传输无法处理所有向其发送邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="9d52e-110">The tightly coupled message store and transport cannot handle all of the recipients to whom the message is addressed.</span></span>
    
<span data-ttu-id="9d52e-111">紧密耦合的消息存储必须考虑邮件状态之前其呈现给 MAPI 后台处理程序下载到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="9d52e-111">A tightly coupled message store must take into account a message's status before it presents it to the MAPI spooler to be downloaded to a transport provider.</span></span> <span data-ttu-id="9d52e-112">有其中显示一条消息，可能需要 MAPI 后台处理程序，但 MAPI 后台处理程序应真正不涉及的情况。</span><span class="sxs-lookup"><span data-stu-id="9d52e-112">There are situations where a message may appear to require the MAPI spooler, but the MAPI spooler should really not be involved.</span></span>
  
<span data-ttu-id="9d52e-113">例如，假设其中用户提交收件箱中的邮件的情况。</span><span class="sxs-lookup"><span data-stu-id="9d52e-113">For example, consider the situation where a user submits a message from the Inbox.</span></span> <span data-ttu-id="9d52e-114">客户端使用紧密耦合的存储和传输。</span><span class="sxs-lookup"><span data-stu-id="9d52e-114">The client is using a tightly coupled store and transport.</span></span> <span data-ttu-id="9d52e-115">如果紧密耦合的消息存储使用的消息的位置用作唯一条件来决定允许 MAPI 后台处理程序有关处理邮件，MAPI 后台处理程序始终会收到消息。</span><span class="sxs-lookup"><span data-stu-id="9d52e-115">If the tightly coupled message store uses the message's location as the sole criteria for deciding about whether or not to allow the MAPI spooler to handle the message, the MAPI spooler will always receive the message.</span></span> <span data-ttu-id="9d52e-116">若要避免这种类型的问题，紧密耦合的消息存储必须检查邮件状态除了邮件位置。</span><span class="sxs-lookup"><span data-stu-id="9d52e-116">To avoid this kind of problem, a tightly coupled message store must check the message status in addition to message location.</span></span> <span data-ttu-id="9d52e-117">具体而言，传输提供程序不应请求 MAPI 后台处理程序下载主动提交任何消息。</span><span class="sxs-lookup"><span data-stu-id="9d52e-117">Specifically, the transport provider should not request that the MAPI spooler download any message that is actively submitted.</span></span>
  
<span data-ttu-id="9d52e-118">邮件传输过程涉及的消息存储提供程序、 一个或多个传输提供程序和 MAPI。</span><span class="sxs-lookup"><span data-stu-id="9d52e-118">The message transmission process involves the message store provider, one or more transport providers, and MAPI.</span></span> <span data-ttu-id="9d52e-119">本节中的主题提供有关邮件传输过程中的特定角色的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="9d52e-119">The topics in this section provide detailed information about specific roles in the message transmission process.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d52e-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d52e-120">See also</span></span>



[<span data-ttu-id="9d52e-121">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="9d52e-121">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="9d52e-122">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="9d52e-122">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)

