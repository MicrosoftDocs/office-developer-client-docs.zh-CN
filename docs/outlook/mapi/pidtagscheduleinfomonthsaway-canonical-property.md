---
title: PidTagScheduleInfoMonthsAway 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoMonthsAway
api_type:
- COM
ms.assetid: 282a8ba1-b786-4d17-b6c5-17e935e59a6b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 90df272a70fd4133a780f205c93b42f26ed1ae96
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392289"
---
# <a name="pidtagscheduleinfomonthsaway-canonical-property"></a><span data-ttu-id="b3a28-103">PidTagScheduleInfoMonthsAway 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3a28-103">PidTagScheduleInfoMonthsAway Canonical Property</span></span>

  
  
<span data-ttu-id="b3a28-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b3a28-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b3a28-105">包含一个文章列表有外出 (OOF) 类型的忙/闲数据的忙/闲邮件中存在的月份。</span><span class="sxs-lookup"><span data-stu-id="b3a28-105">Contains a list of the months for which free/busy data of type out of office (OOF) is present in the free/busy message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b3a28-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b3a28-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b3a28-107">PR_SCHDINFO_MONTHS_OOF</span><span class="sxs-lookup"><span data-stu-id="b3a28-107">PR_SCHDINFO_MONTHS_OOF</span></span>  <br/> |
|<span data-ttu-id="b3a28-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b3a28-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b3a28-109">0x6855</span><span class="sxs-lookup"><span data-stu-id="b3a28-109">0x6855</span></span>  <br/> |
|<span data-ttu-id="b3a28-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b3a28-110">Data type:</span></span>  <br/> |<span data-ttu-id="b3a28-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="b3a28-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="b3a28-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b3a28-112">Area:</span></span>  <br/> |<span data-ttu-id="b3a28-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="b3a28-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b3a28-114">说明</span><span class="sxs-lookup"><span data-stu-id="b3a28-114">Remarks</span></span>

<span data-ttu-id="b3a28-115">格式、 computation 和此属性的约束的那些**PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 相同，但引用标记外出 (OOF) 关联的约会calendar 对象。</span><span class="sxs-lookup"><span data-stu-id="b3a28-115">The format, computation and constraints of this property are the same as those of **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) but refer to appointments that are marked out of office (OOF) on the associated calendar object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b3a28-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="b3a28-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b3a28-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="b3a28-117">Protocol specifications</span></span>

<span data-ttu-id="b3a28-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b3a28-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b3a28-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b3a28-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b3a28-120">[[MS OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b3a28-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b3a28-121">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="b3a28-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b3a28-122">头文件</span><span class="sxs-lookup"><span data-stu-id="b3a28-122">Header files</span></span>

<span data-ttu-id="b3a28-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b3a28-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="b3a28-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b3a28-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="b3a28-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b3a28-125">Mapitags.h</span></span>
  
> <span data-ttu-id="b3a28-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b3a28-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b3a28-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3a28-127">See also</span></span>



[<span data-ttu-id="b3a28-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b3a28-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b3a28-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3a28-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b3a28-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b3a28-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b3a28-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b3a28-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

