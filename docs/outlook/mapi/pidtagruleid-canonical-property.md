---
title: PidTagRuleId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleId
api_type:
- COM
ms.assetid: 341e8db0-52b7-4ba7-aaa6-eedf2783b4e8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8d88838893836c550136be9556299258b44e3e49
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359491"
---
# <a name="pidtagruleid-canonical-property"></a><span data-ttu-id="435fe-103">PidTagRuleId 规范属性</span><span class="sxs-lookup"><span data-stu-id="435fe-103">PidTagRuleId Canonical Property</span></span>

  
  
<span data-ttu-id="435fe-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="435fe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="435fe-105">指定邮件服务器在首次创建规则时为每条规则生成的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="435fe-105">Specifies a unique identifier the messaging server generates for each rule when the rule is first created.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="435fe-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="435fe-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="435fe-107">PR_RULE_ID</span><span class="sxs-lookup"><span data-stu-id="435fe-107">PR_RULE_ID</span></span>  <br/> |
|<span data-ttu-id="435fe-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="435fe-108">Identifier:</span></span>  <br/> |<span data-ttu-id="435fe-109">0x6674</span><span class="sxs-lookup"><span data-stu-id="435fe-109">0x6674</span></span>  <br/> |
|<span data-ttu-id="435fe-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="435fe-110">Data type:</span></span>  <br/> |<span data-ttu-id="435fe-111">PT_I8</span><span class="sxs-lookup"><span data-stu-id="435fe-111">PT_I8</span></span>  <br/> |
|<span data-ttu-id="435fe-112">区域：</span><span class="sxs-lookup"><span data-stu-id="435fe-112">Area:</span></span>  <br/> |<span data-ttu-id="435fe-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="435fe-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="435fe-114">备注</span><span class="sxs-lookup"><span data-stu-id="435fe-114">Remarks</span></span>

<span data-ttu-id="435fe-115">客户端在创建新规则时不得指定此属性，但在修改或删除规则时必须指定此属性。</span><span class="sxs-lookup"><span data-stu-id="435fe-115">The client must not specify this property when creating a new rule but must specify it when modifying or deleting a rule.</span></span>
  
<span data-ttu-id="435fe-116">删除规则时，客户端必须传递的唯一属性是 **PR_RULE_ID，并且** 不应传递任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="435fe-116">When deleting a rule, the only property the client must pass is **PR_RULE_ID** and should not pass in any other property.</span></span> <span data-ttu-id="435fe-117">服务器必须忽略除此属性外的属性。</span><span class="sxs-lookup"><span data-stu-id="435fe-117">The server must ignore properties other than this property.</span></span> <span data-ttu-id="435fe-118">添加规则时，客户端不得传递 **PR_RULE_ID，** 它必须传递 **PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md)) 、PR_RULE_ACTIONS ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) 和 **PR_RULE_PROVIDER** ([PidTagRuleProvider](pidtagruleprovider-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="435fe-118">When adding a rule, the client must not pass in **PR_RULE_ID**, it must pass in the **PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md)), **PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) and **PR_RULE_PROVIDER** ([PidTagRuleProvider](pidtagruleprovider-canonical-property.md)) properties.</span></span> <span data-ttu-id="435fe-119">修改规则时，客户端必须PR_RULE_ID，并且应传递需要修改的其余属性。</span><span class="sxs-lookup"><span data-stu-id="435fe-119">When modifying a rule, the client must pass in **PR_RULE_ID** and should pass in the rest of the properties that need to be modified.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="435fe-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="435fe-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="435fe-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="435fe-121">Protocol specifications</span></span>

<span data-ttu-id="435fe-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="435fe-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="435fe-123">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="435fe-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="435fe-124">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="435fe-124">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="435fe-125">在服务器上处理传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="435fe-125">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="435fe-126">头文件</span><span class="sxs-lookup"><span data-stu-id="435fe-126">Header files</span></span>

<span data-ttu-id="435fe-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="435fe-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="435fe-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="435fe-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="435fe-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="435fe-129">Mapitags.h</span></span>
  
> <span data-ttu-id="435fe-130">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="435fe-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="435fe-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="435fe-131">See also</span></span>



[<span data-ttu-id="435fe-132">PidTagRuleCondition 规范属性</span><span class="sxs-lookup"><span data-stu-id="435fe-132">PidTagRuleCondition Canonical Property</span></span>](pidtagrulecondition-canonical-property.md)
  
[<span data-ttu-id="435fe-133">PidTagRuleActions 规范属性</span><span class="sxs-lookup"><span data-stu-id="435fe-133">PidTagRuleActions Canonical Property</span></span>](pidtagruleactions-canonical-property.md)
  
[<span data-ttu-id="435fe-134">PidTagRuleProvider 规范属性</span><span class="sxs-lookup"><span data-stu-id="435fe-134">PidTagRuleProvider Canonical Property</span></span>](pidtagruleprovider-canonical-property.md)


[<span data-ttu-id="435fe-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="435fe-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="435fe-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="435fe-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="435fe-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="435fe-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="435fe-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="435fe-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

