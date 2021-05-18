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
ms.openlocfilehash: ab246414f7caaf76f462d9b80e762fe614c77c21
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278898"
---
# <a name="pidtagruleactions-canonical-property"></a><span data-ttu-id="8ab44-103">PidTagRuleActions 规范属性</span><span class="sxs-lookup"><span data-stu-id="8ab44-103">PidTagRuleActions Canonical Property</span></span>

  
  
<span data-ttu-id="8ab44-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8ab44-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8ab44-105">包含与规则关联的操作集。</span><span class="sxs-lookup"><span data-stu-id="8ab44-105">Contains the set of actions associated with the rule.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8ab44-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8ab44-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8ab44-107">PR_RULE_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="8ab44-107">PR_RULE_ACTIONS</span></span>  <br/> |
|<span data-ttu-id="8ab44-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8ab44-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8ab44-109">0x6680</span><span class="sxs-lookup"><span data-stu-id="8ab44-109">0x6680</span></span>  <br/> |
|<span data-ttu-id="8ab44-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8ab44-110">Data type:</span></span>  <br/> |<span data-ttu-id="8ab44-111">PT_ACTIONS</span><span class="sxs-lookup"><span data-stu-id="8ab44-111">PT_ACTIONS</span></span>  <br/> |
|<span data-ttu-id="8ab44-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8ab44-112">Area:</span></span>  <br/> |<span data-ttu-id="8ab44-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="8ab44-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8ab44-114">备注</span><span class="sxs-lookup"><span data-stu-id="8ab44-114">Remarks</span></span>

<span data-ttu-id="8ab44-115">操作表示为规则操作，属性值缓冲区包含按 [[MS-OXORULE] 中](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)指定封装的规则操作数据缓冲区结构。</span><span class="sxs-lookup"><span data-stu-id="8ab44-115">The actions are expressed as a rule action and the property value buffer contains the rule action data buffer structure packaged as specified in [[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="8ab44-116">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="8ab44-116">MFCMAPI reference</span></span>

<span data-ttu-id="8ab44-117">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="8ab44-117">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="8ab44-118">**文件**</span><span class="sxs-lookup"><span data-stu-id="8ab44-118">**File**</span></span>|<span data-ttu-id="8ab44-119">**函数**</span><span class="sxs-lookup"><span data-stu-id="8ab44-119">**Function**</span></span>|<span data-ttu-id="8ab44-120">**备注**</span><span class="sxs-lookup"><span data-stu-id="8ab44-120">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ab44-121">ImportProcs.cpp</span><span class="sxs-lookup"><span data-stu-id="8ab44-121">ImportProcs.cpp</span></span>  <br/> |<span data-ttu-id="8ab44-122">PropCopyMore、HrCopyActions</span><span class="sxs-lookup"><span data-stu-id="8ab44-122">PropCopyMore, HrCopyActions</span></span>  <br/> |<span data-ttu-id="8ab44-123">这些函数演示如何分析PT_ACTIONS属性以复制到另一个属性。</span><span class="sxs-lookup"><span data-stu-id="8ab44-123">These functions demonstrate how to parse a PT_ACTIONS property for the purposes of copying to another property.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="8ab44-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="8ab44-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8ab44-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="8ab44-125">Protocol specifications</span></span>

<span data-ttu-id="8ab44-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8ab44-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8ab44-127">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="8ab44-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8ab44-128">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8ab44-128">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8ab44-129">在服务器上处理传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8ab44-129">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8ab44-130">头文件</span><span class="sxs-lookup"><span data-stu-id="8ab44-130">Header files</span></span>

<span data-ttu-id="8ab44-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8ab44-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="8ab44-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8ab44-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="8ab44-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8ab44-133">Mapitags.h</span></span>
  
> <span data-ttu-id="8ab44-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8ab44-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8ab44-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ab44-135">See also</span></span>



[<span data-ttu-id="8ab44-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8ab44-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8ab44-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8ab44-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8ab44-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8ab44-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8ab44-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8ab44-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

