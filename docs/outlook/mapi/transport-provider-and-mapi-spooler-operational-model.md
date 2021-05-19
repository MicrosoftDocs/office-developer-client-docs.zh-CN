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
# <a name="transport-provider-and-mapi-spooler-operational-model"></a><span data-ttu-id="532e0-103">传输提供程序和 MAPI 后台处理程序操作模型</span><span class="sxs-lookup"><span data-stu-id="532e0-103">Transport Provider and MAPI Spooler Operational Model</span></span>

  
  
<span data-ttu-id="532e0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="532e0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="532e0-105">传输提供程序初始化、启动、处理、关闭和取消初始化是通过从 MAPI 后台处理程序到传输提供程序的一系列调用完成的。</span><span class="sxs-lookup"><span data-stu-id="532e0-105">Transport provider initialization, startup, processing, shutdown and deinitialization are accomplished by a series of calls from the MAPI spooler to the transport provider.</span></span> <span data-ttu-id="532e0-106">调用顺序如下：</span><span class="sxs-lookup"><span data-stu-id="532e0-106">The calls are sequenced as follows:</span></span>
  
1. <span data-ttu-id="532e0-107">MAPI 后台处理程序调用 [XPProviderInit](xpproviderinit.md) 函数，传递支持对象，获取提供程序对象，并检查传输提供程序和 MAPI 后台处理程序是否支持 MAPI 版本号的兼容范围。</span><span class="sxs-lookup"><span data-stu-id="532e0-107">The MAPI spooler calls the [XPProviderInit](xpproviderinit.md) function, passes a support object, gets the provider object, and checks that the transport provider and MAPI spooler support a compatible range of MAPI version numbers.</span></span> 
    
2. <span data-ttu-id="532e0-108">MAPI 后台处理程序调用 [IXPProvider：](ixpprovider-transportlogon.md) IUnknown 接口的 [IXPProvider：：TransportLogon](ixpprovideriunknown.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="532e0-108">The MAPI spooler calls the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method of the [IXPProvider : IUnknown](ixpprovideriunknown.md) interface.</span></span> <span data-ttu-id="532e0-109">在 MAPI 后台处理程序和具有配置文件当前部分中凭据的传输提供程序之间建立会话。</span><span class="sxs-lookup"><span data-stu-id="532e0-109">A session is established between the MAPI spooler and the transport provider with the credentials in the current section of the profile.</span></span> <span data-ttu-id="532e0-110">传输提供程序返回登录对象。</span><span class="sxs-lookup"><span data-stu-id="532e0-110">The transport provider returns a logon object.</span></span> 
    
3. <span data-ttu-id="532e0-111">MAPI 后台处理程序调用 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="532e0-111">The MAPI spooler calls the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> <span data-ttu-id="532e0-112">传输提供程序返回 UID 的唯 (标识符列表) 将接受的电子邮件地址类型。</span><span class="sxs-lookup"><span data-stu-id="532e0-112">The transport provider returns a list of the unique identifiers (UIDs) and email address types it will accept.</span></span> 
    
4. <span data-ttu-id="532e0-113">传输提供程序调用 [IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md) 方法以在 MAPI 状态表中创建其行。</span><span class="sxs-lookup"><span data-stu-id="532e0-113">The transport provider calls the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method to create its row in the MAPI status table.</span></span> 
    
5. <span data-ttu-id="532e0-114">MAPI 后台处理程序调用 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) 方法来启用邮件传输和接收。</span><span class="sxs-lookup"><span data-stu-id="532e0-114">The MAPI spooler calls the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method to enable message transmission and reception.</span></span> 
    
6. <span data-ttu-id="532e0-115">如果传输提供程序在返回 **TransportLogon** 调用时请求，MAPI 后台处理程序将定期调用 [IXPLogon：：Idle](ixplogon-idle.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="532e0-115">If requested by the transport provider in its return for the **TransportLogon** call, the MAPI spooler periodically calls the [IXPLogon::Idle](ixplogon-idle.md) method.</span></span> <span data-ttu-id="532e0-116">如果传输提供程序需要轮询基础邮件系统以寻找新邮件或执行其他低优先级任务，则空闲处理非常有用。</span><span class="sxs-lookup"><span data-stu-id="532e0-116">Idle processing is useful if the transport provider needs to poll the underlying messaging system for new messages or perform other low-priority tasks.</span></span> 
    
7. <span data-ttu-id="532e0-117">MAPI 后台处理程序和传输提供程序发送和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="532e0-117">The MAPI spooler and transport provider send and receive messages.</span></span> <span data-ttu-id="532e0-118">有关详细信息，请参阅邮件[提交模型和](message-submission-model.md)[邮件接收模型](message-reception-model.md)。</span><span class="sxs-lookup"><span data-stu-id="532e0-118">For more information, see [Message Submission Model](message-submission-model.md) and [Message Reception Model](message-reception-model.md).</span></span> <span data-ttu-id="532e0-119">MAPI 后台处理程序服务对支持、邮件和附件对象的传输请求和调用。</span><span class="sxs-lookup"><span data-stu-id="532e0-119">The MAPI spooler services transport requests and calls on support, message, and attachment objects.</span></span>
    
8. <span data-ttu-id="532e0-120">MAPI 后台处理程序调用 **TransportNotify** 方法来禁用邮件传输和接收。</span><span class="sxs-lookup"><span data-stu-id="532e0-120">The MAPI spooler calls the **TransportNotify** method to disable message transmission and reception.</span></span> 
    
9. <span data-ttu-id="532e0-121">MAPI 后台处理程序释放登录和提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="532e0-121">The MAPI spooler releases the logon and provider objects.</span></span> <span data-ttu-id="532e0-122">有关详细信息，请参阅 [IXPProvider：：Shutdown](ixpprovider-shutdown.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="532e0-122">For more information, see the [IXPProvider::Shutdown](ixpprovider-shutdown.md) method.</span></span> 
    

