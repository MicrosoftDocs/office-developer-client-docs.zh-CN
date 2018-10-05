---
title: PidLidReminderFileParameter 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidReminderFileParameter
api_type:
- COM
ms.assetid: 1009f0ea-6f35-484d-b04d-5b6e844c14dd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 42eec18c74005e586657482ef6634669c489314d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400381"
---
# <a name="pidlidreminderfileparameter-canonical-property"></a><span data-ttu-id="89e36-103">PidLidReminderFileParameter 规范属性</span><span class="sxs-lookup"><span data-stu-id="89e36-103">PidLidReminderFileParameter Canonical Property</span></span>

  
  
<span data-ttu-id="89e36-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="89e36-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="89e36-105">指定客户端应在该对象的提醒过期时播放的声音的文件名。</span><span class="sxs-lookup"><span data-stu-id="89e36-105">Specifies the filename of the sound that a client should play when the reminder for that object becomes overdue.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="89e36-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="89e36-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="89e36-107">dispidReminderFileParam</span><span class="sxs-lookup"><span data-stu-id="89e36-107">dispidReminderFileParam</span></span>  <br/> |
|<span data-ttu-id="89e36-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="89e36-108">Property set:</span></span>  <br/> |<span data-ttu-id="89e36-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="89e36-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="89e36-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="89e36-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="89e36-111">0x0000851F</span><span class="sxs-lookup"><span data-stu-id="89e36-111">0x0000851F</span></span>  <br/> |
|<span data-ttu-id="89e36-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="89e36-112">Data type:</span></span>  <br/> |<span data-ttu-id="89e36-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="89e36-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="89e36-114">区域：</span><span class="sxs-lookup"><span data-stu-id="89e36-114">Area:</span></span>  <br/> |<span data-ttu-id="89e36-115">Reminder</span><span class="sxs-lookup"><span data-stu-id="89e36-115">Reminder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="89e36-116">说明</span><span class="sxs-lookup"><span data-stu-id="89e36-116">Remarks</span></span>

<span data-ttu-id="89e36-117">如果此属性不存在，则客户端可以使用默认值。</span><span class="sxs-lookup"><span data-stu-id="89e36-117">If this property is not present, the client may use a default value.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="89e36-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="89e36-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="89e36-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="89e36-119">Protocol specifications</span></span>

<span data-ttu-id="89e36-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="89e36-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="89e36-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="89e36-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="89e36-122">[[MS OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="89e36-122">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="89e36-123">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="89e36-123">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="89e36-124">头文件</span><span class="sxs-lookup"><span data-stu-id="89e36-124">Header files</span></span>

<span data-ttu-id="89e36-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="89e36-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="89e36-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="89e36-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="89e36-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89e36-127">See also</span></span>



[<span data-ttu-id="89e36-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="89e36-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="89e36-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="89e36-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="89e36-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="89e36-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="89e36-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="89e36-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

