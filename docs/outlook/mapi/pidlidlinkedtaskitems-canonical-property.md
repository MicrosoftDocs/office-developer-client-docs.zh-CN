---
title: PidLidLinkedTaskItems 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLinkedTaskItems
api_type:
- COM
ms.assetid: ee735ae8-e527-4538-a633-c3f57a36f0a1
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d91e7ceb877a4f1a7ce10d33e1a25a8773db0547
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776892"
---
# <a name="pidlidlinkedtaskitems-canonical-property"></a><span data-ttu-id="ab164-103">PidLidLinkedTaskItems 规范属性</span><span class="sxs-lookup"><span data-stu-id="ab164-103">PidLidLinkedTaskItems Canonical Property</span></span>

  
  
<span data-ttu-id="ab164-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ab164-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ab164-105">指定与日历相关的任务的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的列表。</span><span class="sxs-lookup"><span data-stu-id="ab164-105">Specifies a list of the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property of tasks that are related to the calendar.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ab164-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ab164-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ab164-107">dispidLinkedTaskItems</span><span class="sxs-lookup"><span data-stu-id="ab164-107">dispidLinkedTaskItems</span></span>  <br/> |
|<span data-ttu-id="ab164-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ab164-108">Property set:</span></span>  <br/> |<span data-ttu-id="ab164-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="ab164-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="ab164-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ab164-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ab164-111">0x0000820C</span><span class="sxs-lookup"><span data-stu-id="ab164-111">0x0000820C</span></span>  <br/> |
|<span data-ttu-id="ab164-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ab164-112">Data type:</span></span>  <br/> |<span data-ttu-id="ab164-113">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="ab164-113">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="ab164-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ab164-114">Area:</span></span>  <br/> |<span data-ttu-id="ab164-115">任务</span><span class="sxs-lookup"><span data-stu-id="ab164-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ab164-116">备注</span><span class="sxs-lookup"><span data-stu-id="ab164-116">Remarks</span></span>

<span data-ttu-id="ab164-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="ab164-117">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ab164-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="ab164-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ab164-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="ab164-119">Protocol specifications</span></span>

<span data-ttu-id="ab164-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab164-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ab164-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ab164-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ab164-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab164-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ab164-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="ab164-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ab164-124">头文件</span><span class="sxs-lookup"><span data-stu-id="ab164-124">Header files</span></span>

<span data-ttu-id="ab164-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ab164-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="ab164-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ab164-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ab164-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab164-127">See also</span></span>



[<span data-ttu-id="ab164-128">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="ab164-128">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)


[<span data-ttu-id="ab164-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ab164-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ab164-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ab164-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ab164-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ab164-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ab164-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ab164-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

