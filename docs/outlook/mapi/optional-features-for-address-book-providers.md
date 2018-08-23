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
ms.openlocfilehash: 378dcc3e1506432de22731a27731c58067647952
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565891"
---
# <a name="optional-features-for-address-book-providers"></a><span data-ttu-id="b6295-103">通讯簿提供程序的可选功能</span><span class="sxs-lookup"><span data-stu-id="b6295-103">Optional Features for Address Book Providers</span></span>

  
  
<span data-ttu-id="b6295-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6295-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6295-105">有许多地址簿提供程序的可选功能。</span><span class="sxs-lookup"><span data-stu-id="b6295-105">There are many optional features for address book providers.</span></span> <span data-ttu-id="b6295-106">某些更常见实现的功能包括：</span><span class="sxs-lookup"><span data-stu-id="b6295-106">Some of the more commonly implemented features include:</span></span>
  
- <span data-ttu-id="b6295-107">通过允许从一个容器添加到另一个提供商的容器的条目来充当外的提供程序。</span><span class="sxs-lookup"><span data-stu-id="b6295-107">Acting as a foreign provider by allowing entries from one of your containers to be added to another provider's container.</span></span>
    
- <span data-ttu-id="b6295-108">通过向您容器之一从其他提供程序添加条目充当宿主提供程序。</span><span class="sxs-lookup"><span data-stu-id="b6295-108">Acting as a host provider by adding entries from another provider to one of your containers.</span></span>
    
- <span data-ttu-id="b6295-109">高级搜索。</span><span class="sxs-lookup"><span data-stu-id="b6295-109">Advanced searching.</span></span>
    
- <span data-ttu-id="b6295-110">前缀滚动内容的表格。</span><span class="sxs-lookup"><span data-stu-id="b6295-110">Prefix scrolling through contents tables.</span></span>
    
- <span data-ttu-id="b6295-111">支持通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b6295-111">Support for distribution lists.</span></span>
    
- <span data-ttu-id="b6295-112">事件通知的支持。</span><span class="sxs-lookup"><span data-stu-id="b6295-112">Support for event notification.</span></span>
    
<span data-ttu-id="b6295-113">下表简要介绍这些可选功能和实现它们：</span><span class="sxs-lookup"><span data-stu-id="b6295-113">The following table briefly describes these optional features and how you implement them:</span></span>
  
