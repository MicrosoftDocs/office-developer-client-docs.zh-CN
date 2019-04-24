---
title: PidTagObsoletedMessageIds 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagObsoletedMessageIds
api_type:
- HeaderDef
ms.assetid: bc979398-f1ad-4496-b982-428b95719369
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1f00a57798b03edb368fb0dc59fead7a2e9f5c8f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329244"
---
# <a name="pidtagobsoletedmessageids-canonical-property"></a><span data-ttu-id="e369d-103">PidTagObsoletedMessageIds 规范属性</span><span class="sxs-lookup"><span data-stu-id="e369d-103">PidTagObsoletedMessageIds Canonical Property</span></span>

  
  
<span data-ttu-id="e369d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e369d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e369d-105">包含此消息取代的消息的标识符。</span><span class="sxs-lookup"><span data-stu-id="e369d-105">Contains the identifiers of messages that this message supersedes.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e369d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e369d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e369d-107">PR_OBSOLETED_IPMS</span><span class="sxs-lookup"><span data-stu-id="e369d-107">PR_OBSOLETED_IPMS</span></span>  <br/> |
|<span data-ttu-id="e369d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e369d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e369d-109">0x001F</span><span class="sxs-lookup"><span data-stu-id="e369d-109">0x001F</span></span>  <br/> |
|<span data-ttu-id="e369d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e369d-110">Data type:</span></span>  <br/> |<span data-ttu-id="e369d-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e369d-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e369d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e369d-112">Area:</span></span>  <br/> |<span data-ttu-id="e369d-113">服务器</span><span class="sxs-lookup"><span data-stu-id="e369d-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e369d-114">注解</span><span class="sxs-lookup"><span data-stu-id="e369d-114">Remarks</span></span>

<span data-ttu-id="e369d-115">此属性中包含的标识符是使用**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性格式的标准搜索键。</span><span class="sxs-lookup"><span data-stu-id="e369d-115">The identifiers contained in this property are standard search keys using the format of the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e369d-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="e369d-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="e369d-117">头文件</span><span class="sxs-lookup"><span data-stu-id="e369d-117">Header files</span></span>

<span data-ttu-id="e369d-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e369d-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="e369d-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e369d-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="e369d-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="e369d-120">Mapitags.h</span></span>
  
> <span data-ttu-id="e369d-121">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e369d-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e369d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e369d-122">See also</span></span>



[<span data-ttu-id="e369d-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e369d-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e369d-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e369d-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e369d-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e369d-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e369d-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e369d-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

