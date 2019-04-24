---
title: 委派访问
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a863494f-0071-4d97-a6c4-26707ee00e04
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3d6a0eaf8ad125a0ae1ea3abb57e2aa57e0bdfe3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336734"
---
# <a name="delegate-access"></a><span data-ttu-id="2ce89-103">委派访问</span><span class="sxs-lookup"><span data-stu-id="2ce89-103">Delegate Access</span></span>

  
  
<span data-ttu-id="2ce89-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ce89-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ce89-105">委派访问权限是指用户以其他用户身份发送邮件或为其他用户接收邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="2ce89-105">Delegate access refers to the user's ability to send a message as another user or receive a message for another user.</span></span> <span data-ttu-id="2ce89-106">代理访问是 MAPI 的一种独立于服务提供程序的功能, 传输提供程序可以在选择时支持这些功能。</span><span class="sxs-lookup"><span data-stu-id="2ce89-106">Delegate access is a service provider-independent feature of MAPI that transport providers can support if they choose.</span></span> <span data-ttu-id="2ce89-107">但是, 无需提供程序即可执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2ce89-107">However, no provider is required to do so.</span></span> <span data-ttu-id="2ce89-108">当用户需要向其他用户发送邮件, 或筛选其他用户的传入邮件时, 或者用户必须访问其他用户的邮件存储时, 委派访问非常有用。</span><span class="sxs-lookup"><span data-stu-id="2ce89-108">Delegate access is valuable when it is necessary for a user to send messages as, or filter incoming messages for, another user or when a user must access another user's message store.</span></span> <span data-ttu-id="2ce89-109">在允许代理用户连接到另一个用户的存储之前, 邮件存储提供程序必须验证代理用户是否具有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="2ce89-109">Before allowing a delegate user to connect to another user's store, the message store provider must verify that the delegate user has the proper authority.</span></span> 
  
