---
title: MAPI 主标识
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8787a873-6752-4b17-8ea3-8fed793e1371
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5bf88de280b012c54d4caaac6bdfe877f476ac37
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404720"
---
# <a name="mapi-primary-identity"></a><span data-ttu-id="33d89-103">MAPI 主标识</span><span class="sxs-lookup"><span data-stu-id="33d89-103">MAPI Primary Identity</span></span>

  
  
<span data-ttu-id="33d89-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="33d89-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="33d89-105">大多数 MAPI 会话都有一个为会话提供主标识的特定服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="33d89-105">Most MAPI sessions have a particular service provider that supplies the primary identity for the session.</span></span> <span data-ttu-id="33d89-106">通常，它是通讯簿提供程序，通过邮件传递用户对象或通讯组列表之一提供标识。</span><span class="sxs-lookup"><span data-stu-id="33d89-106">Typically, it is an address book provider, which supplies identity through one of its messaging user objects or distribution lists.</span></span> <span data-ttu-id="33d89-107">事实上，MAPI 建议包含通讯簿提供程序的邮件服务使用其对象之一作为主标识。</span><span class="sxs-lookup"><span data-stu-id="33d89-107">In fact, MAPI recommends that message services that include an address book provider use one of its objects for the primary identity.</span></span> <span data-ttu-id="33d89-108">当属于邮件服务的服务提供商提供主标识时，邮件服务中的所有其他服务提供商将共享此标识。</span><span class="sxs-lookup"><span data-stu-id="33d89-108">When a service provider that belongs to a message service supplies the primary identity, all of the other service providers in the message service share this identity.</span></span>
  
<span data-ttu-id="33d89-109">MAPISVC。INF 配置文件在邮件服务和服务提供商级别都有与标识相关的条目。</span><span class="sxs-lookup"><span data-stu-id="33d89-109">The MAPISVC.INF configuration file has entries relating to identity at both the message service and service provider level.</span></span> <span data-ttu-id="33d89-110">邮件服务部分必须包含一个条目，该条目指出服务是否可以提供主标识;只有在提供程序提供标识时，服务提供程序部分才包括类似的条目。</span><span class="sxs-lookup"><span data-stu-id="33d89-110">Message service sections must include an entry that states whether or not the service can supply the primary identity; service provider sections include a similar entry only when the provider can supply an identity.</span></span>
  
<span data-ttu-id="33d89-111">下表列出了 MAPISVC 中邮件服务和服务提供程序部分出现的条目。INF 文件。</span><span class="sxs-lookup"><span data-stu-id="33d89-111">The following table lists the entries that appear in the message service and service provider sections in the MAPISVC.INF file.</span></span>
  
|<span data-ttu-id="33d89-112">**主要标识供应商**</span><span class="sxs-lookup"><span data-stu-id="33d89-112">**Primary identity supplier**</span></span>|<span data-ttu-id="33d89-113">**PR_RESOURCE_FLAGS设置**</span><span class="sxs-lookup"><span data-stu-id="33d89-113">**PR_RESOURCE_FLAGS setting**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33d89-114">邮件服务</span><span class="sxs-lookup"><span data-stu-id="33d89-114">Message service</span></span>  <br/> | `SERVICE_PRIMARY_IDENTITY` <br/> |
|<span data-ttu-id="33d89-115">不是邮件服务</span><span class="sxs-lookup"><span data-stu-id="33d89-115">Not the message service</span></span>  <br/> | `SERVICE_NO_PRIMARY_IDENTITY` <br/> |
|<span data-ttu-id="33d89-116">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="33d89-116">Service provider</span></span>  <br/> | `STATUS_PRIMARY_IDENTITY` <br/> |
   
<span data-ttu-id="33d89-117">尽管多个邮件服务可以声明它们提供会话的主标识的能力，但仅选择了一个邮件服务来这样做。</span><span class="sxs-lookup"><span data-stu-id="33d89-117">Although multiple message services can declare their ability to provide a session's primary identity, only one message service is selected to do so.</span></span> <span data-ttu-id="33d89-118">此选择可能发生：</span><span class="sxs-lookup"><span data-stu-id="33d89-118">This selection can occur:</span></span>
  
- <span data-ttu-id="33d89-119">创建配置文件时。</span><span class="sxs-lookup"><span data-stu-id="33d89-119">When a profile is created.</span></span>
    
