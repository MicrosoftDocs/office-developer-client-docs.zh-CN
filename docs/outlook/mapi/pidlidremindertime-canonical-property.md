---
title: PidLidReminderTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidReminderTime
api_type:
- COM
ms.assetid: f4068ff0-2aa2-4332-be7d-ecebda30dfff
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6e74dbb1f8e0e64feb2c86eb04e146e201089a4e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777007"
---
# <a name="pidlidremindertime-canonical-property"></a><span data-ttu-id="686f7-103">PidLidReminderTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="686f7-103">PidLidReminderTime Canonical Property</span></span>

  
  
<span data-ttu-id="686f7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="686f7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="686f7-105">指定初始信号时间的提醒。</span><span class="sxs-lookup"><span data-stu-id="686f7-105">Specifies the initial signal time for a reminder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="686f7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="686f7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="686f7-107">dispidReminderTime</span><span class="sxs-lookup"><span data-stu-id="686f7-107">dispidReminderTime</span></span>  <br/> |
|<span data-ttu-id="686f7-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="686f7-108">Property set:</span></span>  <br/> |<span data-ttu-id="686f7-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="686f7-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="686f7-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="686f7-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="686f7-111">0x00008502</span><span class="sxs-lookup"><span data-stu-id="686f7-111">0x00008502</span></span>  <br/> |
|<span data-ttu-id="686f7-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="686f7-112">Data type:</span></span>  <br/> |<span data-ttu-id="686f7-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="686f7-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="686f7-114">区域：</span><span class="sxs-lookup"><span data-stu-id="686f7-114">Area:</span></span>  <br/> |<span data-ttu-id="686f7-115">Reminder</span><span class="sxs-lookup"><span data-stu-id="686f7-115">Reminder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="686f7-116">说明</span><span class="sxs-lookup"><span data-stu-id="686f7-116">Remarks</span></span>

<span data-ttu-id="686f7-117">对于日历对象，此属性表示用户采用延迟的时间这是约会的开始时间。</span><span class="sxs-lookup"><span data-stu-id="686f7-117">For calendar objects, this property represents the time when the user would be late which is the start time of the appointment.</span></span> <span data-ttu-id="686f7-118">客户端必须设置的值以协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="686f7-118">Clients must set the value in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="686f7-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="686f7-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="686f7-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="686f7-120">Protocol specifications</span></span>

<span data-ttu-id="686f7-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="686f7-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="686f7-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="686f7-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="686f7-123">[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="686f7-123">[[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="686f7-124">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="686f7-124">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="686f7-125">头文件</span><span class="sxs-lookup"><span data-stu-id="686f7-125">Header files</span></span>

<span data-ttu-id="686f7-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="686f7-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="686f7-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="686f7-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="686f7-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="686f7-128">See also</span></span>



[<span data-ttu-id="686f7-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="686f7-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="686f7-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="686f7-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="686f7-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="686f7-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="686f7-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="686f7-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

