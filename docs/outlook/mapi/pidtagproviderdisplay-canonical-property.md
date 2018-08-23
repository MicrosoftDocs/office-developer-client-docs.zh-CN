---
title: PidTagProviderDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderDisplay
api_type:
- COM
ms.assetid: 62e96db8-4c3e-4f73-b695-99eb4b2396fd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9a37382cda1a96025f950d941f83fb5b6a0497bb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565499"
---
# <a name="pidtagproviderdisplay-canonical-property"></a><span data-ttu-id="3d027-103">PidTagProviderDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d027-103">PidTagProviderDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="3d027-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3d027-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3d027-105">包含服务提供商的供应商定义的显示名称。</span><span class="sxs-lookup"><span data-stu-id="3d027-105">Contains the vendor-defined display name for a service provider.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3d027-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3d027-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3d027-107">PR_PROVIDER_DISPLAY，PR_PROVIDER_DISPLAY_A，PR_PROVIDER_DISPLAY_W</span><span class="sxs-lookup"><span data-stu-id="3d027-107">PR_PROVIDER_DISPLAY, PR_PROVIDER_DISPLAY_A, PR_PROVIDER_DISPLAY_W</span></span>  <br/> |
|<span data-ttu-id="3d027-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="3d027-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3d027-109">0x3006</span><span class="sxs-lookup"><span data-stu-id="3d027-109">0x3006</span></span>  <br/> |
|<span data-ttu-id="3d027-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3d027-110">Data type:</span></span>  <br/> |<span data-ttu-id="3d027-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3d027-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3d027-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3d027-112">Area:</span></span>  <br/> |<span data-ttu-id="3d027-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="3d027-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3d027-114">注解</span><span class="sxs-lookup"><span data-stu-id="3d027-114">Remarks</span></span>

<span data-ttu-id="3d027-115">仅在属于服务提供商的配置文件部分定义这些属性和**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="3d027-115">These properties and **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) are defined only on profile sections belonging to service providers.</span></span> <span data-ttu-id="3d027-116">它们必须存在于 MAPISVC.INF 中。</span><span class="sxs-lookup"><span data-stu-id="3d027-116">They must be present in MAPISVC.INF.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3d027-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="3d027-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="3d027-118">头文件</span><span class="sxs-lookup"><span data-stu-id="3d027-118">Header files</span></span>

<span data-ttu-id="3d027-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3d027-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="3d027-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3d027-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="3d027-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3d027-121">Mapitags.h</span></span>
  
> <span data-ttu-id="3d027-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3d027-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3d027-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d027-123">See also</span></span>



[<span data-ttu-id="3d027-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3d027-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3d027-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d027-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3d027-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3d027-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3d027-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3d027-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

