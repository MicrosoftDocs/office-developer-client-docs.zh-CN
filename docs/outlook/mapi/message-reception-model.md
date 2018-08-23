---
title: 邮件接收模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d85d269e-2251-4399-9159-a2f47a85e3d1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8fbc09d9d79f88ef783b8effe7a24e4b35564cee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570371"
---
# <a name="message-reception-model"></a><span data-ttu-id="00370-103">邮件接收模型</span><span class="sxs-lookup"><span data-stu-id="00370-103">Message Reception Model</span></span>

  
  
<span data-ttu-id="00370-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="00370-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="00370-105">传输提供程序控制 MAPI 后台处理程序是否必须轮询其为传入邮件或新邮件到达时是否它执行回调到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="00370-105">The transport provider controls whether the MAPI spooler must poll it for incoming mail or whether it performs a call back to the MAPI spooler when new mail arrives.</span></span> <span data-ttu-id="00370-106">返回从[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)轮询请求时，传输提供程序设置 SP_LOGON_POLL 标志。</span><span class="sxs-lookup"><span data-stu-id="00370-106">The transport provider sets the SP_LOGON_POLL flag when it returns from [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) to request polling.</span></span> <span data-ttu-id="00370-107">否则，传输提供程序使用[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)传入邮件时可用。</span><span class="sxs-lookup"><span data-stu-id="00370-107">Otherwise, the transport provider uses [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) when incoming mail is available.</span></span> <span data-ttu-id="00370-108">学习传入邮件可用之后, MAPI 后台处理程序打开一个新邮件，并请求获得要向邮件存储收到的邮件属性的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="00370-108">After learning that incoming mail is available, the MAPI spooler opens a new message and asks the transport provider to store the received message properties into the message.</span></span> 
  
<span data-ttu-id="00370-109">此过程的工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="00370-109">This process works as follows:</span></span>
  
1. <span data-ttu-id="00370-110">通过调用**IMAPISupport::SpoolerNotify**任一传输的提供程序或 MAPI 后台处理程序调用[IXPLogon::Poll](ixplogon-poll.md)表示可用的邮件。</span><span class="sxs-lookup"><span data-stu-id="00370-110">Available messages are indicated by either the transport provider calling **IMAPISupport::SpoolerNotify** or by the MAPI spooler calling [IXPLogon::Poll](ixplogon-poll.md).</span></span>
    
2. <span data-ttu-id="00370-111">MAPI 后台处理程序调用[IXPLogon::StartMessage](ixplogon-startmessage.md)要启动过程。</span><span class="sxs-lookup"><span data-stu-id="00370-111">The MAPI spooler calls [IXPLogon::StartMessage](ixplogon-startmessage.md) to initiate the process.</span></span> 
    
3. <span data-ttu-id="00370-112">传输提供程序将引用值放在**StartMessage**中引用的位置。</span><span class="sxs-lookup"><span data-stu-id="00370-112">The transport provider places a reference value in the location referenced in **StartMessage**.</span></span> <span data-ttu-id="00370-113">这些参考值允许传输提供程序和 MAPI 后台处理程序，以跟踪多个邮件传递时，正在处理的消息。</span><span class="sxs-lookup"><span data-stu-id="00370-113">These reference values allow the transport provider and the MAPI spooler to keep track of which message is being processed when there are multiple messages to deliver.</span></span>
    
4. <span data-ttu-id="00370-114">传输提供程序将消息数据存储到传递[IMessage: IMAPIProp](imessageimapiprop.md)实例。</span><span class="sxs-lookup"><span data-stu-id="00370-114">The transport provider stores the message data into the passed [IMessage : IMAPIProp](imessageimapiprop.md) instance.</span></span> 
    
5. <span data-ttu-id="00370-115">传输提供程序**IMessage**实例上调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，并返回**StartMessage**。</span><span class="sxs-lookup"><span data-stu-id="00370-115">The transport provider calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the **IMessage** instance and returns from **StartMessage**.</span></span>
    
6. <span data-ttu-id="00370-116">MAPI 后台处理程序调用[IXPLogon::TransportNotify](ixplogon-transportnotify.md) ，如果它必须停止邮件传递。</span><span class="sxs-lookup"><span data-stu-id="00370-116">The MAPI spooler calls [IXPLogon::TransportNotify](ixplogon-transportnotify.md) if it must stop message delivery.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="00370-117">如果传输提供程序必须提供大量的消息，而不**IXPLogon::Poll**传输提供程序使用**IMAPISupport::SpoolerNotify** ，应注意不呼叫**SpoolerNotify**过于频繁顺序不到导致丧失 CPU 时间其他传输提供的程序。</span><span class="sxs-lookup"><span data-stu-id="00370-117">If a transport provider must deliver a large number of messages and the transport provider is using **IMAPISupport::SpoolerNotify** instead of **IXPLogon::Poll**, care should be taken not to call **SpoolerNotify** too frequently in order not to deprive other transport providers of CPU time.</span></span> <span data-ttu-id="00370-118">MAPI 后台处理程序具有逻辑以防止此问题的发生，但通常**SpoolerNotify**呼叫之间的间隔应超过所用您的传输提供程序，以处理一条消息的时间。</span><span class="sxs-lookup"><span data-stu-id="00370-118">The MAPI spooler does have logic to prevent this from happening, but in general the interval between **SpoolerNotify** calls should be longer than the time it takes your transport provider to process one message.</span></span> <span data-ttu-id="00370-119">> 此外，MAPI 后台处理程序可能无法立即处理传入消息。</span><span class="sxs-lookup"><span data-stu-id="00370-119">> Also, the MAPI spooler may not process an incoming message immediately.</span></span> <span data-ttu-id="00370-120">MAPI 后台处理程序可能会要求要执行其他任务之前收到的传入消息的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="00370-120">The MAPI spooler may ask the transport provider to perform other tasks before it receives the incoming message.</span></span> 
  

