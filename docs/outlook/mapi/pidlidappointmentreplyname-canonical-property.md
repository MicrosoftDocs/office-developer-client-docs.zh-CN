---
title: PidLidAppointmentReplyName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentReplyName
api_type:
- COM
ms.assetid: 2f3a44d1-600f-412e-bc89-078841db5308
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5b6d88b60f9f5c6a01a92ecc5905f711fbf3ab3e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776644"
---
# <a name="pidlidappointmentreplyname-canonical-property"></a><span data-ttu-id="a7c3e-103">PidLidAppointmentReplyName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7c3e-103">PidLidAppointmentReplyName Canonical Property</span></span>

  
  
<span data-ttu-id="a7c3e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a7c3e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a7c3e-105">指定上次答复会议请求的用户或会议更新对象。</span><span class="sxs-lookup"><span data-stu-id="a7c3e-105">Specifies the user who last replied to the meeting request or meeting update object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a7c3e-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="a7c3e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a7c3e-107">dispidApptReplyName</span><span class="sxs-lookup"><span data-stu-id="a7c3e-107">dispidApptReplyName</span></span>  <br/> |
|<span data-ttu-id="a7c3e-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="a7c3e-108">Property set:</span></span>  <br/> |<span data-ttu-id="a7c3e-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="a7c3e-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="a7c3e-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="a7c3e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a7c3e-111">0x00008230</span><span class="sxs-lookup"><span data-stu-id="a7c3e-111">0x00008230</span></span>  <br/> |
|<span data-ttu-id="a7c3e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a7c3e-112">Data type:</span></span>  <br/> |<span data-ttu-id="a7c3e-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a7c3e-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="a7c3e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="a7c3e-114">Area:</span></span>  <br/> |<span data-ttu-id="a7c3e-115">会议</span><span class="sxs-lookup"><span data-stu-id="a7c3e-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a7c3e-116">备注</span><span class="sxs-lookup"><span data-stu-id="a7c3e-116">Remarks</span></span>

<span data-ttu-id="a7c3e-117">代理人响应时，仅 delegator 设置此属性。</span><span class="sxs-lookup"><span data-stu-id="a7c3e-117">This property is only set for a delegator when a delegate responded.</span></span> <span data-ttu-id="a7c3e-118">值等于代理存储区的**PR_MAILBOX_OWNER_NAME** ([PidTagMailboxOwnerName](pidtagmailboxownername-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a7c3e-118">The value is equal to the **PR_MAILBOX_OWNER_NAME** ([PidTagMailboxOwnerName](pidtagmailboxownername-canonical-property.md)) property for the delegate's store.</span></span> <span data-ttu-id="a7c3e-119">此属性没有任何意义组织者。</span><span class="sxs-lookup"><span data-stu-id="a7c3e-119">This property has no meaning for the organizer.</span></span> <span data-ttu-id="a7c3e-120">有关**PR_MAILBOX_OWNER_NAME**的详细信息，请参阅存储对象[[MS OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)中指定的协议。</span><span class="sxs-lookup"><span data-stu-id="a7c3e-120">For details on **PR_MAILBOX_OWNER_NAME**, see store object protocol specified in [[MS-OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a7c3e-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="a7c3e-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a7c3e-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="a7c3e-122">Protocol specifications</span></span>

<span data-ttu-id="a7c3e-123">[[MS OXCDATA]](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7c3e-123">[[MS-OXCDATA]](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a7c3e-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a7c3e-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="a7c3e-125">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7c3e-125">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a7c3e-126">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="a7c3e-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a7c3e-127">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7c3e-127">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a7c3e-128">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="a7c3e-128">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a7c3e-129">头文件</span><span class="sxs-lookup"><span data-stu-id="a7c3e-129">Header files</span></span>

<span data-ttu-id="a7c3e-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a7c3e-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="a7c3e-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a7c3e-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a7c3e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7c3e-132">See also</span></span>



[<span data-ttu-id="a7c3e-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a7c3e-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a7c3e-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7c3e-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a7c3e-135">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a7c3e-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a7c3e-136">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a7c3e-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

