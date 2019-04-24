---
title: PidTagExtendedRuleMessageActions 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExtendedRuleMessageActions
api_type:
- HeaderDef
ms.assetid: 1cf277d4-76ec-4902-9e54-f1780cee49bf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 70f09d6db5940fcb9b980cc839988113bd3a3e2e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316336"
---
# <a name="pidtagextendedrulemessageactions-canonical-property"></a><span data-ttu-id="6cd68-103">PidTagExtendedRuleMessageActions 规范属性</span><span class="sxs-lookup"><span data-stu-id="6cd68-103">PidTagExtendedRuleMessageActions Canonical Property</span></span>

  
  
<span data-ttu-id="6cd68-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6cd68-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6cd68-105">包含有关在文件夹关联的信息 (FAI) 消息中使用的命名属性的其他信息。</span><span class="sxs-lookup"><span data-stu-id="6cd68-105">Contains additional information about the named properties used in a Folder Associated Information (FAI) message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6cd68-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6cd68-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6cd68-107">PR_EXTENDED_RULE_MSG_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="6cd68-107">PR_EXTENDED_RULE_MSG_ACTIONS</span></span>  <br/> |
|<span data-ttu-id="6cd68-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6cd68-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6cd68-109">0x0E99</span><span class="sxs-lookup"><span data-stu-id="6cd68-109">0x0E99</span></span>  <br/> |
|<span data-ttu-id="6cd68-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6cd68-110">Data type:</span></span>  <br/> |<span data-ttu-id="6cd68-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6cd68-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6cd68-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6cd68-112">Area:</span></span>  <br/> |<span data-ttu-id="6cd68-113">规则</span><span class="sxs-lookup"><span data-stu-id="6cd68-113">Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6cd68-114">注解</span><span class="sxs-lookup"><span data-stu-id="6cd68-114">Remarks</span></span>

<span data-ttu-id="6cd68-115">必须在 FAI 消息上设置此属性。</span><span class="sxs-lookup"><span data-stu-id="6cd68-115">This property must be set on an FAI message.</span></span> <span data-ttu-id="6cd68-116">此属性的用途与**PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) 相同, 但包含有关规则版本和存储在规则操作中的命名属性的其他信息, 以及有关要执行的操作的信息。此规则执行。</span><span class="sxs-lookup"><span data-stu-id="6cd68-116">This property serves the same purpose as **PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)), but contains additional information about the version of the rule and the named properties stored in the rule action, as well as information about the actions to be performed by this rule.</span></span> <span data-ttu-id="6cd68-117">用于包含操作的操作缓冲区的任何部分中包含的所有字符串值都必须采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="6cd68-117">All string values contained in any part of the action buffer used to contain actions must be in Unicode format.</span></span>
  
<span data-ttu-id="6cd68-118">有关此二进制属性的格式的信息, 请参阅[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6cd68-118">For information about the format of this binary property, see [[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6cd68-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="6cd68-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6cd68-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="6cd68-120">Protocol specifications</span></span>

<span data-ttu-id="6cd68-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6cd68-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6cd68-122">提供对相关 Exchange Server 协议规范的引用。。</span><span class="sxs-lookup"><span data-stu-id="6cd68-122">Provides references to related Exchange Server protocol specifications..</span></span>
    
<span data-ttu-id="6cd68-123">[[毫秒-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6cd68-123">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6cd68-124">在服务器上操纵传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6cd68-124">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6cd68-125">头文件</span><span class="sxs-lookup"><span data-stu-id="6cd68-125">Header files</span></span>

<span data-ttu-id="6cd68-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6cd68-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="6cd68-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6cd68-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="6cd68-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="6cd68-128">Mapitags.h</span></span>
  
> <span data-ttu-id="6cd68-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6cd68-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6cd68-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cd68-130">See also</span></span>



[<span data-ttu-id="6cd68-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6cd68-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6cd68-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6cd68-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6cd68-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6cd68-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6cd68-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6cd68-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