<span data-ttu-id="2ce89-110">有两组用于支持代理访问的属性:</span><span class="sxs-lookup"><span data-stu-id="2ce89-110">There are two groups of properties that are used to support delegate access:</span></span>
  
 <span data-ttu-id="2ce89-111">**PR_SENT_REPRESENTING_ADDRTYPE**([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-111">**PR_SENT_REPRESENTING_ADDRTYPE** ([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md))</span></span> 
  
 <span data-ttu-id="2ce89-112">**PR_SENT_REPRESENTING_EMAIL_ADDRESS**([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-112">**PR_SENT_REPRESENTING_EMAIL_ADDRESS** ([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md))</span></span> 
  
 <span data-ttu-id="2ce89-113">**PR_SENT_REPRESENTING_ENTRYID**([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-113">**PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))</span></span> 
  
 <span data-ttu-id="2ce89-114">**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-114">**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span></span> 
  
 <span data-ttu-id="2ce89-115">**PR_SENT_REPRESENTING_SEARCH_KEY**([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-115">**PR_SENT_REPRESENTING_SEARCH_KEY** ([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))</span></span> 
  
 <span data-ttu-id="2ce89-116">**PR_RCVD_REPRESENTING_ADDRTYPE**([PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-116">**PR_RCVD_REPRESENTING_ADDRTYPE** ([PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md))</span></span> 
  
 <span data-ttu-id="2ce89-117">**PR_RCVD_REPRESENTING_EMAIL_ADDRESS**([PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-117">**PR_RCVD_REPRESENTING_EMAIL_ADDRESS** ([PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md))</span></span> 
  
 <span data-ttu-id="2ce89-118">**PR_RCVD_REPRESENTING_ENTRYID**([PidTagReceivedRepresentingEntryId](pidtagreceivedrepresentingentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-118">**PR_RCVD_REPRESENTING_ENTRYID** ([PidTagReceivedRepresentingEntryId](pidtagreceivedrepresentingentryid-canonical-property.md))</span></span> 
  
 <span data-ttu-id="2ce89-119">**PR_RCVD_REPRESENTING_NAME**([PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-119">**PR_RCVD_REPRESENTING_NAME** ([PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))</span></span> 
  
 <span data-ttu-id="2ce89-120">**PR_RCVD_REPRESENTING_SEARCH_KEY**([PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2ce89-120">**PR_RCVD_REPRESENTING_SEARCH_KEY** ([PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))</span></span> 
  
<span data-ttu-id="2ce89-121">在传出邮件上, **PR_SENT_REPRESENTING**属性标识应充当发件人的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="2ce89-121">On outgoing messages, the **PR_SENT_REPRESENTING** properties identify the messaging user that should act as the sender.</span></span> <span data-ttu-id="2ce89-122">客户端可以将这些属性设置为选项。</span><span class="sxs-lookup"><span data-stu-id="2ce89-122">Clients can set these properties as an option.</span></span> <span data-ttu-id="2ce89-123">如果邮件到达支持代理访问的传输提供程序时未设置**PR_SENT_REPRESENTING**属性, 则提供程序负责将它们设置为与**PR_SENDER**属性一起使用。</span><span class="sxs-lookup"><span data-stu-id="2ce89-123">If the **PR_SENT_REPRESENTING** properties are not set by the time the message reaches a transport provider that supports delegate access, it is the provider's responsibility to set them along with the **PR_SENDER** properties.</span></span> 
  
<span data-ttu-id="2ce89-124">在传入邮件中, **PR_RCVD_REPRESENTING**属性标识应充当收件人的用户。</span><span class="sxs-lookup"><span data-stu-id="2ce89-124">On incoming messages, the **PR_RCVD_REPRESENTING** properties identify the user that should act as the recipient.</span></span> <span data-ttu-id="2ce89-125">负责传递委派邮件的传输提供程序必须同时设置**PR_RCVD_REPRESENTING**和**PR_RECEIVED_BY**属性。</span><span class="sxs-lookup"><span data-stu-id="2ce89-125">Transport providers responsible for delivering delegate messages must set both the **PR_RCVD_REPRESENTING** and **PR_RECEIVED_BY** properties.</span></span> <span data-ttu-id="2ce89-126">接收代理消息的客户端应将**PR_SENT_REPRESENTING**属性的值复制到相应的**PR_RCVD_REPRESENTING**属性中。</span><span class="sxs-lookup"><span data-stu-id="2ce89-126">Clients receiving a delegate message should copy the values of the **PR_SENT_REPRESENTING** properties to the corresponding **PR_RCVD_REPRESENTING** properties.</span></span> 
  
<span data-ttu-id="2ce89-127">例如, 假设 John 在 Sally 休假时收到 Sally 的邮件。</span><span class="sxs-lookup"><span data-stu-id="2ce89-127">For example, suppose John is receiving Sally's messages while Sally is on vacation.</span></span> <span data-ttu-id="2ce89-128">**PR_RCVD_REPRESENTING**属性将 John 标识为代理收件人。</span><span class="sxs-lookup"><span data-stu-id="2ce89-128">The **PR_RCVD_REPRESENTING** properties identify John as the delegate recipient.</span></span> <span data-ttu-id="2ce89-129">当 John 将答复发送给他收到的 Sally 邮件时, 邮件的**PR_SENDER**属性会将 John 标识为发件人。</span><span class="sxs-lookup"><span data-stu-id="2ce89-129">When John sends a reply to a message that he has received for Sally, the message's **PR_SENDER** properties identify John as the sender.</span></span> <span data-ttu-id="2ce89-130">因为 John 代表 Sally, 所以**PR_SENT_REPRESENTING**属性标识 Sally。</span><span class="sxs-lookup"><span data-stu-id="2ce89-130">Because John is representing Sally, the **PR_SENT_REPRESENTING** properties identify Sally.</span></span> 
  
<span data-ttu-id="2ce89-131">处理传入代理邮件的传输提供程序通常应以**PR_SENT_REPRESENTING**属性 (而不是由**PR_SENDER**属性标识的用户) 标识的邮件用户的形式传递这些邮件。</span><span class="sxs-lookup"><span data-stu-id="2ce89-131">Transport providers handling incoming delegate messages should usually deliver these messages as the messaging user identified by the **PR_SENT_REPRESENTING** properties rather than as the user identified by the **PR_SENDER** properties.</span></span> <span data-ttu-id="2ce89-132">此规则的例外是在需要匹配访问权限和传输类型时。</span><span class="sxs-lookup"><span data-stu-id="2ce89-132">The exception to this rule is when it is necessary to match access privilege and transport types.</span></span> <span data-ttu-id="2ce89-133">在这种情况下, 传输提供程序可以选择发送标识。</span><span class="sxs-lookup"><span data-stu-id="2ce89-133">In this case, a transport provider can choose a sending identity.</span></span> 
  
<span data-ttu-id="2ce89-134">如果**PR_SENT_REPRESENTING**属性不可用于传入代理邮件, 则传输提供程序处理传递必须使用相应的**PR_SENDER**属性的值进行设置。</span><span class="sxs-lookup"><span data-stu-id="2ce89-134">If the **PR_SENT_REPRESENTING** properties are unavailable for an incoming delegate message, the transport provider handling delivery must set them, using the values of the corresponding **PR_SENDER** properties.</span></span> <span data-ttu-id="2ce89-135">如果**PR_SENT_REPRESENTING**属性可用, 但传输提供程序不支持代理访问, 则可以使用**PR_SENDER**属性进行传递。</span><span class="sxs-lookup"><span data-stu-id="2ce89-135">If the **PR_SENT_REPRESENTING** properties are available but the transport provider does not support delegate access, it can use the **PR_SENDER** properties for delivery.</span></span> 
  

