---
title: PidTagRuleState 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleState
api_type:
- COM
ms.assetid: f62f3055-b855-4203-aa5c-6ba28b58c6f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0e15462cd3dc14c93155e34e47b7caac2c04087
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338610"
---
# <a name="pidtagrulestate-canonical-property"></a><span data-ttu-id="e0a06-103">PidTagRuleState 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0a06-103">PidTagRuleState Canonical Property</span></span>

  
  
<span data-ttu-id="e0a06-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e0a06-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e0a06-105">解释为指定规则状态的标志的位掩码组合的值。</span><span class="sxs-lookup"><span data-stu-id="e0a06-105">A value interpreted as a bitmask combination of flags that specify the state of the rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e0a06-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e0a06-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e0a06-107">PR_RULE_STATE</span><span class="sxs-lookup"><span data-stu-id="e0a06-107">PR_RULE_STATE</span></span>  <br/> |
|<span data-ttu-id="e0a06-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e0a06-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e0a06-109">0x6677</span><span class="sxs-lookup"><span data-stu-id="e0a06-109">0x6677</span></span>  <br/> |
|<span data-ttu-id="e0a06-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e0a06-110">Data type:</span></span>  <br/> |<span data-ttu-id="e0a06-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e0a06-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e0a06-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e0a06-112">Area:</span></span>  <br/> |<span data-ttu-id="e0a06-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="e0a06-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e0a06-114">备注</span><span class="sxs-lookup"><span data-stu-id="e0a06-114">Remarks</span></span>

<span data-ttu-id="e0a06-115">下表定义了此属性的可能值。</span><span class="sxs-lookup"><span data-stu-id="e0a06-115">The following table defines the possible values of this property.</span></span>
  
<span data-ttu-id="e0a06-116">EN (ST_ENABLED、位掩码0x00000001) </span><span class="sxs-lookup"><span data-stu-id="e0a06-116">EN (ST_ENABLED, bitmask 0x00000001)</span></span>
  
> <span data-ttu-id="e0a06-117">规则已启用以执行。</span><span class="sxs-lookup"><span data-stu-id="e0a06-117">The rule is enabled for execution.</span></span> <span data-ttu-id="e0a06-118">如果未设置此标志，则服务器在评估规则时必须跳过此规则。</span><span class="sxs-lookup"><span data-stu-id="e0a06-118">If this flag is not set, the server must skip this rule when evaluating rules.</span></span>
    
<span data-ttu-id="e0a06-119">ER (ST_ERROR、位掩码0x00000002) </span><span class="sxs-lookup"><span data-stu-id="e0a06-119">ER (ST_ERROR, bitmask 0x00000002)</span></span>
  
> <span data-ttu-id="e0a06-120">服务器在处理规则时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="e0a06-120">The server has encountered an error processing the rule.</span></span>
    
<span data-ttu-id="e0a06-121">OF (ST_ONLY_WHEN_OOF、位掩码0x00000004) </span><span class="sxs-lookup"><span data-stu-id="e0a06-121">OF (ST_ONLY_WHEN_OOF, bitmask 0x00000004)</span></span>
  
> <span data-ttu-id="e0a06-122">仅在用户对邮箱设置 Out of Office (OOF) 时执行规则。</span><span class="sxs-lookup"><span data-stu-id="e0a06-122">The rule is executed only when the user sets the Out of Office (OOF) state on the mailbox.</span></span> <span data-ttu-id="e0a06-123">此标志不得在公用文件夹规则中设置。</span><span class="sxs-lookup"><span data-stu-id="e0a06-123">This flag must not be set in a public folder rule.</span></span>
    
<span data-ttu-id="e0a06-124">HI (ST_KEEP_OOF_HIST、位掩码0x00000008) </span><span class="sxs-lookup"><span data-stu-id="e0a06-124">HI (ST_KEEP_OOF_HIST, bitmask 0x00000008)</span></span>
  
> <span data-ttu-id="e0a06-125">此标志不得在公用文件夹规则中设置。</span><span class="sxs-lookup"><span data-stu-id="e0a06-125">This flag must not be set in a public folder rule.</span></span>
    
<span data-ttu-id="e0a06-126">EL (ST_EXIT_LEVEL、位掩码0x00000010) </span><span class="sxs-lookup"><span data-stu-id="e0a06-126">EL (ST_EXIT_LEVEL, bitmask 0x00000010)</span></span>
  
> <span data-ttu-id="e0a06-127">规则评估将在执行此规则后结束，但评估"外出"规则Office除外。</span><span class="sxs-lookup"><span data-stu-id="e0a06-127">Rule evaluation will end after executing this rule, except for evaluation of Out of Office rules.</span></span>
    
<span data-ttu-id="e0a06-128">SCL (ST_SKIP_IF_SCL_IS_SAFE位掩码0x00000020) </span><span class="sxs-lookup"><span data-stu-id="e0a06-128">SCL (ST_SKIP_IF_SCL_IS_SAFE, bitmask 0x00000020)</span></span>
  
