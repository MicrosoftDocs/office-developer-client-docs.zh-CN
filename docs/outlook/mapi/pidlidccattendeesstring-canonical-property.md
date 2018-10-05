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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 12cdbfcc140fb5ea3bb15a2db93f3689923d9390
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386584"
---
# <a name="pidlidccattendeesstring-canonical-property"></a><span data-ttu-id="e0ea0-103">PidLidCcAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0ea0-103">PidLidCcAttendeesString Canonical Property</span></span>

  
  
<span data-ttu-id="e0ea0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e0ea0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e0ea0-105">包含的所有也是可选的与会者可发送与会者的列表。</span><span class="sxs-lookup"><span data-stu-id="e0ea0-105">Contains a list of all the sendable attendees who are also optional attendees.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e0ea0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e0ea0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e0ea0-107">dispidCCAttendeesString</span><span class="sxs-lookup"><span data-stu-id="e0ea0-107">dispidCCAttendeesString</span></span>  <br/> |
|<span data-ttu-id="e0ea0-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="e0ea0-108">Property set:</span></span>  <br/> |<span data-ttu-id="e0ea0-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="e0ea0-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="e0ea0-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="e0ea0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e0ea0-111">0x0000823C</span><span class="sxs-lookup"><span data-stu-id="e0ea0-111">0x0000823C</span></span>  <br/> |
|<span data-ttu-id="e0ea0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e0ea0-112">Data type:</span></span>  <br/> |<span data-ttu-id="e0ea0-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e0ea0-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e0ea0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e0ea0-114">Area:</span></span>  <br/> |<span data-ttu-id="e0ea0-115">会议</span><span class="sxs-lookup"><span data-stu-id="e0ea0-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e0ea0-116">说明</span><span class="sxs-lookup"><span data-stu-id="e0ea0-116">Remarks</span></span>

<span data-ttu-id="e0ea0-117">每个与会者的值是与会者的通讯簿的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e0ea0-117">The value for each attendee is the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of the attendee's address book.</span></span> <span data-ttu-id="e0ea0-118">单独的条目必须用分号跟一个空格分隔。</span><span class="sxs-lookup"><span data-stu-id="e0ea0-118">Separate entries must be delimited by a semicolon followed by a space.</span></span> <span data-ttu-id="e0ea0-119">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="e0ea0-119">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e0ea0-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="e0ea0-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e0ea0-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="e0ea0-121">Protocol specifications</span></span>

<span data-ttu-id="e0ea0-122">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0ea0-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0ea0-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e0ea0-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e0ea0-124">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0ea0-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0ea0-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="e0ea0-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="e0ea0-126">[[MS OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0ea0-126">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0ea0-127">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="e0ea0-127">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e0ea0-128">头文件</span><span class="sxs-lookup"><span data-stu-id="e0ea0-128">Header files</span></span>

<span data-ttu-id="e0ea0-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e0ea0-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="e0ea0-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e0ea0-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e0ea0-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0ea0-131">See also</span></span>



[<span data-ttu-id="e0ea0-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e0ea0-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e0ea0-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0ea0-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e0ea0-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e0ea0-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e0ea0-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e0ea0-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

