---
title: PidTagRelatedMessageIds 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRelatedMessageIds
api_type:
- COM
ms.assetid: 51f0eb8a-0a16-4b45-9380-28caddecf955
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d909a121bdc528a04d0f400555a6f98f29da8f0c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406050"
---
# <a name="pidtagrelatedmessageids-canonical-property"></a><span data-ttu-id="6e860-103">PidTagRelatedMessageIds 规范属性</span><span class="sxs-lookup"><span data-stu-id="6e860-103">PidTagRelatedMessageIds Canonical Property</span></span>

  
  
<span data-ttu-id="6e860-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e860-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e860-105">包含与邮件相关的邮件的标识符列表。</span><span class="sxs-lookup"><span data-stu-id="6e860-105">Contains a list of identifiers for messages to which a message is related.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6e860-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6e860-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6e860-107">PR_RELATED_IPMS</span><span class="sxs-lookup"><span data-stu-id="6e860-107">PR_RELATED_IPMS</span></span>  <br/> |
|<span data-ttu-id="6e860-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6e860-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6e860-109">0x002D</span><span class="sxs-lookup"><span data-stu-id="6e860-109">0x002D</span></span>  <br/> |
|<span data-ttu-id="6e860-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6e860-110">Data type:</span></span>  <br/> |<span data-ttu-id="6e860-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6e860-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6e860-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6e860-112">Area:</span></span>  <br/> |<span data-ttu-id="6e860-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="6e860-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6e860-114">说明</span><span class="sxs-lookup"><span data-stu-id="6e860-114">Remarks</span></span>

<span data-ttu-id="6e860-115">标识符使用的构造规则与用于**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性的特定构造规则相同。</span><span class="sxs-lookup"><span data-stu-id="6e860-115">The identifiers use the same specific construction rules as are used for the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6e860-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="6e860-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="6e860-117">头文件</span><span class="sxs-lookup"><span data-stu-id="6e860-117">Header files</span></span>

<span data-ttu-id="6e860-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6e860-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="6e860-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6e860-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="6e860-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="6e860-120">Mapitags.h</span></span>
  
> <span data-ttu-id="6e860-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6e860-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6e860-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e860-122">See also</span></span>



[<span data-ttu-id="6e860-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6e860-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6e860-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6e860-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6e860-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6e860-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6e860-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6e860-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

