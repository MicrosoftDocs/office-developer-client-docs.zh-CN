---
title: IMsgServiceAdminSetPrimaryIdentity
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.SetPrimaryIdentity
api_type:
- COM
ms.assetid: 763cab41-f6f6-4cb0-8cb8-170fdf2a92e6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 38d55f45280b0b037dc9b5cbbd0dc8809ed04e35
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775861"
---
# <a name="imsgserviceadminsetprimaryidentity"></a><span data-ttu-id="54e24-103">IMsgServiceAdmin::SetPrimaryIdentity</span><span class="sxs-lookup"><span data-stu-id="54e24-103">IMsgServiceAdmin::SetPrimaryIdentity</span></span>

  
  
<span data-ttu-id="54e24-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="54e24-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="54e24-105">指定要配置文件的主标识的供应商的消息服务。</span><span class="sxs-lookup"><span data-stu-id="54e24-105">Designates a message service to be the supplier of the primary identity for the profile.</span></span>
  
```cpp
HRESULT SetPrimaryIdentity(
  LPMAPIUID lpUID,
  ULONG ulFlags  
);
```

## <a name="parameters"></a><span data-ttu-id="54e24-106">参数</span><span class="sxs-lookup"><span data-stu-id="54e24-106">Parameters</span></span>

 <span data-ttu-id="54e24-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="54e24-107">_lpUID_</span></span>
  
