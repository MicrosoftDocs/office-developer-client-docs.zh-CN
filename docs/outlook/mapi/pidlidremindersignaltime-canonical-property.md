---
title: PidLidReminderSignalTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidReminderSignalTime
api_type:
- COM
ms.assetid: 58f6432e-6e88-420b-959f-7f365899f7eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3fcfd00f71a308dce625e6636edbe647f3d7258a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393388"
---
# <a name="pidlidremindersignaltime-canonical-property"></a><span data-ttu-id="2e5be-103">PidLidReminderSignalTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e5be-103">PidLidReminderSignalTime Canonical Property</span></span>

  
  
<span data-ttu-id="2e5be-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e5be-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e5be-105">指定当提醒从过渡挂起到过期时间点。</span><span class="sxs-lookup"><span data-stu-id="2e5be-105">Specifies the point in time when a reminder transitions from pending to overdue.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2e5be-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2e5be-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2e5be-107">dispidReminderNextTime</span><span class="sxs-lookup"><span data-stu-id="2e5be-107">dispidReminderNextTime</span></span>  <br/> |
|<span data-ttu-id="2e5be-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="2e5be-108">Property set:</span></span>  <br/> |<span data-ttu-id="2e5be-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="2e5be-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="2e5be-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="2e5be-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2e5be-111">0x00008560</span><span class="sxs-lookup"><span data-stu-id="2e5be-111">0x00008560</span></span>  <br/> |
|<span data-ttu-id="2e5be-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2e5be-112">Data type:</span></span>  <br/> |<span data-ttu-id="2e5be-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="2e5be-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="2e5be-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2e5be-114">Area:</span></span>  <br/> |<span data-ttu-id="2e5be-115">Reminder</span><span class="sxs-lookup"><span data-stu-id="2e5be-115">Reminder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2e5be-116">说明</span><span class="sxs-lookup"><span data-stu-id="2e5be-116">Remarks</span></span>

<span data-ttu-id="2e5be-117">如果**dispidReminderSet** ([PidLidReminderSet](pidlidreminderset-canonical-property.md)) 属性为 TRUE，则必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="2e5be-117">This property must be set if the **dispidReminderSet** ([PidLidReminderSet](pidlidreminderset-canonical-property.md)) property is TRUE.</span></span> <span data-ttu-id="2e5be-118">客户端必须设置的值以协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="2e5be-118">Clients must set the value in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2e5be-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="2e5be-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2e5be-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="2e5be-120">Protocol specifications</span></span>

<span data-ttu-id="2e5be-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e5be-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e5be-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2e5be-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2e5be-123">[[MS OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e5be-123">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e5be-124">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="2e5be-124">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2e5be-125">头文件</span><span class="sxs-lookup"><span data-stu-id="2e5be-125">Header files</span></span>

<span data-ttu-id="2e5be-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2e5be-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="2e5be-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2e5be-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2e5be-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e5be-128">See also</span></span>



[<span data-ttu-id="2e5be-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2e5be-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2e5be-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e5be-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2e5be-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2e5be-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2e5be-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2e5be-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

