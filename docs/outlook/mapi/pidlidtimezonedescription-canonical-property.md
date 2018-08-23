---
title: PidLidTimeZoneDescription 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTimeZoneDescription
api_type:
- COM
ms.assetid: 24cb6429-1276-45f1-be0e-6c9d2ff6ce19
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f025d54632fdb88a846f978b38a476355395b61
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563371"
---
# <a name="pidlidtimezonedescription-canonical-property"></a><span data-ttu-id="829c7-103">PidLidTimeZoneDescription 规范属性</span><span class="sxs-lookup"><span data-stu-id="829c7-103">PidLidTimeZoneDescription Canonical Property</span></span>

  
  
<span data-ttu-id="829c7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="829c7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="829c7-105">指定时区的字符串的说明。</span><span class="sxs-lookup"><span data-stu-id="829c7-105">Specifies a string description of the time zone.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="829c7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="829c7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="829c7-107">dispidTimeZoneDesc</span><span class="sxs-lookup"><span data-stu-id="829c7-107">dispidTimeZoneDesc</span></span>  <br/> |
|<span data-ttu-id="829c7-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="829c7-108">Property set:</span></span>  <br/> |<span data-ttu-id="829c7-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="829c7-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="829c7-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="829c7-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="829c7-111">0x00008234</span><span class="sxs-lookup"><span data-stu-id="829c7-111">0x00008234</span></span>  <br/> |
|<span data-ttu-id="829c7-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="829c7-112">Data type:</span></span>  <br/> |<span data-ttu-id="829c7-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="829c7-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="829c7-114">区域：</span><span class="sxs-lookup"><span data-stu-id="829c7-114">Area:</span></span>  <br/> |<span data-ttu-id="829c7-115">日历</span><span class="sxs-lookup"><span data-stu-id="829c7-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="829c7-116">注解</span><span class="sxs-lookup"><span data-stu-id="829c7-116">Remarks</span></span>

<span data-ttu-id="829c7-117">此属性指定的可读的时区表示**dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) 属性中的数据的说明。</span><span class="sxs-lookup"><span data-stu-id="829c7-117">This property specifies a human-readable description of the time zone that is represented by the data in the **dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="829c7-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="829c7-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="829c7-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="829c7-119">Protocol specifications</span></span>

<span data-ttu-id="829c7-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="829c7-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="829c7-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="829c7-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="829c7-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="829c7-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="829c7-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="829c7-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="829c7-124">头文件</span><span class="sxs-lookup"><span data-stu-id="829c7-124">Header files</span></span>

<span data-ttu-id="829c7-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="829c7-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="829c7-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="829c7-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="829c7-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="829c7-127">See also</span></span>



[<span data-ttu-id="829c7-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="829c7-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="829c7-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="829c7-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="829c7-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="829c7-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="829c7-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="829c7-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

