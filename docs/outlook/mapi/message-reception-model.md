---
title: 邮件接收模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d85d269e-2251-4399-9159-a2f47a85e3d1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 487598374f15300cc8b899a50d74b535b5a33c91
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356943"
---
# <a name="message-reception-model"></a><span data-ttu-id="326bc-103">邮件接收模型</span><span class="sxs-lookup"><span data-stu-id="326bc-103">Message Reception Model</span></span>

  
  
<span data-ttu-id="326bc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="326bc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="326bc-105">传输提供程序控制 MAPI 后台处理程序是否必须在收到邮件时对其进行轮询, 或者是否在新邮件到达时对 mapi 后台处理程序执行回调。</span><span class="sxs-lookup"><span data-stu-id="326bc-105">The transport provider controls whether the MAPI spooler must poll it for incoming mail or whether it performs a call back to the MAPI spooler when new mail arrives.</span></span> <span data-ttu-id="326bc-106">传输提供程序在从[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)返回到请求轮询时设置 SP_LOGON_POLL 标志。</span><span class="sxs-lookup"><span data-stu-id="326bc-106">The transport provider sets the SP_LOGON_POLL flag when it returns from [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) to request polling.</span></span> <span data-ttu-id="326bc-107">否则, 在传入邮件可用时, 传输提供程序将使用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md) 。</span><span class="sxs-lookup"><span data-stu-id="326bc-107">Otherwise, the transport provider uses [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) when incoming mail is available.</span></span> <span data-ttu-id="326bc-108">了解传入邮件可用后, MAPI 后台处理程序将打开一封新邮件, 并要求传输提供程序将接收到的邮件属性存储到邮件中。</span><span class="sxs-lookup"><span data-stu-id="326bc-108">After learning that incoming mail is available, the MAPI spooler opens a new message and asks the transport provider to store the received message properties into the message.</span></span> 
  
<span data-ttu-id="326bc-109">此过程的工作方式如下所示:</span><span class="sxs-lookup"><span data-stu-id="326bc-109">This process works as follows:</span></span>
  
1. <span data-ttu-id="326bc-110">可用的邮件由传输提供程序调用**IMAPISupport:: SpoolerNotify**或 MAPI 后台处理程序调用[IXPLogon::P oll](ixplogon-poll.md)。</span><span class="sxs-lookup"><span data-stu-id="326bc-110">Available messages are indicated by either the transport provider calling **IMAPISupport::SpoolerNotify** or by the MAPI spooler calling [IXPLogon::Poll](ixplogon-poll.md).</span></span>
    
2. <span data-ttu-id="326bc-111">MAPI 后台处理程序调用[IXPLogon:: StartMessage](ixplogon-startmessage.md)以启动进程。</span><span class="sxs-lookup"><span data-stu-id="326bc-111">The MAPI spooler calls [IXPLogon::StartMessage](ixplogon-startmessage.md) to initiate the process.</span></span> 
    
3. <span data-ttu-id="326bc-112">传输提供程序将引用值放在**StartMessage**中引用的位置。</span><span class="sxs-lookup"><span data-stu-id="326bc-112">The transport provider places a reference value in the location referenced in **StartMessage**.</span></span> <span data-ttu-id="326bc-113">这些引用值允许传输提供程序和 MAPI 后台处理程序在有多个要传递的邮件时跟踪正在处理的邮件。</span><span class="sxs-lookup"><span data-stu-id="326bc-113">These reference values allow the transport provider and the MAPI spooler to keep track of which message is being processed when there are multiple messages to deliver.</span></span>
    
4. <span data-ttu-id="326bc-114">传输提供程序将邮件数据存储到传递的[IMessage: IMAPIProp](imessageimapiprop.md)实例中。</span><span class="sxs-lookup"><span data-stu-id="326bc-114">The transport provider stores the message data into the passed [IMessage : IMAPIProp](imessageimapiprop.md) instance.</span></span> 
    
5. <span data-ttu-id="326bc-115">传输提供程序对**IMessage**实例调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法, 并从**StartMessage**返回。</span><span class="sxs-lookup"><span data-stu-id="326bc-115">The transport provider calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the **IMessage** instance and returns from **StartMessage**.</span></span>
    
6. <span data-ttu-id="326bc-116">MAPI 后台处理程序调用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md) (如果它必须停止邮件传递)。</span><span class="sxs-lookup"><span data-stu-id="326bc-116">The MAPI spooler calls [IXPLogon::TransportNotify](ixplogon-transportnotify.md) if it must stop message delivery.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="326bc-117">如果传输提供程序必须传递大量邮件, 而传输提供程序正在使用**IMAPISupport:: SpoolerNotify**而不是**IXPLogon::P oll**, 则应谨慎地将**SpoolerNotify**调用得过于频繁, 以便不会deprive 其他传输提供程序的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="326bc-117">If a transport provider must deliver a large number of messages and the transport provider is using **IMAPISupport::SpoolerNotify** instead of **IXPLogon::Poll**, care should be taken not to call **SpoolerNotify** too frequently in order not to deprive other transport providers of CPU time.</span></span> <span data-ttu-id="326bc-118">MAPI 后台处理程序具有防止发生这种情况的逻辑, 但一般情况下, **SpoolerNotify**呼叫之间的时间间隔应长于您的传输提供程序处理一封邮件所需的时间。</span><span class="sxs-lookup"><span data-stu-id="326bc-118">The MAPI spooler does have logic to prevent this from happening, but in general the interval between **SpoolerNotify** calls should be longer than the time it takes your transport provider to process one message.</span></span> <span data-ttu-id="326bc-119">> 此外, MAPI 后台处理程序可能不会立即处理传入的邮件。</span><span class="sxs-lookup"><span data-stu-id="326bc-119">> Also, the MAPI spooler may not process an incoming message immediately.</span></span> <span data-ttu-id="326bc-120">MAPI 后台处理程序可能要求传输提供程序在接收传入邮件之前执行其他任务。</span><span class="sxs-lookup"><span data-stu-id="326bc-120">The MAPI spooler may ask the transport provider to perform other tasks before it receives the incoming message.</span></span> 
  

