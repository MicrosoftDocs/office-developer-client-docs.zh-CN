---
title: PidTagRuleLevel 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleLevel
api_type:
- COM
ms.assetid: b1a30543-250d-4afb-87f2-448d90ee7cf9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3de5093f1fa395b1fba061f88a9b67b5dedf4740
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359526"
---
# <a name="pidtagrulelevel-canonical-property"></a><span data-ttu-id="92858-103">PidTagRuleLevel 规范属性</span><span class="sxs-lookup"><span data-stu-id="92858-103">PidTagRuleLevel Canonical Property</span></span>

  
  
<span data-ttu-id="92858-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="92858-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="92858-105">包含规则的退出级别。</span><span class="sxs-lookup"><span data-stu-id="92858-105">Contains the exit level of a rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="92858-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="92858-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="92858-107">PR_RULE_LEVEL</span><span class="sxs-lookup"><span data-stu-id="92858-107">PR_RULE_LEVEL</span></span>  <br/> |
|<span data-ttu-id="92858-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="92858-108">Identifier:</span></span>  <br/> |<span data-ttu-id="92858-109">0x6683</span><span class="sxs-lookup"><span data-stu-id="92858-109">0x6683</span></span>  <br/> |
|<span data-ttu-id="92858-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="92858-110">Data type:</span></span>  <br/> |<span data-ttu-id="92858-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="92858-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="92858-112">区域：</span><span class="sxs-lookup"><span data-stu-id="92858-112">Area:</span></span>  <br/> |<span data-ttu-id="92858-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="92858-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="92858-114">注解</span><span class="sxs-lookup"><span data-stu-id="92858-114">Remarks</span></span>

<span data-ttu-id="92858-115">如果设置此属性, 则客户端必须在0x00000000 中传递。</span><span class="sxs-lookup"><span data-stu-id="92858-115">If setting this property, the client must pass in 0x00000000.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="92858-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="92858-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="92858-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="92858-117">Protocol specifications</span></span>

<span data-ttu-id="92858-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="92858-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="92858-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="92858-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="92858-120">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="92858-120">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="92858-121">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历项目代表另一个用户操作时与之进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="92858-121">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar items when they act on behalf of another user.</span></span>
    
<span data-ttu-id="92858-122">[[毫秒-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="92858-122">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="92858-123">在服务器上操纵传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="92858-123">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="92858-124">头文件</span><span class="sxs-lookup"><span data-stu-id="92858-124">Header files</span></span>

<span data-ttu-id="92858-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="92858-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="92858-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="92858-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="92858-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="92858-127">Mapitags.h</span></span>
  
> <span data-ttu-id="92858-128">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="92858-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="92858-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92858-129">See also</span></span>



[<span data-ttu-id="92858-130">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="92858-130">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="92858-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="92858-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="92858-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="92858-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="92858-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="92858-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="92858-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="92858-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

