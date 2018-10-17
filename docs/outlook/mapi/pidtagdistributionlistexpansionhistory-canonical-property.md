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
ms.openlocfilehash: 0ba27e1eefa85e1651dbd24fa0540f8b1108588a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588466"
---
# <a name="pidtagdistributionlistexpansionhistory-canonical-property"></a><span data-ttu-id="6620f-103">PidTagDistributionListExpansionHistory 规范属性</span><span class="sxs-lookup"><span data-stu-id="6620f-103">PidTagDistributionListExpansionHistory Canonical Property</span></span>

  
  
<span data-ttu-id="6620f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6620f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6620f-105">包含显示如何了通讯组列表扩展期间邮件传输历史记录。</span><span class="sxs-lookup"><span data-stu-id="6620f-105">Contains a history showing how a distribution list has been expanded during message transmission.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6620f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6620f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6620f-107">PR_DL_EXPANSION_HISTORY</span><span class="sxs-lookup"><span data-stu-id="6620f-107">PR_DL_EXPANSION_HISTORY</span></span>  <br/> |
|<span data-ttu-id="6620f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="6620f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6620f-109">0x0013</span><span class="sxs-lookup"><span data-stu-id="6620f-109">0x0013</span></span>  <br/> |
|<span data-ttu-id="6620f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6620f-110">Data type:</span></span>  <br/> |<span data-ttu-id="6620f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6620f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6620f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6620f-112">Area:</span></span>  <br/> |<span data-ttu-id="6620f-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="6620f-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6620f-114">注解</span><span class="sxs-lookup"><span data-stu-id="6620f-114">Remarks</span></span>

<span data-ttu-id="6620f-115">此属性可供如果传输提供程序已将其设置接收客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="6620f-115">This property is available to receiving client applications if the transport provider has set it.</span></span> <span data-ttu-id="6620f-116">如果报表返回邮件内容，则也可以发送的客户端可用的。</span><span class="sxs-lookup"><span data-stu-id="6620f-116">It is also available to the sending client if the message content is returned with a report.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6620f-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="6620f-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="6620f-118">头文件</span><span class="sxs-lookup"><span data-stu-id="6620f-118">Header files</span></span>

<span data-ttu-id="6620f-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6620f-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="6620f-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6620f-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="6620f-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6620f-121">Mapitags.h</span></span>
  
> <span data-ttu-id="6620f-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6620f-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6620f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6620f-123">See also</span></span>



[<span data-ttu-id="6620f-124">PidTagDistributionListExpansionProhibited 规范属性</span><span class="sxs-lookup"><span data-stu-id="6620f-124">PidTagDistributionListExpansionProhibited Canonical Property</span></span>](pidtagdistributionlistexpansionprohibited-canonical-property.md)


[<span data-ttu-id="6620f-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6620f-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6620f-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6620f-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6620f-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6620f-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6620f-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6620f-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
