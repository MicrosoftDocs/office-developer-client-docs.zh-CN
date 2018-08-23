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
ms.openlocfilehash: 56f14488812842d5e9fe63ae228c325059ebe679
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575089"
---
# <a name="pidtagresourcetype-canonical-property"></a><span data-ttu-id="f2922-103">PidTagResourceType 规范属性</span><span class="sxs-lookup"><span data-stu-id="f2922-103">PidTagResourceType Canonical Property</span></span>

  
  
<span data-ttu-id="f2922-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f2922-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f2922-105">包含一个值，指示的服务提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="f2922-105">Contains a value that indicates the service provider type.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f2922-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f2922-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f2922-107">PR_RESOURCE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f2922-107">PR_RESOURCE_TYPE</span></span>  <br/> |
|<span data-ttu-id="f2922-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f2922-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f2922-109">0x3E03</span><span class="sxs-lookup"><span data-stu-id="f2922-109">0x3E03</span></span>  <br/> |
|<span data-ttu-id="f2922-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f2922-110">Data type:</span></span>  <br/> |<span data-ttu-id="f2922-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f2922-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f2922-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f2922-112">Area:</span></span>  <br/> |<span data-ttu-id="f2922-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="f2922-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f2922-114">注解</span><span class="sxs-lookup"><span data-stu-id="f2922-114">Remarks</span></span>

<span data-ttu-id="f2922-115">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="f2922-115">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="f2922-116">MAPI_AB</span><span class="sxs-lookup"><span data-stu-id="f2922-116">MAPI_AB</span></span> 
  
> <span data-ttu-id="f2922-117">通讯簿</span><span class="sxs-lookup"><span data-stu-id="f2922-117">Address book</span></span>
    
<span data-ttu-id="f2922-118">MAPI_AB_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="f2922-118">MAPI_AB_PROVIDER</span></span> 
  
> <span data-ttu-id="f2922-119">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="f2922-119">Address book provider</span></span>
    
<span data-ttu-id="f2922-120">MAPI_HOOK_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="f2922-120">MAPI_HOOK_PROVIDER</span></span> 
  
> <span data-ttu-id="f2922-121">后台处理程序挂接提供程序</span><span class="sxs-lookup"><span data-stu-id="f2922-121">Spooler hook provider</span></span>
    
<span data-ttu-id="f2922-122">MAPI_PROFILE_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="f2922-122">MAPI_PROFILE_PROVIDER</span></span> 
  
> <span data-ttu-id="f2922-123">配置文件提供程序</span><span class="sxs-lookup"><span data-stu-id="f2922-123">Profile provider</span></span>
    
<span data-ttu-id="f2922-124">MAPI_SPOOLER</span><span class="sxs-lookup"><span data-stu-id="f2922-124">MAPI_SPOOLER</span></span> 
  
> <span data-ttu-id="f2922-125">消息后台处理程序</span><span class="sxs-lookup"><span data-stu-id="f2922-125">Message spooler</span></span>
    
<span data-ttu-id="f2922-126">MAPI_STORE_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="f2922-126">MAPI_STORE_PROVIDER</span></span> 
  
> <span data-ttu-id="f2922-127">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="f2922-127">Message store provider</span></span>
    
<span data-ttu-id="f2922-128">MAPI_SUBSYSTEM</span><span class="sxs-lookup"><span data-stu-id="f2922-128">MAPI_SUBSYSTEM</span></span> 
  
> <span data-ttu-id="f2922-129">内部 MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="f2922-129">Internal MAPI subsystem</span></span>
    
<span data-ttu-id="f2922-130">MAPI_TRANSPORT_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="f2922-130">MAPI_TRANSPORT_PROVIDER</span></span> 
  
> <span data-ttu-id="f2922-131">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="f2922-131">Transport provider</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="f2922-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="f2922-132">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f2922-133">头文件</span><span class="sxs-lookup"><span data-stu-id="f2922-133">Header files</span></span>

<span data-ttu-id="f2922-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f2922-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="f2922-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f2922-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="f2922-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f2922-136">Mapitags.h</span></span>
  
> <span data-ttu-id="f2922-137">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f2922-137">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f2922-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2922-138">See also</span></span>



[<span data-ttu-id="f2922-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f2922-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f2922-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f2922-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f2922-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f2922-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f2922-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f2922-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

