---
title: PidTagResourceType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResourceType
api_type:
- COM
ms.assetid: 48b634d7-deea-422b-8944-a8d929d83838
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5d494577721feba01dd9cb93f344308251a8ed33
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778248"
---
# <a name="pidtagresourcetype-canonical-property"></a><span data-ttu-id="c53c9-103">PidTagResourceType 规范属性</span><span class="sxs-lookup"><span data-stu-id="c53c9-103">PidTagResourceType Canonical Property</span></span>

  
  
<span data-ttu-id="c53c9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c53c9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c53c9-105">包含一个值，指示的服务提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="c53c9-105">Contains a value that indicates the service provider type.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c53c9-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="c53c9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c53c9-107">PR_RESOURCE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c53c9-107">PR_RESOURCE_TYPE</span></span>  <br/> |
|<span data-ttu-id="c53c9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c53c9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c53c9-109">0x3E03</span><span class="sxs-lookup"><span data-stu-id="c53c9-109">0x3E03</span></span>  <br/> |
|<span data-ttu-id="c53c9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c53c9-110">Data type:</span></span>  <br/> |<span data-ttu-id="c53c9-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c53c9-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c53c9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c53c9-112">Area:</span></span>  <br/> |<span data-ttu-id="c53c9-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="c53c9-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c53c9-114">备注</span><span class="sxs-lookup"><span data-stu-id="c53c9-114">Remarks</span></span>

<span data-ttu-id="c53c9-115">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="c53c9-115">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="c53c9-116">MAPI_AB</span><span class="sxs-lookup"><span data-stu-id="c53c9-116">MAPI_AB</span></span> 
  
> <span data-ttu-id="c53c9-117">通讯簿</span><span class="sxs-lookup"><span data-stu-id="c53c9-117">Address book</span></span>
    
<span data-ttu-id="c53c9-118">MAPI_AB_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c53c9-118">MAPI_AB_PROVIDER</span></span> 
  
> <span data-ttu-id="c53c9-119">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="c53c9-119">Address book provider</span></span>
    
<span data-ttu-id="c53c9-120">MAPI_HOOK_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c53c9-120">MAPI_HOOK_PROVIDER</span></span> 
  
> <span data-ttu-id="c53c9-121">后台处理程序挂接提供程序</span><span class="sxs-lookup"><span data-stu-id="c53c9-121">Spooler hook provider</span></span>
    
<span data-ttu-id="c53c9-122">MAPI_PROFILE_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c53c9-122">MAPI_PROFILE_PROVIDER</span></span> 
  
> <span data-ttu-id="c53c9-123">配置文件提供程序</span><span class="sxs-lookup"><span data-stu-id="c53c9-123">Profile provider</span></span>
    
<span data-ttu-id="c53c9-124">MAPI_SPOOLER</span><span class="sxs-lookup"><span data-stu-id="c53c9-124">MAPI_SPOOLER</span></span> 
  
> <span data-ttu-id="c53c9-125">消息后台处理程序</span><span class="sxs-lookup"><span data-stu-id="c53c9-125">Message spooler</span></span>
    
<span data-ttu-id="c53c9-126">MAPI_STORE_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c53c9-126">MAPI_STORE_PROVIDER</span></span> 
  
> <span data-ttu-id="c53c9-127">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="c53c9-127">Message store provider</span></span>
    
<span data-ttu-id="c53c9-128">MAPI_SUBSYSTEM</span><span class="sxs-lookup"><span data-stu-id="c53c9-128">MAPI_SUBSYSTEM</span></span> 
  
> <span data-ttu-id="c53c9-129">内部 MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="c53c9-129">Internal MAPI subsystem</span></span>
    
<span data-ttu-id="c53c9-130">MAPI_TRANSPORT_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c53c9-130">MAPI_TRANSPORT_PROVIDER</span></span> 
  
> <span data-ttu-id="c53c9-131">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="c53c9-131">Transport provider</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="c53c9-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="c53c9-132">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c53c9-133">头文件</span><span class="sxs-lookup"><span data-stu-id="c53c9-133">Header files</span></span>

<span data-ttu-id="c53c9-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c53c9-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="c53c9-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c53c9-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="c53c9-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c53c9-136">Mapitags.h</span></span>
  
> <span data-ttu-id="c53c9-137">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c53c9-137">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c53c9-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c53c9-138">See also</span></span>



[<span data-ttu-id="c53c9-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c53c9-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c53c9-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c53c9-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c53c9-141">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c53c9-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c53c9-142">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c53c9-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

