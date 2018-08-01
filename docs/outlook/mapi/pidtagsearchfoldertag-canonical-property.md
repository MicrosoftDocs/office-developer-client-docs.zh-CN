---
title: PidTagSearchFolderTag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: b7a88387-72ff-49e5-b73a-8bafab635658
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e2f158607496a8cee9f9c731f2d7d6e185a2851
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778355"
---
# <a name="pidtagsearchfoldertag-canonical-property"></a><span data-ttu-id="dcafe-103">PidTagSearchFolderTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="dcafe-103">PidTagSearchFolderTag Canonical Property</span></span>

  
  
<span data-ttu-id="dcafe-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dcafe-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dcafe-105">包含用于与匹配的搜索文件夹容器同步此定义消息的值。</span><span class="sxs-lookup"><span data-stu-id="dcafe-105">Contains the value used to synchronize this definition message with the matching search folder container.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dcafe-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dcafe-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dcafe-107">PR_WB_SF_TAG</span><span class="sxs-lookup"><span data-stu-id="dcafe-107">PR_WB_SF_TAG</span></span>  <br/> |
|<span data-ttu-id="dcafe-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="dcafe-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dcafe-109">0x6847</span><span class="sxs-lookup"><span data-stu-id="dcafe-109">0x6847</span></span>  <br/> |
|<span data-ttu-id="dcafe-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dcafe-110">Data type:</span></span>  <br/> |<span data-ttu-id="dcafe-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="dcafe-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="dcafe-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dcafe-112">Area:</span></span>  <br/> |<span data-ttu-id="dcafe-113">搜索</span><span class="sxs-lookup"><span data-stu-id="dcafe-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dcafe-114">说明</span><span class="sxs-lookup"><span data-stu-id="dcafe-114">Remarks</span></span>

<span data-ttu-id="dcafe-115">定义邮件发生更改时，更改此属性。</span><span class="sxs-lookup"><span data-stu-id="dcafe-115">This property is changed when the definition message is changed.</span></span> <span data-ttu-id="dcafe-116">它必须更改每次迭代，但它可能不唯一。</span><span class="sxs-lookup"><span data-stu-id="dcafe-116">It must change each iteration, but it may not be unique.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dcafe-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="dcafe-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dcafe-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="dcafe-118">Protocol specifications</span></span>

<span data-ttu-id="dcafe-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dcafe-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dcafe-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="dcafe-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dcafe-121">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dcafe-121">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dcafe-122">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="dcafe-122">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dcafe-123">头文件</span><span class="sxs-lookup"><span data-stu-id="dcafe-123">Header files</span></span>

<span data-ttu-id="dcafe-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dcafe-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="dcafe-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dcafe-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="dcafe-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="dcafe-126">Mapitags.h</span></span>
  
> <span data-ttu-id="dcafe-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dcafe-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dcafe-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcafe-128">See also</span></span>



[<span data-ttu-id="dcafe-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dcafe-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dcafe-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dcafe-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dcafe-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dcafe-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dcafe-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dcafe-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

