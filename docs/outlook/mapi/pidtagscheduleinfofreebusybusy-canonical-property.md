---
title: PidTagScheduleInfoFreeBusyBusy 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyBusy
api_type:
- COM
ms.assetid: 84d9c5b5-e734-4c07-b4cc-1d7b13c1ed19
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4fbf0d8b80fdb48e44480b2739a71aec43b88a05
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395712"
---
# <a name="pidtagscheduleinfofreebusybusy-canonical-property"></a><span data-ttu-id="d6d12-103">PidTagScheduleInfoFreeBusyBusy 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6d12-103">PidTagScheduleInfoFreeBusyBusy Canonical Property</span></span>

  
  
<span data-ttu-id="d6d12-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6d12-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d6d12-105">包含状态的忙时间的基块。</span><span class="sxs-lookup"><span data-stu-id="d6d12-105">Contains the blocks of time for which the status is busy.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d6d12-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d6d12-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d6d12-107">PR_SCHDINFO_FREEBUSY_BUSY</span><span class="sxs-lookup"><span data-stu-id="d6d12-107">PR_SCHDINFO_FREEBUSY_BUSY</span></span>  <br/> |
|<span data-ttu-id="d6d12-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d6d12-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d6d12-109">0x6854</span><span class="sxs-lookup"><span data-stu-id="d6d12-109">0x6854</span></span>  <br/> |
|<span data-ttu-id="d6d12-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d6d12-110">Data type:</span></span>  <br/> |<span data-ttu-id="d6d12-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="d6d12-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="d6d12-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d6d12-112">Area:</span></span>  <br/> |<span data-ttu-id="d6d12-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="d6d12-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d6d12-114">说明</span><span class="sxs-lookup"><span data-stu-id="d6d12-114">Remarks</span></span>

<span data-ttu-id="d6d12-115">格式、 computation 和此属性的约束的那些**PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 相同，但引用标记的关联的 calendar 对象上繁忙的约会。</span><span class="sxs-lookup"><span data-stu-id="d6d12-115">The format, computation and constraints of this property are the same as those of **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) but refer to appointments that are marked busy on the associated calendar object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d6d12-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="d6d12-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d6d12-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="d6d12-117">Protocol specifications</span></span>

<span data-ttu-id="d6d12-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d6d12-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d6d12-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="d6d12-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d6d12-120">[[MS OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d6d12-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d6d12-121">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="d6d12-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d6d12-122">头文件</span><span class="sxs-lookup"><span data-stu-id="d6d12-122">Header files</span></span>

<span data-ttu-id="d6d12-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d6d12-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="d6d12-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d6d12-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="d6d12-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d6d12-125">Mapitags.h</span></span>
  
> <span data-ttu-id="d6d12-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d6d12-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d6d12-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6d12-127">See also</span></span>



[<span data-ttu-id="d6d12-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d6d12-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d6d12-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6d12-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d6d12-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d6d12-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d6d12-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d6d12-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