> <span data-ttu-id="54e24-108">[in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要提供的主要标识的消息服务的唯一标识符或空值，指示**SetPrimaryIdentity**应清除当前的标识。</span><span class="sxs-lookup"><span data-stu-id="54e24-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to supply the primary identity, or NULL, which indicates that **SetPrimaryIdentity** should clear the current identity.</span></span> 
    
 <span data-ttu-id="54e24-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="54e24-109">_ulFlags_</span></span>
  
> <span data-ttu-id="54e24-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="54e24-110">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="54e24-111">返回值</span><span class="sxs-lookup"><span data-stu-id="54e24-111">Return value</span></span>

<span data-ttu-id="54e24-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="54e24-112">S_OK</span></span> 
  
> <span data-ttu-id="54e24-113">邮件服务已成功分配主标识供应的商。</span><span class="sxs-lookup"><span data-stu-id="54e24-113">The message service was successfully assigned the supplier of the primary identity.</span></span>
    
<span data-ttu-id="54e24-114">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="54e24-114">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="54e24-115">**SetPrimaryIdentity**尝试指定具有其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 SERVICE_NO_PRIMARY_IDENTITY 标志的消息服务。</span><span class="sxs-lookup"><span data-stu-id="54e24-115">**SetPrimaryIdentity** attempted to designate a message service that has the SERVICE_NO_PRIMARY_IDENTITY flag set in its **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="54e24-116">说明</span><span class="sxs-lookup"><span data-stu-id="54e24-116">Remarks</span></span>

<span data-ttu-id="54e24-117">**IMsgServiceAdmin::SetPrimaryIdentity**方法建立作为的配置文件的主标识供应商的消息服务。</span><span class="sxs-lookup"><span data-stu-id="54e24-117">The **IMsgServiceAdmin::SetPrimaryIdentity** method establishes a message service as the supplier of the primary identity for the profile.</span></span> <span data-ttu-id="54e24-118">主标识通常是登录到邮件服务的用户。</span><span class="sxs-lookup"><span data-stu-id="54e24-118">The primary identity is typically the user who is logged on to the message service.</span></span> <span data-ttu-id="54e24-119">它由三个属性表示：</span><span class="sxs-lookup"><span data-stu-id="54e24-119">It is represented by three properties:</span></span> 
  
- <span data-ttu-id="54e24-120">**PR_IDENTITY_DISPLAY**([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="54e24-120">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span></span>
    
- <span data-ttu-id="54e24-121">**PR_IDENTITY_ENTRYID**([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="54e24-121">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="54e24-122">**PR_IDENTITY_SEARCH_KEY**([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="54e24-122">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span></span>
    
<span data-ttu-id="54e24-123">指定的邮件服务中的每个服务提供商将这三个属性设置为显示名称、 条目标识符和提供的主要标识的邮件用户的搜索键。</span><span class="sxs-lookup"><span data-stu-id="54e24-123">Every service provider in the designated message service sets these three properties to the display name, entry identifier, and search key of the messaging user that supplies the primary identity.</span></span> <span data-ttu-id="54e24-124">客户端可以通过调用[IMAPISession::QueryIdentity](imapisession-queryidentity.md)方法检索主标识的项标识符。</span><span class="sxs-lookup"><span data-stu-id="54e24-124">Clients can retrieve the primary identity's entry identifier by calling the [IMAPISession::QueryIdentity](imapisession-queryidentity.md) method.</span></span> 
  
<span data-ttu-id="54e24-125">**PR_RESOURCE_FLAGS**属性设置到 STATUS_PRIMARY_IDENTITY 成员提供的主要标识消息服务的每个服务提供商和 SERVICE_PRIMARY_IDENTITY 消息服务。</span><span class="sxs-lookup"><span data-stu-id="54e24-125">The **PR_RESOURCE_FLAGS** property is set to STATUS_PRIMARY_IDENTITY for every provider that is a member of the message service that supplies the primary identity, and to SERVICE_PRIMARY_IDENTITY for the message service.</span></span> <span data-ttu-id="54e24-126">当服务提供程序不能提供其消息服务的主要标识时，它将**PR_RESOURCE_FLAGS**设置为 STATUS_NO_PRIMARY_IDENTITY。</span><span class="sxs-lookup"><span data-stu-id="54e24-126">When a service provider cannot supply the primary identity for its message service, it sets **PR_RESOURCE_FLAGS** to STATUS_NO_PRIMARY_IDENTITY.</span></span> <span data-ttu-id="54e24-127">**SetPrimaryIdentity**不提供对 SERVICE_NO_PRIMARY_IDENTITY 主标识每个消息服务的**PR_RESOURCE_FLAGS**属性设置。</span><span class="sxs-lookup"><span data-stu-id="54e24-127">**SetPrimaryIdentity** sets the **PR_RESOURCE_FLAGS** property of each message service that is not supplying the primary identity to SERVICE_NO_PRIMARY_IDENTITY.</span></span> 
  
<span data-ttu-id="54e24-128">客户端登录到服务后，MAPI 对每个消息服务提供商可以为每个用户都建立标识。</span><span class="sxs-lookup"><span data-stu-id="54e24-128">Each message service provider that MAPI has information about can establish an identity for each of its users when a client logs on to the service.</span></span> <span data-ttu-id="54e24-129">但是，由于 MAPI 支持的每个 MAPI 会话到多个服务提供商的连接，因此没有严格定义的特定用户的标识作为一个整体; MAPI 会话用户的标识取决于涉及哪项服务。</span><span class="sxs-lookup"><span data-stu-id="54e24-129">However, because MAPI supports connections to multiple service providers for each MAPI session, there is no firm definition of a particular user's identity for the MAPI session as a whole; a user's identity depends on which service is involved.</span></span> <span data-ttu-id="54e24-130">客户端可以调用**SetPrimaryIdentity**要指定多个标识为用户通过消息服务建立，为该用户的主标识之一。</span><span class="sxs-lookup"><span data-stu-id="54e24-130">Clients can call **SetPrimaryIdentity** to designate one of the many identities established for a user by message services as the primary identity for that user.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="54e24-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54e24-131">See also</span></span>



[<span data-ttu-id="54e24-132">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="54e24-132">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)
  
[<span data-ttu-id="54e24-133">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="54e24-133">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="54e24-134">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="54e24-134">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

