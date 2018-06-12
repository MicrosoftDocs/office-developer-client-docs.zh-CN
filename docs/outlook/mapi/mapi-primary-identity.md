---
title: MAPI 主标识
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8787a873-6752-4b17-8ea3-8fed793e1371
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bd6fe1298a38733cb9d4916a931138c616e110bf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776285"
---
# <a name="mapi-primary-identity"></a><span data-ttu-id="7300c-103">MAPI 主标识</span><span class="sxs-lookup"><span data-stu-id="7300c-103">MAPI Primary Identity</span></span>

  
  
<span data-ttu-id="7300c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7300c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7300c-105">大多数 MAPI 会话具有会话中提供的主要标识的特定服务提供商。</span><span class="sxs-lookup"><span data-stu-id="7300c-105">Most MAPI sessions have a particular service provider that supplies the primary identity for the session.</span></span> <span data-ttu-id="7300c-106">通常，它是通讯簿提供程序，它提供标识通过其消息的用户对象或通讯组列表之一。</span><span class="sxs-lookup"><span data-stu-id="7300c-106">Typically, it is an address book provider, which supplies identity through one of its messaging user objects or distribution lists.</span></span> <span data-ttu-id="7300c-107">实际上，MAPI 建议消息服务包括通讯簿提供程序的主标识使用它的一个对象。</span><span class="sxs-lookup"><span data-stu-id="7300c-107">In fact, MAPI recommends that message services that include an address book provider use one of its objects for the primary identity.</span></span> <span data-ttu-id="7300c-108">当所属的消息服务的服务提供商提供的主要标识时，消息服务中其他服务提供商的所有共享此标识。</span><span class="sxs-lookup"><span data-stu-id="7300c-108">When a service provider that belongs to a message service supplies the primary identity, all of the other service providers in the message service share this identity.</span></span>
  
<span data-ttu-id="7300c-109">MAPISVC。INF 配置文件具有与 identity 同时在消息服务和服务提供程序级别的条目。</span><span class="sxs-lookup"><span data-stu-id="7300c-109">The MAPISVC.INF configuration file has entries relating to identity at both the message service and service provider level.</span></span> <span data-ttu-id="7300c-110">消息服务部分必须包括一个条目，指出该服务可以提供的主要标识;服务提供程序部分仅时的提供程序可以提供标识包含类似的项。</span><span class="sxs-lookup"><span data-stu-id="7300c-110">Message service sections must include an entry that states whether or not the service can supply the primary identity; service provider sections include a similar entry only when the provider can supply an identity.</span></span>
  
<span data-ttu-id="7300c-111">下表列出了消息服务和 MAPISVC 中的服务提供程序部分中显示的项。INF 文件。</span><span class="sxs-lookup"><span data-stu-id="7300c-111">The following table lists the entries that appear in the message service and service provider sections in the MAPISVC.INF file.</span></span>
  
|<span data-ttu-id="7300c-112">**主标识供应商**</span><span class="sxs-lookup"><span data-stu-id="7300c-112">**Primary identity supplier**</span></span>|<span data-ttu-id="7300c-113">**PR_RESOURCE_FLAGS 设置**</span><span class="sxs-lookup"><span data-stu-id="7300c-113">**PR_RESOURCE_FLAGS setting**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7300c-114">邮件服务</span><span class="sxs-lookup"><span data-stu-id="7300c-114">Message service</span></span>  <br/> | `SERVICE_PRIMARY_IDENTITY` <br/> |
|<span data-ttu-id="7300c-115">不邮件服务</span><span class="sxs-lookup"><span data-stu-id="7300c-115">Not the message service</span></span>  <br/> | `SERVICE_NO_PRIMARY_IDENTITY` <br/> |
|<span data-ttu-id="7300c-116">服务提供商</span><span class="sxs-lookup"><span data-stu-id="7300c-116">Service provider</span></span>  <br/> | `STATUS_PRIMARY_IDENTITY` <br/> |
   
<span data-ttu-id="7300c-117">虽然多个邮件服务可以将其能够提供会话的主标识声明，只有一个邮件服务处于选中状态，这样做。</span><span class="sxs-lookup"><span data-stu-id="7300c-117">Although multiple message services can declare their ability to provide a session's primary identity, only one message service is selected to do so.</span></span> <span data-ttu-id="7300c-118">可能会出现此选项：</span><span class="sxs-lookup"><span data-stu-id="7300c-118">This selection can occur:</span></span>
  
- <span data-ttu-id="7300c-119">创建一个配置文件时。</span><span class="sxs-lookup"><span data-stu-id="7300c-119">When a profile is created.</span></span>
    
