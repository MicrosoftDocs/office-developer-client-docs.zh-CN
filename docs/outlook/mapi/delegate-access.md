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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427260"
---
# <a name="delegate-access"></a><span data-ttu-id="b9cd9-103">委派访问</span><span class="sxs-lookup"><span data-stu-id="b9cd9-103">Delegate Access</span></span>

  
  
<span data-ttu-id="b9cd9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9cd9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9cd9-105">委派访问是指用户以其他用户发送消息或接收其他用户的邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-105">Delegate access refers to the user's ability to send a message as another user or receive a message for another user.</span></span> <span data-ttu-id="b9cd9-106">委派访问是 MAPI 的独立于服务提供商的功能，传输提供程序可以选择此功能时可支持此功能。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-106">Delegate access is a service provider-independent feature of MAPI that transport providers can support if they choose.</span></span> <span data-ttu-id="b9cd9-107">但是，不需要提供程序来这样做。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-107">However, no provider is required to do so.</span></span> <span data-ttu-id="b9cd9-108">在用户有必要将传入邮件作为其他用户发送邮件或筛选其传入邮件时，或者当用户必须访问其他用户的邮件存储时，委派访问将十分有价值。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-108">Delegate access is valuable when it is necessary for a user to send messages as, or filter incoming messages for, another user or when a user must access another user's message store.</span></span> <span data-ttu-id="b9cd9-109">在允许代理用户连接到其他用户的存储区之前，邮件存储提供程序必须验证委派用户是否具有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-109">Before allowing a delegate user to connect to another user's store, the message store provider must verify that the delegate user has the proper authority.</span></span> 
  
