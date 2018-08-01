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
ms.openlocfilehash: 67f482e347db1b69a248c542f2cb172c41d6f9f1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778051"
---
# <a name="pidtagpriority-canonical-property"></a><span data-ttu-id="a5476-103">PidTagPriority 规范属性</span><span class="sxs-lookup"><span data-stu-id="a5476-103">PidTagPriority Canonical Property</span></span>

  
  
<span data-ttu-id="a5476-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a5476-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a5476-105">包含一条消息的相对优先级。</span><span class="sxs-lookup"><span data-stu-id="a5476-105">Contains the relative priority of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a5476-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a5476-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a5476-107">PR_PRIORITY</span><span class="sxs-lookup"><span data-stu-id="a5476-107">PR_PRIORITY</span></span>  <br/> |
|<span data-ttu-id="a5476-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="a5476-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a5476-109">0x0026</span><span class="sxs-lookup"><span data-stu-id="a5476-109">0x0026</span></span>  <br/> |
|<span data-ttu-id="a5476-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a5476-110">Data type:</span></span>  <br/> |<span data-ttu-id="a5476-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="a5476-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="a5476-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a5476-112">Area:</span></span>  <br/> |<span data-ttu-id="a5476-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="a5476-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a5476-114">说明</span><span class="sxs-lookup"><span data-stu-id="a5476-114">Remarks</span></span>

<span data-ttu-id="a5476-115">此属性和**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md)) 属性不能混淆。</span><span class="sxs-lookup"><span data-stu-id="a5476-115">This property and the **PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md)) property should not be confused.</span></span> <span data-ttu-id="a5476-116">重要性表示到用户的值，而优先级表示订单设计 サ 频率邮件应发送的消息的系统软件的速度。</span><span class="sxs-lookup"><span data-stu-id="a5476-116">Importance indicates a value to users, while priority indicates the order or speed at which the message should be sent by the messaging system software.</span></span> <span data-ttu-id="a5476-117">更高的优先级通常指示较高的开销。</span><span class="sxs-lookup"><span data-stu-id="a5476-117">Higher priority usually indicates a higher cost.</span></span> <span data-ttu-id="a5476-118">更高重要性通常是与用户界面的不同显示相关联。</span><span class="sxs-lookup"><span data-stu-id="a5476-118">Higher importance usually is associated with a different display by the user interface.</span></span>
  
<span data-ttu-id="a5476-119">报告消息的优先级应与原始邮件报告的优先级相同。</span><span class="sxs-lookup"><span data-stu-id="a5476-119">The priority of a report message should be the same as the priority of the original message being reported.</span></span>
  
<span data-ttu-id="a5476-120">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="a5476-120">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="a5476-121">PRIO_NONURGENT</span><span class="sxs-lookup"><span data-stu-id="a5476-121">PRIO_NONURGENT</span></span> 
  
> <span data-ttu-id="a5476-122">该邮件不紧急。</span><span class="sxs-lookup"><span data-stu-id="a5476-122">The message is not urgent.</span></span>
    
<span data-ttu-id="a5476-123">PRIO_NORMAL</span><span class="sxs-lookup"><span data-stu-id="a5476-123">PRIO_NORMAL</span></span> 
  
> <span data-ttu-id="a5476-124">邮件具有正常优先级。</span><span class="sxs-lookup"><span data-stu-id="a5476-124">The message has normal priority.</span></span>
    
<span data-ttu-id="a5476-125">PRIO_URGENT</span><span class="sxs-lookup"><span data-stu-id="a5476-125">PRIO_URGENT</span></span> 
  
> <span data-ttu-id="a5476-126">紧急邮件。</span><span class="sxs-lookup"><span data-stu-id="a5476-126">The message is urgent.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="a5476-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="a5476-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a5476-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="a5476-128">Protocol specifications</span></span>

<span data-ttu-id="a5476-129">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a5476-129">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a5476-130">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="a5476-130">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a5476-131">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a5476-131">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a5476-132">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="a5476-132">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a5476-133">头文件</span><span class="sxs-lookup"><span data-stu-id="a5476-133">Header files</span></span>

<span data-ttu-id="a5476-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a5476-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="a5476-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a5476-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="a5476-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a5476-136">Mapitags.h</span></span>
  
> <span data-ttu-id="a5476-137">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a5476-137">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a5476-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5476-138">See also</span></span>



[<span data-ttu-id="a5476-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a5476-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a5476-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a5476-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a5476-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a5476-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a5476-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a5476-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

