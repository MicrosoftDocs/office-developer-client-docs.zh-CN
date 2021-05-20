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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b237a57dfea020c7bfcb66d49d43428c1f6506c2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430362"
---
# <a name="imsgserviceadminsetprimaryidentity"></a><span data-ttu-id="6e614-103">IMsgServiceAdmin::SetPrimaryIdentity</span><span class="sxs-lookup"><span data-stu-id="6e614-103">IMsgServiceAdmin::SetPrimaryIdentity</span></span>

  
  
<span data-ttu-id="6e614-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e614-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e614-105">指定邮件服务作为配置文件的主标识的供应商。</span><span class="sxs-lookup"><span data-stu-id="6e614-105">Designates a message service to be the supplier of the primary identity for the profile.</span></span>
  
```cpp
HRESULT SetPrimaryIdentity(
  LPMAPIUID lpUID,
  ULONG ulFlags  
);
```

## <a name="parameters"></a><span data-ttu-id="6e614-106">参数</span><span class="sxs-lookup"><span data-stu-id="6e614-106">Parameters</span></span>

 <span data-ttu-id="6e614-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="6e614-107">_lpUID_</span></span>
  
> <span data-ttu-id="6e614-108">[in]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含提供主标识的邮件服务的唯一标识符或 NULL，指示 **SetPrimaryIdentity** 应清除当前标识。</span><span class="sxs-lookup"><span data-stu-id="6e614-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to supply the primary identity, or NULL, which indicates that **SetPrimaryIdentity** should clear the current identity.</span></span> 
    
 <span data-ttu-id="6e614-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6e614-109">_ulFlags_</span></span>
  
> <span data-ttu-id="6e614-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="6e614-110">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6e614-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6e614-111">Return value</span></span>

<span data-ttu-id="6e614-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e614-112">S_OK</span></span> 
  
> <span data-ttu-id="6e614-113">邮件服务已成功分配主标识的供应商。</span><span class="sxs-lookup"><span data-stu-id="6e614-113">The message service was successfully assigned the supplier of the primary identity.</span></span>
    
<span data-ttu-id="6e614-114">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="6e614-114">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="6e614-115">**SetPrimaryIdentity** 尝试指定在其 PR_RESOURCE_FLAGS ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)属性中设置了 **SERVICE_NO_PRIMARY_IDENTITY** 标志) 服务。</span><span class="sxs-lookup"><span data-stu-id="6e614-115">**SetPrimaryIdentity** attempted to designate a message service that has the SERVICE_NO_PRIMARY_IDENTITY flag set in its **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6e614-116">备注</span><span class="sxs-lookup"><span data-stu-id="6e614-116">Remarks</span></span>

<span data-ttu-id="6e614-117">**IMsgServiceAdmin：：SetPrimaryIdentity** 方法将邮件服务建立为配置文件的主标识的供应商。</span><span class="sxs-lookup"><span data-stu-id="6e614-117">The **IMsgServiceAdmin::SetPrimaryIdentity** method establishes a message service as the supplier of the primary identity for the profile.</span></span> <span data-ttu-id="6e614-118">主标识通常是登录到邮件服务的用户。</span><span class="sxs-lookup"><span data-stu-id="6e614-118">The primary identity is typically the user who is logged on to the message service.</span></span> <span data-ttu-id="6e614-119">它由三个属性表示：</span><span class="sxs-lookup"><span data-stu-id="6e614-119">It is represented by three properties:</span></span> 
  
- <span data-ttu-id="6e614-120">**PR_IDENTITY_DISPLAY (** [PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6e614-120">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span></span>
    
- <span data-ttu-id="6e614-121">**PR_IDENTITY_ENTRYID (** [PidTagIdentityEntryId)](pidtagidentityentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="6e614-121">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="6e614-122">**PR_IDENTITY_SEARCH_KEY (** [PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6e614-122">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span></span>
    
<span data-ttu-id="6e614-123">指定邮件服务中的每个服务提供商将这三个属性显示名称提供主标识的邮件用户的名称、条目标识符和搜索密钥。</span><span class="sxs-lookup"><span data-stu-id="6e614-123">Every service provider in the designated message service sets these three properties to the display name, entry identifier, and search key of the messaging user that supplies the primary identity.</span></span> <span data-ttu-id="6e614-124">客户端可以通过调用 [IMAPISession：：QueryIdentity](imapisession-queryidentity.md) 方法检索主标识的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="6e614-124">Clients can retrieve the primary identity's entry identifier by calling the [IMAPISession::QueryIdentity](imapisession-queryidentity.md) method.</span></span> 
  
<span data-ttu-id="6e614-125">对于 **PR_RESOURCE_FLAGS** 主标识的邮件服务成员STATUS_PRIMARY_IDENTITY，将 PR_RESOURCE_FLAGS 属性设置为 SERVICE_PRIMARY_IDENTITY，并针对邮件服务设置此属性。</span><span class="sxs-lookup"><span data-stu-id="6e614-125">The **PR_RESOURCE_FLAGS** property is set to STATUS_PRIMARY_IDENTITY for every provider that is a member of the message service that supplies the primary identity, and to SERVICE_PRIMARY_IDENTITY for the message service.</span></span> <span data-ttu-id="6e614-126">当服务提供商无法提供其邮件服务的主标识时，它会将PR_RESOURCE_FLAGS **设置STATUS_NO_PRIMARY_IDENTITY。**</span><span class="sxs-lookup"><span data-stu-id="6e614-126">When a service provider cannot supply the primary identity for its message service, it sets **PR_RESOURCE_FLAGS** to STATUS_NO_PRIMARY_IDENTITY.</span></span> <span data-ttu-id="6e614-127">**SetPrimaryIdentity** **PR_RESOURCE_FLAGS未** 提供主标识的每个邮件服务的 SERVICE_NO_PRIMARY_IDENTITY。</span><span class="sxs-lookup"><span data-stu-id="6e614-127">**SetPrimaryIdentity** sets the **PR_RESOURCE_FLAGS** property of each message service that is not supplying the primary identity to SERVICE_NO_PRIMARY_IDENTITY.</span></span> 
  
<span data-ttu-id="6e614-128">当客户端登录到服务时，MAPI 具有相关信息的每个邮件服务提供商都可以为每个用户建立标识。</span><span class="sxs-lookup"><span data-stu-id="6e614-128">Each message service provider that MAPI has information about can establish an identity for each of its users when a client logs on to the service.</span></span> <span data-ttu-id="6e614-129">但是，由于 MAPI 支持针对每个 MAPI 会话连接到多个服务提供商，因此对于整个 MAPI 会话的特定用户标识没有明确的定义;用户的标识取决于涉及的服务。</span><span class="sxs-lookup"><span data-stu-id="6e614-129">However, because MAPI supports connections to multiple service providers for each MAPI session, there is no firm definition of a particular user's identity for the MAPI session as a whole; a user's identity depends on which service is involved.</span></span> <span data-ttu-id="6e614-130">客户端可以调用 **SetPrimaryIdentity，** 以将邮件服务为用户建立的众多标识之一指定为该用户的主标识。</span><span class="sxs-lookup"><span data-stu-id="6e614-130">Clients can call **SetPrimaryIdentity** to designate one of the many identities established for a user by message services as the primary identity for that user.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6e614-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e614-131">See also</span></span>



[<span data-ttu-id="6e614-132">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="6e614-132">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)
  
[<span data-ttu-id="6e614-133">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="6e614-133">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="6e614-134">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6e614-134">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