<span data-ttu-id="b9cd9-110">有两组属性用于支持委派访问：</span><span class="sxs-lookup"><span data-stu-id="b9cd9-110">There are two groups of properties that are used to support delegate access:</span></span>
  
 <span data-ttu-id="b9cd9-111">**PR_SENT_REPRESENTING_ADDRTYPE (** [PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b9cd9-111">**PR_SENT_REPRESENTING_ADDRTYPE** ([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md))</span></span> 
  
 <span data-ttu-id="b9cd9-112">**PR_SENT_REPRESENTING_EMAIL_ADDRESS (** [PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b9cd9-112">**PR_SENT_REPRESENTING_EMAIL_ADDRESS** ([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md))</span></span> 
  
 <span data-ttu-id="b9cd9-113">**PR_SENT_REPRESENTING_ENTRYID (** [PidTagSentRepresentingEntryId)](pidtagsentrepresentingentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="b9cd9-113">**PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))</span></span> 
  
 <span data-ttu-id="b9cd9-114">**PR_SENT_REPRESENTING_NAME (** [PidTagSentRepresentingName)](pidtagsentrepresentingname-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="b9cd9-114">**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span></span> 
  
 <span data-ttu-id="b9cd9-115">**PR_SENT_REPRESENTING_SEARCH_KEY (** [PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b9cd9-115">**PR_SENT_REPRESENTING_SEARCH_KEY** ([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))</span></span> 
  
 <span data-ttu-id="b9cd9-116">**PR_RCVD_REPRESENTING_ADDRTYPE (** [PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b9cd9-116">**PR_RCVD_REPRESENTING_ADDRTYPE** ([PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md))</span></span> 
  
 <span data-ttu-id="b9cd9-117">**PR_RCVD_REPRESENTING_EMAIL_ADDRESS (** [PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b9cd9-117">**PR_RCVD_REPRESENTING_EMAIL_ADDRESS** ([PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md))</span></span> 
  
 <span data-ttu-id="b9cd9-118">**PR_RCVD_REPRESENTING_ENTRYID (** [PidTagReceivedRepresentingEntryId)](pidtagreceivedrepresentingentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="b9cd9-118">**PR_RCVD_REPRESENTING_ENTRYID** ([PidTagReceivedRepresentingEntryId](pidtagreceivedrepresentingentryid-canonical-property.md))</span></span> 
  
 <span data-ttu-id="b9cd9-119">**PR_RCVD_REPRESENTING_NAME (** [PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b9cd9-119">**PR_RCVD_REPRESENTING_NAME** ([PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))</span></span> 
  
 <span data-ttu-id="b9cd9-120">**PR_RCVD_REPRESENTING_SEARCH_KEY (** [PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b9cd9-120">**PR_RCVD_REPRESENTING_SEARCH_KEY** ([PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))</span></span> 
  
<span data-ttu-id="b9cd9-121">对于传出邮件 **，PR_SENT_REPRESENTING** 属性标识应充当发件人的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-121">On outgoing messages, the **PR_SENT_REPRESENTING** properties identify the messaging user that should act as the sender.</span></span> <span data-ttu-id="b9cd9-122">客户端可以将这些属性设置为选项。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-122">Clients can set these properties as an option.</span></span> <span data-ttu-id="b9cd9-123">如果 **PR_SENT_REPRESENTING** 到达支持委派访问的传输提供程序时未设置属性，则提供程序负责将它们与 PR_SENDER **属性一** 起设置。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-123">If the **PR_SENT_REPRESENTING** properties are not set by the time the message reaches a transport provider that supports delegate access, it is the provider's responsibility to set them along with the **PR_SENDER** properties.</span></span> 
  
<span data-ttu-id="b9cd9-124">对于传入的邮件 **，PR_RCVD_REPRESENTING** 属性标识应充当收件人的用户。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-124">On incoming messages, the **PR_RCVD_REPRESENTING** properties identify the user that should act as the recipient.</span></span> <span data-ttu-id="b9cd9-125">负责传递委派邮件的传输提供程序必须同时设置 PR_RCVD_REPRESENTING **和\*\*\*\*PR_RECEIVED_BY** 属性。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-125">Transport providers responsible for delivering delegate messages must set both the **PR_RCVD_REPRESENTING** and **PR_RECEIVED_BY** properties.</span></span> <span data-ttu-id="b9cd9-126">接收代理邮件的客户端应该将 PR_SENT_REPRESENTING **属性的值复制到\*\*\*\*相应的** PR_RCVD_REPRESENTING 属性。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-126">Clients receiving a delegate message should copy the values of the **PR_SENT_REPRESENTING** properties to the corresponding **PR_RCVD_REPRESENTING** properties.</span></span> 
  
<span data-ttu-id="b9cd9-127">例如，假设 John 在 Sally 休假期间收到 Sally 的邮件。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-127">For example, suppose John is receiving Sally's messages while Sally is on vacation.</span></span> <span data-ttu-id="b9cd9-128">The **PR_RCVD_REPRESENTING** properties identify John as the delegate recipient.</span><span class="sxs-lookup"><span data-stu-id="b9cd9-128">The **PR_RCVD_REPRESENTING** properties identify John as the delegate recipient.</span></span> <span data-ttu-id="b9cd9-129">当 John 发送对 Sally 收到的邮件的答复时，该邮件 **PR_SENDER属性将** John 标识为发件人。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-129">When John sends a reply to a message that he has received for Sally, the message's **PR_SENDER** properties identify John as the sender.</span></span> <span data-ttu-id="b9cd9-130">由于 John 表示 Sally，因此 **PR_SENT_REPRESENTING标识** Sally。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-130">Because John is representing Sally, the **PR_SENT_REPRESENTING** properties identify Sally.</span></span> 
  
<span data-ttu-id="b9cd9-131">处理传入委派邮件的传输提供程序通常应该将这些邮件作为 PR_SENT_REPRESENTING **属性标识** 的邮件用户而不是由 PR_SENDER **属性标识** 的用户传递。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-131">Transport providers handling incoming delegate messages should usually deliver these messages as the messaging user identified by the **PR_SENT_REPRESENTING** properties rather than as the user identified by the **PR_SENDER** properties.</span></span> <span data-ttu-id="b9cd9-132">此规则的例外情况是，需要匹配访问特权和传输类型。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-132">The exception to this rule is when it is necessary to match access privilege and transport types.</span></span> <span data-ttu-id="b9cd9-133">在这种情况下，传输提供程序可以选择发送标识。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-133">In this case, a transport provider can choose a sending identity.</span></span> 
  
<span data-ttu-id="b9cd9-134">如果 **PR_SENT_REPRESENTING** 属性对传入的委派邮件不可用，则处理传递的传输提供程序必须使用相应的 PR_SENDER **属性的值进行** 设置。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-134">If the **PR_SENT_REPRESENTING** properties are unavailable for an incoming delegate message, the transport provider handling delivery must set them, using the values of the corresponding **PR_SENDER** properties.</span></span> <span data-ttu-id="b9cd9-135">如果 **PR_SENT_REPRESENTING** 属性可用，但传输提供程序不支持委派访问，则传输提供程序可以使用 PR_SENDER **属性进行** 传递。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-135">If the **PR_SENT_REPRESENTING** properties are available but the transport provider does not support delegate access, it can use the **PR_SENDER** properties for delivery.</span></span> 
  