> <span data-ttu-id="e0a06-129">可能会跳过此规则的评估。</span><span class="sxs-lookup"><span data-stu-id="e0a06-129">Evaluation of this rule may be skipped.</span></span>
    
<span data-ttu-id="e0a06-130">PE (ST_RULE_PARSE_ERROR、位掩码0x00000040) </span><span class="sxs-lookup"><span data-stu-id="e0a06-130">PE (ST_RULE_PARSE_ERROR, bitmask 0x00000040)</span></span>
  
> <span data-ttu-id="e0a06-131">服务器在解析客户端提供的规则数据时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="e0a06-131">The server has encountered an error parsing the rule data provided by the client.</span></span>
    
<span data-ttu-id="e0a06-132">X</span><span class="sxs-lookup"><span data-stu-id="e0a06-132">X</span></span>
  
> <span data-ttu-id="e0a06-133">此协议未使用。</span><span class="sxs-lookup"><span data-stu-id="e0a06-133">Unused by this protocol.</span></span> <span data-ttu-id="e0a06-134">客户端不得修改此位。</span><span class="sxs-lookup"><span data-stu-id="e0a06-134">This bit must not be modified by the client.</span></span>
    
<span data-ttu-id="e0a06-135">有关标记与ST_ONLY_WHEN_OOF ST_EXIT_LEVEL交互的注意事项：</span><span class="sxs-lookup"><span data-stu-id="e0a06-135">Note on the interaction between ST_ONLY_WHEN_OOF and ST_EXIT_LEVEL flags:</span></span> 
  
<span data-ttu-id="e0a06-136">在邮箱上设置"out of Office"状态，且规则条件计算结果为 TRUE 时，</span><span class="sxs-lookup"><span data-stu-id="e0a06-136">When the "Out of Office" state is set on the mailbox, and a rule condition evaluates to TRUE,</span></span> 
  
<span data-ttu-id="e0a06-137">AND：</span><span class="sxs-lookup"><span data-stu-id="e0a06-137">AND:</span></span>
  
- <span data-ttu-id="e0a06-138">规则已设置ST_EXIT_LEVEL标志，并且未ST_ONLY_WHEN_OOF该标志。</span><span class="sxs-lookup"><span data-stu-id="e0a06-138">The rule has the ST_EXIT_LEVEL flag set and does not have ST_ONLY_WHEN_OOF flag set.</span></span> <span data-ttu-id="e0a06-139">然后，服务器不得评估未设置标志ST_ONLY_WHEN_OOF规则，并且必须评估已设置ST_ONLY_WHEN_OOF规则。</span><span class="sxs-lookup"><span data-stu-id="e0a06-139">Then, the server must not evaluate subsequent rules that do not have ST_ONLY_WHEN_OOF flag set, and must evaluate subsequent rules that have ST_ONLY_WHEN_OOF flag set.</span></span>
    
<span data-ttu-id="e0a06-140">或者：</span><span class="sxs-lookup"><span data-stu-id="e0a06-140">OR:</span></span>
  
- <span data-ttu-id="e0a06-141">规则同时设置了 ST_EXIT_LEVEL 和 ST_ONLY_WHEN_OOF 标志。</span><span class="sxs-lookup"><span data-stu-id="e0a06-141">The rule has both the ST_EXIT_LEVEL and ST_ONLY_WHEN_OOF flags set.</span></span> <span data-ttu-id="e0a06-142">然后，服务器不得评估任何后续规则。</span><span class="sxs-lookup"><span data-stu-id="e0a06-142">Then, the server must not evaluate any subsequent rules.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="e0a06-143">相关资源</span><span class="sxs-lookup"><span data-stu-id="e0a06-143">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e0a06-144">协议规范</span><span class="sxs-lookup"><span data-stu-id="e0a06-144">Protocol specifications</span></span>

<span data-ttu-id="e0a06-145">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0a06-145">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0a06-146">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="e0a06-146">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e0a06-147">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0a06-147">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0a06-148">在服务器上处理传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e0a06-148">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e0a06-149">头文件</span><span class="sxs-lookup"><span data-stu-id="e0a06-149">Header files</span></span>

<span data-ttu-id="e0a06-150">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e0a06-150">Mapidefs.h</span></span>
  
> <span data-ttu-id="e0a06-151">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e0a06-151">Provides data type definitions.</span></span>
    
<span data-ttu-id="e0a06-152">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e0a06-152">Mapitags.h</span></span>
  
> <span data-ttu-id="e0a06-153">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e0a06-153">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e0a06-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0a06-154">See also</span></span>



[<span data-ttu-id="e0a06-155">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e0a06-155">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e0a06-156">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0a06-156">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e0a06-157">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e0a06-157">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e0a06-158">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e0a06-158">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

