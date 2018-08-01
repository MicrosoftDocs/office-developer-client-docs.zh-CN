---
title: PidTagExtendedRuleMessageCondition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExtendedRuleMessageCondition
api_type:
- HeaderDef
ms.assetid: 891851e1-e4a4-4c20-a26c-7223bcca35f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 81ac1cb85e64b4ecdcf63997d4bdcd0f45b3364b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777608"
---
# <a name="pidtagextendedrulemessagecondition-canonical-property"></a><span data-ttu-id="19971-103">PidTagExtendedRuleMessageCondition 规范属性</span><span class="sxs-lookup"><span data-stu-id="19971-103">PidTagExtendedRuleMessageCondition Canonical Property</span></span>

  
  
<span data-ttu-id="19971-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="19971-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="19971-105">包含有关包含在扩展的规则条件的任何命名属性的信息。</span><span class="sxs-lookup"><span data-stu-id="19971-105">Contains information about any named properties that are contained inside of extended rule conditions.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="19971-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="19971-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="19971-107">PR_EXTENDED_RULE_MSG_CONDITION</span><span class="sxs-lookup"><span data-stu-id="19971-107">PR_EXTENDED_RULE_MSG_CONDITION</span></span>  <br/> |
|<span data-ttu-id="19971-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="19971-108">Identifier:</span></span>  <br/> |<span data-ttu-id="19971-109">0x0E9A</span><span class="sxs-lookup"><span data-stu-id="19971-109">0x0E9A</span></span>  <br/> |
|<span data-ttu-id="19971-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="19971-110">Data type:</span></span>  <br/> |<span data-ttu-id="19971-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="19971-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="19971-112">区域：</span><span class="sxs-lookup"><span data-stu-id="19971-112">Area:</span></span>  <br/> |<span data-ttu-id="19971-113">规则</span><span class="sxs-lookup"><span data-stu-id="19971-113">Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="19971-114">说明</span><span class="sxs-lookup"><span data-stu-id="19971-114">Remarks</span></span>

<span data-ttu-id="19971-115">此属性必须设置对从故障邮件。</span><span class="sxs-lookup"><span data-stu-id="19971-115">This property must be set on an FAI message.</span></span> <span data-ttu-id="19971-116">它**PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md)) 的作用相同，但包含有关使用的命名属性的其他信息。</span><span class="sxs-lookup"><span data-stu-id="19971-116">It serves the same purpose as **PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md)), but contains additional information about the named properties used.</span></span> <span data-ttu-id="19971-117">此条件属性值的任何部分中包含的所有字符串值都必须为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="19971-117">All string values contained in any part of this condition property value must be in Unicode format.</span></span>
  
<span data-ttu-id="19971-118">有关此二进制属性的格式的信息，请参阅[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="19971-118">For information about the format of this binary property, see [[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="19971-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="19971-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="19971-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="19971-120">Protocol specifications</span></span>

<span data-ttu-id="19971-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="19971-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="19971-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="19971-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="19971-123">[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="19971-123">[[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="19971-124">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="19971-124">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="19971-125">头文件</span><span class="sxs-lookup"><span data-stu-id="19971-125">Header files</span></span>

<span data-ttu-id="19971-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="19971-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="19971-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="19971-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="19971-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="19971-128">Mapitags.h</span></span>
  
> <span data-ttu-id="19971-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="19971-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="19971-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19971-130">See also</span></span>



[<span data-ttu-id="19971-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="19971-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="19971-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="19971-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="19971-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="19971-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="19971-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="19971-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

