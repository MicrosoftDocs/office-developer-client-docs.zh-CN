---
title: 通讯簿提供程序的可选功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f1558259-7f0b-4731-80d2-88e51e203df0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9f5d8f0cd1b21f58e4e5c7d7ccd6cb19f3626c38
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414569"
---
# <a name="optional-features-for-address-book-providers"></a><span data-ttu-id="b2bf0-103">通讯簿提供程序的可选功能</span><span class="sxs-lookup"><span data-stu-id="b2bf0-103">Optional Features for Address Book Providers</span></span>

  
  
<span data-ttu-id="b2bf0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b2bf0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b2bf0-105">通讯簿提供程序具有许多可选功能。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-105">There are many optional features for address book providers.</span></span> <span data-ttu-id="b2bf0-106">一些更常实现的功能包括：</span><span class="sxs-lookup"><span data-stu-id="b2bf0-106">Some of the more commonly implemented features include:</span></span>
  
- <span data-ttu-id="b2bf0-107">通过允许将其中一个容器中的条目添加到另一个提供程序的容器中来充当外提供程序。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-107">Acting as a foreign provider by allowing entries from one of your containers to be added to another provider's container.</span></span>
    
- <span data-ttu-id="b2bf0-108">通过将另一个提供程序的条目添加到您的容器之一来充当主机提供程序。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-108">Acting as a host provider by adding entries from another provider to one of your containers.</span></span>
    
- <span data-ttu-id="b2bf0-109">高级搜索。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-109">Advanced searching.</span></span>
    
- <span data-ttu-id="b2bf0-110">在内容表中滚动的前缀。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-110">Prefix scrolling through contents tables.</span></span>
    
- <span data-ttu-id="b2bf0-111">支持通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-111">Support for distribution lists.</span></span>
    
- <span data-ttu-id="b2bf0-112">支持事件通知。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-112">Support for event notification.</span></span>
    
<span data-ttu-id="b2bf0-113">下表简要介绍了这些可选功能以及如何实现它们：</span><span class="sxs-lookup"><span data-stu-id="b2bf0-113">The following table briefly describes these optional features and how you implement them:</span></span>
  
