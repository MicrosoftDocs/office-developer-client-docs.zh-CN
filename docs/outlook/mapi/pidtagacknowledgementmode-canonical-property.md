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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: df426e3525ee70568041e90998833d6c93edcca7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777292"
---
# <a name="pidtagacknowledgementmode-canonical-property"></a><span data-ttu-id="0d042-103">PidTagAcknowledgementMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d042-103">PidTagAcknowledgementMode Canonical Property</span></span>

  
  
<span data-ttu-id="0d042-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0d042-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0d042-105">包含消息确认的模式的标识符。</span><span class="sxs-lookup"><span data-stu-id="0d042-105">Contains the identifier of the mode for message acknowledgment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0d042-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="0d042-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0d042-107">PR_ACKNOWLEDGEMENT_MODE</span><span class="sxs-lookup"><span data-stu-id="0d042-107">PR_ACKNOWLEDGEMENT_MODE</span></span>  <br/> |
|<span data-ttu-id="0d042-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0d042-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0d042-109">0x0001</span><span class="sxs-lookup"><span data-stu-id="0d042-109">0x0001</span></span>  <br/> |
|<span data-ttu-id="0d042-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0d042-110">Data type:</span></span>  <br/> |<span data-ttu-id="0d042-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0d042-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0d042-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0d042-112">Area:</span></span>  <br/> |<span data-ttu-id="0d042-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="0d042-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0d042-114">备注</span><span class="sxs-lookup"><span data-stu-id="0d042-114">Remarks</span></span>

<span data-ttu-id="0d042-115">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="0d042-115">This property can have exactly one of the following values:</span></span>
  
|<span data-ttu-id="0d042-116">**值**</span><span class="sxs-lookup"><span data-stu-id="0d042-116">**Value**</span></span>|<span data-ttu-id="0d042-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="0d042-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d042-118">0</span><span class="sxs-lookup"><span data-stu-id="0d042-118">0</span></span>  <br/> |<span data-ttu-id="0d042-119">手动确认。</span><span class="sxs-lookup"><span data-stu-id="0d042-119">Manual acknowledgment.</span></span>  <br/> |
|<span data-ttu-id="0d042-120">1</span><span class="sxs-lookup"><span data-stu-id="0d042-120">1</span></span>  <br/> |<span data-ttu-id="0d042-121">自动确认。</span><span class="sxs-lookup"><span data-stu-id="0d042-121">Automatic acknowledgment.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="0d042-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="0d042-122">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0d042-123">头文件</span><span class="sxs-lookup"><span data-stu-id="0d042-123">Header files</span></span>

<span data-ttu-id="0d042-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0d042-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="0d042-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0d042-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="0d042-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0d042-126">Mapitags.h</span></span>
  
> <span data-ttu-id="0d042-127">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0d042-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0d042-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d042-128">See also</span></span>



[<span data-ttu-id="0d042-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0d042-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0d042-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d042-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0d042-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0d042-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0d042-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0d042-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

