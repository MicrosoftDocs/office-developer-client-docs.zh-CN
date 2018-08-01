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
ms.openlocfilehash: 519ee2b91275e4253845afa35a9a80470071966d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778297"
---
# <a name="pidtagrulestate-canonical-property"></a><span data-ttu-id="ba597-103">PidTagRuleState 规范属性</span><span class="sxs-lookup"><span data-stu-id="ba597-103">PidTagRuleState Canonical Property</span></span>

  
  
<span data-ttu-id="ba597-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ba597-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ba597-105">解释指定规则的状态标志的位掩码组合为一个值。</span><span class="sxs-lookup"><span data-stu-id="ba597-105">A value interpreted as a bitmask combination of flags that specify the state of the rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ba597-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ba597-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ba597-107">PR_RULE_STATE</span><span class="sxs-lookup"><span data-stu-id="ba597-107">PR_RULE_STATE</span></span>  <br/> |
|<span data-ttu-id="ba597-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ba597-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ba597-109">0x6677</span><span class="sxs-lookup"><span data-stu-id="ba597-109">0x6677</span></span>  <br/> |
|<span data-ttu-id="ba597-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ba597-110">Data type:</span></span>  <br/> |<span data-ttu-id="ba597-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ba597-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ba597-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ba597-112">Area:</span></span>  <br/> |<span data-ttu-id="ba597-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="ba597-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ba597-114">说明</span><span class="sxs-lookup"><span data-stu-id="ba597-114">Remarks</span></span>

<span data-ttu-id="ba597-115">下表定义了此属性的可能值。</span><span class="sxs-lookup"><span data-stu-id="ba597-115">The following table defines the possible values of this property.</span></span>
  
<span data-ttu-id="ba597-116">EN （ST_ENABLED、 位掩码 0x00000001）</span><span class="sxs-lookup"><span data-stu-id="ba597-116">EN (ST_ENABLED, bitmask 0x00000001)</span></span>
  
> <span data-ttu-id="ba597-117">执行启用规则。</span><span class="sxs-lookup"><span data-stu-id="ba597-117">The rule is enabled for execution.</span></span> <span data-ttu-id="ba597-118">如果未设置此标志，服务器在计算规则时必须跳过此规则。</span><span class="sxs-lookup"><span data-stu-id="ba597-118">If this flag is not set, the server must skip this rule when evaluating rules.</span></span>
    
<span data-ttu-id="ba597-119">紧急 （ST_ERROR、 位掩码 0x00000002:uc）</span><span class="sxs-lookup"><span data-stu-id="ba597-119">ER (ST_ERROR, bitmask 0x00000002)</span></span>
  
> <span data-ttu-id="ba597-120">服务器遇到错误处理规则。</span><span class="sxs-lookup"><span data-stu-id="ba597-120">The server has encountered an error processing the rule.</span></span>
    
<span data-ttu-id="ba597-121">(ST_ONLY_WHEN_OOF，位掩码 0x00000004)</span><span class="sxs-lookup"><span data-stu-id="ba597-121">OF (ST_ONLY_WHEN_OOF, bitmask 0x00000004)</span></span>
  
> <span data-ttu-id="ba597-122">仅当用户邮箱上设置外出 (OOF) 状态时，才执行规则。</span><span class="sxs-lookup"><span data-stu-id="ba597-122">The rule is executed only when the user sets the Out of Office (OOF) state on the mailbox.</span></span> <span data-ttu-id="ba597-123">未必须在公用文件夹规则中设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ba597-123">This flag must not be set in a public folder rule.</span></span>
    
<span data-ttu-id="ba597-124">你好 （ST_KEEP_OOF_HIST、 位掩码 0x00000008）</span><span class="sxs-lookup"><span data-stu-id="ba597-124">HI (ST_KEEP_OOF_HIST, bitmask 0x00000008)</span></span>
  
> <span data-ttu-id="ba597-125">未必须在公用文件夹规则中设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ba597-125">This flag must not be set in a public folder rule.</span></span>
    
<span data-ttu-id="ba597-126">EL （ST_EXIT_LEVEL、 位掩码 0x00000010）</span><span class="sxs-lookup"><span data-stu-id="ba597-126">EL (ST_EXIT_LEVEL, bitmask 0x00000010)</span></span>
  
> <span data-ttu-id="ba597-127">规则评估将结束后执行此规则的外出规则评估除外。</span><span class="sxs-lookup"><span data-stu-id="ba597-127">Rule evaluation will end after executing this rule, except for evaluation of Out of Office rules.</span></span>
    
<span data-ttu-id="ba597-128">SCL （ST_SKIP_IF_SCL_IS_SAFE、 位掩码 0x00000020）</span><span class="sxs-lookup"><span data-stu-id="ba597-128">SCL (ST_SKIP_IF_SCL_IS_SAFE, bitmask 0x00000020)</span></span>
  
