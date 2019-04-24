---
title: PidTagExtendedRuleSizeLimit 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExtendedRuleSizeLimit
api_type:
- HeaderDef
ms.assetid: 87186764-fb58-4cdf-804d-bb13c5a8cb65
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 347d84021b7e9ece925acb99e8b539ba608337a9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316343"
---
# <a name="pidtagextendedrulesizelimit-canonical-property"></a><span data-ttu-id="c5e62-103">PidTagExtendedRuleSizeLimit 规范属性</span><span class="sxs-lookup"><span data-stu-id="c5e62-103">PidTagExtendedRuleSizeLimit Canonical Property</span></span>

  
  
<span data-ttu-id="c5e62-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c5e62-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c5e62-105">包含允许用户为单个 "扩展" 规则累积的最大大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="c5e62-105">Contains the maximum size, in bytes, the user is allowed to accumulate for a single "extended" rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c5e62-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c5e62-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c5e62-107">PR_EXTENDED_RULE_SIZE_LIMIT</span><span class="sxs-lookup"><span data-stu-id="c5e62-107">PR_EXTENDED_RULE_SIZE_LIMIT</span></span>  <br/> |
|<span data-ttu-id="c5e62-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c5e62-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c5e62-109">0x0E9B</span><span class="sxs-lookup"><span data-stu-id="c5e62-109">0x0E9B</span></span>  <br/> |
|<span data-ttu-id="c5e62-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c5e62-110">Data type:</span></span>  <br/> |<span data-ttu-id="c5e62-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c5e62-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c5e62-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c5e62-112">Area:</span></span>  <br/> |<span data-ttu-id="c5e62-113">规则</span><span class="sxs-lookup"><span data-stu-id="c5e62-113">Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c5e62-114">注解</span><span class="sxs-lookup"><span data-stu-id="c5e62-114">Remarks</span></span>

<span data-ttu-id="c5e62-115">如果在 logon 对象上设置了此属性, 客户端应在此属性指定的值下保留**PR_EXTENDED_RULE_MSG_CONDITION** ([PidTagExtendedRuleMessageCondition](pidtagextendedrulemessagecondition-canonical-property.md)) 属性的大小。</span><span class="sxs-lookup"><span data-stu-id="c5e62-115">If this property is set on the logon object, the client should keep the size of the **PR_EXTENDED_RULE_MSG_CONDITION** ([PidTagExtendedRuleMessageCondition](pidtagextendedrulemessagecondition-canonical-property.md)) property under the value specified by this property.</span></span> <span data-ttu-id="c5e62-116">相反, 如果客户端尝试设置过大的二进制属性, 服务器将返回一个错误。</span><span class="sxs-lookup"><span data-stu-id="c5e62-116">Conversely, the server should return an error if the client does attempt to set a binary property that is too large.</span></span>
  
<span data-ttu-id="c5e62-117">有关扩展规则的详细信息, 请参阅[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c5e62-117">For information about extended rules, see [[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c5e62-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="c5e62-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c5e62-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="c5e62-119">Protocol specifications</span></span>

<span data-ttu-id="c5e62-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5e62-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c5e62-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c5e62-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c5e62-122">[[毫秒-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5e62-122">[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c5e62-123">指定核心邮件存储对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="c5e62-123">Specifies permissible operations for the core message store objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c5e62-124">头文件</span><span class="sxs-lookup"><span data-stu-id="c5e62-124">Header files</span></span>

<span data-ttu-id="c5e62-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c5e62-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="c5e62-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c5e62-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="c5e62-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c5e62-127">Mapitags.h</span></span>
  
> <span data-ttu-id="c5e62-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c5e62-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c5e62-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5e62-129">See also</span></span>



[<span data-ttu-id="c5e62-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c5e62-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c5e62-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c5e62-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c5e62-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c5e62-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c5e62-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c5e62-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

