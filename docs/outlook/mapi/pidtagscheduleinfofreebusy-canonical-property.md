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
ms.openlocfilehash: 018e3e907e6ff2250b4c0e5322af52b37d8e2817
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330070"
---
# <a name="pidtagscheduleinfofreebusy-canonical-property"></a><span data-ttu-id="98d35-103">PidTagScheduleInfoFreeBusy 规范属性</span><span class="sxs-lookup"><span data-stu-id="98d35-103">PidTagScheduleInfoFreeBusy Canonical Property</span></span>

  
  
<span data-ttu-id="98d35-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="98d35-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="98d35-105">包含过时信息。</span><span class="sxs-lookup"><span data-stu-id="98d35-105">Contains obsolete information.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="98d35-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="98d35-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="98d35-107">PR_SCHDINFO_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="98d35-107">PR_SCHDINFO_FREEBUSY</span></span>  <br/> |
|<span data-ttu-id="98d35-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="98d35-108">Identifier:</span></span>  <br/> |<span data-ttu-id="98d35-109">0x686C</span><span class="sxs-lookup"><span data-stu-id="98d35-109">0x686C</span></span>  <br/> |
|<span data-ttu-id="98d35-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="98d35-110">Data type:</span></span>  <br/> |<span data-ttu-id="98d35-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="98d35-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="98d35-112">区域：</span><span class="sxs-lookup"><span data-stu-id="98d35-112">Area:</span></span>  <br/> |<span data-ttu-id="98d35-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="98d35-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="98d35-114">注解</span><span class="sxs-lookup"><span data-stu-id="98d35-114">Remarks</span></span>

<span data-ttu-id="98d35-115">不应设置此属性, 必须将其忽略。</span><span class="sxs-lookup"><span data-stu-id="98d35-115">This property should not be set and must be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="98d35-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="98d35-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="98d35-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="98d35-117">Protocol specifications</span></span>

<span data-ttu-id="98d35-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="98d35-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="98d35-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="98d35-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="98d35-120">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="98d35-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="98d35-121">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="98d35-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="98d35-122">头文件</span><span class="sxs-lookup"><span data-stu-id="98d35-122">Header files</span></span>

<span data-ttu-id="98d35-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="98d35-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="98d35-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="98d35-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="98d35-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="98d35-125">Mapitags.h</span></span>
  
> <span data-ttu-id="98d35-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="98d35-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="98d35-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98d35-127">See also</span></span>



[<span data-ttu-id="98d35-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="98d35-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="98d35-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="98d35-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="98d35-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="98d35-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="98d35-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="98d35-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

