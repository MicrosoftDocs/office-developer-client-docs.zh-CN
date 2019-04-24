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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f6707c49c70804aeb757119aa411ca4059e378eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356040"
---
# <a name="pidlidappointmentreplyname-canonical-property"></a><span data-ttu-id="486a2-103">PidLidAppointmentReplyName 规范属性</span><span class="sxs-lookup"><span data-stu-id="486a2-103">PidLidAppointmentReplyName Canonical Property</span></span>

  
  
<span data-ttu-id="486a2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="486a2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="486a2-105">指定上次答复会议请求或会议更新对象的用户。</span><span class="sxs-lookup"><span data-stu-id="486a2-105">Specifies the user who last replied to the meeting request or meeting update object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="486a2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="486a2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="486a2-107">dispidApptReplyName</span><span class="sxs-lookup"><span data-stu-id="486a2-107">dispidApptReplyName</span></span>  <br/> |
|<span data-ttu-id="486a2-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="486a2-108">Property set:</span></span>  <br/> |<span data-ttu-id="486a2-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="486a2-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="486a2-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="486a2-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="486a2-111">0x00008230</span><span class="sxs-lookup"><span data-stu-id="486a2-111">0x00008230</span></span>  <br/> |
|<span data-ttu-id="486a2-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="486a2-112">Data type:</span></span>  <br/> |<span data-ttu-id="486a2-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="486a2-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="486a2-114">区域：</span><span class="sxs-lookup"><span data-stu-id="486a2-114">Area:</span></span>  <br/> |<span data-ttu-id="486a2-115">会议</span><span class="sxs-lookup"><span data-stu-id="486a2-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="486a2-116">注解</span><span class="sxs-lookup"><span data-stu-id="486a2-116">Remarks</span></span>

<span data-ttu-id="486a2-117">此属性仅在代理响应时设置为代理者。</span><span class="sxs-lookup"><span data-stu-id="486a2-117">This property is only set for a delegator when a delegate responded.</span></span> <span data-ttu-id="486a2-118">值等于委托的存储区的**PR_MAILBOX_OWNER_NAME** ([PidTagMailboxOwnerName](pidtagmailboxownername-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="486a2-118">The value is equal to the **PR_MAILBOX_OWNER_NAME** ([PidTagMailboxOwnerName](pidtagmailboxownername-canonical-property.md)) property for the delegate's store.</span></span> <span data-ttu-id="486a2-119">此属性对组织器没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="486a2-119">This property has no meaning for the organizer.</span></span> <span data-ttu-id="486a2-120">有关**PR_MAILBOX_OWNER_NAME**的详细信息, 请参阅存储对象协议 (在[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)中指定)。</span><span class="sxs-lookup"><span data-stu-id="486a2-120">For details on **PR_MAILBOX_OWNER_NAME**, see store object protocol specified in [[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="486a2-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="486a2-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="486a2-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="486a2-122">Protocol specifications</span></span>

<span data-ttu-id="486a2-123">[[毫秒-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="486a2-123">[[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="486a2-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="486a2-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="486a2-125">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="486a2-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="486a2-126">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="486a2-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="486a2-127">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="486a2-127">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="486a2-128">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="486a2-128">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="486a2-129">头文件</span><span class="sxs-lookup"><span data-stu-id="486a2-129">Header files</span></span>

<span data-ttu-id="486a2-130">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="486a2-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="486a2-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="486a2-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="486a2-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="486a2-132">See also</span></span>



[<span data-ttu-id="486a2-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="486a2-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="486a2-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="486a2-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="486a2-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="486a2-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="486a2-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="486a2-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

