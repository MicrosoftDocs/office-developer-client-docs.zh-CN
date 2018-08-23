---
title: PidTagAcknowledgementMode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAcknowledgementMode
api_type:
- HeaderDef
ms.assetid: 23329ca3-89f9-4e5a-9c8a-6262f2a2d26f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28b42e6abee5d918dbcca69c13642f3ebcc859e1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581935"
---
# <a name="pidtagacknowledgementmode-canonical-property"></a><span data-ttu-id="44fe1-103">PidTagAcknowledgementMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="44fe1-103">PidTagAcknowledgementMode Canonical Property</span></span>

  
  
<span data-ttu-id="44fe1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="44fe1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="44fe1-105">包含消息确认的模式的标识符。</span><span class="sxs-lookup"><span data-stu-id="44fe1-105">Contains the identifier of the mode for message acknowledgment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="44fe1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="44fe1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="44fe1-107">PR_ACKNOWLEDGEMENT_MODE</span><span class="sxs-lookup"><span data-stu-id="44fe1-107">PR_ACKNOWLEDGEMENT_MODE</span></span>  <br/> |
|<span data-ttu-id="44fe1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="44fe1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="44fe1-109">0x0001</span><span class="sxs-lookup"><span data-stu-id="44fe1-109">0x0001</span></span>  <br/> |
|<span data-ttu-id="44fe1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="44fe1-110">Data type:</span></span>  <br/> |<span data-ttu-id="44fe1-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="44fe1-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="44fe1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="44fe1-112">Area:</span></span>  <br/> |<span data-ttu-id="44fe1-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="44fe1-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="44fe1-114">注解</span><span class="sxs-lookup"><span data-stu-id="44fe1-114">Remarks</span></span>

<span data-ttu-id="44fe1-115">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="44fe1-115">This property can have exactly one of the following values:</span></span>
  
|<span data-ttu-id="44fe1-116">**值**</span><span class="sxs-lookup"><span data-stu-id="44fe1-116">**Value**</span></span>|<span data-ttu-id="44fe1-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="44fe1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44fe1-118">0</span><span class="sxs-lookup"><span data-stu-id="44fe1-118">0</span></span>  <br/> |<span data-ttu-id="44fe1-119">手动确认。</span><span class="sxs-lookup"><span data-stu-id="44fe1-119">Manual acknowledgment.</span></span>  <br/> |
|<span data-ttu-id="44fe1-120">1</span><span class="sxs-lookup"><span data-stu-id="44fe1-120">1</span></span>  <br/> |<span data-ttu-id="44fe1-121">自动确认。</span><span class="sxs-lookup"><span data-stu-id="44fe1-121">Automatic acknowledgment.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="44fe1-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="44fe1-122">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="44fe1-123">头文件</span><span class="sxs-lookup"><span data-stu-id="44fe1-123">Header files</span></span>

<span data-ttu-id="44fe1-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="44fe1-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="44fe1-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="44fe1-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="44fe1-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="44fe1-126">Mapitags.h</span></span>
  
> <span data-ttu-id="44fe1-127">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="44fe1-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="44fe1-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44fe1-128">See also</span></span>



[<span data-ttu-id="44fe1-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="44fe1-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="44fe1-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="44fe1-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="44fe1-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="44fe1-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="44fe1-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="44fe1-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