|<span data-ttu-id="b6295-114">**功能**</span><span class="sxs-lookup"><span data-stu-id="b6295-114">**Feature**</span></span>|<span data-ttu-id="b6295-115">**如何实现**</span><span class="sxs-lookup"><span data-stu-id="b6295-115">**How to implement**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6295-116">提供用于创建收件人列表的邮件项的模板</span><span class="sxs-lookup"><span data-stu-id="b6295-116">Supply templates for creating entries for message recipient lists</span></span>  <br/> |<span data-ttu-id="b6295-117">实现[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b6295-117">Implement the [IABLogon::GetOneOffTable](iablogon-getoneofftable.md) method.</span></span> <span data-ttu-id="b6295-118">有关详细信息，请参阅[一次性表](one-off-tables.md)和[实现一次性表](implementing-one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="b6295-118">For more information, see [One-Off Tables](one-off-tables.md) and [Implementing One-Off Tables](implementing-one-off-tables.md).</span></span>  <br/> |
|<span data-ttu-id="b6295-119">到命名单元组收件人</span><span class="sxs-lookup"><span data-stu-id="b6295-119">Group recipients into a named unit</span></span>  <br/> |<span data-ttu-id="b6295-120">支持通讯组列表的属性，通过实现[IDistList: IMAPIContainer](idistlistimapicontainer.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b6295-120">Support the properties of distribution lists by implementing the [IDistList : IMAPIContainer](idistlistimapicontainer.md) interface.</span></span>  <br/> |
|<span data-ttu-id="b6295-121">用作外部地址簿提供程序，从而条目添加到容器中其他提供程序</span><span class="sxs-lookup"><span data-stu-id="b6295-121">Act as a foreign address book provider by allowing entries to be added to a container in another provider</span></span>  <br/> | <span data-ttu-id="b6295-122">支持的宿主提供程序中的数据绑定代码：</span><span class="sxs-lookup"><span data-stu-id="b6295-122">Support binding code to data in the host provider by:</span></span>  <br/>  <span data-ttu-id="b6295-123">消息用户和通讯组列表上支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b6295-123">Supporting the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property on messaging users and distribution lists.</span></span> <span data-ttu-id="b6295-124">有关详细信息，请参阅[地址簿标识符](address-book-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="b6295-124">For more information, see [Address Book Identifiers](address-book-identifiers.md).</span></span>  <br/>  <span data-ttu-id="b6295-125">实现[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b6295-125">Implementing the [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> <span data-ttu-id="b6295-126">有关详细信息，请参阅[充当外的通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="b6295-126">For more information, see [Acting as a Foreign Address Book Provider](acting-as-a-foreign-address-book-provider.md).</span></span>  <br/> |
|<span data-ttu-id="b6295-127">通过从其他提供程序插入条目充当主机通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="b6295-127">Acting as a host address book provider by inserting entries from another provider</span></span>  <br/> |<span data-ttu-id="b6295-128">支持将数据绑定到代码从外的提供程序通过调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b6295-128">Support binding data to code from a foreign provider by calling the [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) method.</span></span> <span data-ttu-id="b6295-129">有关详细信息，请参阅[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="b6295-129">For more information, see [Acting as a Host Address Book Provider](acting-as-a-host-address-book-provider.md).</span></span>  <br/> |
|<span data-ttu-id="b6295-130">前缀滚动</span><span class="sxs-lookup"><span data-stu-id="b6295-130">Prefix scrolling</span></span>  <br/> |<span data-ttu-id="b6295-131">支持容器内容表上的限制。</span><span class="sxs-lookup"><span data-stu-id="b6295-131">Support restrictions on container contents tables.</span></span> <span data-ttu-id="b6295-132">有关详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="b6295-132">For more information, see [About Restrictions](about-restrictions.md).</span></span>  <br/> |
|<span data-ttu-id="b6295-133">高级搜索容器中</span><span class="sxs-lookup"><span data-stu-id="b6295-133">Advanced searching in a container</span></span>  <br/> |<span data-ttu-id="b6295-134">在容器支持**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 的属性。</span><span class="sxs-lookup"><span data-stu-id="b6295-134">Support the **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) property on containers.</span></span> <span data-ttu-id="b6295-135">有关详细信息，请参阅[实现高级搜索](implementing-advanced-searching.md)。</span><span class="sxs-lookup"><span data-stu-id="b6295-135">For more information, see [Implementing Advanced Searching](implementing-advanced-searching.md).</span></span>  <br/> |
|<span data-ttu-id="b6295-136">事件通知</span><span class="sxs-lookup"><span data-stu-id="b6295-136">Event notification</span></span>  <br/> |<span data-ttu-id="b6295-137">实现[IABLogon::Advise](iablogon-advise.md)和[IABLogon::Unadvise](iablogon-unadvise.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b6295-137">Implement the [IABLogon::Advise](iablogon-advise.md) and [IABLogon::Unadvise](iablogon-unadvise.md) methods.</span></span> <span data-ttu-id="b6295-138">有关详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="b6295-138">For more information, see [Event Notification in MAPI](event-notification-in-mapi.md) and [Supporting Event Notification](supporting-event-notification.md).</span></span>  <br/> |
   
<span data-ttu-id="b6295-139">事件通知**IABLogon::Advise**方法将由调用 MAPI 客户端呼叫**IAddrBook::Advise**注册任一您容器上的通知消息用户或通讯组列表时。</span><span class="sxs-lookup"><span data-stu-id="b6295-139">For event notification, your **IABLogon::Advise** method will be called by MAPI when a client calls **IAddrBook::Advise** to register for notifications on any one of your containers, messaging users, or distribution lists.</span></span> <span data-ttu-id="b6295-140">但是，由于支持事件通知的操作是可选的您可以从这些方法返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="b6295-140">However, because supporting event notification is optional, you can return MAPI_E_NO_SUPPORT from these methods.</span></span> <span data-ttu-id="b6295-141">但是，MAPI 建议您至少支持内容表上的通知和鼓励您支持所有对象除_fnevSearchComplete_和_fnevCriticalError_事件的通知中添加值的类型。</span><span class="sxs-lookup"><span data-stu-id="b6295-141">However, MAPI does recommend that you at least support notifications on your contents tables and encourages you to support all types of object notification except for  _fnevSearchComplete_ and the  _fnevCriticalError_ event to add value.</span></span> 
  

