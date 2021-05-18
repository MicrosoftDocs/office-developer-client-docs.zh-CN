---
title: PidTagIdentityEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIdentityEntryId
api_type:
- HeaderDef
ms.assetid: 61a9d403-e0e5-45c3-8d18-4d53207ab927
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 099df2211e87e253ab1be520378b3a2b2ca7d4c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423333"
---
# <a name="pidtagidentityentryid-canonical-property"></a><span data-ttu-id="0a089-103">PidTagIdentityEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="0a089-103">PidTagIdentityEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="0a089-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0a089-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0a089-105">包含服务提供商标识的条目标识符，如邮件系统内所定义。</span><span class="sxs-lookup"><span data-stu-id="0a089-105">Contains the entry identifier for a service provider's identity as defined within a messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0a089-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0a089-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0a089-107">PR_IDENTITY_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="0a089-107">PR_IDENTITY_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="0a089-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0a089-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0a089-109">0x3E01</span><span class="sxs-lookup"><span data-stu-id="0a089-109">0x3E01</span></span>  <br/> |
|<span data-ttu-id="0a089-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0a089-110">Data type:</span></span>  <br/> |<span data-ttu-id="0a089-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="0a089-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="0a089-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0a089-112">Area:</span></span>  <br/> |<span data-ttu-id="0a089-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="0a089-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0a089-114">备注</span><span class="sxs-lookup"><span data-stu-id="0a089-114">Remarks</span></span>

<span data-ttu-id="0a089-115">此属性不会在任何对象上显示为属性，而只显示为状态表中的列。</span><span class="sxs-lookup"><span data-stu-id="0a089-115">This property does not appear as a property on any object but only as a column in a status table.</span></span> <span data-ttu-id="0a089-116">它是公开状态表行的服务提供商标识的一部分。</span><span class="sxs-lookup"><span data-stu-id="0a089-116">It is part of the identity of the service provider exposing the status table row.</span></span> <span data-ttu-id="0a089-117">提供程序的标识通常指其在服务器上的帐户，但可以引用提供程序在邮件系统中定义的任何表示形式。</span><span class="sxs-lookup"><span data-stu-id="0a089-117">The provider's identity typically refers to its account on the server, but can refer to any representation the provider defines within the messaging system.</span></span> 
  
<span data-ttu-id="0a089-118">此属性通常设置为相应的通讯簿条目标识符。</span><span class="sxs-lookup"><span data-stu-id="0a089-118">This proprerty is commonly set to the appropriate address book entry identifier.</span></span> 
  
<span data-ttu-id="0a089-119">提供任何标识属性的服务提供商应提供所有标识属性。</span><span class="sxs-lookup"><span data-stu-id="0a089-119">A service provider furnishing any of the identity properties should furnish all of them.</span></span> <span data-ttu-id="0a089-120">属于同一邮件服务的提供程序应公开标识属性的相同值。</span><span class="sxs-lookup"><span data-stu-id="0a089-120">Providers that belong to the same message service should expose the same values for the identity properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0a089-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="0a089-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0a089-122">头文件</span><span class="sxs-lookup"><span data-stu-id="0a089-122">Header files</span></span>

<span data-ttu-id="0a089-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0a089-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="0a089-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0a089-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="0a089-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0a089-125">Mapitags.h</span></span>
  
> <span data-ttu-id="0a089-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0a089-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0a089-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a089-127">See also</span></span>



[<span data-ttu-id="0a089-128">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="0a089-128">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)


[<span data-ttu-id="0a089-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0a089-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0a089-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0a089-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0a089-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0a089-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0a089-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0a089-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

