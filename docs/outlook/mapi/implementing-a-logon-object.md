---
title: 实现登录对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 41e5c88c-d79d-4e9f-81f4-c4365cfaa15d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f9d77313012c2d133dc9352707ebc5e0c69c9973
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433043"
---
# <a name="implementing-a-logon-object"></a><span data-ttu-id="d6092-103">实现登录对象</span><span class="sxs-lookup"><span data-stu-id="d6092-103">Implementing a Logon Object</span></span>

  
  
<span data-ttu-id="d6092-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6092-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d6092-105">每个通讯簿、邮件存储和传输提供程序都会实例化登录对象，作为[实现 IABProvider：：Logon、IMSProvider：：Logon](iabprovider-logon.md)或[IXPProvider：：TransportLogon](ixpprovider-transportlogon.md)的一部分。 [](imsprovider-logon.md)</span><span class="sxs-lookup"><span data-stu-id="d6092-105">Every address book, message store, and transport provider instantiates a logon object as part of its implementation of [IABProvider::Logon](iabprovider-logon.md), [IMSProvider::Logon](imsprovider-logon.md), or [IXPProvider::TransportLogon](ixpprovider-transportlogon.md).</span></span> <span data-ttu-id="d6092-106">登录对象实现可帮助 MAPI 服务客户端请求的方法。</span><span class="sxs-lookup"><span data-stu-id="d6092-106">Logon objects implement methods that help MAPI service client requests.</span></span> <span data-ttu-id="d6092-107">根据服务提供商的类型，您的登录对象将支持以下接口之一。</span><span class="sxs-lookup"><span data-stu-id="d6092-107">Depending on your type of service provider, your logon object will support one of the following interfaces.</span></span> 
  