|<span data-ttu-id="b2bf0-114">**功能**</span><span class="sxs-lookup"><span data-stu-id="b2bf0-114">**Feature**</span></span>|<span data-ttu-id="b2bf0-115">**如何实现**</span><span class="sxs-lookup"><span data-stu-id="b2bf0-115">**How to implement**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b2bf0-116">提供用于创建邮件收件人列表条目的模板</span><span class="sxs-lookup"><span data-stu-id="b2bf0-116">Supply templates for creating entries for message recipient lists</span></span>  <br/> |<span data-ttu-id="b2bf0-117">实现 [IABLogon：：GetOneOffTable](iablogon-getoneofftable.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-117">Implement the [IABLogon::GetOneOffTable](iablogon-getoneofftable.md) method.</span></span> <span data-ttu-id="b2bf0-118">有关详细信息，请参阅一键 [式表](one-off-tables.md) 和实现One-Off [表](implementing-one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-118">For more information, see [One-Off Tables](one-off-tables.md) and [Implementing One-Off Tables](implementing-one-off-tables.md).</span></span>  <br/> |
|<span data-ttu-id="b2bf0-119">将收件人分组到命名单位</span><span class="sxs-lookup"><span data-stu-id="b2bf0-119">Group recipients into a named unit</span></span>  <br/> |<span data-ttu-id="b2bf0-120">通过实现 [IDistList ： IMAPIContainer](idistlistimapicontainer.md) 接口支持通讯组列表的属性。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-120">Support the properties of distribution lists by implementing the [IDistList : IMAPIContainer](idistlistimapicontainer.md) interface.</span></span>  <br/> |
|<span data-ttu-id="b2bf0-121">通过允许将条目添加到另一个提供程序中的容器来充当外通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="b2bf0-121">Act as a foreign address book provider by allowing entries to be added to a container in another provider</span></span>  <br/> | <span data-ttu-id="b2bf0-122">支持通过以下方法将代码绑定到主机提供程序中的数据：</span><span class="sxs-lookup"><span data-stu-id="b2bf0-122">Support binding code to data in the host provider by:</span></span>  <br/>  <span data-ttu-id="b2bf0-123">支持邮件 **PR_TEMPLATEID (** 列表) [PidTagTemplateid](pidtagtemplateid-canonical-property.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-123">Supporting the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property on messaging users and distribution lists.</span></span> <span data-ttu-id="b2bf0-124">有关详细信息，请参阅 [通讯簿标识符](address-book-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-124">For more information, see [Address Book Identifiers](address-book-identifiers.md).</span></span>  <br/>  <span data-ttu-id="b2bf0-125">实现 [IABLogon：：OpenTemplateID](iablogon-opentemplateid.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-125">Implementing the [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> <span data-ttu-id="b2bf0-126">有关详细信息，请参阅代理 [外通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-126">For more information, see [Acting as a Foreign Address Book Provider](acting-as-a-foreign-address-book-provider.md).</span></span>  <br/> |
|<span data-ttu-id="b2bf0-127">通过插入另一个提供商的条目来充当主机通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="b2bf0-127">Acting as a host address book provider by inserting entries from another provider</span></span>  <br/> |<span data-ttu-id="b2bf0-128">支持通过调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md) 方法将数据绑定到来自外提供程序的代码。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-128">Support binding data to code from a foreign provider by calling the [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) method.</span></span> <span data-ttu-id="b2bf0-129">有关详细信息，请参阅代理 [主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-129">For more information, see [Acting as a Host Address Book Provider](acting-as-a-host-address-book-provider.md).</span></span>  <br/> |
|<span data-ttu-id="b2bf0-130">前缀滚动</span><span class="sxs-lookup"><span data-stu-id="b2bf0-130">Prefix scrolling</span></span>  <br/> |<span data-ttu-id="b2bf0-131">支持对容器内容表的限制。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-131">Support restrictions on container contents tables.</span></span> <span data-ttu-id="b2bf0-132">有关详细信息，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-132">For more information, see [About Restrictions](about-restrictions.md).</span></span>  <br/> |
|<span data-ttu-id="b2bf0-133">容器中的高级搜索</span><span class="sxs-lookup"><span data-stu-id="b2bf0-133">Advanced searching in a container</span></span>  <br/> |<span data-ttu-id="b2bf0-134">支持 **PR_SEARCH (** [PidTagSearch)](pidtagsearch-canonical-property.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-134">Support the **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) property on containers.</span></span> <span data-ttu-id="b2bf0-135">有关详细信息，请参阅 [实现高级搜索](implementing-advanced-searching.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-135">For more information, see [Implementing Advanced Searching](implementing-advanced-searching.md).</span></span>  <br/> |
|<span data-ttu-id="b2bf0-136">事件通知</span><span class="sxs-lookup"><span data-stu-id="b2bf0-136">Event notification</span></span>  <br/> |<span data-ttu-id="b2bf0-137">实现 [IABLogon：：Advise](iablogon-advise.md) 和 [IABLogon：：Unadvise](iablogon-unadvise.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-137">Implement the [IABLogon::Advise](iablogon-advise.md) and [IABLogon::Unadvise](iablogon-unadvise.md) methods.</span></span> <span data-ttu-id="b2bf0-138">有关详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)[和支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-138">For more information, see [Event Notification in MAPI](event-notification-in-mapi.md) and [Supporting Event Notification](supporting-event-notification.md).</span></span>  <br/> |
   
<span data-ttu-id="b2bf0-139">对于事件通知，当客户端调用 **IAddrBook：：Advise** 以注册任何容器、邮件用户或通讯组列表上的通知时，MAPI 将调用 **IABLogon：：Advise** 方法。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-139">For event notification, your **IABLogon::Advise** method will be called by MAPI when a client calls **IAddrBook::Advise** to register for notifications on any one of your containers, messaging users, or distribution lists.</span></span> <span data-ttu-id="b2bf0-140">但是，由于支持事件通知是可选的，因此可以从MAPI_E_NO_SUPPORT返回事件通知。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-140">However, because supporting event notification is optional, you can return MAPI_E_NO_SUPPORT from these methods.</span></span> <span data-ttu-id="b2bf0-141">但是，MAPI 建议你至少支持有关内容表的通知，并鼓励你支持所有类型的对象通知  _，fnevSearchComplete_ 和  _fnevCriticalError_ 事件除外以添加值。</span><span class="sxs-lookup"><span data-stu-id="b2bf0-141">However, MAPI does recommend that you at least support notifications on your contents tables and encourages you to support all types of object notification except for  _fnevSearchComplete_ and the  _fnevCriticalError_ event to add value.</span></span> 
  

