---
title: PidTagSearchFolderExpiration 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSearchFolderExpiration
api_type:
- COM
ms.assetid: e5746090-c850-4e95-b1e7-a07e42c87179
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bd70d18242fadee964ad96305728e63617a0276f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778359"
---
# <a name="pidtagsearchfolderexpiration-canonical-property"></a><span data-ttu-id="e0f17-103">PidTagSearchFolderExpiration 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0f17-103">PidTagSearchFolderExpiration Canonical Property</span></span>

  
  
<span data-ttu-id="e0f17-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e0f17-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e0f17-105">包含搜索文件夹容器将过期时间和应更新或重新创建。</span><span class="sxs-lookup"><span data-stu-id="e0f17-105">Contains the time at which the search folder container will be stale and should be updated or recreated.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e0f17-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="e0f17-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e0f17-107">PR_WB_SF_EXPIRATION</span><span class="sxs-lookup"><span data-stu-id="e0f17-107">PR_WB_SF_EXPIRATION</span></span>  <br/> |
|<span data-ttu-id="e0f17-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e0f17-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e0f17-109">0x683A</span><span class="sxs-lookup"><span data-stu-id="e0f17-109">0x683A</span></span>  <br/> |
|<span data-ttu-id="e0f17-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e0f17-110">Data type:</span></span>  <br/> |<span data-ttu-id="e0f17-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e0f17-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e0f17-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e0f17-112">Area:</span></span>  <br/> |<span data-ttu-id="e0f17-113">搜索</span><span class="sxs-lookup"><span data-stu-id="e0f17-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e0f17-114">备注</span><span class="sxs-lookup"><span data-stu-id="e0f17-114">Remarks</span></span>

<span data-ttu-id="e0f17-115">此属性的格式必须为协调世界时 (UTC) 午夜 1601 年 1 月 1 日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="e0f17-115">This property must be formatted as the number of minutes since midnight Coordinated Universal Time (UTC) January 1, 1601.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e0f17-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="e0f17-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e0f17-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="e0f17-117">Protocol specifications</span></span>

<span data-ttu-id="e0f17-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0f17-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0f17-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e0f17-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e0f17-120">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0f17-120">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0f17-121">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="e0f17-121">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e0f17-122">头文件</span><span class="sxs-lookup"><span data-stu-id="e0f17-122">Header files</span></span>

<span data-ttu-id="e0f17-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e0f17-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="e0f17-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e0f17-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="e0f17-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e0f17-125">Mapitags.h</span></span>
  
> <span data-ttu-id="e0f17-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e0f17-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e0f17-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0f17-127">See also</span></span>



[<span data-ttu-id="e0f17-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e0f17-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e0f17-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0f17-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e0f17-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e0f17-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e0f17-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e0f17-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

