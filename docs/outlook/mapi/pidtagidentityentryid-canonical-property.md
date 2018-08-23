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
ms.openlocfilehash: a8810b6c39b909ebaa612496824150499cd15165
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584840"
---
# <a name="pidtagidentityentryid-canonical-property"></a><span data-ttu-id="17724-103">PidTagIdentityEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="17724-103">PidTagIdentityEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="17724-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="17724-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="17724-105">包含服务提供商的标识在邮件系统中定义的项标识符。</span><span class="sxs-lookup"><span data-stu-id="17724-105">Contains the entry identifier for a service provider's identity as defined within a messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="17724-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="17724-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="17724-107">PR_IDENTITY_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="17724-107">PR_IDENTITY_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="17724-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="17724-108">Identifier:</span></span>  <br/> |<span data-ttu-id="17724-109">0x3E01</span><span class="sxs-lookup"><span data-stu-id="17724-109">0x3E01</span></span>  <br/> |
|<span data-ttu-id="17724-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="17724-110">Data type:</span></span>  <br/> |<span data-ttu-id="17724-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="17724-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="17724-112">区域：</span><span class="sxs-lookup"><span data-stu-id="17724-112">Area:</span></span>  <br/> |<span data-ttu-id="17724-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="17724-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="17724-114">注解</span><span class="sxs-lookup"><span data-stu-id="17724-114">Remarks</span></span>

<span data-ttu-id="17724-115">此属性不显示任何对象的属性但只能作为状态表中的列。</span><span class="sxs-lookup"><span data-stu-id="17724-115">This property does not appear as a property on any object but only as a column in a status table.</span></span> <span data-ttu-id="17724-116">它是标识的公开状态表格行的服务提供程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="17724-116">It is part of the identity of the service provider exposing the status table row.</span></span> <span data-ttu-id="17724-117">提供程序的标识通常是指其帐户的服务器上，但可以参考消息系统中定义的提供程序的任何表示。</span><span class="sxs-lookup"><span data-stu-id="17724-117">The provider's identity typically refers to its account on the server, but can refer to any representation the provider defines within the messaging system.</span></span> 
  
<span data-ttu-id="17724-118">则此属性通常设置为适当的通讯簿条目标识符。</span><span class="sxs-lookup"><span data-stu-id="17724-118">This proprerty is commonly set to the appropriate address book entry identifier.</span></span> 
  
<span data-ttu-id="17724-119">Furnishing 任一标识属性的服务提供程序应提供所有这些。</span><span class="sxs-lookup"><span data-stu-id="17724-119">A service provider furnishing any of the identity properties should furnish all of them.</span></span> <span data-ttu-id="17724-120">属于同一消息服务的提供程序应公开的 identity 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="17724-120">Providers that belong to the same message service should expose the same values for the identity properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="17724-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="17724-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="17724-122">头文件</span><span class="sxs-lookup"><span data-stu-id="17724-122">Header files</span></span>

<span data-ttu-id="17724-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="17724-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="17724-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="17724-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="17724-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="17724-125">Mapitags.h</span></span>
  
> <span data-ttu-id="17724-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="17724-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="17724-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17724-127">See also</span></span>



[<span data-ttu-id="17724-128">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="17724-128">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)


[<span data-ttu-id="17724-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="17724-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="17724-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="17724-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="17724-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="17724-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="17724-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="17724-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

