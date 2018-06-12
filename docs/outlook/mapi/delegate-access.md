---
title: 委派访问
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a863494f-0071-4d97-a6c4-26707ee00e04
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d969fd806e5038e6c918da45041402a981554a49
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774772"
---
# <a name="delegate-access"></a><span data-ttu-id="28b35-103">委派访问</span><span class="sxs-lookup"><span data-stu-id="28b35-103">Delegate Access</span></span>

  
  
<span data-ttu-id="28b35-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="28b35-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="28b35-105">委派访问指作为其他用户发送一条消息，或收到另一个用户的邮件用户的功能。</span><span class="sxs-lookup"><span data-stu-id="28b35-105">Delegate access refers to the user's ability to send a message as another user or receive a message for another user.</span></span> <span data-ttu-id="28b35-106">代理访问是如果他们的选择，可支持传输提供程序的 MAPI 服务提供程序无关功能。</span><span class="sxs-lookup"><span data-stu-id="28b35-106">Delegate access is a service provider-independent feature of MAPI that transport providers can support if they choose.</span></span> <span data-ttu-id="28b35-107">但是，没有提供程序需要这样做。</span><span class="sxs-lookup"><span data-stu-id="28b35-107">However, no provider is required to do so.</span></span> <span data-ttu-id="28b35-108">如有必要，用户可以发送邮件作为，或筛选传入消息的另一个用户或用户时必须访问另一个用户的消息存储库时，可以有价值代理访问。</span><span class="sxs-lookup"><span data-stu-id="28b35-108">Delegate access is valuable when it is necessary for a user to send messages as, or filter incoming messages for, another user or when a user must access another user's message store.</span></span> <span data-ttu-id="28b35-109">允许委派用户连接到另一个用户存储区之前, 的消息存储提供程序必须验证的代理用户具有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="28b35-109">Before allowing a delegate user to connect to another user's store, the message store provider must verify that the delegate user has the proper authority.</span></span> 
  
