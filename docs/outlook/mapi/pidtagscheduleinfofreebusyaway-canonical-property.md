---
title: PidTagScheduleInfoFreeBusyAway 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyAway
api_type:
- COM
ms.assetid: 7b5d013a-15ac-469a-98c8-3ed1e80f6faf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3535e8969ceff975077285aed89f979c24821bdf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778335"
---
# <a name="pidtagscheduleinfofreebusyaway-canonical-property"></a><span data-ttu-id="15d73-103">PidTagScheduleInfoFreeBusyAway 规范属性</span><span class="sxs-lookup"><span data-stu-id="15d73-103">PidTagScheduleInfoFreeBusyAway Canonical Property</span></span>

  
  
<span data-ttu-id="15d73-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="15d73-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="15d73-105">包含的时间的忙/闲状态设置为 OOF。</span><span class="sxs-lookup"><span data-stu-id="15d73-105">Contains the times for which the free/busy status is set to OOF.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="15d73-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="15d73-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="15d73-107">PR_SCHDINFO_FREEBUSY_OOF</span><span class="sxs-lookup"><span data-stu-id="15d73-107">PR_SCHDINFO_FREEBUSY_OOF</span></span>  <br/> |
|<span data-ttu-id="15d73-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="15d73-108">Identifier:</span></span>  <br/> |<span data-ttu-id="15d73-109">0x6856</span><span class="sxs-lookup"><span data-stu-id="15d73-109">0x6856</span></span>  <br/> |
|<span data-ttu-id="15d73-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="15d73-110">Data type:</span></span>  <br/> |<span data-ttu-id="15d73-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="15d73-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="15d73-112">区域：</span><span class="sxs-lookup"><span data-stu-id="15d73-112">Area:</span></span>  <br/> |<span data-ttu-id="15d73-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="15d73-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="15d73-114">说明</span><span class="sxs-lookup"><span data-stu-id="15d73-114">Remarks</span></span>

<span data-ttu-id="15d73-115">格式、 computation 和此属性的约束的那些**PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 相同，但参考关联的日历标记 OOF 的约会。</span><span class="sxs-lookup"><span data-stu-id="15d73-115">The format, computation and constraints of this property are the same as those of **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) but refer to appointments that are marked OOF on the associated calendar.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="15d73-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="15d73-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="15d73-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="15d73-117">Protocol specifications</span></span>

<span data-ttu-id="15d73-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15d73-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15d73-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="15d73-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="15d73-120">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15d73-120">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15d73-121">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="15d73-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="15d73-122">头文件</span><span class="sxs-lookup"><span data-stu-id="15d73-122">Header files</span></span>

<span data-ttu-id="15d73-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="15d73-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="15d73-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="15d73-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="15d73-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="15d73-125">Mapitags.h</span></span>
  
> <span data-ttu-id="15d73-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="15d73-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="15d73-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15d73-127">See also</span></span>



[<span data-ttu-id="15d73-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="15d73-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="15d73-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="15d73-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="15d73-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="15d73-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="15d73-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="15d73-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

