---
title: PidTagProviderUid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderUid
api_type:
- COM
ms.assetid: 993f5bca-58a6-455d-8a25-6e08b441ad31
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cca22b466b1e0d2da9ca9cc009586df08316270c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581053"
---
# <a name="pidtagprovideruid-canonical-property"></a><span data-ttu-id="9cfc0-103">PidTagProviderUid 规范属性</span><span class="sxs-lookup"><span data-stu-id="9cfc0-103">PidTagProviderUid Canonical Property</span></span>

  
  
<span data-ttu-id="9cfc0-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9cfc0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9cfc0-105">包含正在处理一条消息的服务提供商**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="9cfc0-105">Contains a **MAPIUID** structure of the service provider that is handling a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9cfc0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9cfc0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9cfc0-107">PR_PROVIDER_UID</span><span class="sxs-lookup"><span data-stu-id="9cfc0-107">PR_PROVIDER_UID</span></span>  <br/> |
|<span data-ttu-id="9cfc0-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="9cfc0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9cfc0-109">0x300C</span><span class="sxs-lookup"><span data-stu-id="9cfc0-109">0x300C</span></span>  <br/> |
|<span data-ttu-id="9cfc0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9cfc0-110">Data type:</span></span>  <br/> |<span data-ttu-id="9cfc0-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9cfc0-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9cfc0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9cfc0-112">Area:</span></span>  <br/> |<span data-ttu-id="9cfc0-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="9cfc0-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9cfc0-114">注解</span><span class="sxs-lookup"><span data-stu-id="9cfc0-114">Remarks</span></span>

<span data-ttu-id="9cfc0-115">此属性由所有服务提供商计算。</span><span class="sxs-lookup"><span data-stu-id="9cfc0-115">This property is computed by all service providers.</span></span> <span data-ttu-id="9cfc0-116">它包含提供商的[MAPIUID](mapiuid.md)结构相关联，且通常硬编码。</span><span class="sxs-lookup"><span data-stu-id="9cfc0-116">It contains a [MAPIUID](mapiuid.md) structure associated with, and usually hard-coded by, the provider.</span></span> <span data-ttu-id="9cfc0-117">通常使用感仅特定的提供商所提供的通讯簿容器中的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="9cfc0-117">It is typically used by a client application that is interested in only the address book containers supplied by a particular provider.</span></span> 
  
<span data-ttu-id="9cfc0-118">此属性仅显示为提供程序表中的列条目。</span><span class="sxs-lookup"><span data-stu-id="9cfc0-118">This property appears only as a column entry in the provider table.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9cfc0-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="9cfc0-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9cfc0-120">头文件</span><span class="sxs-lookup"><span data-stu-id="9cfc0-120">Header files</span></span>

<span data-ttu-id="9cfc0-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9cfc0-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="9cfc0-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9cfc0-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="9cfc0-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9cfc0-123">Mapitags.h</span></span>
  
> <span data-ttu-id="9cfc0-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9cfc0-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9cfc0-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cfc0-125">See also</span></span>



[<span data-ttu-id="9cfc0-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9cfc0-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9cfc0-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9cfc0-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9cfc0-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9cfc0-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9cfc0-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9cfc0-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

