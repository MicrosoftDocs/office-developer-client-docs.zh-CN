---
title: PidTagRuleCondition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleCondition
api_type:
- COM
ms.assetid: 8a11e846-c62f-4c06-876f-94623d50cc3b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5b513bc5ff6b95b26a96e36a4d04a49737cf6216
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389594"
---
# <a name="pidtagrulecondition-canonical-property"></a><span data-ttu-id="45812-103">PidTagRuleCondition 规范属性</span><span class="sxs-lookup"><span data-stu-id="45812-103">PidTagRuleCondition Canonical Property</span></span>

  
  
<span data-ttu-id="45812-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="45812-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="45812-105">使用评估规则时的条件。</span><span class="sxs-lookup"><span data-stu-id="45812-105">The condition used when you evaluate the rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="45812-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="45812-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="45812-107">PR_RULE_CONDITION</span><span class="sxs-lookup"><span data-stu-id="45812-107">PR_RULE_CONDITION</span></span>  <br/> |
|<span data-ttu-id="45812-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="45812-108">Identifier:</span></span>  <br/> |<span data-ttu-id="45812-109">0x6679</span><span class="sxs-lookup"><span data-stu-id="45812-109">0x6679</span></span>  <br/> |
|<span data-ttu-id="45812-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="45812-110">Data type:</span></span>  <br/> |<span data-ttu-id="45812-111">PT_SRESTRICTION</span><span class="sxs-lookup"><span data-stu-id="45812-111">PT_SRESTRICTION</span></span>  <br/> |
|<span data-ttu-id="45812-112">区域：</span><span class="sxs-lookup"><span data-stu-id="45812-112">Area:</span></span>  <br/> |<span data-ttu-id="45812-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="45812-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="45812-114">说明</span><span class="sxs-lookup"><span data-stu-id="45812-114">Remarks</span></span>

<span data-ttu-id="45812-115">条件表示为**限制**，并且**PropertyValue**缓冲区包含打包为[[MS OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)中指定的**限制**结构。</span><span class="sxs-lookup"><span data-stu-id="45812-115">The condition is expressed as a **Restriction** and the **PropertyValue** buffer contains the **Restriction** structure packaged as specified in [[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="45812-116">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="45812-116">MFCMAPI reference</span></span>

<span data-ttu-id="45812-117">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="45812-117">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="45812-118">**文件**</span><span class="sxs-lookup"><span data-stu-id="45812-118">**File**</span></span>|<span data-ttu-id="45812-119">**函数**</span><span class="sxs-lookup"><span data-stu-id="45812-119">**Function**</span></span>|<span data-ttu-id="45812-120">**备注**</span><span class="sxs-lookup"><span data-stu-id="45812-120">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="45812-121">ImportProcs.cpp</span><span class="sxs-lookup"><span data-stu-id="45812-121">ImportProcs.cpp</span></span>  <br/> |<span data-ttu-id="45812-122">PropCopyMore HrCopyRestriction</span><span class="sxs-lookup"><span data-stu-id="45812-122">PropCopyMore, HrCopyRestriction</span></span>  <br/> |<span data-ttu-id="45812-123">这些函数演示如何将复制到另一个属性对于分析**PT_SRESTRICTION**属性。</span><span class="sxs-lookup"><span data-stu-id="45812-123">These functions demonstrate how to parse a **PT_SRESTRICTION** property for the purposes of copying to another property.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="45812-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="45812-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="45812-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="45812-125">Protocol specifications</span></span>

<span data-ttu-id="45812-126">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="45812-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="45812-127">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="45812-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="45812-128">[[MS OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="45812-128">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="45812-129">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="45812-129">Manipulates incoming email messages on a server.</span></span>
    
<span data-ttu-id="45812-130">[[MS OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="45812-130">[[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="45812-131">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="45812-131">Defines the basic data structures that are used in remote operations.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="45812-132">头文件</span><span class="sxs-lookup"><span data-stu-id="45812-132">Header files</span></span>

<span data-ttu-id="45812-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="45812-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="45812-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="45812-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="45812-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="45812-135">Mapitags.h</span></span>
  
> <span data-ttu-id="45812-136">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="45812-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="45812-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45812-137">See also</span></span>



[<span data-ttu-id="45812-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="45812-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="45812-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="45812-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="45812-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="45812-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="45812-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="45812-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

