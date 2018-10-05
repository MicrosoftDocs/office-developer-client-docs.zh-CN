---
title: PidTagRuleUserFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleUserFlags
api_type:
- COM
ms.assetid: c5dfb21f-b35e-4521-bf2b-e3d03d98d75d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 235efce341e1870f0c33917f1c6d42b021727308
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392723"
---
# <a name="pidtagruleuserflags-canonical-property"></a><span data-ttu-id="156cb-103">PidTagRuleUserFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="156cb-103">PidTagRuleUserFlags Canonical Property</span></span>

  
  
<span data-ttu-id="156cb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="156cb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="156cb-105">此属性由客户端使用的客户端设置。</span><span class="sxs-lookup"><span data-stu-id="156cb-105">This property is set by the client for the exclusive use of the client.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="156cb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="156cb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="156cb-107">PR_RULE_USER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="156cb-107">PR_RULE_USER_FLAGS</span></span>  <br/> |
|<span data-ttu-id="156cb-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="156cb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="156cb-109">0x6678</span><span class="sxs-lookup"><span data-stu-id="156cb-109">0x6678</span></span>  <br/> |
|<span data-ttu-id="156cb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="156cb-110">Data type:</span></span>  <br/> |<span data-ttu-id="156cb-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="156cb-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="156cb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="156cb-112">Area:</span></span>  <br/> |<span data-ttu-id="156cb-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="156cb-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="156cb-114">说明</span><span class="sxs-lookup"><span data-stu-id="156cb-114">Remarks</span></span>

<span data-ttu-id="156cb-115">如果它已设置由客户端，服务器必须保留此属性的值。</span><span class="sxs-lookup"><span data-stu-id="156cb-115">The server must preserve the value of this property if it was set by the client.</span></span> <span data-ttu-id="156cb-116">服务器必须规则评估和处理过程中忽略它。</span><span class="sxs-lookup"><span data-stu-id="156cb-116">The server must ignore it during rule evaluation and processing.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="156cb-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="156cb-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="156cb-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="156cb-118">Protocol specifications</span></span>

<span data-ttu-id="156cb-119">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="156cb-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="156cb-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="156cb-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="156cb-121">[[MS OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="156cb-121">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="156cb-122">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="156cb-122">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="156cb-123">头文件</span><span class="sxs-lookup"><span data-stu-id="156cb-123">Header files</span></span>

<span data-ttu-id="156cb-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="156cb-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="156cb-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="156cb-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="156cb-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="156cb-126">Mapitags.h</span></span>
  
> <span data-ttu-id="156cb-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="156cb-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="156cb-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="156cb-128">See also</span></span>



[<span data-ttu-id="156cb-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="156cb-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="156cb-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="156cb-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="156cb-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="156cb-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="156cb-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="156cb-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

