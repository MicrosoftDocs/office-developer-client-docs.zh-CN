---
title: PidTagSwappedToDoData 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSwappedToDoData
api_type:
- COM
ms.assetid: d2a82fc8-de5d-4819-906e-b8314fd06ea0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8086bc3ea35fdbb4e0f7758b7931e305259a3a9e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578666"
---
# <a name="pidtagswappedtododata-canonical-property"></a><span data-ttu-id="5784f-103">PidTagSwappedToDoData 规范属性</span><span class="sxs-lookup"><span data-stu-id="5784f-103">PidTagSwappedToDoData Canonical Property</span></span>

  
  
<span data-ttu-id="5784f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5784f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5784f-105">维护第二个组不会影响已标记的状态的消息对象的属性值。</span><span class="sxs-lookup"><span data-stu-id="5784f-105">Maintains a second set of property values that do not affect the flagged state of the Message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5784f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5784f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5784f-107">PR_SWAPPED_TODO_DATA</span><span class="sxs-lookup"><span data-stu-id="5784f-107">PR_SWAPPED_TODO_DATA</span></span>  <br/> |
|<span data-ttu-id="5784f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="5784f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5784f-109">0x0E2D</span><span class="sxs-lookup"><span data-stu-id="5784f-109">0x0E2D</span></span>  <br/> |
|<span data-ttu-id="5784f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5784f-110">Data type:</span></span>  <br/> |<span data-ttu-id="5784f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="5784f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="5784f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5784f-112">Area:</span></span>  <br/> |<span data-ttu-id="5784f-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="5784f-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5784f-114">注解</span><span class="sxs-lookup"><span data-stu-id="5784f-114">Remarks</span></span>

<span data-ttu-id="5784f-115">作为辅助标志存储位置，如果发件人标志或发件人提醒受支持，此结构提供中用来存储的所有发件人标志中支持的信息的标记协议与相关属性和所有的位置属性与提醒设置协议有关支持的发件人提醒而无需公开的标志发件人或收件人的邮件的发件人提醒信息。</span><span class="sxs-lookup"><span data-stu-id="5784f-115">Acting as the secondary flag storage location if sender flags or sender reminders are supported, this structure provides a location in which to store all of the properties relating to the Informational Flagging Protocol that are supported in sender flags, and all properties relating to the Reminder Settings Protocol that are supported in sender reminders without exposing the sender flag or sender reminder information to the recipients of a message.</span></span>
  
<span data-ttu-id="5784f-116">同样，此结构提供中用于存储所有到信息性标记协议有关的属性的受支持的收件人的标志和提醒设置协议与相关的属性的受支持的收件人的位置以前发送的消息的提醒。</span><span class="sxs-lookup"><span data-stu-id="5784f-116">Similarly, this structure provides a location in which to store all of the properties relating to the Informational Flagging Protocol that are supported in recipient flags and properties relating to the Reminder Settings Protocol that are supported in recipient reminders on a previously sent message.</span></span>
  
<span data-ttu-id="5784f-117">有关此属性的详细信息，请参阅[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5784f-117">For more information about this property, see [[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5784f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="5784f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5784f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="5784f-119">Protocol specifications</span></span>

<span data-ttu-id="5784f-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5784f-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5784f-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="5784f-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5784f-122">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5784f-122">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5784f-123">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="5784f-123">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="5784f-124">[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5784f-124">[[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5784f-125">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="5784f-125">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5784f-126">头文件</span><span class="sxs-lookup"><span data-stu-id="5784f-126">Header files</span></span>

<span data-ttu-id="5784f-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5784f-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="5784f-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5784f-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="5784f-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5784f-129">Mapitags.h</span></span>
  
> <span data-ttu-id="5784f-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5784f-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5784f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5784f-131">See also</span></span>



[<span data-ttu-id="5784f-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5784f-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5784f-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5784f-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5784f-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5784f-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5784f-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5784f-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

