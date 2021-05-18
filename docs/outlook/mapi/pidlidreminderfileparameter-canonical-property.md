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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360099"
---
# <a name="pidlidreminderfileparameter-canonical-property"></a><span data-ttu-id="5d125-103">PidLidReminderFileParameter 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d125-103">PidLidReminderFileParameter Canonical Property</span></span>

  
  
<span data-ttu-id="5d125-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d125-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d125-105">指定客户端在该对象的提醒过期时应播放的声音的文件名。</span><span class="sxs-lookup"><span data-stu-id="5d125-105">Specifies the filename of the sound that a client should play when the reminder for that object becomes overdue.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5d125-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5d125-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5d125-107">dispidReminderFileParam</span><span class="sxs-lookup"><span data-stu-id="5d125-107">dispidReminderFileParam</span></span>  <br/> |
|<span data-ttu-id="5d125-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="5d125-108">Property set:</span></span>  <br/> |<span data-ttu-id="5d125-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="5d125-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="5d125-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="5d125-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="5d125-111">0x0000851F</span><span class="sxs-lookup"><span data-stu-id="5d125-111">0x0000851F</span></span>  <br/> |
|<span data-ttu-id="5d125-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5d125-112">Data type:</span></span>  <br/> |<span data-ttu-id="5d125-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5d125-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="5d125-114">区域：</span><span class="sxs-lookup"><span data-stu-id="5d125-114">Area:</span></span>  <br/> |<span data-ttu-id="5d125-115">Reminder</span><span class="sxs-lookup"><span data-stu-id="5d125-115">Reminder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5d125-116">备注</span><span class="sxs-lookup"><span data-stu-id="5d125-116">Remarks</span></span>

<span data-ttu-id="5d125-117">如果此属性不存在，客户端可能会使用默认值。</span><span class="sxs-lookup"><span data-stu-id="5d125-117">If this property is not present, the client may use a default value.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5d125-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="5d125-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5d125-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="5d125-119">Protocol specifications</span></span>

<span data-ttu-id="5d125-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d125-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5d125-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="5d125-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5d125-122">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d125-122">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5d125-123">指定电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="5d125-123">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5d125-124">头文件</span><span class="sxs-lookup"><span data-stu-id="5d125-124">Header files</span></span>

<span data-ttu-id="5d125-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5d125-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="5d125-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5d125-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5d125-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d125-127">See also</span></span>



[<span data-ttu-id="5d125-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5d125-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5d125-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d125-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5d125-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5d125-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5d125-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5d125-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

