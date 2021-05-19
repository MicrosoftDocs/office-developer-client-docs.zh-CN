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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1c7a35ded4861d724520b02ec5d61246774ca5cf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434954"
---
# <a name="pidtagresourcetype-canonical-property"></a><span data-ttu-id="c4844-103">PidTagResourceType 规范属性</span><span class="sxs-lookup"><span data-stu-id="c4844-103">PidTagResourceType Canonical Property</span></span>

  
  
<span data-ttu-id="c4844-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c4844-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c4844-105">包含一个值，该值指示服务提供商类型。</span><span class="sxs-lookup"><span data-stu-id="c4844-105">Contains a value that indicates the service provider type.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c4844-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c4844-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c4844-107">PR_RESOURCE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c4844-107">PR_RESOURCE_TYPE</span></span>  <br/> |
|<span data-ttu-id="c4844-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c4844-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c4844-109">0x3E03</span><span class="sxs-lookup"><span data-stu-id="c4844-109">0x3E03</span></span>  <br/> |
|<span data-ttu-id="c4844-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c4844-110">Data type:</span></span>  <br/> |<span data-ttu-id="c4844-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c4844-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c4844-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c4844-112">Area:</span></span>  <br/> |<span data-ttu-id="c4844-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="c4844-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c4844-114">备注</span><span class="sxs-lookup"><span data-stu-id="c4844-114">Remarks</span></span>

<span data-ttu-id="c4844-115">此属性可以正好具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="c4844-115">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="c4844-116">MAPI_AB</span><span class="sxs-lookup"><span data-stu-id="c4844-116">MAPI_AB</span></span> 
  
> <span data-ttu-id="c4844-117">通讯簿</span><span class="sxs-lookup"><span data-stu-id="c4844-117">Address book</span></span>
    
<span data-ttu-id="c4844-118">MAPI_AB_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c4844-118">MAPI_AB_PROVIDER</span></span> 
  
> <span data-ttu-id="c4844-119">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="c4844-119">Address book provider</span></span>
    
<span data-ttu-id="c4844-120">MAPI_HOOK_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c4844-120">MAPI_HOOK_PROVIDER</span></span> 
  
> <span data-ttu-id="c4844-121">后台处理程序挂钩提供程序</span><span class="sxs-lookup"><span data-stu-id="c4844-121">Spooler hook provider</span></span>
    
<span data-ttu-id="c4844-122">MAPI_PROFILE_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c4844-122">MAPI_PROFILE_PROVIDER</span></span> 
  
> <span data-ttu-id="c4844-123">配置文件提供程序</span><span class="sxs-lookup"><span data-stu-id="c4844-123">Profile provider</span></span>
    
<span data-ttu-id="c4844-124">MAPI_SPOOLER</span><span class="sxs-lookup"><span data-stu-id="c4844-124">MAPI_SPOOLER</span></span> 
  
> <span data-ttu-id="c4844-125">邮件后台处理程序</span><span class="sxs-lookup"><span data-stu-id="c4844-125">Message spooler</span></span>
    
<span data-ttu-id="c4844-126">MAPI_STORE_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c4844-126">MAPI_STORE_PROVIDER</span></span> 
  
> <span data-ttu-id="c4844-127">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="c4844-127">Message store provider</span></span>
    
<span data-ttu-id="c4844-128">MAPI_SUBSYSTEM</span><span class="sxs-lookup"><span data-stu-id="c4844-128">MAPI_SUBSYSTEM</span></span> 
  
> <span data-ttu-id="c4844-129">内部 MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="c4844-129">Internal MAPI subsystem</span></span>
    
<span data-ttu-id="c4844-130">MAPI_TRANSPORT_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="c4844-130">MAPI_TRANSPORT_PROVIDER</span></span> 
  
> <span data-ttu-id="c4844-131">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="c4844-131">Transport provider</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="c4844-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="c4844-132">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c4844-133">头文件</span><span class="sxs-lookup"><span data-stu-id="c4844-133">Header files</span></span>

<span data-ttu-id="c4844-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c4844-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="c4844-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c4844-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="c4844-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c4844-136">Mapitags.h</span></span>
  
> <span data-ttu-id="c4844-137">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c4844-137">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c4844-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4844-138">See also</span></span>



[<span data-ttu-id="c4844-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c4844-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c4844-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c4844-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c4844-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c4844-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c4844-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c4844-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