> <span data-ttu-id="ba597-129">可能会跳过此规则的评估。</span><span class="sxs-lookup"><span data-stu-id="ba597-129">Evaluation of this rule may be skipped.</span></span>
    
<span data-ttu-id="ba597-130">PE （ST_RULE_PARSE_ERROR、 位掩码 0x00000040）</span><span class="sxs-lookup"><span data-stu-id="ba597-130">PE (ST_RULE_PARSE_ERROR, bitmask 0x00000040)</span></span>
  
> <span data-ttu-id="ba597-131">服务器遇到错误分析所提供由客户端规则数据。</span><span class="sxs-lookup"><span data-stu-id="ba597-131">The server has encountered an error parsing the rule data provided by the client.</span></span>
    
<span data-ttu-id="ba597-132">X</span><span class="sxs-lookup"><span data-stu-id="ba597-132">X</span></span>
  
> <span data-ttu-id="ba597-133">未使用此协议。</span><span class="sxs-lookup"><span data-stu-id="ba597-133">Unused by this protocol.</span></span> <span data-ttu-id="ba597-134">由客户端不能修改此位。</span><span class="sxs-lookup"><span data-stu-id="ba597-134">This bit must not be modified by the client.</span></span>
    
<span data-ttu-id="ba597-135">请注意上 ST_ONLY_WHEN_OOF 和 ST_EXIT_LEVEL 之间的交互标志：</span><span class="sxs-lookup"><span data-stu-id="ba597-135">Note on the interaction between ST_ONLY_WHEN_OOF and ST_EXIT_LEVEL flags:</span></span> 
  
<span data-ttu-id="ba597-136">当邮箱，设置"外出"状态和一个规则条件的计算结果为 TRUE，</span><span class="sxs-lookup"><span data-stu-id="ba597-136">When the "Out of Office" state is set on the mailbox, and a rule condition evaluates to TRUE,</span></span> 
  
<span data-ttu-id="ba597-137">和：</span><span class="sxs-lookup"><span data-stu-id="ba597-137">AND:</span></span>
  
- <span data-ttu-id="ba597-138">规则已设置了 ST_EXIT_LEVEL 标记，并且没有设置 ST_ONLY_WHEN_OOF 标志。</span><span class="sxs-lookup"><span data-stu-id="ba597-138">The rule has the ST_EXIT_LEVEL flag set and does not have ST_ONLY_WHEN_OOF flag set.</span></span> <span data-ttu-id="ba597-139">然后，服务器必须不会评估后续规则不具有 ST_ONLY_WHEN_OOF 标记集和必须评估设置 ST_ONLY_WHEN_OOF 标志的后续规则。</span><span class="sxs-lookup"><span data-stu-id="ba597-139">Then, the server must not evaluate subsequent rules that do not have ST_ONLY_WHEN_OOF flag set, and must evaluate subsequent rules that have ST_ONLY_WHEN_OOF flag set.</span></span>
    
<span data-ttu-id="ba597-140">OR:</span><span class="sxs-lookup"><span data-stu-id="ba597-140">OR:</span></span>
  
- <span data-ttu-id="ba597-141">规则均具有的 ST_EXIT_LEVEL 和 ST_ONLY_WHEN_OOF 设置的标志。</span><span class="sxs-lookup"><span data-stu-id="ba597-141">The rule has both the ST_EXIT_LEVEL and ST_ONLY_WHEN_OOF flags set.</span></span> <span data-ttu-id="ba597-142">然后，服务器必须不会评估任何后续规则。</span><span class="sxs-lookup"><span data-stu-id="ba597-142">Then, the server must not evaluate any subsequent rules.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="ba597-143">相关资源</span><span class="sxs-lookup"><span data-stu-id="ba597-143">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ba597-144">协议规范</span><span class="sxs-lookup"><span data-stu-id="ba597-144">Protocol specifications</span></span>

<span data-ttu-id="ba597-145">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ba597-145">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ba597-146">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ba597-146">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ba597-147">[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ba597-147">[[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ba597-148">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="ba597-148">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ba597-149">头文件</span><span class="sxs-lookup"><span data-stu-id="ba597-149">Header files</span></span>

<span data-ttu-id="ba597-150">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ba597-150">Mapidefs.h</span></span>
  
> <span data-ttu-id="ba597-151">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ba597-151">Provides data type definitions.</span></span>
    
<span data-ttu-id="ba597-152">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ba597-152">Mapitags.h</span></span>
  
> <span data-ttu-id="ba597-153">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ba597-153">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ba597-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba597-154">See also</span></span>



[<span data-ttu-id="ba597-155">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ba597-155">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ba597-156">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ba597-156">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ba597-157">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ba597-157">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ba597-158">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ba597-158">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

