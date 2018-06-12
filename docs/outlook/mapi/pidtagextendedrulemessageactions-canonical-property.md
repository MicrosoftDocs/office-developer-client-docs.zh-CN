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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5425496a5b7845daabf736978e6ed24518451fe0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777624"
---
# <a name="pidtagextendedrulemessageactions-canonical-property"></a><span data-ttu-id="9a55b-103">PidTagExtendedRuleMessageActions 规范属性</span><span class="sxs-lookup"><span data-stu-id="9a55b-103">PidTagExtendedRuleMessageActions Canonical Property</span></span>

  
  
<span data-ttu-id="9a55b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9a55b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9a55b-105">包含有关文件夹关联的信息 （从故障） 消息中使用的命名属性的其他信息。</span><span class="sxs-lookup"><span data-stu-id="9a55b-105">Contains additional information about the named properties used in a Folder Associated Information (FAI) message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9a55b-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="9a55b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9a55b-107">PR_EXTENDED_RULE_MSG_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="9a55b-107">PR_EXTENDED_RULE_MSG_ACTIONS</span></span>  <br/> |
|<span data-ttu-id="9a55b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9a55b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9a55b-109">0x0E99</span><span class="sxs-lookup"><span data-stu-id="9a55b-109">0x0E99</span></span>  <br/> |
|<span data-ttu-id="9a55b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9a55b-110">Data type:</span></span>  <br/> |<span data-ttu-id="9a55b-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9a55b-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9a55b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9a55b-112">Area:</span></span>  <br/> |<span data-ttu-id="9a55b-113">规则</span><span class="sxs-lookup"><span data-stu-id="9a55b-113">Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9a55b-114">备注</span><span class="sxs-lookup"><span data-stu-id="9a55b-114">Remarks</span></span>

<span data-ttu-id="9a55b-115">此属性必须设置对从故障邮件。</span><span class="sxs-lookup"><span data-stu-id="9a55b-115">This property must be set on an FAI message.</span></span> <span data-ttu-id="9a55b-116">此属性的作用相同作为**PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md))，但包含版本的规则，以及规则操作中, 存储的命名的属性的其他信息，以及有关为操作的信息此规则执行。</span><span class="sxs-lookup"><span data-stu-id="9a55b-116">This property serves the same purpose as **PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)), but contains additional information about the version of the rule and the named properties stored in the rule action, as well as information about the actions to be performed by this rule.</span></span> <span data-ttu-id="9a55b-117">用来包含操作的操作任何的缓冲区部分中包含的所有字符串值都必须为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="9a55b-117">All string values contained in any part of the action buffer used to contain actions must be in Unicode format.</span></span>
  
<span data-ttu-id="9a55b-118">有关此二进制属性的格式的信息，请参阅[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9a55b-118">For information about the format of this binary property, see [[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9a55b-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="9a55b-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9a55b-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="9a55b-120">Protocol specifications</span></span>

<span data-ttu-id="9a55b-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9a55b-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9a55b-122">提供了相关的 Exchange Server 协议规范的参考正在</span><span class="sxs-lookup"><span data-stu-id="9a55b-122">Provides references to related Exchange Server protocol specifications..</span></span>
    
<span data-ttu-id="9a55b-123">[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9a55b-123">[[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9a55b-124">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="9a55b-124">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9a55b-125">头文件</span><span class="sxs-lookup"><span data-stu-id="9a55b-125">Header files</span></span>

<span data-ttu-id="9a55b-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9a55b-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="9a55b-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9a55b-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="9a55b-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9a55b-128">Mapitags.h</span></span>
  
> <span data-ttu-id="9a55b-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9a55b-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9a55b-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a55b-130">See also</span></span>



[<span data-ttu-id="9a55b-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9a55b-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9a55b-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9a55b-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9a55b-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9a55b-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9a55b-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9a55b-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

