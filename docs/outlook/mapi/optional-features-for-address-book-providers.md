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
# <a name="optional-features-for-address-book-providers"></a><span data-ttu-id="2e363-103">通讯簿提供程序的可选功能</span><span class="sxs-lookup"><span data-stu-id="2e363-103">Optional Features for Address Book Providers</span></span>

  
  
<span data-ttu-id="2e363-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e363-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e363-105">通讯簿提供程序有许多可选功能。</span><span class="sxs-lookup"><span data-stu-id="2e363-105">There are many optional features for address book providers.</span></span> <span data-ttu-id="2e363-106">一些更常用的一些功能包括:</span><span class="sxs-lookup"><span data-stu-id="2e363-106">Some of the more commonly implemented features include:</span></span>
  
- <span data-ttu-id="2e363-107">通过允许将某个容器中的项添加到另一个提供程序的容器, 充当外部提供程序。</span><span class="sxs-lookup"><span data-stu-id="2e363-107">Acting as a foreign provider by allowing entries from one of your containers to be added to another provider's container.</span></span>
    
- <span data-ttu-id="2e363-108">通过向某个容器添加其他提供程序中的项来充当主机提供程序。</span><span class="sxs-lookup"><span data-stu-id="2e363-108">Acting as a host provider by adding entries from another provider to one of your containers.</span></span>
    
- <span data-ttu-id="2e363-109">高级搜索。</span><span class="sxs-lookup"><span data-stu-id="2e363-109">Advanced searching.</span></span>
    
- <span data-ttu-id="2e363-110">通过内容表滚动的前缀。</span><span class="sxs-lookup"><span data-stu-id="2e363-110">Prefix scrolling through contents tables.</span></span>
    
- <span data-ttu-id="2e363-111">对通讯组列表的支持。</span><span class="sxs-lookup"><span data-stu-id="2e363-111">Support for distribution lists.</span></span>
    
- <span data-ttu-id="2e363-112">支持事件通知。</span><span class="sxs-lookup"><span data-stu-id="2e363-112">Support for event notification.</span></span>
    
<span data-ttu-id="2e363-113">下表简要介绍了这些可选功能以及如何实现这些功能:</span><span class="sxs-lookup"><span data-stu-id="2e363-113">The following table briefly describes these optional features and how you implement them:</span></span>
  
