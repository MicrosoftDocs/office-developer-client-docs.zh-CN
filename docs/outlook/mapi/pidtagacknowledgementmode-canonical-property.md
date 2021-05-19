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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418916"
---
# <a name="pidtagacknowledgementmode-canonical-property"></a><span data-ttu-id="9d10e-103">PidTagAcknowledgementMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="9d10e-103">PidTagAcknowledgementMode Canonical Property</span></span>

  
  
<span data-ttu-id="9d10e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9d10e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9d10e-105">包含消息确认的模式的标识符。</span><span class="sxs-lookup"><span data-stu-id="9d10e-105">Contains the identifier of the mode for message acknowledgment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9d10e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9d10e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9d10e-107">PR_ACKNOWLEDGEMENT_MODE</span><span class="sxs-lookup"><span data-stu-id="9d10e-107">PR_ACKNOWLEDGEMENT_MODE</span></span>  <br/> |
|<span data-ttu-id="9d10e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9d10e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9d10e-109">0x0001</span><span class="sxs-lookup"><span data-stu-id="9d10e-109">0x0001</span></span>  <br/> |
|<span data-ttu-id="9d10e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9d10e-110">Data type:</span></span>  <br/> |<span data-ttu-id="9d10e-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="9d10e-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="9d10e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9d10e-112">Area:</span></span>  <br/> |<span data-ttu-id="9d10e-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="9d10e-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9d10e-114">备注</span><span class="sxs-lookup"><span data-stu-id="9d10e-114">Remarks</span></span>

<span data-ttu-id="9d10e-115">此属性可以正好具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="9d10e-115">This property can have exactly one of the following values:</span></span>
  
|<span data-ttu-id="9d10e-116">**值**</span><span class="sxs-lookup"><span data-stu-id="9d10e-116">**Value**</span></span>|<span data-ttu-id="9d10e-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="9d10e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9d10e-118">0</span><span class="sxs-lookup"><span data-stu-id="9d10e-118">0</span></span>  <br/> |<span data-ttu-id="9d10e-119">手动确认。</span><span class="sxs-lookup"><span data-stu-id="9d10e-119">Manual acknowledgment.</span></span>  <br/> |
|<span data-ttu-id="9d10e-120">1</span><span class="sxs-lookup"><span data-stu-id="9d10e-120">1</span></span>  <br/> |<span data-ttu-id="9d10e-121">自动确认。</span><span class="sxs-lookup"><span data-stu-id="9d10e-121">Automatic acknowledgment.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="9d10e-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="9d10e-122">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9d10e-123">头文件</span><span class="sxs-lookup"><span data-stu-id="9d10e-123">Header files</span></span>

<span data-ttu-id="9d10e-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9d10e-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="9d10e-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9d10e-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="9d10e-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9d10e-126">Mapitags.h</span></span>
  
> <span data-ttu-id="9d10e-127">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9d10e-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9d10e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d10e-128">See also</span></span>



[<span data-ttu-id="9d10e-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9d10e-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9d10e-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9d10e-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9d10e-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9d10e-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9d10e-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9d10e-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

