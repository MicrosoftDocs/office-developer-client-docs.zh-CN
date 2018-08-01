---
title: PidTagRuleProviderData 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleProviderData
api_type:
- COM
ms.assetid: b04a277c-b483-4f54-b360-311034b9a7ee
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 054299e6bdf685163bc23678a2070f5d702a4529
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778292"
---
# <a name="pidtagruleproviderdata-canonical-property"></a><span data-ttu-id="0d902-103">PidTagRuleProviderData 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d902-103">PidTagRuleProviderData Canonical Property</span></span>

  
  
<span data-ttu-id="0d902-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0d902-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0d902-105">客户端将使用的客户端设置不透明属性。</span><span class="sxs-lookup"><span data-stu-id="0d902-105">An opaque property that the client sets for the exclusive use of the client.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0d902-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0d902-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0d902-107">PR_RULE_PROVIDER_DATA</span><span class="sxs-lookup"><span data-stu-id="0d902-107">PR_RULE_PROVIDER_DATA</span></span>  <br/> |
|<span data-ttu-id="0d902-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="0d902-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0d902-109">0x6684</span><span class="sxs-lookup"><span data-stu-id="0d902-109">0x6684</span></span>  <br/> |
|<span data-ttu-id="0d902-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0d902-110">Data type:</span></span>  <br/> |<span data-ttu-id="0d902-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="0d902-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="0d902-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0d902-112">Area:</span></span>  <br/> |<span data-ttu-id="0d902-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="0d902-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0d902-114">说明</span><span class="sxs-lookup"><span data-stu-id="0d902-114">Remarks</span></span>

<span data-ttu-id="0d902-115">服务器必须保留此属性的值，如果它已设置由客户端，但必须规则评估和处理过程中忽略其内容。</span><span class="sxs-lookup"><span data-stu-id="0d902-115">The server must preserve the value of this property if it was set by the client but must ignore its contents during rule evaluation and processing.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0d902-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="0d902-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0d902-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="0d902-117">Protocol specifications</span></span>

<span data-ttu-id="0d902-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0d902-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0d902-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="0d902-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0d902-120">[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0d902-120">[[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0d902-121">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="0d902-121">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0d902-122">头文件</span><span class="sxs-lookup"><span data-stu-id="0d902-122">Header files</span></span>

<span data-ttu-id="0d902-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0d902-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="0d902-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0d902-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="0d902-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0d902-125">Mapitags.h</span></span>
  
> <span data-ttu-id="0d902-126">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0d902-126">Contains definitions of properties listed as associated properties.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="0d902-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d902-127">See also</span></span>



[<span data-ttu-id="0d902-128">PidTagRuleProvider 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d902-128">PidTagRuleProvider Canonical Property</span></span>](pidtagruleprovider-canonical-property.md)


[<span data-ttu-id="0d902-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0d902-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0d902-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d902-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0d902-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0d902-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0d902-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0d902-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

