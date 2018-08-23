---
title: PidTagScheduleInfoMonthsMerged 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoMonthsMerged
api_type:
- COM
ms.assetid: b13b5d7b-413e-4405-8a35-0422477a9e86
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6de470a284b91126854a0c1324f5665fd72868ef
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577350"
---
# <a name="pidtagscheduleinfomonthsmerged-canonical-property"></a><span data-ttu-id="d5274-103">PidTagScheduleInfoMonthsMerged 规范属性</span><span class="sxs-lookup"><span data-stu-id="d5274-103">PidTagScheduleInfoMonthsMerged Canonical Property</span></span>

  
  
<span data-ttu-id="d5274-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d5274-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d5274-105">包含的列表的忙/闲忙类型的数据或外出 (oof) 月消息中不存在的忙/闲信息的邮件。</span><span class="sxs-lookup"><span data-stu-id="d5274-105">Contains a list of the months for which free/busy data of type busy or an out of office (OOF) message is present in the free/busy message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d5274-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d5274-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d5274-107">PR_SCHDINFO_MONTHS_MERGED</span><span class="sxs-lookup"><span data-stu-id="d5274-107">PR_SCHDINFO_MONTHS_MERGED</span></span>  <br/> |
|<span data-ttu-id="d5274-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d5274-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d5274-109">0x684F</span><span class="sxs-lookup"><span data-stu-id="d5274-109">0x684F</span></span>  <br/> |
|<span data-ttu-id="d5274-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d5274-110">Data type:</span></span>  <br/> |<span data-ttu-id="d5274-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="d5274-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="d5274-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d5274-112">Area:</span></span>  <br/> |<span data-ttu-id="d5274-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="d5274-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d5274-114">注解</span><span class="sxs-lookup"><span data-stu-id="d5274-114">Remarks</span></span>

<span data-ttu-id="d5274-115">此属性中不包含暂定的忙/闲信息的类型的事件。</span><span class="sxs-lookup"><span data-stu-id="d5274-115">Events of free/busy type tentative are not included in this property.</span></span> <span data-ttu-id="d5274-116">语法/格式和约束此属性是那些**PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) 相同，但引用标记 OOF 或忙碌关联的 calendar 对象的约会。</span><span class="sxs-lookup"><span data-stu-id="d5274-116">The syntax/format and constraints of this property are the same as those of **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) but refer to appointments that are marked OOF or Busy on the associated calendar object.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d5274-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d5274-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d5274-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="d5274-118">Protocol specifications</span></span>

<span data-ttu-id="d5274-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d5274-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d5274-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="d5274-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d5274-121">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d5274-121">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d5274-122">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="d5274-122">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d5274-123">头文件</span><span class="sxs-lookup"><span data-stu-id="d5274-123">Header files</span></span>

<span data-ttu-id="d5274-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d5274-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="d5274-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d5274-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="d5274-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d5274-126">Mapitags.h</span></span>
  
> <span data-ttu-id="d5274-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d5274-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d5274-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5274-128">See also</span></span>



[<span data-ttu-id="d5274-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d5274-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d5274-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d5274-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d5274-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d5274-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d5274-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d5274-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

