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
ms.openlocfilehash: cee99b93d41ac8cd4a3dee18cad6cd4ab01cabe3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335278"
---
# <a name="pidtagacknowledgementmode-canonical-property"></a><span data-ttu-id="bf670-103">PidTagAcknowledgementMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="bf670-103">PidTagAcknowledgementMode Canonical Property</span></span>

  
  
<span data-ttu-id="bf670-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bf670-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bf670-105">包含用于消息确认的模式的标识符。</span><span class="sxs-lookup"><span data-stu-id="bf670-105">Contains the identifier of the mode for message acknowledgment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bf670-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bf670-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bf670-107">PR_ACKNOWLEDGEMENT_MODE</span><span class="sxs-lookup"><span data-stu-id="bf670-107">PR_ACKNOWLEDGEMENT_MODE</span></span>  <br/> |
|<span data-ttu-id="bf670-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="bf670-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bf670-109">0x0001</span><span class="sxs-lookup"><span data-stu-id="bf670-109">0x0001</span></span>  <br/> |
|<span data-ttu-id="bf670-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bf670-110">Data type:</span></span>  <br/> |<span data-ttu-id="bf670-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="bf670-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="bf670-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bf670-112">Area:</span></span>  <br/> |<span data-ttu-id="bf670-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="bf670-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bf670-114">注解</span><span class="sxs-lookup"><span data-stu-id="bf670-114">Remarks</span></span>

<span data-ttu-id="bf670-115">此属性可以具有下列值之一:</span><span class="sxs-lookup"><span data-stu-id="bf670-115">This property can have exactly one of the following values:</span></span>
  
|<span data-ttu-id="bf670-116">**Value**</span><span class="sxs-lookup"><span data-stu-id="bf670-116">**Value**</span></span>|<span data-ttu-id="bf670-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf670-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf670-118">0</span><span class="sxs-lookup"><span data-stu-id="bf670-118">0</span></span>  <br/> |<span data-ttu-id="bf670-119">手动确认。</span><span class="sxs-lookup"><span data-stu-id="bf670-119">Manual acknowledgment.</span></span>  <br/> |
|<span data-ttu-id="bf670-120">1</span><span class="sxs-lookup"><span data-stu-id="bf670-120">1</span></span>  <br/> |<span data-ttu-id="bf670-121">自动确认。</span><span class="sxs-lookup"><span data-stu-id="bf670-121">Automatic acknowledgment.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="bf670-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="bf670-122">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="bf670-123">头文件</span><span class="sxs-lookup"><span data-stu-id="bf670-123">Header files</span></span>

<span data-ttu-id="bf670-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="bf670-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="bf670-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bf670-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="bf670-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="bf670-126">Mapitags.h</span></span>
  
> <span data-ttu-id="bf670-127">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bf670-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bf670-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf670-128">See also</span></span>



[<span data-ttu-id="bf670-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bf670-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bf670-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bf670-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bf670-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bf670-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bf670-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bf670-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

