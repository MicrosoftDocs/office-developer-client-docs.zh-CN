---
title: PidTagFlagCompleteTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFlagCompleteTime
api_type:
- HeaderDef
ms.assetid: effc738a-30f4-4a5e-b21d-04b50dad1f45
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5dd0d4c19f30e189218b1aeddd333df58e42102a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316287"
---
# <a name="pidtagflagcompletetime-canonical-property"></a><span data-ttu-id="82aff-103">PidTagFlagCompleteTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="82aff-103">PidTagFlagCompleteTime Canonical Property</span></span>

  
  
<span data-ttu-id="82aff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82aff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82aff-105">指定邮件对象标记为已完成 (UTC) 协调世界时日期和时间。</span><span class="sxs-lookup"><span data-stu-id="82aff-105">Specifies the date and time in Coordinated Universal Time (UTC) that the message object was flagged as completed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="82aff-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="82aff-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="82aff-107">PR_FLAG_COMPLETE_TIME</span><span class="sxs-lookup"><span data-stu-id="82aff-107">PR_FLAG_COMPLETE_TIME</span></span>  <br/> |
|<span data-ttu-id="82aff-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="82aff-108">Identifier:</span></span>  <br/> |<span data-ttu-id="82aff-109">0x1091</span><span class="sxs-lookup"><span data-stu-id="82aff-109">0x1091</span></span>  <br/> |
|<span data-ttu-id="82aff-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="82aff-110">Data type:</span></span>  <br/> |<span data-ttu-id="82aff-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="82aff-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="82aff-112">区域：</span><span class="sxs-lookup"><span data-stu-id="82aff-112">Area:</span></span>  <br/> |<span data-ttu-id="82aff-113">其他</span><span class="sxs-lookup"><span data-stu-id="82aff-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="82aff-114">备注</span><span class="sxs-lookup"><span data-stu-id="82aff-114">Remarks</span></span>

<span data-ttu-id="82aff-115">如果邮件对象未标记为完成，则删除此属性。</span><span class="sxs-lookup"><span data-stu-id="82aff-115">This property is deleted if the message object is not flagged complete.</span></span> <span data-ttu-id="82aff-116">时间最短的分辨率必须为分钟数 (该值必须是 600，000，000 的倍数) 。</span><span class="sxs-lookup"><span data-stu-id="82aff-116">The time's smallest resolution must be minutes (the value must be a multiple of 600,000,000).</span></span> <span data-ttu-id="82aff-117">如果对象是会议相关的对象，则此属性不能存在，并且不应存在于任务对象上。</span><span class="sxs-lookup"><span data-stu-id="82aff-117">This property must not exist if the object is a meeting-related object, and it should not exist on a task object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="82aff-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="82aff-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="82aff-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="82aff-119">Protocol specifications</span></span>

<span data-ttu-id="82aff-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="82aff-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="82aff-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="82aff-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="82aff-122">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="82aff-122">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="82aff-123">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="82aff-123">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="82aff-124">头文件</span><span class="sxs-lookup"><span data-stu-id="82aff-124">Header files</span></span>

<span data-ttu-id="82aff-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="82aff-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="82aff-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="82aff-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="82aff-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="82aff-127">Mapitags.h</span></span>
  
> <span data-ttu-id="82aff-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="82aff-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="82aff-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82aff-129">See also</span></span>



[<span data-ttu-id="82aff-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="82aff-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="82aff-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="82aff-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="82aff-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="82aff-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="82aff-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="82aff-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

