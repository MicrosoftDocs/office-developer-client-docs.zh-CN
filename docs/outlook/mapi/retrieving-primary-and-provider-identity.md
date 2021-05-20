---
title: 检索主标识和提供程序标识
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d81bb81d-1708-4a8d-a4d5-c3ba087db9b7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f59695eca2af71dd592c5b3a755d021ac53b3e31
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430810"
---
# <a name="retrieving-primary-and-provider-identity"></a><span data-ttu-id="910d2-103">检索主标识和提供程序标识</span><span class="sxs-lookup"><span data-stu-id="910d2-103">Retrieving Primary and Provider Identity</span></span>

  
  
<span data-ttu-id="910d2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="910d2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="910d2-105">服务提供商（通常是通讯簿提供程序）可以选择提供可用于表示各种情况下的会话的标识。</span><span class="sxs-lookup"><span data-stu-id="910d2-105">Service providers, typically address book providers, have the option of supplying an identity that can be used to represent the session in a variety of situations.</span></span> <span data-ttu-id="910d2-106">三个属性描述提供程序的标识：</span><span class="sxs-lookup"><span data-stu-id="910d2-106">Three properties describe a provider's identity:</span></span>
  
- <span data-ttu-id="910d2-107">**PR_IDENTITY_ENTRYID (** [PidTagIdentityEntryId)](pidtagidentityentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="910d2-107">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span></span> 
    
- <span data-ttu-id="910d2-108">**PR_IDENTITY_DISPLAY (** [PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="910d2-108">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span></span> 
    
- <span data-ttu-id="910d2-109">**PR_IDENTITY_SEARCH_KEY (** [PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="910d2-109">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span></span> 
    
<span data-ttu-id="910d2-110">这些属性设置为对应的标识对象（通常为消息用户）的条目标识符、显示名称和搜索键。</span><span class="sxs-lookup"><span data-stu-id="910d2-110">These properties are set to the entry identifier, display name, and search key of the corresponding identity object, which is typically a messaging user.</span></span> <span data-ttu-id="910d2-111">提供标识的提供程序还会在 [PidTagResourceFlags](pidtagresourceflags-canonical-property.md) STATUS_PRIMARY_IDENTITY属性 **中设置PR_RESOURCE_FLAGS (** 标记) 标记。</span><span class="sxs-lookup"><span data-stu-id="910d2-111">Providers that supply an identity also set the STATUS_PRIMARY_IDENTITY flag in their **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="910d2-112">根据您的需要，您可能会使用特定提供程序的标识或会话的主标识。</span><span class="sxs-lookup"><span data-stu-id="910d2-112">Depending on your needs, you might use a particular provider's identity or the primary identity for the session.</span></span> <span data-ttu-id="910d2-113">还可以将提供程序的标识用于显示目的或检索属性，如 PR_RESOURCE_PATH ([PidTagResourcePath](pidtagresourcepath-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="910d2-113">You can use a provider's identity also for display purposes or to retrieve properties, such as **PR_RESOURCE_PATH** ([PidTagResourcePath](pidtagresourcepath-canonical-property.md)).</span></span> <span data-ttu-id="910d2-114">**PR_RESOURCE_PATH**，如果设置，则包含提供程序使用或创建的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="910d2-114">**PR_RESOURCE_PATH**, if set, contains the path to files used or created by the provider.</span></span> <span data-ttu-id="910d2-115">在 **PR_RESOURCE_PATH** 与会话用户相关的文件时，检索提供主标识的提供程序的 PR_RESOURCE_PATH 属性。</span><span class="sxs-lookup"><span data-stu-id="910d2-115">Retrieve the **PR_RESOURCE_PATH** property for the provider supplying the primary identity when you want to locate files that pertain to the user of the session.</span></span> 
  
 <span data-ttu-id="910d2-116">**检索特定提供程序的标识**</span><span class="sxs-lookup"><span data-stu-id="910d2-116">**To retrieve the identity of a specific provider**</span></span>
  
1. <span data-ttu-id="910d2-117">调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 以访问状态表。</span><span class="sxs-lookup"><span data-stu-id="910d2-117">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="910d2-118">使用 [SPropertyRestriction](spropertyrestriction.md) 结构构建限制，以将 **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 列与指定提供程序的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="910d2-118">Build a restriction using an [SPropertyRestriction](spropertyrestriction.md) structure to match the **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) column with the name of the specified provider.</span></span> 
    
3. <span data-ttu-id="910d2-119">调用 [IMAPITable：：FindRow](imapitable-findrow.md) 以查找提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="910d2-119">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate the provider's row.</span></span> <span data-ttu-id="910d2-120">提供程序的标识将存储在 **PR_IDENTITY_ENTRYID列（** 如果存在）。</span><span class="sxs-lookup"><span data-stu-id="910d2-120">The provider's identity will be stored in the **PR_IDENTITY_ENTRYID** column, if it exists.</span></span> 
    
 <span data-ttu-id="910d2-121">**检索会话的主标识**</span><span class="sxs-lookup"><span data-stu-id="910d2-121">**To retrieve the primary identity for a session**</span></span>
  
- <span data-ttu-id="910d2-122">调用 [IMAPISession：：QueryIdentity](imapisession-queryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="910d2-122">Call [IMAPISession::QueryIdentity](imapisession-queryidentity.md).</span></span> <span data-ttu-id="910d2-123">**QueryIdentity** 基于状态表中某STATUS_PRIMARY_IDENTITY行的 PR_RESOURCE_FLAGS 列是否存在值来建立会话标识。</span><span class="sxs-lookup"><span data-stu-id="910d2-123">**QueryIdentity** bases session identity on the existence of the STATUS_PRIMARY_IDENTITY value in the **PR_RESOURCE_FLAGS** column for one of the rows in the status table.</span></span> <span data-ttu-id="910d2-124">如果没有一个状态行设置了此值 **，QueryIdentity** 会向第一个设置这三个状态PR_IDENTITY标识。</span><span class="sxs-lookup"><span data-stu-id="910d2-124">If none of the status rows have this value set, **QueryIdentity** assigns identity to the first service provider that sets the three PR_IDENTITY properties.</span></span> <span data-ttu-id="910d2-125">如果没有服务提供商提供标识 **，QueryIdentity** 将返回MAPI_W_NO_SERVICE。</span><span class="sxs-lookup"><span data-stu-id="910d2-125">If no service provider supplies an identity, **QueryIdentity** returns MAPI_W_NO_SERVICE.</span></span> <span data-ttu-id="910d2-126">发生这种情况时，您应该创建一个字符串来表示可作为主标识的通用用户。</span><span class="sxs-lookup"><span data-stu-id="910d2-126">When this happens, you should create a character string to represent a generic user that can serve as the primary identity.</span></span> 
    
 <span data-ttu-id="910d2-127">**显式设置会话的主标识**</span><span class="sxs-lookup"><span data-stu-id="910d2-127">**To explicitly set the primary identity for a session**</span></span>
  
- <span data-ttu-id="910d2-128">调用 [IMsgServiceAdmin：：SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="910d2-128">Call [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md).</span></span> <span data-ttu-id="910d2-129">传递 **目标服务提供商的 MAPIUID。**</span><span class="sxs-lookup"><span data-stu-id="910d2-129">Pass the **MAPIUID** for the target service provider.</span></span> 
    

