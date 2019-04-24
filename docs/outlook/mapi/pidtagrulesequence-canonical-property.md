---
title: PidTagRuleSequence 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleSequence
api_type:
- COM
ms.assetid: c42f2539-f7d6-464a-a82c-f0ac51823168
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 70e7a20a69b7467c1d8c31469273dcc28ce219ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321243"
---
# <a name="pidtagrulesequence-canonical-property"></a><span data-ttu-id="3faea-103">PidTagRuleSequence 规范属性</span><span class="sxs-lookup"><span data-stu-id="3faea-103">PidTagRuleSequence Canonical Property</span></span>

  
  
<span data-ttu-id="3faea-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3faea-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3faea-105">一个值, 用于确定评估和执行规则的顺序。</span><span class="sxs-lookup"><span data-stu-id="3faea-105">A value used to determine the order in which rules are evaluated and executed.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3faea-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3faea-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3faea-107">PR_RULE_SEQUENCE</span><span class="sxs-lookup"><span data-stu-id="3faea-107">PR_RULE_SEQUENCE</span></span>  <br/> |
|<span data-ttu-id="3faea-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3faea-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3faea-109">0x6676</span><span class="sxs-lookup"><span data-stu-id="3faea-109">0x6676</span></span>  <br/> |
|<span data-ttu-id="3faea-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3faea-110">Data type:</span></span>  <br/> |<span data-ttu-id="3faea-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="3faea-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="3faea-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3faea-112">Area:</span></span>  <br/> |<span data-ttu-id="3faea-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="3faea-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3faea-114">注解</span><span class="sxs-lookup"><span data-stu-id="3faea-114">Remarks</span></span>

<span data-ttu-id="3faea-115">根据此值的升序顺序对规则进行排序。</span><span class="sxs-lookup"><span data-stu-id="3faea-115">Rules are evaluated in sequence according to the increasing order of this value.</span></span> <span data-ttu-id="3faea-116">未定义在此属性中具有相同值的规则的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="3faea-116">The evaluation order for rules that have the same value in this property is undefined.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3faea-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="3faea-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3faea-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="3faea-118">Protocol specifications</span></span>

<span data-ttu-id="3faea-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3faea-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3faea-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="3faea-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3faea-121">[[毫秒-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3faea-121">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3faea-122">在服务器上操纵传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3faea-122">Manipulates incoming email messages on a server.</span></span>
    
<span data-ttu-id="3faea-123">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3faea-123">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3faea-124">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历项目代表另一个用户操作时与之进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="3faea-124">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar items when they act on behalf of another user.</span></span>
    
<span data-ttu-id="3faea-125">[[毫秒-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3faea-125">[[MS-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3faea-126">包括核心表对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="3faea-126">Includes permissible operations for the core table objects.</span></span>
    
<span data-ttu-id="3faea-127">[[毫秒-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3faea-127">[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3faea-128">指定核心邮件存储对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="3faea-128">Specifies permissible operations for the core message store objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3faea-129">头文件</span><span class="sxs-lookup"><span data-stu-id="3faea-129">Header files</span></span>

<span data-ttu-id="3faea-130">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="3faea-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="3faea-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3faea-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="3faea-132">Mapitags</span><span class="sxs-lookup"><span data-stu-id="3faea-132">Mapitags.h</span></span>
  
> <span data-ttu-id="3faea-133">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3faea-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3faea-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3faea-134">See also</span></span>



[<span data-ttu-id="3faea-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3faea-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3faea-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3faea-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3faea-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3faea-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3faea-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3faea-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

