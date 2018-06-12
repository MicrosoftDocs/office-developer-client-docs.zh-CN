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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b15b87064cc30035004596e93c20ca7d5f653c9f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777924"
---
# <a name="pidtagobsoletedmessageids-canonical-property"></a><span data-ttu-id="86238-103">PidTagObsoletedMessageIds 规范属性</span><span class="sxs-lookup"><span data-stu-id="86238-103">PidTagObsoletedMessageIds Canonical Property</span></span>

  
  
<span data-ttu-id="86238-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="86238-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="86238-105">包含此消息取代的消息的标识符。</span><span class="sxs-lookup"><span data-stu-id="86238-105">Contains the identifiers of messages that this message supersedes.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="86238-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="86238-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="86238-107">PR_OBSOLETED_IPMS</span><span class="sxs-lookup"><span data-stu-id="86238-107">PR_OBSOLETED_IPMS</span></span>  <br/> |
|<span data-ttu-id="86238-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="86238-108">Identifier:</span></span>  <br/> |<span data-ttu-id="86238-109">0x001F</span><span class="sxs-lookup"><span data-stu-id="86238-109">0x001F</span></span>  <br/> |
|<span data-ttu-id="86238-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="86238-110">Data type:</span></span>  <br/> |<span data-ttu-id="86238-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="86238-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="86238-112">区域：</span><span class="sxs-lookup"><span data-stu-id="86238-112">Area:</span></span>  <br/> |<span data-ttu-id="86238-113">Server</span><span class="sxs-lookup"><span data-stu-id="86238-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="86238-114">备注</span><span class="sxs-lookup"><span data-stu-id="86238-114">Remarks</span></span>

<span data-ttu-id="86238-115">此属性中包含的标识符是标准搜索键使用**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性的格式。</span><span class="sxs-lookup"><span data-stu-id="86238-115">The identifiers contained in this property are standard search keys using the format of the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="86238-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="86238-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="86238-117">头文件</span><span class="sxs-lookup"><span data-stu-id="86238-117">Header files</span></span>

<span data-ttu-id="86238-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="86238-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="86238-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="86238-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="86238-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="86238-120">Mapitags.h</span></span>
  
> <span data-ttu-id="86238-121">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="86238-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="86238-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86238-122">See also</span></span>



[<span data-ttu-id="86238-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="86238-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="86238-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="86238-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="86238-125">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="86238-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="86238-126">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="86238-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