|<span data-ttu-id="d6092-108">**登录对象接口**</span><span class="sxs-lookup"><span data-stu-id="d6092-108">**Logon object interface**</span></span>|<span data-ttu-id="d6092-109">**服务提供程序**</span><span class="sxs-lookup"><span data-stu-id="d6092-109">**Service provider**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d6092-110">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d6092-110">IABLogon : IUnknown</span></span>](iablogoniunknown.md) <br/> |<span data-ttu-id="d6092-111">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="d6092-111">Address book provider</span></span>  <br/> |
|[<span data-ttu-id="d6092-112">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d6092-112">IMSLogon : IUnknown</span></span>](imslogoniunknown.md) <br/> |<span data-ttu-id="d6092-113">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="d6092-113">Message store provider</span></span>  <br/> |
|[<span data-ttu-id="d6092-114">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d6092-114">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md) <br/> |<span data-ttu-id="d6092-115">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="d6092-115">Transport provider</span></span>  <br/> |
   
<span data-ttu-id="d6092-116">通讯簿和邮件存储提供程序在登录对象中实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="d6092-116">Address book and message store providers implement the following features in their logon objects:</span></span>
  
- <span data-ttu-id="d6092-117">支持事件通知 (**Advise** 和 **Unadvise** 方法) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-117">Support for event notification (**Advise** and **Unadvise** methods).</span></span> <span data-ttu-id="d6092-118">有关事件通知的概述，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-118">For an overview of event notification, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="d6092-119">有关在登录对象中支持通知的信息，请参阅 [支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-119">For more information about supporting notification in your logon object, see [Supporting Event Notification](supporting-event-notification.md).</span></span> 
    
- <span data-ttu-id="d6092-120">**CompareEntryIDs** (的条目标识符) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-120">Entry identifier comparison (**CompareEntryIDs** method).</span></span> <span data-ttu-id="d6092-121">有关条目标识符的常规信息，请参阅 [MAPI 条目标识符](mapi-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-121">For general information about entry identifiers, see [MAPI Entry Identifiers](mapi-entry-identifiers.md).</span></span> <span data-ttu-id="d6092-122">有关在登录对象的 **CompareEntryIDs** 方法中比较条目标识符的信息，请参阅S [supporting Object Access and Comparison。](supporting-object-access-and-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="d6092-122">For more information about comparing entry identifiers in your logon object's **CompareEntryIDs** method, see [Supporting Object Access and Comparison](supporting-object-access-and-comparison.md).</span></span>
    
- <span data-ttu-id="d6092-123">使用 **GetLastError** 方法 (访问其他) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-123">Access to additional error information (**GetLastError** method).</span></span> <span data-ttu-id="d6092-124">有关处理 MAPI 中的错误的详细信息，请参阅 [MAPI 中的错误处理](error-handling-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-124">For more information about handling errors in MAPI, see [Error Handling in MAPI](error-handling-in-mapi.md).</span></span> 
    
- <span data-ttu-id="d6092-125">使用 **OpenEntry** 方法访问由服务提供商 (的对象) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-125">Access to objects implemented by the service provider (**OpenEntry** method).</span></span> <span data-ttu-id="d6092-126">有关详细信息，请参阅支持 [对象访问和比较](supporting-object-access-and-comparison.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-126">For more information, see [Supporting Object Access and Comparison](supporting-object-access-and-comparison.md).</span></span>
    
- <span data-ttu-id="d6092-127">使用 **OpenStatusEntry** 方法 (访问状态) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-127">Access to a status object (**OpenStatusEntry** method).</span></span> <span data-ttu-id="d6092-128">有关状态对象的一般信息，请参阅 [MAPI Status Objects](mapi-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-128">For general information about status objects, see [MAPI Status Objects](mapi-status-objects.md).</span></span> <span data-ttu-id="d6092-129">有关实现状态对象的特定信息，请参阅 [状态对象实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-129">For specific information about implementing a status object, see [Status Object Implementation](status-object-implementation.md).</span></span>
    
- <span data-ttu-id="d6092-130">使用 Logoff 方法 **(注销**) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-130">A logoff process (**Logoff** method).</span></span> <span data-ttu-id="d6092-131">有关详细信息，请参阅 [关闭服务提供程序](shutting-down-a-service-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-131">For more information, see [Shutting Down a Service Provider](shutting-down-a-service-provider.md).</span></span>
    
<span data-ttu-id="d6092-132">如果您的提供程序是通讯簿提供程序，则还将实现以下方法和关联功能：</span><span class="sxs-lookup"><span data-stu-id="d6092-132">If your provider is an address book provider, you will also implement the following methods and associated features:</span></span>
  
- <span data-ttu-id="d6092-133">[IABLogon：：GetOneOffTable，](iablogon-getoneofftable.md) 用于提供支持创建新收件人的模板列表。</span><span class="sxs-lookup"><span data-stu-id="d6092-133">[IABLogon::GetOneOffTable](iablogon-getoneofftable.md) to provide a listing of the templates that you support for creating new recipients.</span></span> <span data-ttu-id="d6092-134">有关详细信息，请参阅一键 [式表](one-off-tables.md) 或 [实现提供程序One-Off表](implementing-a-provider-one-off-table.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-134">For more information, see [One-Off Tables](one-off-tables.md) or [Implementing a Provider One-Off Table](implementing-a-provider-one-off-table.md).</span></span>
    
- <span data-ttu-id="d6092-135">[IABLogon：：OpenTemplateID，](iablogon-opentemplateid.md) 用于提供对数据驻留在主机通讯簿提供程序中的收件人的实现的访问。</span><span class="sxs-lookup"><span data-stu-id="d6092-135">[IABLogon::OpenTemplateID](iablogon-opentemplateid.md) to provide access to the implementation of a recipient whose data resides in a host address book provider.</span></span> <span data-ttu-id="d6092-136">有关详细信息，请参阅代理 [外通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-136">For more information, see [Acting as a Foreign Address Book Provider](acting-as-a-foreign-address-book-provider.md).</span></span> 
    
- <span data-ttu-id="d6092-137">[IABLogon：:P repareRecips](iablogon-preparerecips.md) 以确保适当的属性可用于收件人列表中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="d6092-137">[IABLogon::PrepareRecips](iablogon-preparerecips.md) to ensure that the appropriate properties are available for all of the recipients in a recipient list.</span></span> <span data-ttu-id="d6092-138">有关详细信息，请参阅 [IABLogon：:P repareRecips](iablogon-preparerecips.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-138">For more information, see [IABLogon::PrepareRecips](iablogon-preparerecips.md).</span></span> 
    
<span data-ttu-id="d6092-139">实现 [IXPLogon ： IUnknown](ixplogoniunknown.md)的传输提供程序的登录对象与其他类型的服务提供商实现的登录对象完全不同。</span><span class="sxs-lookup"><span data-stu-id="d6092-139">A transport provider's logon object, which implements [IXPLogon : IUnknown](ixplogoniunknown.md), is quite different from the logon objects implemented by the other types of service providers.</span></span> <span data-ttu-id="d6092-140">它只有两个与其他登录对象共同的功能：通过 [IXPLogon：：OpenStatusEntry](ixplogon-openstatusentry.md) 方法访问状态对象，以及通过 [IXPLogon：：TransportLogoff](ixplogon-transportlogoff.md) 方法执行注销操作。</span><span class="sxs-lookup"><span data-stu-id="d6092-140">It has only two features in common with the other logon objects: access to a status object through the [IXPLogon::OpenStatusEntry](ixplogon-openstatusentry.md) method and a logoff operation through the [IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) method.</span></span> <span data-ttu-id="d6092-141">传输提供程序在登录对象中实现以下唯一功能：</span><span class="sxs-lookup"><span data-stu-id="d6092-141">Transport providers implement the following unique features in their logon objects:</span></span> 
  
- <span data-ttu-id="d6092-142">使用 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) (注册地址类型) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-142">Registration for address types ([IXPLogon::AddressTypes](ixplogon-addresstypes.md) method).</span></span> <span data-ttu-id="d6092-143">有关注册地址类型的信息，请参阅传输提供程序和 [MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-143">For more information about registering an address type, see [Transport Provider and MAPI Spooler Operational Model](transport-provider-and-mapi-spooler-operational-model.md).</span></span>
    
- <span data-ttu-id="d6092-144">控制邮件传输 ([IXPLogon：：StartMessage、IXPLogon：：EndMessage](ixplogon-startmessage.md)和[IXPLogon：：SubmitMessage](ixplogon-submitmessage.md)) 。 [](ixplogon-endmessage.md)</span><span class="sxs-lookup"><span data-stu-id="d6092-144">Control of message transmission ([IXPLogon::StartMessage](ixplogon-startmessage.md), [IXPLogon::EndMessage](ixplogon-endmessage.md), and [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) methods).</span></span> <span data-ttu-id="d6092-145">有关详细信息，请参阅邮件 [接收模型](message-reception-model.md)、与 [MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)和 [邮件提交模型](message-submission-model.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-145">For more information, see [Message Reception Model](message-reception-model.md), [Interacting with the MAPI Spooler](interacting-with-the-mapi-spooler.md), and [Message Submission Model](message-submission-model.md).</span></span>
    
- <span data-ttu-id="d6092-146">[IXPLogon (：：ValidateState 方法的内部](ixplogon-validatestate.md)) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-146">Internal state validation ([IXPLogon::ValidateState](ixplogon-validatestate.md) method).</span></span> 
    
- <span data-ttu-id="d6092-147">使用 [IXPLogon：：FlushQueues](ixplogon-flushqueues.md) (按需下载或上载) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-147">Ability to download or upload messages on demand ([IXPLogon::FlushQueues](ixplogon-flushqueues.md) method).</span></span> <span data-ttu-id="d6092-148">有关详细信息，请参阅实现 [FlushQueues 方法](implementing-the-flushqueues-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-148">For more information, see [Implementing the FlushQueues Method](implementing-the-flushqueues-method.md).</span></span>
    
- <span data-ttu-id="d6092-149">使用 ([IXPLogon：:P方法](ixplogon-poll.md) 查询挂起) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-149">Ability to query for pending messages ([IXPLogon::Poll](ixplogon-poll.md) method).</span></span> <span data-ttu-id="d6092-150">有关详细信息，请参阅邮件 [接收模型](message-reception-model.md)。</span><span class="sxs-lookup"><span data-stu-id="d6092-150">For more information, see [Message Reception Model](message-reception-model.md).</span></span>
    
- <span data-ttu-id="d6092-151">[IXPLogon (：：Idle 方法的空闲](ixplogon-idle.md)状态) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-151">Idle state detection ([IXPLogon::Idle](ixplogon-idle.md) method).</span></span> 
    
- <span data-ttu-id="d6092-152">与 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) (MAPI 后台处理程序的) 。</span><span class="sxs-lookup"><span data-stu-id="d6092-152">Interaction with the MAPI spooler ([IXPLogon::TransportNotify](ixplogon-transportnotify.md) method).</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="d6092-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6092-153">See also</span></span>



[<span data-ttu-id="d6092-154">实现服务提供程序登录</span><span class="sxs-lookup"><span data-stu-id="d6092-154">Implementing Service Provider Logon</span></span>](implementing-service-provider-logon.md)

