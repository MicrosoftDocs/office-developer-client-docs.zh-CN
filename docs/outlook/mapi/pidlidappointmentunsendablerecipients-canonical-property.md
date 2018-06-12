---
title: PidLidAppointmentUnsendableRecipients 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidLidAppointmentUnsendableRecipients
api_type:
- COM
ms.assetid: ba154612-1b0f-4ef3-8d9f-7981b1c61a2c
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: dc273e757f173515e8c49827c1a55aa04e1faaf0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776712"
---
# <a name="pidlidappointmentunsendablerecipients-canonical-property"></a><span data-ttu-id="b2cd9-103">PidLidAppointmentUnsendableRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="b2cd9-103">PidLidAppointmentUnsendableRecipients Canonical Property</span></span>

  
  
<span data-ttu-id="b2cd9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b2cd9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b2cd9-105">包含不可发送与会者列表。</span><span class="sxs-lookup"><span data-stu-id="b2cd9-105">Contains a list of unsendable attendees.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b2cd9-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="b2cd9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b2cd9-107">dispidApptUnsendableRecips</span><span class="sxs-lookup"><span data-stu-id="b2cd9-107">dispidApptUnsendableRecips</span></span>  <br/> |
|<span data-ttu-id="b2cd9-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b2cd9-108">Property set:</span></span>  <br/> |<span data-ttu-id="b2cd9-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="b2cd9-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="b2cd9-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b2cd9-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b2cd9-111">0x0000823D</span><span class="sxs-lookup"><span data-stu-id="b2cd9-111">0x0000823D</span></span>  <br/> |
|<span data-ttu-id="b2cd9-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b2cd9-112">Data type:</span></span>  <br/> |<span data-ttu-id="b2cd9-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b2cd9-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b2cd9-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b2cd9-114">Area:</span></span>  <br/> |<span data-ttu-id="b2cd9-115">会议</span><span class="sxs-lookup"><span data-stu-id="b2cd9-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b2cd9-116">备注</span><span class="sxs-lookup"><span data-stu-id="b2cd9-116">Remarks</span></span>

<span data-ttu-id="b2cd9-117">此属性，则不需要，但应设置。</span><span class="sxs-lookup"><span data-stu-id="b2cd9-117">This property is not required but should be set.</span></span> <span data-ttu-id="b2cd9-118">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中详细说明了其格式。</span><span class="sxs-lookup"><span data-stu-id="b2cd9-118">Its format is detailed in [[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b2cd9-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="b2cd9-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b2cd9-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="b2cd9-120">Protocol specifications</span></span>

<span data-ttu-id="b2cd9-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b2cd9-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b2cd9-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b2cd9-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b2cd9-123">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b2cd9-123">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b2cd9-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="b2cd9-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b2cd9-125">头文件</span><span class="sxs-lookup"><span data-stu-id="b2cd9-125">Header files</span></span>

<span data-ttu-id="b2cd9-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b2cd9-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="b2cd9-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b2cd9-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b2cd9-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2cd9-128">See also</span></span>



[<span data-ttu-id="b2cd9-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b2cd9-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b2cd9-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b2cd9-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b2cd9-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b2cd9-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b2cd9-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b2cd9-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

