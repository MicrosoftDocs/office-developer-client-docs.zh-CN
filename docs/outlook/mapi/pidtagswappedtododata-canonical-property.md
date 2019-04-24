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
ms.openlocfilehash: 3ecfa1e89688ae525a28e221424fb4a8194fc217
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359134"
---
# <a name="pidtagswappedtododata-canonical-property"></a><span data-ttu-id="31dcc-103">PidTagSwappedToDoData 规范属性</span><span class="sxs-lookup"><span data-stu-id="31dcc-103">PidTagSwappedToDoData Canonical Property</span></span>

  
  
<span data-ttu-id="31dcc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="31dcc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="31dcc-105">维护不影响邮件对象的标记状态的第二组属性值。</span><span class="sxs-lookup"><span data-stu-id="31dcc-105">Maintains a second set of property values that do not affect the flagged state of the Message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="31dcc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="31dcc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="31dcc-107">PR_SWAPPED_TODO_DATA</span><span class="sxs-lookup"><span data-stu-id="31dcc-107">PR_SWAPPED_TODO_DATA</span></span>  <br/> |
|<span data-ttu-id="31dcc-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="31dcc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="31dcc-109">0x0E2D</span><span class="sxs-lookup"><span data-stu-id="31dcc-109">0x0E2D</span></span>  <br/> |
|<span data-ttu-id="31dcc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="31dcc-110">Data type:</span></span>  <br/> |<span data-ttu-id="31dcc-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="31dcc-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="31dcc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="31dcc-112">Area:</span></span>  <br/> |<span data-ttu-id="31dcc-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="31dcc-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="31dcc-114">注解</span><span class="sxs-lookup"><span data-stu-id="31dcc-114">Remarks</span></span>

<span data-ttu-id="31dcc-115">充当辅助标志存储位置如果支持发件人标志或发件人标志, 则此结构将提供一个位置, 以在其中存储与发件人标志中支持的信息标记协议相关的所有属性, 以及所有与发件人提醒中支持的提醒设置协议相关的属性, 而不会将发件人标志或发件人提醒信息暴露给邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="31dcc-115">Acting as the secondary flag storage location if sender flags or sender reminders are supported, this structure provides a location in which to store all of the properties relating to the Informational Flagging Protocol that are supported in sender flags, and all properties relating to the Reminder Settings Protocol that are supported in sender reminders without exposing the sender flag or sender reminder information to the recipients of a message.</span></span>
  
<span data-ttu-id="31dcc-116">同样, 此结构还提供一个位置, 以存储与收件人中支持的提醒设置协议相关的收件人标志和属性中所支持的信息标记协议相关的所有属性。有关以前发送的邮件的提醒。</span><span class="sxs-lookup"><span data-stu-id="31dcc-116">Similarly, this structure provides a location in which to store all of the properties relating to the Informational Flagging Protocol that are supported in recipient flags and properties relating to the Reminder Settings Protocol that are supported in recipient reminders on a previously sent message.</span></span>
  
<span data-ttu-id="31dcc-117">有关此属性的详细信息, 请参阅[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="31dcc-117">For more information about this property, see [[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="31dcc-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="31dcc-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="31dcc-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="31dcc-119">Protocol specifications</span></span>

<span data-ttu-id="31dcc-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31dcc-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31dcc-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="31dcc-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="31dcc-122">[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31dcc-122">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31dcc-123">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="31dcc-123">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="31dcc-124">[[毫秒-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31dcc-124">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31dcc-125">指定用于电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="31dcc-125">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="31dcc-126">头文件</span><span class="sxs-lookup"><span data-stu-id="31dcc-126">Header files</span></span>

<span data-ttu-id="31dcc-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="31dcc-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="31dcc-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="31dcc-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="31dcc-129">Mapitags</span><span class="sxs-lookup"><span data-stu-id="31dcc-129">Mapitags.h</span></span>
  
> <span data-ttu-id="31dcc-130">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="31dcc-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="31dcc-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31dcc-131">See also</span></span>



[<span data-ttu-id="31dcc-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="31dcc-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="31dcc-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="31dcc-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="31dcc-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="31dcc-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="31dcc-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="31dcc-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

