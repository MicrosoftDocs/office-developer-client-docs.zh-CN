---
title: PidTagRuleActions 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleActions
api_type:
- COM
ms.assetid: 3ec4259a-8fe9-46c3-82b8-42c6907b8515
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6edebdb63a63b9df830ae549c0f0d9146f6eb82e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778257"
---
# <a name="pidtagruleactions-canonical-property"></a><span data-ttu-id="1343f-103">PidTagRuleActions 规范属性</span><span class="sxs-lookup"><span data-stu-id="1343f-103">PidTagRuleActions Canonical Property</span></span>

  
  
<span data-ttu-id="1343f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1343f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1343f-105">包含一的组与规则关联的操作。</span><span class="sxs-lookup"><span data-stu-id="1343f-105">Contains the set of actions associated with the rule.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1343f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1343f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1343f-107">PR_RULE_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="1343f-107">PR_RULE_ACTIONS</span></span>  <br/> |
|<span data-ttu-id="1343f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1343f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1343f-109">0x6680</span><span class="sxs-lookup"><span data-stu-id="1343f-109">0x6680</span></span>  <br/> |
|<span data-ttu-id="1343f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1343f-110">Data type:</span></span>  <br/> |<span data-ttu-id="1343f-111">PT_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="1343f-111">PT_ACTIONS</span></span>  <br/> |
|<span data-ttu-id="1343f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1343f-112">Area:</span></span>  <br/> |<span data-ttu-id="1343f-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="1343f-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1343f-114">说明</span><span class="sxs-lookup"><span data-stu-id="1343f-114">Remarks</span></span>

<span data-ttu-id="1343f-115">操作表示为规则操作和属性值缓冲区包含打包为[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)中指定规则操作数据缓冲区结构。</span><span class="sxs-lookup"><span data-stu-id="1343f-115">The actions are expressed as a rule action and the property value buffer contains the rule action data buffer structure packaged as specified in [[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1343f-116">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1343f-116">MFCMAPI reference</span></span>

<span data-ttu-id="1343f-117">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1343f-117">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1343f-118">**文件**</span><span class="sxs-lookup"><span data-stu-id="1343f-118">**File**</span></span>|<span data-ttu-id="1343f-119">**函数**</span><span class="sxs-lookup"><span data-stu-id="1343f-119">**Function**</span></span>|<span data-ttu-id="1343f-120">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1343f-120">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1343f-121">ImportProcs.cpp</span><span class="sxs-lookup"><span data-stu-id="1343f-121">ImportProcs.cpp</span></span>  <br/> |<span data-ttu-id="1343f-122">PropCopyMore HrCopyActions</span><span class="sxs-lookup"><span data-stu-id="1343f-122">PropCopyMore, HrCopyActions</span></span>  <br/> |<span data-ttu-id="1343f-123">这些函数演示如何将复制到另一个属性对于分析 PT_ACTIONS 属性。</span><span class="sxs-lookup"><span data-stu-id="1343f-123">These functions demonstrate how to parse a PT_ACTIONS property for the purposes of copying to another property.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="1343f-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="1343f-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1343f-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="1343f-125">Protocol specifications</span></span>

<span data-ttu-id="1343f-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1343f-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1343f-127">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="1343f-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1343f-128">[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1343f-128">[[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1343f-129">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="1343f-129">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1343f-130">头文件</span><span class="sxs-lookup"><span data-stu-id="1343f-130">Header files</span></span>

<span data-ttu-id="1343f-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1343f-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="1343f-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1343f-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="1343f-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1343f-133">Mapitags.h</span></span>
  
> <span data-ttu-id="1343f-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1343f-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1343f-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1343f-135">See also</span></span>



[<span data-ttu-id="1343f-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1343f-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1343f-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1343f-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1343f-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1343f-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1343f-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1343f-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

