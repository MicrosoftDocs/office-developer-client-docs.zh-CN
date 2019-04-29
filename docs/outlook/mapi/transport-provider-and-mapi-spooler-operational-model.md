---
title: 传输提供程序和 MAPI 后台处理程序操作模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b0f8d8f0-fed7-4a7c-bc40-e935f159591d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5987111844f087801c63989b905992900ff6909c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426623"
---
# <a name="transport-provider-and-mapi-spooler-operational-model"></a><span data-ttu-id="77e6c-103">传输提供程序和 MAPI 后台处理程序操作模型</span><span class="sxs-lookup"><span data-stu-id="77e6c-103">Transport Provider and MAPI Spooler Operational Model</span></span>

  
  
<span data-ttu-id="77e6c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="77e6c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="77e6c-105">传输提供程序初始化、启动、处理、关闭和 deinitialization 都是通过从 MAPI 后台处理程序到传输提供程序的一系列呼叫来完成的。</span><span class="sxs-lookup"><span data-stu-id="77e6c-105">Transport provider initialization, startup, processing, shutdown and deinitialization are accomplished by a series of calls from the MAPI spooler to the transport provider.</span></span> <span data-ttu-id="77e6c-106">这些调用的序列化如下所示:</span><span class="sxs-lookup"><span data-stu-id="77e6c-106">The calls are sequenced as follows:</span></span>
  
1. <span data-ttu-id="77e6c-107">MAPI 后台处理程序调用[XPProviderInit](xpproviderinit.md)函数, 传递支持对象, 获取 provider 对象, 并检查传输提供程序和 mapi 后台处理程序是否支持 mapi 版本号的兼容范围。</span><span class="sxs-lookup"><span data-stu-id="77e6c-107">The MAPI spooler calls the [XPProviderInit](xpproviderinit.md) function, passes a support object, gets the provider object, and checks that the transport provider and MAPI spooler support a compatible range of MAPI version numbers.</span></span> 
    
2. <span data-ttu-id="77e6c-108">MAPI 后台处理程序调用[IXPProvider: IUnknown](ixpprovideriunknown.md)接口的[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)方法。</span><span class="sxs-lookup"><span data-stu-id="77e6c-108">The MAPI spooler calls the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method of the [IXPProvider : IUnknown](ixpprovideriunknown.md) interface.</span></span> <span data-ttu-id="77e6c-109">在 MAPI 后台处理程序和传输提供程序之间, 将在配置文件的当前节中的凭据之间建立会话。</span><span class="sxs-lookup"><span data-stu-id="77e6c-109">A session is established between the MAPI spooler and the transport provider with the credentials in the current section of the profile.</span></span> <span data-ttu-id="77e6c-110">传输提供程序返回一个登录对象。</span><span class="sxs-lookup"><span data-stu-id="77e6c-110">The transport provider returns a logon object.</span></span> 
    
3. <span data-ttu-id="77e6c-111">MAPI 后台处理程序调用[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法。</span><span class="sxs-lookup"><span data-stu-id="77e6c-111">The MAPI spooler calls the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> <span data-ttu-id="77e6c-112">传输提供程序将返回它将接受的唯一标识符 (uid) 和电子邮件地址类型的列表。</span><span class="sxs-lookup"><span data-stu-id="77e6c-112">The transport provider returns a list of the unique identifiers (UIDs) and email address types it will accept.</span></span> 
    
4. <span data-ttu-id="77e6c-113">传输提供程序调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法来创建其在 MAPI 状态表中的行。</span><span class="sxs-lookup"><span data-stu-id="77e6c-113">The transport provider calls the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method to create its row in the MAPI status table.</span></span> 
    
5. <span data-ttu-id="77e6c-114">MAPI 后台处理程序调用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法来启用邮件传输和接收。</span><span class="sxs-lookup"><span data-stu-id="77e6c-114">The MAPI spooler calls the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method to enable message transmission and reception.</span></span> 
    
6. <span data-ttu-id="77e6c-115">如果传输提供程序在其返回的**TransportLogon**呼叫中请求, MAPI 后台处理程序将定期调用[IXPLogon:: Idle](ixplogon-idle.md)方法。</span><span class="sxs-lookup"><span data-stu-id="77e6c-115">If requested by the transport provider in its return for the **TransportLogon** call, the MAPI spooler periodically calls the [IXPLogon::Idle](ixplogon-idle.md) method.</span></span> <span data-ttu-id="77e6c-116">如果传输提供程序需要轮询基础邮件系统中的新邮件或执行其他低优先级任务, 空闲处理将非常有用。</span><span class="sxs-lookup"><span data-stu-id="77e6c-116">Idle processing is useful if the transport provider needs to poll the underlying messaging system for new messages or perform other low-priority tasks.</span></span> 
    
7. <span data-ttu-id="77e6c-117">MAPI 后台处理程序和传输提供程序发送和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="77e6c-117">The MAPI spooler and transport provider send and receive messages.</span></span> <span data-ttu-id="77e6c-118">有关详细信息, 请参阅[邮件提交模型](message-submission-model.md)和[邮件接收模型](message-reception-model.md)。</span><span class="sxs-lookup"><span data-stu-id="77e6c-118">For more information, see [Message Submission Model](message-submission-model.md) and [Message Reception Model](message-reception-model.md).</span></span> <span data-ttu-id="77e6c-119">MAPI 后台处理程序服务传输请求和对支持、消息和附件对象的调用。</span><span class="sxs-lookup"><span data-stu-id="77e6c-119">The MAPI spooler services transport requests and calls on support, message, and attachment objects.</span></span>
    
8. <span data-ttu-id="77e6c-120">MAPI 后台处理程序调用**TransportNotify**方法以禁用邮件传输和接收。</span><span class="sxs-lookup"><span data-stu-id="77e6c-120">The MAPI spooler calls the **TransportNotify** method to disable message transmission and reception.</span></span> 
    
9. <span data-ttu-id="77e6c-121">MAPI 后台处理程序释放登录和提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="77e6c-121">The MAPI spooler releases the logon and provider objects.</span></span> <span data-ttu-id="77e6c-122">有关详细信息, 请参阅[IXPProvider:: Shutdown](ixpprovider-shutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="77e6c-122">For more information, see the [IXPProvider::Shutdown](ixpprovider-shutdown.md) method.</span></span> 
    

