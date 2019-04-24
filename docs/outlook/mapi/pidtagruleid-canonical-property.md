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
# <a name="pidtagruleid-canonical-property"></a><span data-ttu-id="d117d-103">PidTagRuleId 规范属性</span><span class="sxs-lookup"><span data-stu-id="d117d-103">PidTagRuleId Canonical Property</span></span>

  
  
<span data-ttu-id="d117d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d117d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d117d-105">指定邮件服务器在首次创建规则时为每个规则生成的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d117d-105">Specifies a unique identifier the messaging server generates for each rule when the rule is first created.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d117d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d117d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d117d-107">PR_RULE_ID</span><span class="sxs-lookup"><span data-stu-id="d117d-107">PR_RULE_ID</span></span>  <br/> |
|<span data-ttu-id="d117d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d117d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d117d-109">0x6674</span><span class="sxs-lookup"><span data-stu-id="d117d-109">0x6674</span></span>  <br/> |
|<span data-ttu-id="d117d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d117d-110">Data type:</span></span>  <br/> |<span data-ttu-id="d117d-111">PT_I8</span><span class="sxs-lookup"><span data-stu-id="d117d-111">PT_I8</span></span>  <br/> |
|<span data-ttu-id="d117d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d117d-112">Area:</span></span>  <br/> |<span data-ttu-id="d117d-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="d117d-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d117d-114">注解</span><span class="sxs-lookup"><span data-stu-id="d117d-114">Remarks</span></span>

<span data-ttu-id="d117d-115">在创建新规则时, 客户端不能指定此属性, 但必须在修改或删除规则时指定该属性。</span><span class="sxs-lookup"><span data-stu-id="d117d-115">The client must not specify this property when creating a new rule but must specify it when modifying or deleting a rule.</span></span>
  
<span data-ttu-id="d117d-116">删除规则时, 客户端必须传递的唯一属性是**PR_RULE_ID** , 不应传入任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="d117d-116">When deleting a rule, the only property the client must pass is **PR_RULE_ID** and should not pass in any other property.</span></span> <span data-ttu-id="d117d-117">服务器必须忽略此属性以外的属性。</span><span class="sxs-lookup"><span data-stu-id="d117d-117">The server must ignore properties other than this property.</span></span> <span data-ttu-id="d117d-118">添加规则时, 客户端不得传入**PR_RULE_ID**, 它必须传入**PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md))、 **PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) 和**PR_RULE_PROVIDER** ([PidTagRuleProvider](pidtagruleprovider-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d117d-118">When adding a rule, the client must not pass in **PR_RULE_ID**, it must pass in the **PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md)), **PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) and **PR_RULE_PROVIDER** ([PidTagRuleProvider](pidtagruleprovider-canonical-property.md)) properties.</span></span> <span data-ttu-id="d117d-119">修改规则时, 客户端必须传递**PR_RULE_ID** , 并应传递需要修改的其他属性。</span><span class="sxs-lookup"><span data-stu-id="d117d-119">When modifying a rule, the client must pass in **PR_RULE_ID** and should pass in the rest of the properties that need to be modified.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d117d-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="d117d-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d117d-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="d117d-121">Protocol specifications</span></span>

<span data-ttu-id="d117d-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d117d-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d117d-123">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d117d-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d117d-124">[[毫秒-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d117d-124">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d117d-125">在服务器上操纵传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d117d-125">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d117d-126">头文件</span><span class="sxs-lookup"><span data-stu-id="d117d-126">Header files</span></span>

<span data-ttu-id="d117d-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d117d-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="d117d-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d117d-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="d117d-129">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d117d-129">Mapitags.h</span></span>
  
> <span data-ttu-id="d117d-130">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d117d-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d117d-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d117d-131">See also</span></span>



[<span data-ttu-id="d117d-132">PidTagRuleCondition 规范属性</span><span class="sxs-lookup"><span data-stu-id="d117d-132">PidTagRuleCondition Canonical Property</span></span>](pidtagrulecondition-canonical-property.md)
  
[<span data-ttu-id="d117d-133">PidTagRuleActions 规范属性</span><span class="sxs-lookup"><span data-stu-id="d117d-133">PidTagRuleActions Canonical Property</span></span>](pidtagruleactions-canonical-property.md)
  
[<span data-ttu-id="d117d-134">PidTagRuleProvider 规范属性</span><span class="sxs-lookup"><span data-stu-id="d117d-134">PidTagRuleProvider Canonical Property</span></span>](pidtagruleprovider-canonical-property.md)


[<span data-ttu-id="d117d-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d117d-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d117d-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d117d-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d117d-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d117d-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d117d-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d117d-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

