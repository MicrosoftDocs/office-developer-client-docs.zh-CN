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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4fa7647de7edc6b731b39048777db79b4e193afb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391134"
---
# <a name="pidlidlinkedtaskitems-canonical-property"></a><span data-ttu-id="ae328-103">PidLidLinkedTaskItems 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae328-103">PidLidLinkedTaskItems Canonical Property</span></span>

  
  
<span data-ttu-id="ae328-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ae328-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ae328-105">指定与日历相关的任务的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的列表。</span><span class="sxs-lookup"><span data-stu-id="ae328-105">Specifies a list of the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property of tasks that are related to the calendar.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ae328-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ae328-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ae328-107">dispidLinkedTaskItems</span><span class="sxs-lookup"><span data-stu-id="ae328-107">dispidLinkedTaskItems</span></span>  <br/> |
|<span data-ttu-id="ae328-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ae328-108">Property set:</span></span>  <br/> |<span data-ttu-id="ae328-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="ae328-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="ae328-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ae328-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ae328-111">0x0000820C</span><span class="sxs-lookup"><span data-stu-id="ae328-111">0x0000820C</span></span>  <br/> |
|<span data-ttu-id="ae328-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ae328-112">Data type:</span></span>  <br/> |<span data-ttu-id="ae328-113">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="ae328-113">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="ae328-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ae328-114">Area:</span></span>  <br/> |<span data-ttu-id="ae328-115">Task</span><span class="sxs-lookup"><span data-stu-id="ae328-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ae328-116">说明</span><span class="sxs-lookup"><span data-stu-id="ae328-116">Remarks</span></span>

<span data-ttu-id="ae328-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="ae328-117">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ae328-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="ae328-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ae328-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="ae328-119">Protocol specifications</span></span>

<span data-ttu-id="ae328-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae328-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ae328-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ae328-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ae328-122">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae328-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ae328-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="ae328-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ae328-124">头文件</span><span class="sxs-lookup"><span data-stu-id="ae328-124">Header files</span></span>

<span data-ttu-id="ae328-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ae328-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="ae328-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ae328-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ae328-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae328-127">See also</span></span>



[<span data-ttu-id="ae328-128">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae328-128">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)


[<span data-ttu-id="ae328-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ae328-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ae328-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae328-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ae328-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ae328-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ae328-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ae328-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

