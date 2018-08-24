---
title: PidTagScheduleInfoFreeBusy 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusy
api_type:
- COM
ms.assetid: 54e65b23-7c5f-4ef3-9e32-329f5f461e1e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 37a79d0106de9ec2e75e8ea3954105d7ebaa52b5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595277"
---
# <a name="pidtagscheduleinfofreebusy-canonical-property"></a><span data-ttu-id="2215e-103">PidTagScheduleInfoFreeBusy 规范属性</span><span class="sxs-lookup"><span data-stu-id="2215e-103">PidTagScheduleInfoFreeBusy Canonical Property</span></span>

  
  
<span data-ttu-id="2215e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2215e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2215e-105">包含过时信息。</span><span class="sxs-lookup"><span data-stu-id="2215e-105">Contains obsolete information.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2215e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2215e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2215e-107">PR_SCHDINFO_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="2215e-107">PR_SCHDINFO_FREEBUSY</span></span>  <br/> |
|<span data-ttu-id="2215e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="2215e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2215e-109">0x686C</span><span class="sxs-lookup"><span data-stu-id="2215e-109">0x686C</span></span>  <br/> |
|<span data-ttu-id="2215e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2215e-110">Data type:</span></span>  <br/> |<span data-ttu-id="2215e-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2215e-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2215e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2215e-112">Area:</span></span>  <br/> |<span data-ttu-id="2215e-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="2215e-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2215e-114">注解</span><span class="sxs-lookup"><span data-stu-id="2215e-114">Remarks</span></span>

<span data-ttu-id="2215e-115">此属性不应设置，必须被忽略。</span><span class="sxs-lookup"><span data-stu-id="2215e-115">This property should not be set and must be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2215e-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="2215e-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2215e-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="2215e-117">Protocol specifications</span></span>

<span data-ttu-id="2215e-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2215e-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2215e-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="2215e-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2215e-120">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2215e-120">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2215e-121">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="2215e-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2215e-122">头文件</span><span class="sxs-lookup"><span data-stu-id="2215e-122">Header files</span></span>

<span data-ttu-id="2215e-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2215e-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="2215e-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2215e-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="2215e-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2215e-125">Mapitags.h</span></span>
  
> <span data-ttu-id="2215e-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2215e-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2215e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2215e-127">See also</span></span>



[<span data-ttu-id="2215e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2215e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2215e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2215e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2215e-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2215e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2215e-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2215e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

