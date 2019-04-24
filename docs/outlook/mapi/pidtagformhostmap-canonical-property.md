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
ms.openlocfilehash: 346776635fc36ffd8efd10cb232846831add20f7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316224"
---
# <a name="pidtagformhostmap-canonical-property"></a><span data-ttu-id="71b2b-103">PidTagFormHostMap 规范属性</span><span class="sxs-lookup"><span data-stu-id="71b2b-103">PidTagFormHostMap Canonical Property</span></span>

  
  
<span data-ttu-id="71b2b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="71b2b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="71b2b-105">包含可用表单的主机图。</span><span class="sxs-lookup"><span data-stu-id="71b2b-105">Contains a host map of available forms.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="71b2b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="71b2b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="71b2b-107">PR_FORM_HOST_MAP</span><span class="sxs-lookup"><span data-stu-id="71b2b-107">PR_FORM_HOST_MAP</span></span>  <br/> |
|<span data-ttu-id="71b2b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="71b2b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="71b2b-109">0x3306</span><span class="sxs-lookup"><span data-stu-id="71b2b-109">0x3306</span></span>  <br/> |
|<span data-ttu-id="71b2b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="71b2b-110">Data type:</span></span>  <br/> |<span data-ttu-id="71b2b-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="71b2b-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="71b2b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="71b2b-112">Area:</span></span>  <br/> |<span data-ttu-id="71b2b-113">MAPI 通用</span><span class="sxs-lookup"><span data-stu-id="71b2b-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="71b2b-114">注解</span><span class="sxs-lookup"><span data-stu-id="71b2b-114">Remarks</span></span>

<span data-ttu-id="71b2b-115">当更改**IMAPIFormProp**接口中的基础结构时, 客户端应用程序应更新此属性以及**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="71b2b-115">A client application should update this property, along with the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property, when changing the underlying structure in the **IMAPIFormProp** interface.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="71b2b-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="71b2b-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="71b2b-117">头文件</span><span class="sxs-lookup"><span data-stu-id="71b2b-117">Header files</span></span>

<span data-ttu-id="71b2b-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="71b2b-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="71b2b-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="71b2b-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="71b2b-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="71b2b-120">Mapitags.h</span></span>
  
> <span data-ttu-id="71b2b-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="71b2b-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="71b2b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71b2b-122">See also</span></span>



[<span data-ttu-id="71b2b-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="71b2b-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="71b2b-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="71b2b-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="71b2b-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="71b2b-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="71b2b-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="71b2b-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

