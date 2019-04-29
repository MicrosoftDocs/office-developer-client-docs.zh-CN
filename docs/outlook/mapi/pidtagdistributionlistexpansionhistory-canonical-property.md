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
ms.openlocfilehash: a172fa1e04f1ea50c29955febda47be6e52663b4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422955"
---
# <a name="pidtagdistributionlistexpansionhistory-canonical-property"></a><span data-ttu-id="d3587-103">PidTagDistributionListExpansionHistory 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3587-103">PidTagDistributionListExpansionHistory Canonical Property</span></span>

  
  
<span data-ttu-id="d3587-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3587-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3587-105">包含演示如何在邮件传输过程中扩展通讯组列表的历史记录。</span><span class="sxs-lookup"><span data-stu-id="d3587-105">Contains a history showing how a distribution list has been expanded during message transmission.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d3587-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d3587-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d3587-107">PR_DL_EXPANSION_HISTORY</span><span class="sxs-lookup"><span data-stu-id="d3587-107">PR_DL_EXPANSION_HISTORY</span></span>  <br/> |
|<span data-ttu-id="d3587-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d3587-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d3587-109">0x0013</span><span class="sxs-lookup"><span data-stu-id="d3587-109">0x0013</span></span>  <br/> |
|<span data-ttu-id="d3587-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d3587-110">Data type:</span></span>  <br/> |<span data-ttu-id="d3587-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d3587-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d3587-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d3587-112">Area:</span></span>  <br/> |<span data-ttu-id="d3587-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="d3587-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d3587-114">说明</span><span class="sxs-lookup"><span data-stu-id="d3587-114">Remarks</span></span>

<span data-ttu-id="d3587-115">如果传输提供程序已对其进行设置, 则可使用此属性接收客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3587-115">This property is available to receiving client applications if the transport provider has set it.</span></span> <span data-ttu-id="d3587-116">如果邮件内容随报告一起返回, 则发送客户端也可使用它。</span><span class="sxs-lookup"><span data-stu-id="d3587-116">It is also available to the sending client if the message content is returned with a report.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d3587-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d3587-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d3587-118">头文件</span><span class="sxs-lookup"><span data-stu-id="d3587-118">Header files</span></span>

<span data-ttu-id="d3587-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d3587-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="d3587-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d3587-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="d3587-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d3587-121">Mapitags.h</span></span>
  
> <span data-ttu-id="d3587-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d3587-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d3587-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3587-123">See also</span></span>



[<span data-ttu-id="d3587-124">PidTagDistributionListExpansionProhibited 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3587-124">PidTagDistributionListExpansionProhibited Canonical Property</span></span>](pidtagdistributionlistexpansionprohibited-canonical-property.md)


[<span data-ttu-id="d3587-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d3587-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d3587-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3587-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d3587-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d3587-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d3587-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d3587-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

