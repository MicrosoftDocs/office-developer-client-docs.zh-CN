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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7a42a3b50cfa5630ac66cb03caac06dd7cb00e6f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778081"
---
# <a name="pidtagprovideruid-canonical-property"></a><span data-ttu-id="9332d-103">PidTagProviderUid 规范属性</span><span class="sxs-lookup"><span data-stu-id="9332d-103">PidTagProviderUid Canonical Property</span></span>

  
  
<span data-ttu-id="9332d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9332d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9332d-105">包含正在处理一条消息的服务提供商**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="9332d-105">Contains a **MAPIUID** structure of the service provider that is handling a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9332d-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="9332d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9332d-107">PR_PROVIDER_UID</span><span class="sxs-lookup"><span data-stu-id="9332d-107">PR_PROVIDER_UID</span></span>  <br/> |
|<span data-ttu-id="9332d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9332d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9332d-109">0x300C</span><span class="sxs-lookup"><span data-stu-id="9332d-109">0x300C</span></span>  <br/> |
|<span data-ttu-id="9332d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9332d-110">Data type:</span></span>  <br/> |<span data-ttu-id="9332d-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9332d-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9332d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9332d-112">Area:</span></span>  <br/> |<span data-ttu-id="9332d-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="9332d-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9332d-114">备注</span><span class="sxs-lookup"><span data-stu-id="9332d-114">Remarks</span></span>

<span data-ttu-id="9332d-115">此属性由所有服务提供商计算。</span><span class="sxs-lookup"><span data-stu-id="9332d-115">This property is computed by all service providers.</span></span> <span data-ttu-id="9332d-116">它包含提供商的[MAPIUID](mapiuid.md)结构相关联，且通常硬编码。</span><span class="sxs-lookup"><span data-stu-id="9332d-116">It contains a [MAPIUID](mapiuid.md) structure associated with, and usually hard-coded by, the provider.</span></span> <span data-ttu-id="9332d-117">通常使用感仅特定的提供商所提供的通讯簿容器中的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="9332d-117">It is typically used by a client application that is interested in only the address book containers supplied by a particular provider.</span></span> 
  
<span data-ttu-id="9332d-118">此属性仅显示为提供程序表中的列条目。</span><span class="sxs-lookup"><span data-stu-id="9332d-118">This property appears only as a column entry in the provider table.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9332d-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="9332d-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9332d-120">头文件</span><span class="sxs-lookup"><span data-stu-id="9332d-120">Header files</span></span>

<span data-ttu-id="9332d-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9332d-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="9332d-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9332d-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="9332d-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9332d-123">Mapitags.h</span></span>
  
> <span data-ttu-id="9332d-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9332d-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9332d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9332d-125">See also</span></span>



[<span data-ttu-id="9332d-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9332d-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9332d-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9332d-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9332d-128">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9332d-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9332d-129">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9332d-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

