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
ms.openlocfilehash: 99a8473abf01467c534c0ea829e342fa46489e99
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568019"
---
# <a name="implementing-a-logon-object"></a><span data-ttu-id="75e90-103">实现登录对象</span><span class="sxs-lookup"><span data-stu-id="75e90-103">Implementing a Logon Object</span></span>

  
  
<span data-ttu-id="75e90-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="75e90-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="75e90-105">每个通讯簿、 消息存储和传输提供程序实例化的[IABProvider::Logon](iabprovider-logon.md)、 [IMSProvider::Logon](imsprovider-logon.md)，或[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)其实现一部分登录对象。</span><span class="sxs-lookup"><span data-stu-id="75e90-105">Every address book, message store, and transport provider instantiates a logon object as part of its implementation of [IABProvider::Logon](iabprovider-logon.md), [IMSProvider::Logon](imsprovider-logon.md), or [IXPProvider::TransportLogon](ixpprovider-transportlogon.md).</span></span> <span data-ttu-id="75e90-106">登录对象实现帮助 MAPI 服务客户端请求的方法。</span><span class="sxs-lookup"><span data-stu-id="75e90-106">Logon objects implement methods that help MAPI service client requests.</span></span> <span data-ttu-id="75e90-107">根据您的服务提供商的类型，登录对象将支持以下接口之一。</span><span class="sxs-lookup"><span data-stu-id="75e90-107">Depending on your type of service provider, your logon object will support one of the following interfaces.</span></span> 
  
|<span data-ttu-id="75e90-108">**登录对象接口**</span><span class="sxs-lookup"><span data-stu-id="75e90-108">**Logon object interface**</span></span>|<span data-ttu-id="75e90-109">**服务提供商**</span><span class="sxs-lookup"><span data-stu-id="75e90-109">**Service provider**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="75e90-110">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="75e90-110">IABLogon : IUnknown</span></span>](iablogoniunknown.md) <br/> |<span data-ttu-id="75e90-111">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="75e90-111">Address book provider</span></span>  <br/> |
|[<span data-ttu-id="75e90-112">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="75e90-112">IMSLogon : IUnknown</span></span>](imslogoniunknown.md) <br/> |<span data-ttu-id="75e90-113">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="75e90-113">Message store provider</span></span>  <br/> |
|[<span data-ttu-id="75e90-114">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="75e90-114">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md) <br/> |<span data-ttu-id="75e90-115">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="75e90-115">Transport provider</span></span>  <br/> |
   
<span data-ttu-id="75e90-116">通讯簿和消息存储提供程序实现以下功能在其登录对象中：</span><span class="sxs-lookup"><span data-stu-id="75e90-116">Address book and message store providers implement the following features in their logon objects:</span></span>
  
- <span data-ttu-id="75e90-117">事件通知 （**Advise**和**Unadvise**方法） 的支持。</span><span class="sxs-lookup"><span data-stu-id="75e90-117">Support for event notification (**Advise** and **Unadvise** methods).</span></span> <span data-ttu-id="75e90-118">事件通知的概述，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-118">For an overview of event notification, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="75e90-119">有关登录对象中支持通知的详细信息，请参阅[支持的事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-119">For more information about supporting notification in your logon object, see [Supporting Event Notification](supporting-event-notification.md).</span></span> 
    
