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
ms.openlocfilehash: 8371418aabc557f48c74039320305df59624d7ac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358707"
---
# <a name="pidlidremindertime-canonical-property"></a><span data-ttu-id="dae77-103">PidLidReminderTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="dae77-103">PidLidReminderTime Canonical Property</span></span>

  
  
<span data-ttu-id="dae77-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dae77-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dae77-105">指定提醒的初始信号时间。</span><span class="sxs-lookup"><span data-stu-id="dae77-105">Specifies the initial signal time for a reminder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dae77-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dae77-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dae77-107">dispidReminderTime</span><span class="sxs-lookup"><span data-stu-id="dae77-107">dispidReminderTime</span></span>  <br/> |
|<span data-ttu-id="dae77-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="dae77-108">Property set:</span></span>  <br/> |<span data-ttu-id="dae77-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="dae77-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="dae77-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="dae77-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="dae77-111">0x00008502</span><span class="sxs-lookup"><span data-stu-id="dae77-111">0x00008502</span></span>  <br/> |
|<span data-ttu-id="dae77-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dae77-112">Data type:</span></span>  <br/> |<span data-ttu-id="dae77-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="dae77-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="dae77-114">区域：</span><span class="sxs-lookup"><span data-stu-id="dae77-114">Area:</span></span>  <br/> |<span data-ttu-id="dae77-115">提醒</span><span class="sxs-lookup"><span data-stu-id="dae77-115">Reminder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dae77-116">注解</span><span class="sxs-lookup"><span data-stu-id="dae77-116">Remarks</span></span>

<span data-ttu-id="dae77-117">对于 calendar 对象, 此属性表示用户延迟的时间, 即约会的开始时间。</span><span class="sxs-lookup"><span data-stu-id="dae77-117">For calendar objects, this property represents the time when the user would be late which is the start time of the appointment.</span></span> <span data-ttu-id="dae77-118">客户端必须以协调世界时 (UTC) 设置值。</span><span class="sxs-lookup"><span data-stu-id="dae77-118">Clients must set the value in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dae77-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="dae77-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dae77-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="dae77-120">Protocol specifications</span></span>

<span data-ttu-id="dae77-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dae77-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dae77-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="dae77-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dae77-123">[[毫秒-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dae77-123">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dae77-124">指定用于电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="dae77-124">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dae77-125">头文件</span><span class="sxs-lookup"><span data-stu-id="dae77-125">Header files</span></span>

<span data-ttu-id="dae77-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="dae77-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="dae77-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dae77-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dae77-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dae77-128">See also</span></span>



[<span data-ttu-id="dae77-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dae77-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dae77-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dae77-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dae77-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dae77-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dae77-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dae77-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

