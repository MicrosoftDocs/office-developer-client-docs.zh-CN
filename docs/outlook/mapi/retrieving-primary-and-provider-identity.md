---
title: 检索主和标识提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d81bb81d-1708-4a8d-a4d5-c3ba087db9b7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2a87e32fe21aa6fb1d9296c568a74da994c146bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778635"
---
# <a name="retrieving-primary-and-provider-identity"></a><span data-ttu-id="b46be-103">检索主和标识提供程序</span><span class="sxs-lookup"><span data-stu-id="b46be-103">Retrieving Primary and Provider Identity</span></span>

  
  
<span data-ttu-id="b46be-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b46be-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b46be-105">服务提供商，通常通讯簿提供程序，必须提供标识的可以用来代表会话中很多情况下的选项。</span><span class="sxs-lookup"><span data-stu-id="b46be-105">Service providers, typically address book providers, have the option of supplying an identity that can be used to represent the session in a variety of situations.</span></span> <span data-ttu-id="b46be-106">三个属性说明提供程序的标识：</span><span class="sxs-lookup"><span data-stu-id="b46be-106">Three properties describe a provider's identity:</span></span>
  
- <span data-ttu-id="b46be-107">**PR_IDENTITY_ENTRYID**([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b46be-107">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span></span> 
    
- <span data-ttu-id="b46be-108">**PR_IDENTITY_DISPLAY**([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b46be-108">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span></span> 
    
- <span data-ttu-id="b46be-109">**PR_IDENTITY_SEARCH_KEY**([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b46be-109">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span></span> 
    
<span data-ttu-id="b46be-110">这些属性设置为条目标识符、 显示名称和相应的标识对象，它通常是邮件用户的搜索键。</span><span class="sxs-lookup"><span data-stu-id="b46be-110">These properties are set to the entry identifier, display name, and search key of the corresponding identity object, which is typically a messaging user.</span></span> <span data-ttu-id="b46be-111">提供标识提供程序还会在其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 STATUS_PRIMARY_IDENTITY 标志。</span><span class="sxs-lookup"><span data-stu-id="b46be-111">Providers that supply an identity also set the STATUS_PRIMARY_IDENTITY flag in their **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="b46be-112">根据您的需要，可能会话使用特定提供程序的标识或主标识。</span><span class="sxs-lookup"><span data-stu-id="b46be-112">Depending on your needs, you might use a particular provider's identity or the primary identity for the session.</span></span> <span data-ttu-id="b46be-113">此外显示为了或检索属性，如**PR_RESOURCE_PATH** ([PidTagResourcePath](pidtagresourcepath-canonical-property.md))，您可以使用提供程序的标识。</span><span class="sxs-lookup"><span data-stu-id="b46be-113">You can use a provider's identity also for display purposes or to retrieve properties, such as **PR_RESOURCE_PATH** ([PidTagResourcePath](pidtagresourcepath-canonical-property.md)).</span></span> <span data-ttu-id="b46be-114">**PR_RESOURCE_PATH**，如果设置，包含使用或提供程序创建的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="b46be-114">**PR_RESOURCE_PATH**, if set, contains the path to files used or created by the provider.</span></span> <span data-ttu-id="b46be-115">检索**PR_RESOURCE_PATH**属性时要查找文件相关的会话的用户提供的主要标识提供程序。</span><span class="sxs-lookup"><span data-stu-id="b46be-115">Retrieve the **PR_RESOURCE_PATH** property for the provider supplying the primary identity when you want to locate files that pertain to the user of the session.</span></span> 
  
 <span data-ttu-id="b46be-116">**若要检索特定提供程序的标识**</span><span class="sxs-lookup"><span data-stu-id="b46be-116">**To retrieve the identity of a specific provider**</span></span>
  
1. <span data-ttu-id="b46be-117">调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表。</span><span class="sxs-lookup"><span data-stu-id="b46be-117">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="b46be-118">构建使用[SPropertyRestriction](spropertyrestriction.md)结构以匹配具有指定的提供程序的名称的**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 列限制。</span><span class="sxs-lookup"><span data-stu-id="b46be-118">Build a restriction using an [SPropertyRestriction](spropertyrestriction.md) structure to match the **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) column with the name of the specified provider.</span></span> 
    
3. <span data-ttu-id="b46be-119">调用[IMAPITable::FindRow](imapitable-findrow.md)以找到提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="b46be-119">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate the provider's row.</span></span> <span data-ttu-id="b46be-120">将在**PR_IDENTITY_ENTRYID**列中，存储提供程序的标识，如果存在。</span><span class="sxs-lookup"><span data-stu-id="b46be-120">The provider's identity will be stored in the **PR_IDENTITY_ENTRYID** column, if it exists.</span></span> 
    
 <span data-ttu-id="b46be-121">**若要检索主标识会话**</span><span class="sxs-lookup"><span data-stu-id="b46be-121">**To retrieve the primary identity for a session**</span></span>
  
- <span data-ttu-id="b46be-122">调用[IMAPISession::QueryIdentity](imapisession-queryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="b46be-122">Call [IMAPISession::QueryIdentity](imapisession-queryidentity.md).</span></span> <span data-ttu-id="b46be-123">**QueryIdentity**基于状态表中的行之一**PR_RESOURCE_FLAGS**列中的 STATUS_PRIMARY_IDENTITY 值存在的会话标识。</span><span class="sxs-lookup"><span data-stu-id="b46be-123">**QueryIdentity** bases session identity on the existence of the STATUS_PRIMARY_IDENTITY value in the **PR_RESOURCE_FLAGS** column for one of the rows in the status table.</span></span> <span data-ttu-id="b46be-124">如果没有的状态行设置此值， **QueryIdentity**会将标识分配给设置三个 PR_IDENTITY 属性的第一个服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="b46be-124">If none of the status rows have this value set, **QueryIdentity** assigns identity to the first service provider that sets the three PR_IDENTITY properties.</span></span> <span data-ttu-id="b46be-125">如果没有服务提供商提供标识， **QueryIdentity**返回 MAPI_W_NO_SERVICE。</span><span class="sxs-lookup"><span data-stu-id="b46be-125">If no service provider supplies an identity, **QueryIdentity** returns MAPI_W_NO_SERVICE.</span></span> <span data-ttu-id="b46be-126">这种情况下，您应创建一个字符串，表示可以充当主标识一般用户。</span><span class="sxs-lookup"><span data-stu-id="b46be-126">When this happens, you should create a character string to represent a generic user that can serve as the primary identity.</span></span> 
    
 <span data-ttu-id="b46be-127">**会话中明确地设置主标识**</span><span class="sxs-lookup"><span data-stu-id="b46be-127">**To explicitly set the primary identity for a session**</span></span>
  
- <span data-ttu-id="b46be-128">调用[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。</span><span class="sxs-lookup"><span data-stu-id="b46be-128">Call [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md).</span></span> <span data-ttu-id="b46be-129">将**MAPIUID**传递的目标服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="b46be-129">Pass the **MAPIUID** for the target service provider.</span></span> 
    

