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
ms.openlocfilehash: fb62c7dac13e422c52e70a223f3942e1b3bf2c78
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591805"
---
# <a name="pidtagrulelevel-canonical-property"></a><span data-ttu-id="77389-103">PidTagRuleLevel 规范属性</span><span class="sxs-lookup"><span data-stu-id="77389-103">PidTagRuleLevel Canonical Property</span></span>

  
  
<span data-ttu-id="77389-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="77389-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="77389-105">包含规则退出级别。</span><span class="sxs-lookup"><span data-stu-id="77389-105">Contains the exit level of a rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="77389-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="77389-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="77389-107">PR_RULE_LEVEL</span><span class="sxs-lookup"><span data-stu-id="77389-107">PR_RULE_LEVEL</span></span>  <br/> |
|<span data-ttu-id="77389-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="77389-108">Identifier:</span></span>  <br/> |<span data-ttu-id="77389-109">0x6683</span><span class="sxs-lookup"><span data-stu-id="77389-109">0x6683</span></span>  <br/> |
|<span data-ttu-id="77389-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="77389-110">Data type:</span></span>  <br/> |<span data-ttu-id="77389-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="77389-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="77389-112">区域：</span><span class="sxs-lookup"><span data-stu-id="77389-112">Area:</span></span>  <br/> |<span data-ttu-id="77389-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="77389-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="77389-114">注解</span><span class="sxs-lookup"><span data-stu-id="77389-114">Remarks</span></span>

<span data-ttu-id="77389-115">如果设置此属性，必须在 0x00000000 传递客户端。</span><span class="sxs-lookup"><span data-stu-id="77389-115">If setting this property, the client must pass in 0x00000000.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="77389-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="77389-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="77389-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="77389-117">Protocol specifications</span></span>

<span data-ttu-id="77389-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="77389-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="77389-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="77389-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="77389-120">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="77389-120">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="77389-121">指定连接到和配置为代理人，以及与邮件和日历项目交互的邮箱，当这些代表其他用户操作的方法。</span><span class="sxs-lookup"><span data-stu-id="77389-121">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar items when they act on behalf of another user.</span></span>
    
<span data-ttu-id="77389-122">[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="77389-122">[[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="77389-123">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="77389-123">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="77389-124">头文件</span><span class="sxs-lookup"><span data-stu-id="77389-124">Header files</span></span>

<span data-ttu-id="77389-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="77389-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="77389-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="77389-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="77389-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="77389-127">Mapitags.h</span></span>
  
> <span data-ttu-id="77389-128">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="77389-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="77389-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77389-129">See also</span></span>



[<span data-ttu-id="77389-130">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="77389-130">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="77389-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="77389-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="77389-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="77389-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="77389-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="77389-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="77389-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="77389-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

