---
title: PidLidReminderOverride 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidReminderOverride
api_type:
- COM
ms.assetid: ad7e37e1-bd12-409f-87e5-ebc0c298a072
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4956ce33d00135c34193dec3df832c6878b2c6db
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385961"
---
# <a name="pidlidreminderoverride-canonical-property"></a><span data-ttu-id="6995e-103">PidLidReminderOverride 规范属性</span><span class="sxs-lookup"><span data-stu-id="6995e-103">PidLidReminderOverride Canonical Property</span></span>

  
  
<span data-ttu-id="6995e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6995e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6995e-105">指定客户端是否应尊重**dispidReminderPlaySound** ([PidLidReminderPlaySound](pidlidreminderplaysound-canonical-property.md)) 和**dispidReminderFileParam** ( [PidLidReminderFileParameter ](pidlidreminderfileparameter-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="6995e-105">Specifies whether the client should respect the values of the **dispidReminderPlaySound** ([PidLidReminderPlaySound](pidlidreminderplaysound-canonical-property.md)) and **dispidReminderFileParam** ( [ PidLidReminderFileParameter ](pidlidreminderfileparameter-canonical-property.md)) properties.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6995e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6995e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6995e-107">dispidReminderOverride</span><span class="sxs-lookup"><span data-stu-id="6995e-107">dispidReminderOverride</span></span>  <br/> |
|<span data-ttu-id="6995e-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="6995e-108">Property set:</span></span>  <br/> |<span data-ttu-id="6995e-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="6995e-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="6995e-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="6995e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6995e-111">0x0000851C</span><span class="sxs-lookup"><span data-stu-id="6995e-111">0x0000851C</span></span>  <br/> |
|<span data-ttu-id="6995e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6995e-112">Data type:</span></span>  <br/> |<span data-ttu-id="6995e-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="6995e-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="6995e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6995e-114">Area:</span></span>  <br/> |<span data-ttu-id="6995e-115">Reminder</span><span class="sxs-lookup"><span data-stu-id="6995e-115">Reminder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6995e-116">说明</span><span class="sxs-lookup"><span data-stu-id="6995e-116">Remarks</span></span>

<span data-ttu-id="6995e-117">客户端可以使用默认值来代替**dispidReminderPlaySound**和**dispidReminderFileParam**属性的值。</span><span class="sxs-lookup"><span data-stu-id="6995e-117">A client may use default values in place of the values of the **dispidReminderPlaySound** and **dispidReminderFileParam** properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6995e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="6995e-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6995e-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="6995e-119">Protocol specifications</span></span>

<span data-ttu-id="6995e-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6995e-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6995e-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6995e-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6995e-122">[[MS OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6995e-122">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6995e-123">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="6995e-123">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6995e-124">头文件</span><span class="sxs-lookup"><span data-stu-id="6995e-124">Header files</span></span>

<span data-ttu-id="6995e-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6995e-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="6995e-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6995e-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6995e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6995e-127">See also</span></span>



[<span data-ttu-id="6995e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6995e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6995e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6995e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6995e-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6995e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6995e-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6995e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
