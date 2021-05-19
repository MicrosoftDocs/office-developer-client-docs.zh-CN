---
title: PidLidIntendedBusyStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidIntendedBusyStatus
api_type:
- COM
ms.assetid: 84221dd3-de71-4c10-abd7-9f15aefd02ed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f64ff019212065efd651fd2562c48519b0c7c2d0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332968"
---
# <a name="pidlidintendedbusystatus-canonical-property"></a><span data-ttu-id="35880-103">PidLidIntendedBusyStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="35880-103">PidLidIntendedBusyStatus Canonical Property</span></span>

  
  
<span data-ttu-id="35880-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="35880-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="35880-105">发送会议请求或会议更新时 (组织者日历中会议上的 **dispidBusyStatus** ([PidLidBusyStatus](pidlidbusystatus-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="35880-105">Specifies the value of the **dispidBusyStatus** ([PidLidBusyStatus](pidlidbusystatus-canonical-property.md)) property on the meeting in the organizer's calendar when the meeting request or meeting update was sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="35880-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="35880-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="35880-107">dispidIntendedBusyStatus</span><span class="sxs-lookup"><span data-stu-id="35880-107">dispidIntendedBusyStatus</span></span>  <br/> |
|<span data-ttu-id="35880-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="35880-108">Property set:</span></span>  <br/> |<span data-ttu-id="35880-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="35880-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="35880-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="35880-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="35880-111">0x00008224</span><span class="sxs-lookup"><span data-stu-id="35880-111">0x00008224</span></span>  <br/> |
|<span data-ttu-id="35880-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="35880-112">Data type:</span></span>  <br/> |<span data-ttu-id="35880-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="35880-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="35880-114">区域：</span><span class="sxs-lookup"><span data-stu-id="35880-114">Area:</span></span>  <br/> |<span data-ttu-id="35880-115">会议</span><span class="sxs-lookup"><span data-stu-id="35880-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="35880-116">备注</span><span class="sxs-lookup"><span data-stu-id="35880-116">Remarks</span></span>

<span data-ttu-id="35880-117">此属性的允许值与属性 **dispidBusyStatus** 的允许值相同。</span><span class="sxs-lookup"><span data-stu-id="35880-117">The allowable values of this property are the same as those for the property **dispidBusyStatus**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="35880-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="35880-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="35880-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="35880-119">Protocol specifications</span></span>

<span data-ttu-id="35880-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="35880-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="35880-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="35880-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="35880-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="35880-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="35880-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="35880-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="35880-124">头文件</span><span class="sxs-lookup"><span data-stu-id="35880-124">Header files</span></span>

<span data-ttu-id="35880-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="35880-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="35880-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="35880-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="35880-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35880-127">See also</span></span>



[<span data-ttu-id="35880-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="35880-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="35880-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="35880-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="35880-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="35880-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="35880-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="35880-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

