---
title: PidLidToAttendeesString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidToAttendeesString
api_type:
- COM
ms.assetid: ca1eedba-c617-4403-8490-315ab75f2edb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 75439fccaf13665c68321cac5d39d0373ca923e1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571092"
---
# <a name="pidlidtoattendeesstring-canonical-property"></a><span data-ttu-id="4f78c-103">PidLidToAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="4f78c-103">PidLidToAttendeesString Canonical Property</span></span>

  
  
<span data-ttu-id="4f78c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f78c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4f78c-105">包含的所有也是必需的与会者可发送与会者的列表。</span><span class="sxs-lookup"><span data-stu-id="4f78c-105">Contains a list of all the sendable attendees who are also required attendees.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4f78c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4f78c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4f78c-107">dispidToAttendeesString</span><span class="sxs-lookup"><span data-stu-id="4f78c-107">dispidToAttendeesString</span></span>  <br/> |
|<span data-ttu-id="4f78c-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="4f78c-108">Property set:</span></span>  <br/> |<span data-ttu-id="4f78c-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="4f78c-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="4f78c-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="4f78c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="4f78c-111">0x0000823B</span><span class="sxs-lookup"><span data-stu-id="4f78c-111">0x0000823B</span></span>  <br/> |
|<span data-ttu-id="4f78c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4f78c-112">Data type:</span></span>  <br/> |<span data-ttu-id="4f78c-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4f78c-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="4f78c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="4f78c-114">Area:</span></span>  <br/> |<span data-ttu-id="4f78c-115">会议</span><span class="sxs-lookup"><span data-stu-id="4f78c-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4f78c-116">注解</span><span class="sxs-lookup"><span data-stu-id="4f78c-116">Remarks</span></span>

<span data-ttu-id="4f78c-117">每个与会者的值是与会者的通讯簿的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="4f78c-117">The value for each attendee is the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of the attendee's Address Book.</span></span> <span data-ttu-id="4f78c-118">单独的条目必须用分号跟一个空格分隔。</span><span class="sxs-lookup"><span data-stu-id="4f78c-118">Separate entries must be delimited by a semicolon followed by a space.</span></span> <span data-ttu-id="4f78c-119">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="4f78c-119">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4f78c-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="4f78c-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4f78c-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="4f78c-121">Protocol specifications</span></span>

<span data-ttu-id="4f78c-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4f78c-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4f78c-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="4f78c-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4f78c-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4f78c-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4f78c-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="4f78c-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4f78c-126">头文件</span><span class="sxs-lookup"><span data-stu-id="4f78c-126">Header files</span></span>

<span data-ttu-id="4f78c-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4f78c-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="4f78c-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4f78c-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4f78c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f78c-129">See also</span></span>



[<span data-ttu-id="4f78c-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4f78c-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4f78c-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4f78c-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4f78c-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4f78c-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4f78c-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4f78c-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

