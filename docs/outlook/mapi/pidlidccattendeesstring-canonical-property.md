---
title: PidLidCcAttendeesString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCcAttendeesString
api_type:
- COM
ms.assetid: 697d5c93-ec7f-4608-9866-9e249a093dbc
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bb24d17e478de6b428750efb8d61797c8628b16d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776719"
---
# <a name="pidlidccattendeesstring-canonical-property"></a><span data-ttu-id="ffc62-103">PidLidCcAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="ffc62-103">PidLidCcAttendeesString Canonical Property</span></span>

  
  
<span data-ttu-id="ffc62-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ffc62-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ffc62-105">包含的所有也是可选的与会者可发送与会者的列表。</span><span class="sxs-lookup"><span data-stu-id="ffc62-105">Contains a list of all the sendable attendees who are also optional attendees.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ffc62-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ffc62-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ffc62-107">dispidCCAttendeesString</span><span class="sxs-lookup"><span data-stu-id="ffc62-107">dispidCCAttendeesString</span></span>  <br/> |
|<span data-ttu-id="ffc62-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ffc62-108">Property set:</span></span>  <br/> |<span data-ttu-id="ffc62-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="ffc62-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="ffc62-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ffc62-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ffc62-111">0x0000823C</span><span class="sxs-lookup"><span data-stu-id="ffc62-111">0x0000823C</span></span>  <br/> |
|<span data-ttu-id="ffc62-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ffc62-112">Data type:</span></span>  <br/> |<span data-ttu-id="ffc62-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ffc62-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ffc62-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ffc62-114">Area:</span></span>  <br/> |<span data-ttu-id="ffc62-115">会议</span><span class="sxs-lookup"><span data-stu-id="ffc62-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ffc62-116">备注</span><span class="sxs-lookup"><span data-stu-id="ffc62-116">Remarks</span></span>

<span data-ttu-id="ffc62-117">每个与会者的值是与会者的通讯簿的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ffc62-117">The value for each attendee is the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of the attendee's address book.</span></span> <span data-ttu-id="ffc62-118">单独的条目必须用分号跟一个空格分隔。</span><span class="sxs-lookup"><span data-stu-id="ffc62-118">Separate entries must be delimited by a semicolon followed by a space.</span></span> <span data-ttu-id="ffc62-119">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="ffc62-119">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ffc62-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="ffc62-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ffc62-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="ffc62-121">Protocol specifications</span></span>

<span data-ttu-id="ffc62-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ffc62-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ffc62-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ffc62-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ffc62-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ffc62-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ffc62-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="ffc62-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="ffc62-126">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ffc62-126">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ffc62-127">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="ffc62-127">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ffc62-128">头文件</span><span class="sxs-lookup"><span data-stu-id="ffc62-128">Header files</span></span>

<span data-ttu-id="ffc62-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ffc62-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="ffc62-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ffc62-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ffc62-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffc62-131">See also</span></span>



[<span data-ttu-id="ffc62-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ffc62-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ffc62-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ffc62-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ffc62-134">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ffc62-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ffc62-135">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ffc62-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

