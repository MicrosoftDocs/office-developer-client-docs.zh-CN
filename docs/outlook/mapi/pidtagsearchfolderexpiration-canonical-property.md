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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a119bb735f752719d292371d4dc43e72450b33c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336468"
---
# <a name="pidtagsearchfolderexpiration-canonical-property"></a><span data-ttu-id="4b535-103">PidTagSearchFolderExpiration 规范属性</span><span class="sxs-lookup"><span data-stu-id="4b535-103">PidTagSearchFolderExpiration Canonical Property</span></span>

  
  
<span data-ttu-id="4b535-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4b535-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4b535-105">包含搜索文件夹容器的失效时间, 应进行更新或重新创建。</span><span class="sxs-lookup"><span data-stu-id="4b535-105">Contains the time at which the search folder container will be stale and should be updated or recreated.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4b535-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4b535-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4b535-107">PR_WB_SF_EXPIRATION</span><span class="sxs-lookup"><span data-stu-id="4b535-107">PR_WB_SF_EXPIRATION</span></span>  <br/> |
|<span data-ttu-id="4b535-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4b535-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4b535-109">0x683A</span><span class="sxs-lookup"><span data-stu-id="4b535-109">0x683A</span></span>  <br/> |
|<span data-ttu-id="4b535-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4b535-110">Data type:</span></span>  <br/> |<span data-ttu-id="4b535-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="4b535-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="4b535-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4b535-112">Area:</span></span>  <br/> |<span data-ttu-id="4b535-113">搜索</span><span class="sxs-lookup"><span data-stu-id="4b535-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4b535-114">注解</span><span class="sxs-lookup"><span data-stu-id="4b535-114">Remarks</span></span>

<span data-ttu-id="4b535-115">此属性的格式必须为自 "协调世界时 (UTC)" 1601 年1月1日午夜开始的分钟数。</span><span class="sxs-lookup"><span data-stu-id="4b535-115">This property must be formatted as the number of minutes since midnight Coordinated Universal Time (UTC) January 1, 1601.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4b535-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="4b535-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4b535-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="4b535-117">Protocol specifications</span></span>

<span data-ttu-id="4b535-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4b535-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4b535-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="4b535-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4b535-120">[[毫秒-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4b535-120">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4b535-121">指定用于操作搜索文件夹列表配置的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4b535-121">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4b535-122">头文件</span><span class="sxs-lookup"><span data-stu-id="4b535-122">Header files</span></span>

<span data-ttu-id="4b535-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4b535-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="4b535-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4b535-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="4b535-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="4b535-125">Mapitags.h</span></span>
  
> <span data-ttu-id="4b535-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4b535-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4b535-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b535-127">See also</span></span>



[<span data-ttu-id="4b535-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4b535-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4b535-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4b535-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4b535-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4b535-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4b535-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4b535-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

