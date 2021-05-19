---
title: 邮件提交模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4bcd19f6-c225-43ac-8c27-c46388e9097a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 090a765fd6c758e5f146caa0e7f36276b052f69e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421121"
---
# <a name="message-submission-model"></a><span data-ttu-id="c88a8-103">邮件提交模型</span><span class="sxs-lookup"><span data-stu-id="c88a8-103">Message Submission Model</span></span>

  
  
<span data-ttu-id="c88a8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c88a8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c88a8-105">邮件提交是通过从 MAPI 后台处理程序到传输提供程序的一系列调用完成的。</span><span class="sxs-lookup"><span data-stu-id="c88a8-105">Message submission is accomplished by a series of calls from the MAPI spooler to the transport provider.</span></span> <span data-ttu-id="c88a8-106">调用顺序如下：</span><span class="sxs-lookup"><span data-stu-id="c88a8-106">The calls are sequenced as follows:</span></span>
  
1. <span data-ttu-id="c88a8-107">MAPI 后台处理程序调用 [IXPLogon：：SubmitMessage，](ixplogon-submitmessage.md)以传递 [IMessage ： IMAPIProp](imessageimapiprop.md) 实例，以开始此过程。</span><span class="sxs-lookup"><span data-stu-id="c88a8-107">The MAPI spooler calls [IXPLogon::SubmitMessage](ixplogon-submitmessage.md), passing in an [IMessage : IMAPIProp](imessageimapiprop.md) instance, to begin the process.</span></span> 
    
2. <span data-ttu-id="c88a8-108">然后，传输提供程序将在 **SubmitMessage** 中引用的位置中提供引用值（在以后引用此邮件时所使用的传输定义标识符）。</span><span class="sxs-lookup"><span data-stu-id="c88a8-108">The transport provider then places a reference value — a transport-defined identifier used in future references to this message — in the location referenced in **SubmitMessage**.</span></span>
    
3. <span data-ttu-id="c88a8-109">传输提供程序使用传递的 **IMessage 实例访问邮件** 数据。</span><span class="sxs-lookup"><span data-stu-id="c88a8-109">The transport provider accesses the message data by using the passed **IMessage** instance.</span></span> <span data-ttu-id="c88a8-110">对于它接受责任的传递 **IMessage** 中的每个收件人，传输提供程序将 **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性，然后返回。</span><span class="sxs-lookup"><span data-stu-id="c88a8-110">For each recipient in the passed **IMessage** for which it accepts responsibility, the transport provider sets the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property, and then returns.</span></span>
    
4. <span data-ttu-id="c88a8-111">传输提供程序可以使用 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法来指示它识别无法传递到的任何收件人，或创建标准送达报告。</span><span class="sxs-lookup"><span data-stu-id="c88a8-111">The transport provider can use the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method to indicate if it recognizes any recipients that cannot be delivered to, or to create a standard delivery report.</span></span> <span data-ttu-id="c88a8-112">**StatusRecips** 是一种便捷方式，传输提供程序已确定某些收件人无法传递到用户或客户端应用程序可能认为有用的基础邮件系统，或者接收了来自其基础邮件系统的传递信息。</span><span class="sxs-lookup"><span data-stu-id="c88a8-112">**StatusRecips** is a convenience for transport providers that have determined that some of the recipients cannot be delivered to or that have received delivery information from their underlying messaging system that the user or client application might find useful.</span></span> 
    
5. <span data-ttu-id="c88a8-113">MAPI 后台处理程序对 [IXPLogon：：EndMessage](ixplogon-endmessage.md) 的调用是最终负责将邮件从 MAPI 后台处理程序传输给传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="c88a8-113">The MAPI spooler's call to [IXPLogon::EndMessage](ixplogon-endmessage.md) is the final responsibility hand-off for the message from the MAPI spooler to the transport provider.</span></span> 
    
6. <span data-ttu-id="c88a8-114">MAPI 后台处理程序可以使用 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) 在 **SubmitMessage** 或 **EndMessage** 调用期间取消邮件处理。</span><span class="sxs-lookup"><span data-stu-id="c88a8-114">The MAPI spooler can use [IXPLogon::TransportNotify](ixplogon-transportnotify.md) to cancel message processing during the **SubmitMessage** or **EndMessage** calls.</span></span> 
    

