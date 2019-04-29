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
# <a name="retrieving-primary-and-provider-identity"></a><span data-ttu-id="019cc-103">检索主标识和提供程序标识</span><span class="sxs-lookup"><span data-stu-id="019cc-103">Retrieving Primary and Provider Identity</span></span>

  
  
<span data-ttu-id="019cc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="019cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="019cc-105">服务提供商 (通常为通讯簿提供程序) 可以提供可用于在各种情况下表示会话的标识。</span><span class="sxs-lookup"><span data-stu-id="019cc-105">Service providers, typically address book providers, have the option of supplying an identity that can be used to represent the session in a variety of situations.</span></span> <span data-ttu-id="019cc-106">三个属性描述提供程序的标识:</span><span class="sxs-lookup"><span data-stu-id="019cc-106">Three properties describe a provider's identity:</span></span>
  
- <span data-ttu-id="019cc-107">**PR_IDENTITY_ENTRYID**([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="019cc-107">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span></span> 
    
- <span data-ttu-id="019cc-108">**PR_IDENTITY_DISPLAY**([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="019cc-108">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span></span> 
    
- <span data-ttu-id="019cc-109">**PR_IDENTITY_SEARCH_KEY**([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="019cc-109">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span></span> 
    
<span data-ttu-id="019cc-110">这些属性设置为 "条目标识符"、"显示名称" 和 "搜索密钥", 后者通常是邮件用户。</span><span class="sxs-lookup"><span data-stu-id="019cc-110">These properties are set to the entry identifier, display name, and search key of the corresponding identity object, which is typically a messaging user.</span></span> <span data-ttu-id="019cc-111">提供标识的提供程序也会在其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 STATUS_PRIMARY_IDENTITY 标志。</span><span class="sxs-lookup"><span data-stu-id="019cc-111">Providers that supply an identity also set the STATUS_PRIMARY_IDENTITY flag in their **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="019cc-112">根据您的需要, 您可以使用特定提供程序的标识或会话的主要标识。</span><span class="sxs-lookup"><span data-stu-id="019cc-112">Depending on your needs, you might use a particular provider's identity or the primary identity for the session.</span></span> <span data-ttu-id="019cc-113">您可以使用提供程序的标识来显示, 也可以检索属性, 如**PR_RESOURCE_PATH** ([PidTagResourcePath](pidtagresourcepath-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="019cc-113">You can use a provider's identity also for display purposes or to retrieve properties, such as **PR_RESOURCE_PATH** ([PidTagResourcePath](pidtagresourcepath-canonical-property.md)).</span></span> <span data-ttu-id="019cc-114">**PR_RESOURCE_PATH**(如果设置) 包含由提供程序使用或创建的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="019cc-114">**PR_RESOURCE_PATH**, if set, contains the path to files used or created by the provider.</span></span> <span data-ttu-id="019cc-115">当您想要查找与会话用户相关的文件时, 请检索提供主标识的提供程序的**PR_RESOURCE_PATH**属性。</span><span class="sxs-lookup"><span data-stu-id="019cc-115">Retrieve the **PR_RESOURCE_PATH** property for the provider supplying the primary identity when you want to locate files that pertain to the user of the session.</span></span> 
  
 <span data-ttu-id="019cc-116">**检索特定提供程序的标识**</span><span class="sxs-lookup"><span data-stu-id="019cc-116">**To retrieve the identity of a specific provider**</span></span>
  
1. <span data-ttu-id="019cc-117">调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)以访问状态表。</span><span class="sxs-lookup"><span data-stu-id="019cc-117">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="019cc-118">使用[SPropertyRestriction](spropertyrestriction.md)结构生成限制, 将**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 列与指定的提供程序的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="019cc-118">Build a restriction using an [SPropertyRestriction](spropertyrestriction.md) structure to match the **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) column with the name of the specified provider.</span></span> 
    
3. <span data-ttu-id="019cc-119">调用[IMAPITable:: FindRow](imapitable-findrow.md)以查找提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="019cc-119">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate the provider's row.</span></span> <span data-ttu-id="019cc-120">提供程序的标识将存储在 " **PR_IDENTITY_ENTRYID** " 列中 (如果存在)。</span><span class="sxs-lookup"><span data-stu-id="019cc-120">The provider's identity will be stored in the **PR_IDENTITY_ENTRYID** column, if it exists.</span></span> 
    
 <span data-ttu-id="019cc-121">**检索会话的主标识**</span><span class="sxs-lookup"><span data-stu-id="019cc-121">**To retrieve the primary identity for a session**</span></span>
  
- <span data-ttu-id="019cc-122">调用[IMAPISession:: QueryIdentity](imapisession-queryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="019cc-122">Call [IMAPISession::QueryIdentity](imapisession-queryidentity.md).</span></span> <span data-ttu-id="019cc-123">**QueryIdentity**在状态表中某一行的**PR_RESOURCE_FLAGS**列中是否存在 STATUS_PRIMARY_IDENTITY 值的会话标识。</span><span class="sxs-lookup"><span data-stu-id="019cc-123">**QueryIdentity** bases session identity on the existence of the STATUS_PRIMARY_IDENTITY value in the **PR_RESOURCE_FLAGS** column for one of the rows in the status table.</span></span> <span data-ttu-id="019cc-124">如果没有一个状态行设置了此值, 则**QueryIdentity**会将 identity 分配给设置三个 PR_IDENTITY 属性的第一个服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="019cc-124">If none of the status rows have this value set, **QueryIdentity** assigns identity to the first service provider that sets the three PR_IDENTITY properties.</span></span> <span data-ttu-id="019cc-125">如果没有服务提供程序提供标识, **QueryIdentity**将返回 MAPI_W_NO_SERVICE。</span><span class="sxs-lookup"><span data-stu-id="019cc-125">If no service provider supplies an identity, **QueryIdentity** returns MAPI_W_NO_SERVICE.</span></span> <span data-ttu-id="019cc-126">当发生这种情况时, 您应创建一个字符串来表示可用作主要标识的一般用户。</span><span class="sxs-lookup"><span data-stu-id="019cc-126">When this happens, you should create a character string to represent a generic user that can serve as the primary identity.</span></span> 
    
 <span data-ttu-id="019cc-127">**为会话显式设置主标识**</span><span class="sxs-lookup"><span data-stu-id="019cc-127">**To explicitly set the primary identity for a session**</span></span>
  
- <span data-ttu-id="019cc-128">调用[IMsgServiceAdmin:: SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="019cc-128">Call [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md).</span></span> <span data-ttu-id="019cc-129">为目标服务提供程序传递**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="019cc-129">Pass the **MAPIUID** for the target service provider.</span></span> 
    