- <span data-ttu-id="33d89-120">当客户端调用 **IMsgServiceAdmin：：SetPrimaryIdentity** 以明确建立特定邮件服务作为会话标识的提供程序时。</span><span class="sxs-lookup"><span data-stu-id="33d89-120">When a client calls **IMsgServiceAdmin::SetPrimaryIdentity** to explicitly establish a particular message service as the provider of the session identity.</span></span> <span data-ttu-id="33d89-121">有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="33d89-121">For more information.</span></span> <span data-ttu-id="33d89-122">请参阅 [IMsgServiceAdmin：：SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="33d89-122">See [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md).</span></span>
    
<span data-ttu-id="33d89-123">创建配置文件时，MAPI 指定要配置的第一个邮件服务，其中包括在其 PR_RESOURCE_FLAGS ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置了 **STATUS_PRIMARY_IDENTITY** 标志的提供程序，以提供主标识。</span><span class="sxs-lookup"><span data-stu-id="33d89-123">When a profile is created, MAPI designates the first message service to be configured that includes a provider with the STATUS_PRIMARY_IDENTITY flag set in its **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property to supply the primary identity.</span></span> <span data-ttu-id="33d89-124">在指定的邮件服务中，将选择第一个要配置此资源标志集的提供程序，以提供该服务的标识。</span><span class="sxs-lookup"><span data-stu-id="33d89-124">Within the designated message service, the first provider to be configured with this resource flag set is chosen to provide the identity for the service.</span></span> <span data-ttu-id="33d89-125">为STATUS_PRIMARY_IDENTITY服务中的所有其他提供程序和配置文件中的其他邮件服务清除此标记。</span><span class="sxs-lookup"><span data-stu-id="33d89-125">The STATUS_PRIMARY_IDENTITY flag is cleared for all other providers in the designated service and other message services in the profile.</span></span> <span data-ttu-id="33d89-126">如果随时从配置文件中删除提供主标识的提供程序，MAPI 将角色分配给下一个可以提供标识的提供程序。</span><span class="sxs-lookup"><span data-stu-id="33d89-126">If at any time the provider supplying primary identity is removed from the profile, MAPI assigns the role to the next provider to be configured that can supply identity.</span></span> <span data-ttu-id="33d89-127">这由  `PR_RESOURCE_FLAGS=STATUS_PRIMARY_IDENTITY` MAPISVC.INF 中提供程序部分中条目的外观决定。</span><span class="sxs-lookup"><span data-stu-id="33d89-127">This is determined by the appearance of the  `PR_RESOURCE_FLAGS=STATUS_PRIMARY_IDENTITY` entry in the provider's section in MAPISVC.INF.</span></span> 
  
<span data-ttu-id="33d89-128">当客户端调用邮件服务的 **IMsgServiceAdmin：：SetPrimaryIdentity** 方法时，它会为目标服务中的服务提供商指定 MAPIUID。</span><span class="sxs-lookup"><span data-stu-id="33d89-128">When a client calls a message service's **IMsgServiceAdmin::SetPrimaryIdentity** method, it specifies the MAPIUID for a service provider within the target service.</span></span> <span data-ttu-id="33d89-129">有关详细信息，请参阅 [MAPIUID](mapiuid.md)。</span><span class="sxs-lookup"><span data-stu-id="33d89-129">For more information, see [MAPIUID](mapiuid.md).</span></span> <span data-ttu-id="33d89-130">**MAPIUID** 表示的服务提供商被分配为提供邮件服务和会话的主标识，服务中的所有其他提供程序将共享此标识。</span><span class="sxs-lookup"><span data-stu-id="33d89-130">The service provider represented by the **MAPIUID** is assigned to supply the primary identity for the message service and for the session, and all of the other providers in the service will share this identity.</span></span> 
  
<span data-ttu-id="33d89-131">邮件服务中负责提供主标识的每一个提供程序都会更新其状态表中的行，以包括以下属性。</span><span class="sxs-lookup"><span data-stu-id="33d89-131">Every provider in the message service responsible for supplying the primary identity updates its row in the status table to include the following properties.</span></span>
  
|<span data-ttu-id="33d89-132">**主标识属性**</span><span class="sxs-lookup"><span data-stu-id="33d89-132">**Primary identity property**</span></span>|<span data-ttu-id="33d89-133">**设置为**</span><span class="sxs-lookup"><span data-stu-id="33d89-133">**Set to**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33d89-134">**PR_IDENTITY_DISPLAY (** [PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="33d89-134">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33d89-135">提供主标识的对象的显示名称。</span><span class="sxs-lookup"><span data-stu-id="33d89-135">Display name of the object supplying the primary identity.</span></span>  <br/> |
|<span data-ttu-id="33d89-136">**PR_IDENTITY_SEARCH_KEY (** [PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="33d89-136">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33d89-137">提供主标识的对象的搜索键。</span><span class="sxs-lookup"><span data-stu-id="33d89-137">Search key for the object supplying the primary identity.</span></span>  <br/> |
|<span data-ttu-id="33d89-138">**PR_IDENTITY_ENTRYID (** [PidTagIdentityEntryId)](pidtagidentityentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="33d89-138">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33d89-139">提供主标识的对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="33d89-139">Entry identifier for the object supplying the primary identity.</span></span>  <br/> |
   
 <span data-ttu-id="33d89-140">**检索提供主标识的对象的条目标识符**</span><span class="sxs-lookup"><span data-stu-id="33d89-140">**To retrieve the entry identifier for the object supplying the primary identity**</span></span>
  
- <span data-ttu-id="33d89-141">调用 **IMAPISession：：QueryIdentity** 方法。</span><span class="sxs-lookup"><span data-stu-id="33d89-141">Call the **IMAPISession::QueryIdentity** method.</span></span> <span data-ttu-id="33d89-142">有关详细信息，请参阅 [IMAPISession：：QueryIdentity](imapisession-queryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="33d89-142">For more information, see [IMAPISession::QueryIdentity](imapisession-queryidentity.md).</span></span> <span data-ttu-id="33d89-143">**QueryIdentity** 在状态表中搜索在其 PR_RESOURCE_FLAGS 列中包含 **值 STATUS_PRIMARY_IDENTITY** 的行，并返回相应的 **PR_IDENTITY_ENTRYID** 作为主标识的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="33d89-143">**QueryIdentity** searches the status table for the row that contains the value STATUS_PRIMARY_IDENTITY in its **PR_RESOURCE_FLAGS** column and returns the corresponding **PR_IDENTITY_ENTRYID** as the entry identifier for the primary identity.</span></span> 
    

