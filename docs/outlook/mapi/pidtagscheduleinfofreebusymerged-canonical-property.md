---
title: PidTagScheduleInfoFreeBusyMerged 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyMerged
api_type:
- COM
ms.assetid: 3ebfccb6-967a-4f8e-9d94-94c50ba65438
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0e1fbab53589a4ebf8681d5fe738ad625d31c18f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778337"
---
# <a name="pidtagscheduleinfofreebusymerged-canonical-property"></a><span data-ttu-id="35562-103">PidTagScheduleInfoFreeBusyMerged 规范属性</span><span class="sxs-lookup"><span data-stu-id="35562-103">PidTagScheduleInfoFreeBusyMerged Canonical Property</span></span>

  
  
<span data-ttu-id="35562-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="35562-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="35562-105">包含为其设置的忙/闲状态的时间为繁忙或 OOF。</span><span class="sxs-lookup"><span data-stu-id="35562-105">Contains the times for which the free/busy status is set to busy or OOF.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="35562-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="35562-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="35562-107">PR_SCHDINFO_FREEBUSY_MERGED</span><span class="sxs-lookup"><span data-stu-id="35562-107">PR_SCHDINFO_FREEBUSY_MERGED</span></span>  <br/> |
|<span data-ttu-id="35562-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="35562-108">Identifier:</span></span>  <br/> |<span data-ttu-id="35562-109">0x6850</span><span class="sxs-lookup"><span data-stu-id="35562-109">0x6850</span></span>  <br/> |
|<span data-ttu-id="35562-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="35562-110">Data type:</span></span>  <br/> |<span data-ttu-id="35562-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="35562-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="35562-112">区域：</span><span class="sxs-lookup"><span data-stu-id="35562-112">Area:</span></span>  <br/> |<span data-ttu-id="35562-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="35562-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="35562-114">说明</span><span class="sxs-lookup"><span data-stu-id="35562-114">Remarks</span></span>

<span data-ttu-id="35562-115">此属性中不包含暂定的忙/闲信息的类型的事件。</span><span class="sxs-lookup"><span data-stu-id="35562-115">Events of free/busy type tentative are not included in this property.</span></span> <span data-ttu-id="35562-116">格式、 computation 和此属性的限制是那些**PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 相同，但参考标记 OOF 或关联的日历闲的约会。</span><span class="sxs-lookup"><span data-stu-id="35562-116">The format, computation and the restrictions of this property are the same as those of **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) but refer to appointments that are marked OOF or busy on the associated calendar.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="35562-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="35562-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="35562-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="35562-118">Protocol specifications</span></span>

<span data-ttu-id="35562-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="35562-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="35562-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="35562-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="35562-121">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="35562-121">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="35562-122">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="35562-122">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="35562-123">头文件</span><span class="sxs-lookup"><span data-stu-id="35562-123">Header files</span></span>

<span data-ttu-id="35562-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="35562-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="35562-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="35562-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="35562-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="35562-126">Mapitags.h</span></span>
  
> <span data-ttu-id="35562-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="35562-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="35562-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35562-128">See also</span></span>



[<span data-ttu-id="35562-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="35562-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="35562-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="35562-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="35562-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="35562-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="35562-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="35562-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

