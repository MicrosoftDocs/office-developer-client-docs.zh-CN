---
title: PidTagPriority 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPriority
api_type:
- COM
ms.assetid: 0f3a628f-5f8e-4716-98cc-868bd3400ba9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b9c0f5ebeae21d6d683bbb5def727d29a34bcdb6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385450"
---
# <a name="pidtagpriority-canonical-property"></a><span data-ttu-id="8a446-103">PidTagPriority 规范属性</span><span class="sxs-lookup"><span data-stu-id="8a446-103">PidTagPriority Canonical Property</span></span>

  
  
<span data-ttu-id="8a446-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8a446-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8a446-105">包含一条消息的相对优先级。</span><span class="sxs-lookup"><span data-stu-id="8a446-105">Contains the relative priority of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8a446-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8a446-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8a446-107">PR_PRIORITY</span><span class="sxs-lookup"><span data-stu-id="8a446-107">PR_PRIORITY</span></span>  <br/> |
|<span data-ttu-id="8a446-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8a446-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8a446-109">0x0026</span><span class="sxs-lookup"><span data-stu-id="8a446-109">0x0026</span></span>  <br/> |
|<span data-ttu-id="8a446-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8a446-110">Data type:</span></span>  <br/> |<span data-ttu-id="8a446-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8a446-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8a446-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8a446-112">Area:</span></span>  <br/> |<span data-ttu-id="8a446-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="8a446-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8a446-114">说明</span><span class="sxs-lookup"><span data-stu-id="8a446-114">Remarks</span></span>

<span data-ttu-id="8a446-115">此属性和**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md)) 属性不能混淆。</span><span class="sxs-lookup"><span data-stu-id="8a446-115">This property and the **PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md)) property should not be confused.</span></span> <span data-ttu-id="8a446-116">重要性表示到用户的值，而优先级表示订单设计 サ 频率邮件应发送的消息的系统软件的速度。</span><span class="sxs-lookup"><span data-stu-id="8a446-116">Importance indicates a value to users, while priority indicates the order or speed at which the message should be sent by the messaging system software.</span></span> <span data-ttu-id="8a446-117">更高的优先级通常指示较高的开销。</span><span class="sxs-lookup"><span data-stu-id="8a446-117">Higher priority usually indicates a higher cost.</span></span> <span data-ttu-id="8a446-118">更高重要性通常是与用户界面的不同显示相关联。</span><span class="sxs-lookup"><span data-stu-id="8a446-118">Higher importance usually is associated with a different display by the user interface.</span></span>
  
<span data-ttu-id="8a446-119">报告消息的优先级应与原始邮件报告的优先级相同。</span><span class="sxs-lookup"><span data-stu-id="8a446-119">The priority of a report message should be the same as the priority of the original message being reported.</span></span>
  
<span data-ttu-id="8a446-120">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="8a446-120">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="8a446-121">PRIO_NONURGENT</span><span class="sxs-lookup"><span data-stu-id="8a446-121">PRIO_NONURGENT</span></span> 
  
> <span data-ttu-id="8a446-122">该邮件不紧急。</span><span class="sxs-lookup"><span data-stu-id="8a446-122">The message is not urgent.</span></span>
    
<span data-ttu-id="8a446-123">PRIO_NORMAL</span><span class="sxs-lookup"><span data-stu-id="8a446-123">PRIO_NORMAL</span></span> 
  
> <span data-ttu-id="8a446-124">邮件具有正常优先级。</span><span class="sxs-lookup"><span data-stu-id="8a446-124">The message has normal priority.</span></span>
    
<span data-ttu-id="8a446-125">PRIO_URGENT</span><span class="sxs-lookup"><span data-stu-id="8a446-125">PRIO_URGENT</span></span> 
  
> <span data-ttu-id="8a446-126">紧急邮件。</span><span class="sxs-lookup"><span data-stu-id="8a446-126">The message is urgent.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="8a446-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="8a446-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8a446-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="8a446-128">Protocol specifications</span></span>

<span data-ttu-id="8a446-129">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8a446-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8a446-130">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="8a446-130">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8a446-131">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8a446-131">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8a446-132">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="8a446-132">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8a446-133">头文件</span><span class="sxs-lookup"><span data-stu-id="8a446-133">Header files</span></span>

<span data-ttu-id="8a446-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8a446-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="8a446-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8a446-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="8a446-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8a446-136">Mapitags.h</span></span>
  
> <span data-ttu-id="8a446-137">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8a446-137">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8a446-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a446-138">See also</span></span>



[<span data-ttu-id="8a446-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8a446-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8a446-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8a446-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8a446-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8a446-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8a446-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8a446-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

