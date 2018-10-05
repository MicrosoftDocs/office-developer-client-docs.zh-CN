---
title: PidLidForwardInstance 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidForwardInstance
api_type:
- COM
ms.assetid: 055bdcaf-5002-44a6-b2b6-87244b2bea93
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 585e1a5400965288aa4a4c321888a570270021c8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394774"
---
# <a name="pidlidforwardinstance-canonical-property"></a><span data-ttu-id="7cfd2-103">PidLidForwardInstance 规范属性</span><span class="sxs-lookup"><span data-stu-id="7cfd2-103">PidLidForwardInstance Canonical Property</span></span>

  
  
<span data-ttu-id="7cfd2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7cfd2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7cfd2-105">指示会议请求中表示的异常定期系列，并且它已转发 （即使是在由组织者转发） 而不是由组织者发送的邀请。</span><span class="sxs-lookup"><span data-stu-id="7cfd2-105">Indicates that the meeting request represents an exception to a recurring series, and it was forwarded (even when forwarded by the organizer) rather than being an invitation sent by the organizer.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7cfd2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7cfd2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7cfd2-107">dispidFwrdInstance</span><span class="sxs-lookup"><span data-stu-id="7cfd2-107">dispidFwrdInstance</span></span>  <br/> |
|<span data-ttu-id="7cfd2-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="7cfd2-108">Property set:</span></span>  <br/> |<span data-ttu-id="7cfd2-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="7cfd2-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="7cfd2-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="7cfd2-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7cfd2-111">0x0000820A</span><span class="sxs-lookup"><span data-stu-id="7cfd2-111">0x0000820A</span></span>  <br/> |
|<span data-ttu-id="7cfd2-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7cfd2-112">Data type:</span></span>  <br/> |<span data-ttu-id="7cfd2-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="7cfd2-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="7cfd2-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7cfd2-114">Area:</span></span>  <br/> |<span data-ttu-id="7cfd2-115">会议</span><span class="sxs-lookup"><span data-stu-id="7cfd2-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7cfd2-116">说明</span><span class="sxs-lookup"><span data-stu-id="7cfd2-116">Remarks</span></span>

<span data-ttu-id="7cfd2-117">此属性为 FALSE 的值指示会议请求不是转发的实例。</span><span class="sxs-lookup"><span data-stu-id="7cfd2-117">A value of FALSE for this property indicates that the meeting request is not a forwarded instance.</span></span> <span data-ttu-id="7cfd2-118">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="7cfd2-118">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7cfd2-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="7cfd2-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7cfd2-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="7cfd2-120">Protocol specifications</span></span>

<span data-ttu-id="7cfd2-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7cfd2-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7cfd2-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7cfd2-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7cfd2-123">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7cfd2-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7cfd2-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="7cfd2-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7cfd2-125">头文件</span><span class="sxs-lookup"><span data-stu-id="7cfd2-125">Header files</span></span>

<span data-ttu-id="7cfd2-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7cfd2-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="7cfd2-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7cfd2-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7cfd2-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cfd2-128">See also</span></span>



[<span data-ttu-id="7cfd2-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7cfd2-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7cfd2-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7cfd2-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7cfd2-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7cfd2-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7cfd2-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7cfd2-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

