---
title: 邮件提交模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4bcd19f6-c225-43ac-8c27-c46388e9097a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 653a9df6ec414aa18c44d8035a59f021d7cc19b8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776523"
---
# <a name="message-submission-model"></a><span data-ttu-id="2a4e4-103">邮件提交模型</span><span class="sxs-lookup"><span data-stu-id="2a4e4-103">Message Submission Model</span></span>

  
  
<span data-ttu-id="2a4e4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2a4e4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2a4e4-105">提交邮件被通过一系列调用从 MAPI 后台打印到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2a4e4-105">Message submission is accomplished by a series of calls from the MAPI spooler to the transport provider.</span></span> <span data-ttu-id="2a4e4-106">呼叫顺序编排会出现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2a4e4-106">The calls are sequenced as follows:</span></span>
  
1. <span data-ttu-id="2a4e4-107">MAPI 后台处理程序调用[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)，传递中[IMessage: IMAPIProp](imessageimapiprop.md)实例，以开始过程。</span><span class="sxs-lookup"><span data-stu-id="2a4e4-107">The MAPI spooler calls [IXPLogon::SubmitMessage](ixplogon-submitmessage.md), passing in an [IMessage : IMAPIProp](imessageimapiprop.md) instance, to begin the process.</span></span> 
    
2. <span data-ttu-id="2a4e4-108">传输提供程序然后放置引用值 — 传输定义的标识符在将来使用引用此消息 — **SubmitMessage**中引用的位置。</span><span class="sxs-lookup"><span data-stu-id="2a4e4-108">The transport provider then places a reference value — a transport-defined identifier used in future references to this message — in the location referenced in **SubmitMessage**.</span></span>
    
3. <span data-ttu-id="2a4e4-109">传输提供程序使用传递的**IMessage**实例访问邮件数据。</span><span class="sxs-lookup"><span data-stu-id="2a4e4-109">The transport provider accesses the message data by using the passed **IMessage** instance.</span></span> <span data-ttu-id="2a4e4-110">为其接受责任传递**IMessage**中每个收件人，传输提供程序将**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性，设置，然后返回。</span><span class="sxs-lookup"><span data-stu-id="2a4e4-110">For each recipient in the passed **IMessage** for which it accepts responsibility, the transport provider sets the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property, and then returns.</span></span>
    
4. <span data-ttu-id="2a4e4-111">传输提供程序可以使用[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法，以指示是否识别无法送达，任何收件人，或创建一个标准送达报告。</span><span class="sxs-lookup"><span data-stu-id="2a4e4-111">The transport provider can use the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method to indicate if it recognizes any recipients that cannot be delivered to, or to create a standard delivery report.</span></span> <span data-ttu-id="2a4e4-112">**StatusRecips**是已确定某些收件人不能传送到传输提供程序方便或其基础的消息系统的用户或客户端应用程序可能已接收的传递信息发现有用。</span><span class="sxs-lookup"><span data-stu-id="2a4e4-112">**StatusRecips** is a convenience for transport providers that have determined that some of the recipients cannot be delivered to or that have received delivery information from their underlying messaging system that the user or client application might find useful.</span></span> 
    
5. <span data-ttu-id="2a4e4-113">对[IXPLogon::EndMessage](ixplogon-endmessage.md)的 MAPI 后台处理程序的调用是最终的责任交付 MAPI 后台处理程序从到传输提供程序的邮件。</span><span class="sxs-lookup"><span data-stu-id="2a4e4-113">The MAPI spooler's call to [IXPLogon::EndMessage](ixplogon-endmessage.md) is the final responsibility hand-off for the message from the MAPI spooler to the transport provider.</span></span> 
    
6. <span data-ttu-id="2a4e4-114">MAPI 后台处理程序可以使用[IXPLogon::TransportNotify](ixplogon-transportnotify.md)取消**SubmitMessage**或**EndMessage**呼叫过程中处理的消息。</span><span class="sxs-lookup"><span data-stu-id="2a4e4-114">The MAPI spooler can use [IXPLogon::TransportNotify](ixplogon-transportnotify.md) to cancel message processing during the **SubmitMessage** or **EndMessage** calls.</span></span> 
    

