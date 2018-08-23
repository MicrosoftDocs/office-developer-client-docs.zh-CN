---
title: PidLidNonSendCcTrackStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidNonSendCcTrackStatus
api_type:
- COM
ms.assetid: e2654fad-444b-45bc-976d-3c5cbbc81b84
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1ee68f0f60f96798130115cbd313f6d7cd403486
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590496"
---
# <a name="pidlidnonsendcctrackstatus-canonical-property"></a><span data-ttu-id="026ae-103">PidLidNonSendCcTrackStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="026ae-103">PidLidNonSendCcTrackStatus Canonical Property</span></span>

  
  
<span data-ttu-id="026ae-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="026ae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="026ae-105">包含的每个与会者的**dispidNonSendableCC** ([PidLidNonSendableCc](pidlidnonsendablecc-canonical-property.md)) 属性中列出的值。</span><span class="sxs-lookup"><span data-stu-id="026ae-105">Contains the value for each attendee listed in the **dispidNonSendableCC** ([PidLidNonSendableCc](pidlidnonsendablecc-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="026ae-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="026ae-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="026ae-107">dispidNonSendCcTrackStatus</span><span class="sxs-lookup"><span data-stu-id="026ae-107">dispidNonSendCcTrackStatus</span></span>  <br/> |
|<span data-ttu-id="026ae-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="026ae-108">Property set:</span></span>  <br/> |<span data-ttu-id="026ae-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="026ae-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="026ae-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="026ae-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="026ae-111">0x00008544</span><span class="sxs-lookup"><span data-stu-id="026ae-111">0x00008544</span></span>  <br/> |
|<span data-ttu-id="026ae-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="026ae-112">Data type:</span></span>  <br/> |<span data-ttu-id="026ae-113">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="026ae-113">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="026ae-114">区域：</span><span class="sxs-lookup"><span data-stu-id="026ae-114">Area:</span></span>  <br/> |<span data-ttu-id="026ae-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="026ae-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="026ae-116">注解</span><span class="sxs-lookup"><span data-stu-id="026ae-116">Remarks</span></span>

<span data-ttu-id="026ae-117">仅当**dispidNonSendableCC**属性设置时，此属性是必需的。</span><span class="sxs-lookup"><span data-stu-id="026ae-117">This property is required only when the **dispidNonSendableCC** property is set.</span></span> <span data-ttu-id="026ae-118">此属性中的值的数目必须等于**dispidNonSendableCC**中值的数目。</span><span class="sxs-lookup"><span data-stu-id="026ae-118">The number of values in this property must equal the number of values in **dispidNonSendableCC**.</span></span> <span data-ttu-id="026ae-119">此属性中的每个 PT_LONG 值对应于**dispidNonSendableCC**属性在同一索引中的与会者。</span><span class="sxs-lookup"><span data-stu-id="026ae-119">Each PT_LONG value in this property corresponds to the attendee in the **dispidNonSendableCC** property at the same index.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="026ae-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="026ae-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="026ae-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="026ae-121">Protocol specifications</span></span>

<span data-ttu-id="026ae-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="026ae-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="026ae-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="026ae-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="026ae-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="026ae-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="026ae-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="026ae-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="026ae-126">头文件</span><span class="sxs-lookup"><span data-stu-id="026ae-126">Header files</span></span>

<span data-ttu-id="026ae-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="026ae-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="026ae-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="026ae-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="026ae-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="026ae-129">See also</span></span>



[<span data-ttu-id="026ae-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="026ae-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="026ae-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="026ae-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="026ae-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="026ae-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="026ae-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="026ae-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

