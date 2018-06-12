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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 52a6132dcd6aa2c3a2951f3d1a6458808364dccb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778272"
---
# <a name="pidtagruleid-canonical-property"></a><span data-ttu-id="04694-103">PidTagRuleId 规范属性</span><span class="sxs-lookup"><span data-stu-id="04694-103">PidTagRuleId Canonical Property</span></span>

  
  
<span data-ttu-id="04694-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="04694-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="04694-105">指定首次创建规则时，消息服务器将生成的每个规则的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="04694-105">Specifies a unique identifier the messaging server generates for each rule when the rule is first created.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="04694-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="04694-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="04694-107">PR_RULE_ID</span><span class="sxs-lookup"><span data-stu-id="04694-107">PR_RULE_ID</span></span>  <br/> |
|<span data-ttu-id="04694-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="04694-108">Identifier:</span></span>  <br/> |<span data-ttu-id="04694-109">0x6674</span><span class="sxs-lookup"><span data-stu-id="04694-109">0x6674</span></span>  <br/> |
|<span data-ttu-id="04694-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="04694-110">Data type:</span></span>  <br/> |<span data-ttu-id="04694-111">PT_I8</span><span class="sxs-lookup"><span data-stu-id="04694-111">PT_I8</span></span>  <br/> |
|<span data-ttu-id="04694-112">区域：</span><span class="sxs-lookup"><span data-stu-id="04694-112">Area:</span></span>  <br/> |<span data-ttu-id="04694-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="04694-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="04694-114">备注</span><span class="sxs-lookup"><span data-stu-id="04694-114">Remarks</span></span>

<span data-ttu-id="04694-115">客户端不能指定此属性时创建一个新规则，但必须指定时修改或删除规则。</span><span class="sxs-lookup"><span data-stu-id="04694-115">The client must not specify this property when creating a new rule but must specify it when modifying or deleting a rule.</span></span>
  
<span data-ttu-id="04694-116">如果删除规则，传递客户端必须仅属性为**PR_RULE_ID** ，并不应将传递中任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="04694-116">When deleting a rule, the only property the client must pass is **PR_RULE_ID** and should not pass in any other property.</span></span> <span data-ttu-id="04694-117">服务器必须忽略此属性之外的属性。</span><span class="sxs-lookup"><span data-stu-id="04694-117">The server must ignore properties other than this property.</span></span> <span data-ttu-id="04694-118">当添加规则中**PR_RULE_ID**, 不传递客户端，必须时，它必须**PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md))、 **PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) 和**PR_RULE_PROVIDER** ([中传递PidTagRuleProvider](pidtagruleprovider-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="04694-118">When adding a rule, the client must not pass in **PR_RULE_ID**, it must pass in the **PR_RULE_CONDITION** ([PidTagRuleCondition](pidtagrulecondition-canonical-property.md)), **PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) and **PR_RULE_PROVIDER** ([PidTagRuleProvider](pidtagruleprovider-canonical-property.md)) properties.</span></span> <span data-ttu-id="04694-119">修改的规则时, 客户端中**PR_RULE_ID**必须经过，并应传入需要进行修改的属性的其余部分。</span><span class="sxs-lookup"><span data-stu-id="04694-119">When modifying a rule, the client must pass in **PR_RULE_ID** and should pass in the rest of the properties that need to be modified.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="04694-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="04694-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="04694-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="04694-121">Protocol specifications</span></span>

<span data-ttu-id="04694-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="04694-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="04694-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="04694-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="04694-124">[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="04694-124">[[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="04694-125">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="04694-125">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="04694-126">头文件</span><span class="sxs-lookup"><span data-stu-id="04694-126">Header files</span></span>

<span data-ttu-id="04694-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="04694-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="04694-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="04694-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="04694-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="04694-129">Mapitags.h</span></span>
  
> <span data-ttu-id="04694-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="04694-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="04694-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04694-131">See also</span></span>



[<span data-ttu-id="04694-132">PidTagRuleCondition 规范属性</span><span class="sxs-lookup"><span data-stu-id="04694-132">PidTagRuleCondition Canonical Property</span></span>](pidtagrulecondition-canonical-property.md)
  
[<span data-ttu-id="04694-133">PidTagRuleActions 规范属性</span><span class="sxs-lookup"><span data-stu-id="04694-133">PidTagRuleActions Canonical Property</span></span>](pidtagruleactions-canonical-property.md)
  
[<span data-ttu-id="04694-134">PidTagRuleProvider 规范属性</span><span class="sxs-lookup"><span data-stu-id="04694-134">PidTagRuleProvider Canonical Property</span></span>](pidtagruleprovider-canonical-property.md)


[<span data-ttu-id="04694-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="04694-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="04694-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="04694-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="04694-137">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="04694-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="04694-138">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="04694-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

