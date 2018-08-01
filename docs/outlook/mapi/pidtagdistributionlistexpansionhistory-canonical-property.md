---
title: PidTagDistributionListExpansionHistory 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDistributionListExpansionHistory
api_type:
- HeaderDef
ms.assetid: fc1e0162-d655-4761-92e7-b469579c270b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3989532388d9c88c293427a4ce7109579a832ad1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777581"
---
# <a name="pidtagdistributionlistexpansionhistory-canonical-property"></a><span data-ttu-id="8b88d-103">PidTagDistributionListExpansionHistory 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b88d-103">PidTagDistributionListExpansionHistory Canonical Property</span></span>

  
  
<span data-ttu-id="8b88d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8b88d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8b88d-105">包含显示如何了通讯组列表扩展期间邮件传输历史记录。</span><span class="sxs-lookup"><span data-stu-id="8b88d-105">Contains a history showing how a distribution list has been expanded during message transmission.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8b88d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8b88d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8b88d-107">PR_DL_EXPANSION_HISTORY</span><span class="sxs-lookup"><span data-stu-id="8b88d-107">PR_DL_EXPANSION_HISTORY</span></span>  <br/> |
|<span data-ttu-id="8b88d-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8b88d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8b88d-109">0x0013</span><span class="sxs-lookup"><span data-stu-id="8b88d-109">0x0013</span></span>  <br/> |
|<span data-ttu-id="8b88d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8b88d-110">Data type:</span></span>  <br/> |<span data-ttu-id="8b88d-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8b88d-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8b88d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8b88d-112">Area:</span></span>  <br/> |<span data-ttu-id="8b88d-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="8b88d-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8b88d-114">说明</span><span class="sxs-lookup"><span data-stu-id="8b88d-114">Remarks</span></span>

<span data-ttu-id="8b88d-115">此属性可供如果传输提供程序已将其设置接收客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b88d-115">This property is available to receiving client applications if the transport provider has set it.</span></span> <span data-ttu-id="8b88d-116">如果报表返回邮件内容，则也可以发送的客户端可用的。</span><span class="sxs-lookup"><span data-stu-id="8b88d-116">It is also available to the sending client if the message content is returned with a report.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8b88d-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="8b88d-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8b88d-118">头文件</span><span class="sxs-lookup"><span data-stu-id="8b88d-118">Header files</span></span>

<span data-ttu-id="8b88d-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8b88d-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="8b88d-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8b88d-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="8b88d-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8b88d-121">Mapitags.h</span></span>
  
> <span data-ttu-id="8b88d-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8b88d-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8b88d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b88d-123">See also</span></span>



[<span data-ttu-id="8b88d-124">PidTagDistributionListExpansionProhibited 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b88d-124">PidTagDistributionListExpansionProhibited Canonical Property</span></span>](pidtagdistributionlistexpansionprohibited-canonical-property.md)


[<span data-ttu-id="8b88d-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8b88d-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8b88d-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b88d-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8b88d-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8b88d-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8b88d-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8b88d-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

