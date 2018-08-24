---
title: 传输提供程序和 MAPI 后台处理程序操作模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b0f8d8f0-fed7-4a7c-bc40-e935f159591d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 26d9982248fde015a584eb79cc248bafc5afc6bb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594031"
---
# <a name="transport-provider-and-mapi-spooler-operational-model"></a><span data-ttu-id="fc9ee-103">传输提供程序和 MAPI 后台处理程序操作模型</span><span class="sxs-lookup"><span data-stu-id="fc9ee-103">Transport Provider and MAPI Spooler Operational Model</span></span>

  
  
<span data-ttu-id="fc9ee-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fc9ee-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fc9ee-105">传输提供程序初始化、 启动、 处理、 关机和取消初始化通过一系列调用从 MAPI 后台打印到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-105">Transport provider initialization, startup, processing, shutdown and deinitialization are accomplished by a series of calls from the MAPI spooler to the transport provider.</span></span> <span data-ttu-id="fc9ee-106">呼叫顺序编排会出现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fc9ee-106">The calls are sequenced as follows:</span></span>
  
1. <span data-ttu-id="fc9ee-107">MAPI 后台处理程序调用[XPProviderInit](xpproviderinit.md)函数，将支持对象传递，获取提供商对象，并检查传输提供程序和 MAPI 后台处理程序支持兼容的 MAPI 版本号。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-107">The MAPI spooler calls the [XPProviderInit](xpproviderinit.md) function, passes a support object, gets the provider object, and checks that the transport provider and MAPI spooler support a compatible range of MAPI version numbers.</span></span> 
    
2. <span data-ttu-id="fc9ee-108">MAPI 后台处理程序调用的[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)方法[IXPProvider: IUnknown](ixpprovideriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-108">The MAPI spooler calls the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method of the [IXPProvider : IUnknown](ixpprovideriunknown.md) interface.</span></span> <span data-ttu-id="fc9ee-109">MAPI 后台处理程序和配置文件的当前节中的凭据与传输提供程序之间建立会话。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-109">A session is established between the MAPI spooler and the transport provider with the credentials in the current section of the profile.</span></span> <span data-ttu-id="fc9ee-110">传输提供程序返回登录对象。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-110">The transport provider returns a logon object.</span></span> 
    
3. <span data-ttu-id="fc9ee-111">MAPI 后台处理程序调用[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-111">The MAPI spooler calls the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> <span data-ttu-id="fc9ee-112">传输提供程序返回唯一标识符 (Uid) 及其将接受的电子邮件地址类型的列表。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-112">The transport provider returns a list of the unique identifiers (UIDs) and email address types it will accept.</span></span> 
    
4. <span data-ttu-id="fc9ee-113">传输提供程序调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法来创建 MAPI 状态表中其所在行。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-113">The transport provider calls the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method to create its row in the MAPI status table.</span></span> 
    
5. <span data-ttu-id="fc9ee-114">MAPI 后台处理程序调用[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法来启用邮件的传输和接收。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-114">The MAPI spooler calls the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method to enable message transmission and reception.</span></span> 
    
6. <span data-ttu-id="fc9ee-115">如果请求**TransportLogon**呼叫其返回传输提供程序，MAPI 后台处理程序定期调用[IXPLogon::Idle](ixplogon-idle.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-115">If requested by the transport provider in its return for the **TransportLogon** call, the MAPI spooler periodically calls the [IXPLogon::Idle](ixplogon-idle.md) method.</span></span> <span data-ttu-id="fc9ee-116">如果传输提供程序需要轮询新邮件基础邮件系统或执行其他低优先级任务有用空闲时间处理。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-116">Idle processing is useful if the transport provider needs to poll the underlying messaging system for new messages or perform other low-priority tasks.</span></span> 
    
7. <span data-ttu-id="fc9ee-117">MAPI 后台处理程序和传输提供程序发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-117">The MAPI spooler and transport provider send and receive messages.</span></span> <span data-ttu-id="fc9ee-118">有关详细信息，请参阅[消息提交模型](message-submission-model.md)和[消息接收模型](message-reception-model.md)。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-118">For more information, see [Message Submission Model](message-submission-model.md) and [Message Reception Model](message-reception-model.md).</span></span> <span data-ttu-id="fc9ee-119">MAPI 后台处理程序传输请求提供服务，并支持、 消息和附件对象上调用。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-119">The MAPI spooler services transport requests and calls on support, message, and attachment objects.</span></span>
    
8. <span data-ttu-id="fc9ee-120">MAPI 后台处理程序调用**TransportNotify**方法来禁用邮件传输和接收。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-120">The MAPI spooler calls the **TransportNotify** method to disable message transmission and reception.</span></span> 
    
9. <span data-ttu-id="fc9ee-121">MAPI 后台处理程序释放的登录和提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-121">The MAPI spooler releases the logon and provider objects.</span></span> <span data-ttu-id="fc9ee-122">有关详细信息，请参阅[IXPProvider::Shutdown](ixpprovider-shutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fc9ee-122">For more information, see the [IXPProvider::Shutdown](ixpprovider-shutdown.md) method.</span></span> 
    

