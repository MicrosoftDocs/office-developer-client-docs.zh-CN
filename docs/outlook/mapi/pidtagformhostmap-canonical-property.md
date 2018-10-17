---
title: PidTagFormHostMap 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFormHostMap
api_type:
- HeaderDef
ms.assetid: 92742747-cce0-4c54-9ece-1fcf652ac498
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8c024f71279fac5dbb3d771442d9fbfb8a50e0f5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578869"
---
# <a name="pidtagformhostmap-canonical-property"></a><span data-ttu-id="cf2a2-103">PidTagFormHostMap 规范属性</span><span class="sxs-lookup"><span data-stu-id="cf2a2-103">PidTagFormHostMap Canonical Property</span></span>

  
  
<span data-ttu-id="cf2a2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cf2a2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cf2a2-105">包含主机地图的可用窗体。</span><span class="sxs-lookup"><span data-stu-id="cf2a2-105">Contains a host map of available forms.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cf2a2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cf2a2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cf2a2-107">PR_FORM_HOST_MAP</span><span class="sxs-lookup"><span data-stu-id="cf2a2-107">PR_FORM_HOST_MAP</span></span>  <br/> |
|<span data-ttu-id="cf2a2-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="cf2a2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cf2a2-109">0x3306</span><span class="sxs-lookup"><span data-stu-id="cf2a2-109">0x3306</span></span>  <br/> |
|<span data-ttu-id="cf2a2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cf2a2-110">Data type:</span></span>  <br/> |<span data-ttu-id="cf2a2-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="cf2a2-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="cf2a2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cf2a2-112">Area:</span></span>  <br/> |<span data-ttu-id="cf2a2-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="cf2a2-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cf2a2-114">注解</span><span class="sxs-lookup"><span data-stu-id="cf2a2-114">Remarks</span></span>

<span data-ttu-id="cf2a2-115">更改**IMAPIFormProp**接口的基础结构时，客户端应用程序应更新以及**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性，此属性。</span><span class="sxs-lookup"><span data-stu-id="cf2a2-115">A client application should update this property, along with the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property, when changing the underlying structure in the **IMAPIFormProp** interface.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="cf2a2-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="cf2a2-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="cf2a2-117">头文件</span><span class="sxs-lookup"><span data-stu-id="cf2a2-117">Header files</span></span>

<span data-ttu-id="cf2a2-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cf2a2-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="cf2a2-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cf2a2-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="cf2a2-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cf2a2-120">Mapitags.h</span></span>
  
> <span data-ttu-id="cf2a2-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cf2a2-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cf2a2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf2a2-122">See also</span></span>



[<span data-ttu-id="cf2a2-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cf2a2-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cf2a2-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cf2a2-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cf2a2-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cf2a2-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cf2a2-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cf2a2-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