|<span data-ttu-id="2e363-114">**功能**</span><span class="sxs-lookup"><span data-stu-id="2e363-114">**Feature**</span></span>|<span data-ttu-id="2e363-115">**如何实现**</span><span class="sxs-lookup"><span data-stu-id="2e363-115">**How to implement**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e363-116">提供用于创建邮件收件人列表条目的模板</span><span class="sxs-lookup"><span data-stu-id="2e363-116">Supply templates for creating entries for message recipient lists</span></span>  <br/> |<span data-ttu-id="2e363-117">实现[IABLogon:: GetOneOffTable](iablogon-getoneofftable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2e363-117">Implement the [IABLogon::GetOneOffTable](iablogon-getoneofftable.md) method.</span></span> <span data-ttu-id="2e363-118">有关详细信息, 请参阅[一次性表](one-off-tables.md)和[实现一次性表](implementing-one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="2e363-118">For more information, see [One-Off Tables](one-off-tables.md) and [Implementing One-Off Tables](implementing-one-off-tables.md).</span></span>  <br/> |
|<span data-ttu-id="2e363-119">将收件人分组为命名的单位</span><span class="sxs-lookup"><span data-stu-id="2e363-119">Group recipients into a named unit</span></span>  <br/> |<span data-ttu-id="2e363-120">通过实现[IDistList: IMAPIContainer](idistlistimapicontainer.md)接口, 支持通讯组列表的属性。</span><span class="sxs-lookup"><span data-stu-id="2e363-120">Support the properties of distribution lists by implementing the [IDistList : IMAPIContainer](idistlistimapicontainer.md) interface.</span></span>  <br/> |
|<span data-ttu-id="2e363-121">通过允许将条目添加到另一个提供程序中的容器来充当外部通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="2e363-121">Act as a foreign address book provider by allowing entries to be added to a container in another provider</span></span>  <br/> | <span data-ttu-id="2e363-122">通过以下方式支持向主机提供程序中的数据绑定代码:</span><span class="sxs-lookup"><span data-stu-id="2e363-122">Support binding code to data in the host provider by:</span></span>  <br/>  <span data-ttu-id="2e363-123">支持邮件用户和通讯组列表上的**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2e363-123">Supporting the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property on messaging users and distribution lists.</span></span> <span data-ttu-id="2e363-124">有关详细信息, 请参阅[通讯簿标识符](address-book-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="2e363-124">For more information, see [Address Book Identifiers](address-book-identifiers.md).</span></span>  <br/>  <span data-ttu-id="2e363-125">实现[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2e363-125">Implementing the [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> <span data-ttu-id="2e363-126">有关详细信息, 请参阅[充当外部通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="2e363-126">For more information, see [Acting as a Foreign Address Book Provider](acting-as-a-foreign-address-book-provider.md).</span></span>  <br/> |
|<span data-ttu-id="2e363-127">通过从另一个提供程序插入条目充当主机通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="2e363-127">Acting as a host address book provider by inserting entries from another provider</span></span>  <br/> |<span data-ttu-id="2e363-128">通过调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)方法, 支持将数据绑定到来自外部提供程序的代码。</span><span class="sxs-lookup"><span data-stu-id="2e363-128">Support binding data to code from a foreign provider by calling the [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) method.</span></span> <span data-ttu-id="2e363-129">有关详细信息, 请参阅[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="2e363-129">For more information, see [Acting as a Host Address Book Provider](acting-as-a-host-address-book-provider.md).</span></span>  <br/> |
|<span data-ttu-id="2e363-130">前缀滚动</span><span class="sxs-lookup"><span data-stu-id="2e363-130">Prefix scrolling</span></span>  <br/> |<span data-ttu-id="2e363-131">支持对容器内容表的限制。</span><span class="sxs-lookup"><span data-stu-id="2e363-131">Support restrictions on container contents tables.</span></span> <span data-ttu-id="2e363-132">有关详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="2e363-132">For more information, see [About Restrictions](about-restrictions.md).</span></span>  <br/> |
|<span data-ttu-id="2e363-133">容器中的高级搜索</span><span class="sxs-lookup"><span data-stu-id="2e363-133">Advanced searching in a container</span></span>  <br/> |<span data-ttu-id="2e363-134">支持容器上的**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2e363-134">Support the **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) property on containers.</span></span> <span data-ttu-id="2e363-135">有关详细信息, 请参阅[实施高级搜索](implementing-advanced-searching.md)。</span><span class="sxs-lookup"><span data-stu-id="2e363-135">For more information, see [Implementing Advanced Searching](implementing-advanced-searching.md).</span></span>  <br/> |
|<span data-ttu-id="2e363-136">事件通知</span><span class="sxs-lookup"><span data-stu-id="2e363-136">Event notification</span></span>  <br/> |<span data-ttu-id="2e363-137">实现[IABLogon:: Advise](iablogon-advise.md)和[IABLogon:: Unadvise](iablogon-unadvise.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2e363-137">Implement the [IABLogon::Advise](iablogon-advise.md) and [IABLogon::Unadvise](iablogon-unadvise.md) methods.</span></span> <span data-ttu-id="2e363-138">有关详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="2e363-138">For more information, see [Event Notification in MAPI](event-notification-in-mapi.md) and [Supporting Event Notification](supporting-event-notification.md).</span></span>  <br/> |
   
<span data-ttu-id="2e363-139">对于事件通知, 当客户端调用**IAddrBook:: 建议**在任何一个容器、邮件用户或通讯组列表中注册通知时, MAPI 将调用**IABLogon:: advise**方法。</span><span class="sxs-lookup"><span data-stu-id="2e363-139">For event notification, your **IABLogon::Advise** method will be called by MAPI when a client calls **IAddrBook::Advise** to register for notifications on any one of your containers, messaging users, or distribution lists.</span></span> <span data-ttu-id="2e363-140">但是, 由于支持事件通知是可选的, 因此可以从这些方法返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="2e363-140">However, because supporting event notification is optional, you can return MAPI_E_NO_SUPPORT from these methods.</span></span> <span data-ttu-id="2e363-141">但是, MAPI 确实建议您至少支持对内容表的通知, 并鼓励您支持所有类型的对象通知, 除了_fnevSearchComplete_和_fnevCriticalError_事件以添加值之外。</span><span class="sxs-lookup"><span data-stu-id="2e363-141">However, MAPI does recommend that you at least support notifications on your contents tables and encourages you to support all types of object notification except for  _fnevSearchComplete_ and the  _fnevCriticalError_ event to add value.</span></span> 
  