<span data-ttu-id="28b35-110">有两组用于支持代理访问的属性：</span><span class="sxs-lookup"><span data-stu-id="28b35-110">There are two groups of properties that are used to support delegate access:</span></span>
  
 <span data-ttu-id="28b35-111">**PR_SENT_REPRESENTING_ADDRTYPE**([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-111">**PR_SENT_REPRESENTING_ADDRTYPE** ([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md))</span></span> 
  
 <span data-ttu-id="28b35-112">**PR_SENT_REPRESENTING_EMAIL_ADDRESS**([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-112">**PR_SENT_REPRESENTING_EMAIL_ADDRESS** ([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md))</span></span> 
  
 <span data-ttu-id="28b35-113">**PR_SENT_REPRESENTING_ENTRYID**([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-113">**PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))</span></span> 
  
 <span data-ttu-id="28b35-114">**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-114">**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span></span> 
  
 <span data-ttu-id="28b35-115">**PR_SENT_REPRESENTING_SEARCH_KEY**([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-115">**PR_SENT_REPRESENTING_SEARCH_KEY** ([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))</span></span> 
  
 <span data-ttu-id="28b35-116">**PR_RCVD_REPRESENTING_ADDRTYPE**([PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-116">**PR_RCVD_REPRESENTING_ADDRTYPE** ([PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md))</span></span> 
  
 <span data-ttu-id="28b35-117">**PR_RCVD_REPRESENTING_EMAIL_ADDRESS**([PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-117">**PR_RCVD_REPRESENTING_EMAIL_ADDRESS** ([PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md))</span></span> 
  
 <span data-ttu-id="28b35-118">**PR_RCVD_REPRESENTING_ENTRYID**([PidTagReceivedRepresentingEntryId](pidtagreceivedrepresentingentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-118">**PR_RCVD_REPRESENTING_ENTRYID** ([PidTagReceivedRepresentingEntryId](pidtagreceivedrepresentingentryid-canonical-property.md))</span></span> 
  
 <span data-ttu-id="28b35-119">**PR_RCVD_REPRESENTING_NAME**([PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-119">**PR_RCVD_REPRESENTING_NAME** ([PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))</span></span> 
  
 <span data-ttu-id="28b35-120">**PR_RCVD_REPRESENTING_SEARCH_KEY**([PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28b35-120">**PR_RCVD_REPRESENTING_SEARCH_KEY** ([PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))</span></span> 
  
<span data-ttu-id="28b35-121">对传出邮件**PR_SENT_REPRESENTING**属性确定应作为发件人的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="28b35-121">On outgoing messages, the **PR_SENT_REPRESENTING** properties identify the messaging user that should act as the sender.</span></span> <span data-ttu-id="28b35-122">客户端可以作为选项来设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="28b35-122">Clients can set these properties as an option.</span></span> <span data-ttu-id="28b35-123">如果**PR_SENT_REPRESENTING**属性设置不按时间消息到达传输提供程序的支持代理访问，则提供程序负责将它们设置以及**PR_SENDER**属性。</span><span class="sxs-lookup"><span data-stu-id="28b35-123">If the **PR_SENT_REPRESENTING** properties are not set by the time the message reaches a transport provider that supports delegate access, it is the provider's responsibility to set them along with the **PR_SENDER** properties.</span></span> 
  
<span data-ttu-id="28b35-124">对传入邮件**PR_RCVD_REPRESENTING**属性标识的用户的应作为收件人。</span><span class="sxs-lookup"><span data-stu-id="28b35-124">On incoming messages, the **PR_RCVD_REPRESENTING** properties identify the user that should act as the recipient.</span></span> <span data-ttu-id="28b35-125">传输提供程序负责委托邮件传递必须设置的**PR_RCVD_REPRESENTING**和**PR_RECEIVED_BY**属性。</span><span class="sxs-lookup"><span data-stu-id="28b35-125">Transport providers responsible for delivering delegate messages must set both the **PR_RCVD_REPRESENTING** and **PR_RECEIVED_BY** properties.</span></span> <span data-ttu-id="28b35-126">客户端接收委托邮件应将**PR_SENT_REPRESENTING**属性的值复制到相应的**PR_RCVD_REPRESENTING**属性。</span><span class="sxs-lookup"><span data-stu-id="28b35-126">Clients receiving a delegate message should copy the values of the **PR_SENT_REPRESENTING** properties to the corresponding **PR_RCVD_REPRESENTING** properties.</span></span> 
  
<span data-ttu-id="28b35-127">例如，假设 John Sally 度假时接收 Sally 的邮件。</span><span class="sxs-lookup"><span data-stu-id="28b35-127">For example, suppose John is receiving Sally's messages while Sally is on vacation.</span></span> <span data-ttu-id="28b35-128">**PR_RCVD_REPRESENTING**属性标识为委托收件人 John。</span><span class="sxs-lookup"><span data-stu-id="28b35-128">The **PR_RCVD_REPRESENTING** properties identify John as the delegate recipient.</span></span> <span data-ttu-id="28b35-129">当 John 的 Sally 发送答复他已收到一条消息时，该消息的**PR_SENDER**属性标识发件人为 John。</span><span class="sxs-lookup"><span data-stu-id="28b35-129">When John sends a reply to a message that he has received for Sally, the message's **PR_SENDER** properties identify John as the sender.</span></span> <span data-ttu-id="28b35-130">John 代表 Sally，因为**PR_SENT_REPRESENTING**属性确定 Sally。</span><span class="sxs-lookup"><span data-stu-id="28b35-130">Because John is representing Sally, the **PR_SENT_REPRESENTING** properties identify Sally.</span></span> 
  
<span data-ttu-id="28b35-131">传输提供程序处理传入委托消息通常应为标识**PR_SENT_REPRESENTING**属性并由它们的邮件用户而不是由**PR_SENDER**属性标识的用户提供这些消息。</span><span class="sxs-lookup"><span data-stu-id="28b35-131">Transport providers handling incoming delegate messages should usually deliver these messages as the messaging user identified by the **PR_SENT_REPRESENTING** properties rather than as the user identified by the **PR_SENDER** properties.</span></span> <span data-ttu-id="28b35-132">如有必要，以匹配访问权限和传输类型时，此规则的例外。</span><span class="sxs-lookup"><span data-stu-id="28b35-132">The exception to this rule is when it is necessary to match access privilege and transport types.</span></span> <span data-ttu-id="28b35-133">在这种情况下，传输提供程序可以选择发送的标识。</span><span class="sxs-lookup"><span data-stu-id="28b35-133">In this case, a transport provider can choose a sending identity.</span></span> 
  
<span data-ttu-id="28b35-134">如果为传入委托消息**PR_SENT_REPRESENTING**属性不可用，处理传递传输提供程序必须设置，使用相应的**PR_SENDER**属性的值。</span><span class="sxs-lookup"><span data-stu-id="28b35-134">If the **PR_SENT_REPRESENTING** properties are unavailable for an incoming delegate message, the transport provider handling delivery must set them, using the values of the corresponding **PR_SENDER** properties.</span></span> <span data-ttu-id="28b35-135">如果**PR_SENT_REPRESENTING**属性均可用，但传输提供程序不支持代理访问，它可以传递使用**PR_SENDER**属性。</span><span class="sxs-lookup"><span data-stu-id="28b35-135">If the **PR_SENT_REPRESENTING** properties are available but the transport provider does not support delegate access, it can use the **PR_SENDER** properties for delivery.</span></span> 
  