- <span data-ttu-id="75e90-120">项标识符比较 （**CompareEntryIDs**方法）。</span><span class="sxs-lookup"><span data-stu-id="75e90-120">Entry identifier comparison (**CompareEntryIDs** method).</span></span> <span data-ttu-id="75e90-121">有关条目标识符的常规信息，请参阅[MAPI 条目标识符](mapi-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-121">For general information about entry identifiers, see [MAPI Entry Identifiers](mapi-entry-identifiers.md).</span></span> <span data-ttu-id="75e90-122">有关比较登录对象的**CompareEntryIDs**方法中的项标识符的详细信息，请参阅[支持对象访问和比较](supporting-object-access-and-comparison.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-122">For more information about comparing entry identifiers in your logon object's **CompareEntryIDs** method, see [Supporting Object Access and Comparison](supporting-object-access-and-comparison.md).</span></span>
    
- <span data-ttu-id="75e90-123">访问其他错误信息 （**GetLastError**方法）。</span><span class="sxs-lookup"><span data-stu-id="75e90-123">Access to additional error information (**GetLastError** method).</span></span> <span data-ttu-id="75e90-124">有关处理 MAPI 中的错误的详细信息，请参阅[MAPI 中的错误处理](error-handling-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-124">For more information about handling errors in MAPI, see [Error Handling in MAPI](error-handling-in-mapi.md).</span></span> 
    
- <span data-ttu-id="75e90-125">实现由服务提供商 （**OpenEntry**方法） 的对象的访问。</span><span class="sxs-lookup"><span data-stu-id="75e90-125">Access to objects implemented by the service provider (**OpenEntry** method).</span></span> <span data-ttu-id="75e90-126">有关详细信息，请参阅[支持对象访问和比较](supporting-object-access-and-comparison.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-126">For more information, see [Supporting Object Access and Comparison](supporting-object-access-and-comparison.md).</span></span>
    
- <span data-ttu-id="75e90-127">访问状态对象 （**OpenStatusEntry**方法）。</span><span class="sxs-lookup"><span data-stu-id="75e90-127">Access to a status object (**OpenStatusEntry** method).</span></span> <span data-ttu-id="75e90-128">有关状态的对象的常规信息，请参阅[MAPI 状态对象](mapi-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-128">For general information about status objects, see [MAPI Status Objects](mapi-status-objects.md).</span></span> <span data-ttu-id="75e90-129">有关实现状态对象的特定信息，请参阅[状态对象实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-129">For specific information about implementing a status object, see [Status Object Implementation](status-object-implementation.md).</span></span>
    
- <span data-ttu-id="75e90-130">注销过程 （**Logoff**方法）。</span><span class="sxs-lookup"><span data-stu-id="75e90-130">A logoff process (**Logoff** method).</span></span> <span data-ttu-id="75e90-131">有关详细信息，请参阅[关机的情况下服务 Provider](shutting-down-a-service-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-131">For more information, see [Shutting Down a Service Provider](shutting-down-a-service-provider.md).</span></span>
    
<span data-ttu-id="75e90-132">如果您的提供商的地址簿提供程序，您将实现以下方法和关联的功能：</span><span class="sxs-lookup"><span data-stu-id="75e90-132">If your provider is an address book provider, you will also implement the following methods and associated features:</span></span>
  
- <span data-ttu-id="75e90-133">[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)来提供支持用于创建新的收件人的模板的列表。</span><span class="sxs-lookup"><span data-stu-id="75e90-133">[IABLogon::GetOneOffTable](iablogon-getoneofftable.md) to provide a listing of the templates that you support for creating new recipients.</span></span> <span data-ttu-id="75e90-134">有关详细信息，请参阅[一次性表](one-off-tables.md)或[实现提供程序一次性表](implementing-a-provider-one-off-table.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-134">For more information, see [One-Off Tables](one-off-tables.md) or [Implementing a Provider One-Off Table](implementing-a-provider-one-off-table.md).</span></span>
    
- <span data-ttu-id="75e90-135">[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)以提供对收件人的实现访问其数据位于主机通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="75e90-135">[IABLogon::OpenTemplateID](iablogon-opentemplateid.md) to provide access to the implementation of a recipient whose data resides in a host address book provider.</span></span> <span data-ttu-id="75e90-136">有关详细信息，请参阅[充当外的通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-136">For more information, see [Acting as a Foreign Address Book Provider](acting-as-a-foreign-address-book-provider.md).</span></span> 
    
- <span data-ttu-id="75e90-137">[IABLogon::PrepareRecips](iablogon-preparerecips.md) ，以确保的相应属性可用于所有收件人列表中的收件人。</span><span class="sxs-lookup"><span data-stu-id="75e90-137">[IABLogon::PrepareRecips](iablogon-preparerecips.md) to ensure that the appropriate properties are available for all of the recipients in a recipient list.</span></span> <span data-ttu-id="75e90-138">有关详细信息，请参阅[IABLogon::PrepareRecips](iablogon-preparerecips.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-138">For more information, see [IABLogon::PrepareRecips](iablogon-preparerecips.md).</span></span> 
    
<span data-ttu-id="75e90-139">传输提供程序的登录对象，实现[IXPLogon: IUnknown](ixplogoniunknown.md)，则由其他类型的服务提供商实现的登录对象从完全不同。</span><span class="sxs-lookup"><span data-stu-id="75e90-139">A transport provider's logon object, which implements [IXPLogon : IUnknown](ixplogoniunknown.md), is quite different from the logon objects implemented by the other types of service providers.</span></span> <span data-ttu-id="75e90-140">它具有共同之处的其他登录对象只有两个功能： 访问[IXPLogon::OpenStatusEntry](ixplogon-openstatusentry.md)方法通过状态对象和通过[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md)方法注销操作。</span><span class="sxs-lookup"><span data-stu-id="75e90-140">It has only two features in common with the other logon objects: access to a status object through the [IXPLogon::OpenStatusEntry](ixplogon-openstatusentry.md) method and a logoff operation through the [IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) method.</span></span> <span data-ttu-id="75e90-141">传输提供程序在其登录对象中实现以下唯一功能：</span><span class="sxs-lookup"><span data-stu-id="75e90-141">Transport providers implement the following unique features in their logon objects:</span></span> 
  
- <span data-ttu-id="75e90-142">注册地址类型 （[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法）。</span><span class="sxs-lookup"><span data-stu-id="75e90-142">Registration for address types ([IXPLogon::AddressTypes](ixplogon-addresstypes.md) method).</span></span> <span data-ttu-id="75e90-143">有关注册地址类型的详细信息，请参阅[传输提供程序和 MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-143">For more information about registering an address type, see [Transport Provider and MAPI Spooler Operational Model](transport-provider-and-mapi-spooler-operational-model.md).</span></span>
    
- <span data-ttu-id="75e90-144">邮件传输 （[IXPLogon::StartMessage](ixplogon-startmessage.md)、 [IXPLogon::EndMessage](ixplogon-endmessage.md)和[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法） 的控件。</span><span class="sxs-lookup"><span data-stu-id="75e90-144">Control of message transmission ([IXPLogon::StartMessage](ixplogon-startmessage.md), [IXPLogon::EndMessage](ixplogon-endmessage.md), and [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) methods).</span></span> <span data-ttu-id="75e90-145">有关详细信息，请参阅[消息接收模型](message-reception-model.md)、[与 MAPI 后台处理程序的交互](interacting-with-the-mapi-spooler.md)和[消息提交模型](message-submission-model.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-145">For more information, see [Message Reception Model](message-reception-model.md), [Interacting with the MAPI Spooler](interacting-with-the-mapi-spooler.md), and [Message Submission Model](message-submission-model.md).</span></span>
    
- <span data-ttu-id="75e90-146">内部状态验证 （[IXPLogon::ValidateState](ixplogon-validatestate.md)方法）。</span><span class="sxs-lookup"><span data-stu-id="75e90-146">Internal state validation ([IXPLogon::ValidateState](ixplogon-validatestate.md) method).</span></span> 
    
- <span data-ttu-id="75e90-147">若要下载或上载按需型 （[IXPLogon::FlushQueues](ixplogon-flushqueues.md)方法） 的消息的功能。</span><span class="sxs-lookup"><span data-stu-id="75e90-147">Ability to download or upload messages on demand ([IXPLogon::FlushQueues](ixplogon-flushqueues.md) method).</span></span> <span data-ttu-id="75e90-148">有关详细信息，请参阅[实现 FlushQueues 方法](implementing-the-flushqueues-method.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-148">For more information, see [Implementing the FlushQueues Method](implementing-the-flushqueues-method.md).</span></span>
    
- <span data-ttu-id="75e90-149">待处理的邮件 （[IXPLogon::Poll](ixplogon-poll.md)方法） 查询的能力。</span><span class="sxs-lookup"><span data-stu-id="75e90-149">Ability to query for pending messages ([IXPLogon::Poll](ixplogon-poll.md) method).</span></span> <span data-ttu-id="75e90-150">有关详细信息，请参阅[消息接收模型](message-reception-model.md)。</span><span class="sxs-lookup"><span data-stu-id="75e90-150">For more information, see [Message Reception Model](message-reception-model.md).</span></span>
    
- <span data-ttu-id="75e90-151">空闲状态检测 （[IXPLogon::Idle](ixplogon-idle.md)方法）。</span><span class="sxs-lookup"><span data-stu-id="75e90-151">Idle state detection ([IXPLogon::Idle](ixplogon-idle.md) method).</span></span> 
    
- <span data-ttu-id="75e90-152">与 MAPI 后台处理程序 （[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法） 进行交互。</span><span class="sxs-lookup"><span data-stu-id="75e90-152">Interaction with the MAPI spooler ([IXPLogon::TransportNotify](ixplogon-transportnotify.md) method).</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="75e90-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75e90-153">See also</span></span>



[<span data-ttu-id="75e90-154">实现服务提供程序登录</span><span class="sxs-lookup"><span data-stu-id="75e90-154">Implementing Service Provider Logon</span></span>](implementing-service-provider-logon.md)

