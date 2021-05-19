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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415115"
---
# <a name="message-reception-model"></a><span data-ttu-id="cf64a-103">邮件接收模型</span><span class="sxs-lookup"><span data-stu-id="cf64a-103">Message Reception Model</span></span>

  
  
<span data-ttu-id="cf64a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cf64a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cf64a-105">传输提供程序控制 MAPI 后台处理程序是否必须轮询它以接收传入的邮件，或者是否执行新邮件到达时对 MAPI 后台处理程序的调用。</span><span class="sxs-lookup"><span data-stu-id="cf64a-105">The transport provider controls whether the MAPI spooler must poll it for incoming mail or whether it performs a call back to the MAPI spooler when new mail arrives.</span></span> <span data-ttu-id="cf64a-106">传输提供程序在从 [IXPProvider：：TransportLogon](ixpprovider-transportlogon.md) 返回SP_LOGON_POLL请求轮询时设置该标志。</span><span class="sxs-lookup"><span data-stu-id="cf64a-106">The transport provider sets the SP_LOGON_POLL flag when it returns from [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) to request polling.</span></span> <span data-ttu-id="cf64a-107">否则，当传入邮件可用时，传输提供程序将使用[IMAPISupport：：SpoolerNotify。](imapisupport-spoolernotify.md)</span><span class="sxs-lookup"><span data-stu-id="cf64a-107">Otherwise, the transport provider uses [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) when incoming mail is available.</span></span> <span data-ttu-id="cf64a-108">在了解传入邮件可用后，MAPI 后台处理程序将打开一封新邮件，并要求传输提供程序将接收的邮件属性存储到该邮件中。</span><span class="sxs-lookup"><span data-stu-id="cf64a-108">After learning that incoming mail is available, the MAPI spooler opens a new message and asks the transport provider to store the received message properties into the message.</span></span> 
  
<span data-ttu-id="cf64a-109">此过程的工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="cf64a-109">This process works as follows:</span></span>
  
1. <span data-ttu-id="cf64a-110">可用消息由调用 **IMAPISupport：：SpoolerNotify** 的传输提供程序或调用 [IXPLogon：:P oll](ixplogon-poll.md)的 MAPI 后台处理程序指示。</span><span class="sxs-lookup"><span data-stu-id="cf64a-110">Available messages are indicated by either the transport provider calling **IMAPISupport::SpoolerNotify** or by the MAPI spooler calling [IXPLogon::Poll](ixplogon-poll.md).</span></span>
    
2. <span data-ttu-id="cf64a-111">MAPI 后台处理程序调用 [IXPLogon：：StartMessage](ixplogon-startmessage.md) 以启动此过程。</span><span class="sxs-lookup"><span data-stu-id="cf64a-111">The MAPI spooler calls [IXPLogon::StartMessage](ixplogon-startmessage.md) to initiate the process.</span></span> 
    
3. <span data-ttu-id="cf64a-112">传输提供程序在 **StartMessage** 中引用的位置中提供引用值。</span><span class="sxs-lookup"><span data-stu-id="cf64a-112">The transport provider places a reference value in the location referenced in **StartMessage**.</span></span> <span data-ttu-id="cf64a-113">这些引用值允许传输提供程序和 MAPI 后台处理程序在有多个要传递的邮件时跟踪正在处理的邮件。</span><span class="sxs-lookup"><span data-stu-id="cf64a-113">These reference values allow the transport provider and the MAPI spooler to keep track of which message is being processed when there are multiple messages to deliver.</span></span>
    
4. <span data-ttu-id="cf64a-114">传输提供程序将邮件数据存储到传递 [的 IMessage ： IMAPIProp](imessageimapiprop.md) 实例中。</span><span class="sxs-lookup"><span data-stu-id="cf64a-114">The transport provider stores the message data into the passed [IMessage : IMAPIProp](imessageimapiprop.md) instance.</span></span> 
    
5. <span data-ttu-id="cf64a-115">传输提供程序对 **IMessage** 实例调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)方法，然后从 **StartMessage 返回**。</span><span class="sxs-lookup"><span data-stu-id="cf64a-115">The transport provider calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the **IMessage** instance and returns from **StartMessage**.</span></span>
    
6. <span data-ttu-id="cf64a-116">如果必须停止邮件传递，MAPI 后台处理程序将调用[IXPLogon：：TransportNotify。](ixplogon-transportnotify.md)</span><span class="sxs-lookup"><span data-stu-id="cf64a-116">The MAPI spooler calls [IXPLogon::TransportNotify](ixplogon-transportnotify.md) if it must stop message delivery.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="cf64a-117">如果传输提供程序必须传递大量邮件，并且传输提供程序使用 **IMAPISupport：：SpoolerNotify** 而不是 **IXPLogon：:P oll，** 则应该注意不要过于频繁地调用 **SpoolerNotify，** 以便不会占用其他传输提供商的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="cf64a-117">If a transport provider must deliver a large number of messages and the transport provider is using **IMAPISupport::SpoolerNotify** instead of **IXPLogon::Poll**, care should be taken not to call **SpoolerNotify** too frequently in order not to deprive other transport providers of CPU time.</span></span> <span data-ttu-id="cf64a-118">MAPI 后台处理程序确实具有防止发生这种情况的逻辑，但通常 **，SpoolerNotify** 调用之间的间隔应长于传输提供程序处理一封邮件所花的时间。</span><span class="sxs-lookup"><span data-stu-id="cf64a-118">The MAPI spooler does have logic to prevent this from happening, but in general the interval between **SpoolerNotify** calls should be longer than the time it takes your transport provider to process one message.</span></span> <span data-ttu-id="cf64a-119">>，MAPI 后台处理程序可能不会立即处理传入邮件。</span><span class="sxs-lookup"><span data-stu-id="cf64a-119">> Also, the MAPI spooler may not process an incoming message immediately.</span></span> <span data-ttu-id="cf64a-120">MAPI 后台处理程序可能会要求传输提供程序在接收传入邮件之前执行其他任务。</span><span class="sxs-lookup"><span data-stu-id="cf64a-120">The MAPI spooler may ask the transport provider to perform other tasks before it receives the incoming message.</span></span> 
  