- <span data-ttu-id="7300c-120">当客户端调用**IMsgServiceAdmin::SetPrimaryIdentity**以显式建立的会话标识提供程序的特定消息服务。</span><span class="sxs-lookup"><span data-stu-id="7300c-120">When a client calls **IMsgServiceAdmin::SetPrimaryIdentity** to explicitly establish a particular message service as the provider of the session identity.</span></span> <span data-ttu-id="7300c-121">有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="7300c-121">For more information.</span></span> <span data-ttu-id="7300c-122">请参阅[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="7300c-122">See [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md).</span></span>
    
<span data-ttu-id="7300c-123">MAPI 配置文件创建时，指定第一个邮件服务配置包含用 STATUS_PRIMARY_IDENTITY 标志设置其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中提供的主要标识提供程序.</span><span class="sxs-lookup"><span data-stu-id="7300c-123">When a profile is created, MAPI designates the first message service to be configured that includes a provider with the STATUS_PRIMARY_IDENTITY flag set in its **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property to supply the primary identity.</span></span> <span data-ttu-id="7300c-124">中指定的邮件服务，要配置设置此资源标志的第一个提供程序选择提供服务的标识。</span><span class="sxs-lookup"><span data-stu-id="7300c-124">Within the designated message service, the first provider to be configured with this resource flag set is chosen to provide the identity for the service.</span></span> <span data-ttu-id="7300c-125">对指定的服务和配置文件中的其他消息服务中的所有其他提供程序清除 STATUS_PRIMARY_IDENTITY 标志。</span><span class="sxs-lookup"><span data-stu-id="7300c-125">The STATUS_PRIMARY_IDENTITY flag is cleared for all other providers in the designated service and other message services in the profile.</span></span> <span data-ttu-id="7300c-126">如果在任何时候提供主要身份提供程序已从配置文件，MAPI 分配到要配置的下一个提供程序可以提供标识的角色。</span><span class="sxs-lookup"><span data-stu-id="7300c-126">If at any time the provider supplying primary identity is removed from the profile, MAPI assigns the role to the next provider to be configured that can supply identity.</span></span> <span data-ttu-id="7300c-127">这由的外观`PR_RESOURCE_FLAGS=STATUS_PRIMARY_IDENTITY`中 MAPISVC.INF 的提供程序的一节中的条目。</span><span class="sxs-lookup"><span data-stu-id="7300c-127">This is determined by the appearance of the  `PR_RESOURCE_FLAGS=STATUS_PRIMARY_IDENTITY` entry in the provider's section in MAPISVC.INF.</span></span> 
  
<span data-ttu-id="7300c-128">当客户端呼叫消息服务的**IMsgServiceAdmin::SetPrimaryIdentity**方法时，它指定 MAPIUID 中目标服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="7300c-128">When a client calls a message service's **IMsgServiceAdmin::SetPrimaryIdentity** method, it specifies the MAPIUID for a service provider within the target service.</span></span> <span data-ttu-id="7300c-129">有关详细信息，请参阅[MAPIUID](mapiuid.md)。</span><span class="sxs-lookup"><span data-stu-id="7300c-129">For more information, see [MAPIUID](mapiuid.md).</span></span> <span data-ttu-id="7300c-130">分配由**MAPIUID**服务提供商提供的主要标识邮件服务和会话，且所有服务中的其他提供程序将共享此标识。</span><span class="sxs-lookup"><span data-stu-id="7300c-130">The service provider represented by the **MAPIUID** is assigned to supply the primary identity for the message service and for the session, and all of the other providers in the service will share this identity.</span></span> 
  
<span data-ttu-id="7300c-131">负责提供的主要标识的消息服务中的每个提供程序更新其状态表，包括以下属性中的行。</span><span class="sxs-lookup"><span data-stu-id="7300c-131">Every provider in the message service responsible for supplying the primary identity updates its row in the status table to include the following properties.</span></span>
  
|<span data-ttu-id="7300c-132">**主要的 identity 属性**</span><span class="sxs-lookup"><span data-stu-id="7300c-132">**Primary identity property**</span></span>|<span data-ttu-id="7300c-133">**设置为**</span><span class="sxs-lookup"><span data-stu-id="7300c-133">**Set to**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7300c-134">**PR_IDENTITY_DISPLAY**([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7300c-134">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="7300c-135">提供的主要标识对象的显示名称。</span><span class="sxs-lookup"><span data-stu-id="7300c-135">Display name of the object supplying the primary identity.</span></span>  <br/> |
|<span data-ttu-id="7300c-136">**PR_IDENTITY_SEARCH_KEY**([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7300c-136">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="7300c-137">搜索对象提供的主要标识键。</span><span class="sxs-lookup"><span data-stu-id="7300c-137">Search key for the object supplying the primary identity.</span></span>  <br/> |
|<span data-ttu-id="7300c-138">**PR_IDENTITY_ENTRYID**([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7300c-138">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="7300c-139">提供的主要标识的对象的项标识符。</span><span class="sxs-lookup"><span data-stu-id="7300c-139">Entry identifier for the object supplying the primary identity.</span></span>  <br/> |
   
 <span data-ttu-id="7300c-140">**若要检索的对象提供的主要标识的条目标识符**</span><span class="sxs-lookup"><span data-stu-id="7300c-140">**To retrieve the entry identifier for the object supplying the primary identity**</span></span>
  
- <span data-ttu-id="7300c-141">调用**IMAPISession::QueryIdentity**方法。</span><span class="sxs-lookup"><span data-stu-id="7300c-141">Call the **IMAPISession::QueryIdentity** method.</span></span> <span data-ttu-id="7300c-142">有关详细信息，请参阅[IMAPISession::QueryIdentity](imapisession-queryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="7300c-142">For more information, see [IMAPISession::QueryIdentity](imapisession-queryidentity.md).</span></span> <span data-ttu-id="7300c-143">**QueryIdentity**搜索状态表，包含其**PR_RESOURCE_FLAGS**列中的值 STATUS_PRIMARY_IDENTITY 并返回相应**PR_IDENTITY_ENTRYID**作为主的项标识符的行标识。</span><span class="sxs-lookup"><span data-stu-id="7300c-143">**QueryIdentity** searches the status table for the row that contains the value STATUS_PRIMARY_IDENTITY in its **PR_RESOURCE_FLAGS** column and returns the corresponding **PR_IDENTITY_ENTRYID** as the entry identifier for the primary identity.</span></span> 
    

