---
title: PidLidAllAttendeesString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAllAttendeesString
api_type:
- COM
ms.assetid: 2ffc0609-341d-4e35-8f53-ed3096c6fa7f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 11b4ea96283bbef2dcb9afb109a6a81102727efc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570455"
---
# <a name="pidlidallattendeesstring-canonical-property"></a><span data-ttu-id="b1955-103">PidLidAllAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="b1955-103">PidLidAllAttendeesString Canonical Property</span></span>

  
  
<span data-ttu-id="b1955-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b1955-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b1955-105">指定除组织者，包括资源和不可发送与会者之外的所有与会者的列表。</span><span class="sxs-lookup"><span data-stu-id="b1955-105">Specifies a list of all the attendees except for the organizer, including resources and unsendable attendees.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b1955-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b1955-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b1955-107">dispidAllAttendeesString</span><span class="sxs-lookup"><span data-stu-id="b1955-107">dispidAllAttendeesString</span></span>  <br/> |
|<span data-ttu-id="b1955-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b1955-108">Property set:</span></span>  <br/> |<span data-ttu-id="b1955-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="b1955-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="b1955-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b1955-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b1955-111">0x00008238</span><span class="sxs-lookup"><span data-stu-id="b1955-111">0x00008238</span></span>  <br/> |
|<span data-ttu-id="b1955-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b1955-112">Data type:</span></span>  <br/> |<span data-ttu-id="b1955-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b1955-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b1955-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b1955-114">Area:</span></span>  <br/> |<span data-ttu-id="b1955-115">会议</span><span class="sxs-lookup"><span data-stu-id="b1955-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b1955-116">注解</span><span class="sxs-lookup"><span data-stu-id="b1955-116">Remarks</span></span>

<span data-ttu-id="b1955-117">每个与会者的值是与会者的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b1955-117">The value for each attendee is the attendee's display name.</span></span> <span data-ttu-id="b1955-118">单独的条目必须用分号跟一个空格分隔。</span><span class="sxs-lookup"><span data-stu-id="b1955-118">Separate entries must be delimited by a semicolon followed by a space.</span></span> <span data-ttu-id="b1955-119">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="b1955-119">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b1955-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="b1955-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b1955-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="b1955-121">Protocol specifications</span></span>

<span data-ttu-id="b1955-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b1955-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b1955-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b1955-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b1955-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b1955-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b1955-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="b1955-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b1955-126">头文件</span><span class="sxs-lookup"><span data-stu-id="b1955-126">Header files</span></span>

<span data-ttu-id="b1955-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b1955-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="b1955-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b1955-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b1955-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1955-129">See also</span></span>



[<span data-ttu-id="b1955-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b1955-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b1955-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b1955-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b1955-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b1955-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b1955-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b1955-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

