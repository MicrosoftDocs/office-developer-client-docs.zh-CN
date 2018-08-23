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
ms.openlocfilehash: 0c3b200c416a21dab00e1ad31e70b58fbdbf845e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590608"
---
# <a name="pidtagrelatedmessageids-canonical-property"></a><span data-ttu-id="14968-103">PidTagRelatedMessageIds 规范属性</span><span class="sxs-lookup"><span data-stu-id="14968-103">PidTagRelatedMessageIds Canonical Property</span></span>

  
  
<span data-ttu-id="14968-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="14968-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="14968-105">包含与邮件相关的消息的标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="14968-105">Contains a list of identifiers for messages to which a message is related.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="14968-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="14968-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="14968-107">PR_RELATED_IPMS</span><span class="sxs-lookup"><span data-stu-id="14968-107">PR_RELATED_IPMS</span></span>  <br/> |
|<span data-ttu-id="14968-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="14968-108">Identifier:</span></span>  <br/> |<span data-ttu-id="14968-109">0x002D</span><span class="sxs-lookup"><span data-stu-id="14968-109">0x002D</span></span>  <br/> |
|<span data-ttu-id="14968-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="14968-110">Data type:</span></span>  <br/> |<span data-ttu-id="14968-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="14968-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="14968-112">区域：</span><span class="sxs-lookup"><span data-stu-id="14968-112">Area:</span></span>  <br/> |<span data-ttu-id="14968-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="14968-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="14968-114">注解</span><span class="sxs-lookup"><span data-stu-id="14968-114">Remarks</span></span>

<span data-ttu-id="14968-115">标识符使用相同的特定构造规则，如用于**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="14968-115">The identifiers use the same specific construction rules as are used for the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="14968-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="14968-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="14968-117">头文件</span><span class="sxs-lookup"><span data-stu-id="14968-117">Header files</span></span>

<span data-ttu-id="14968-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="14968-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="14968-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="14968-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="14968-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="14968-120">Mapitags.h</span></span>
  
> <span data-ttu-id="14968-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="14968-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="14968-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14968-122">See also</span></span>



[<span data-ttu-id="14968-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="14968-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="14968-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="14968-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="14968-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="14968-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="14968-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="14968-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

