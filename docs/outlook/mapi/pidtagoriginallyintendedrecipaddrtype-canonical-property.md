---
title: PidTagOriginallyIntendedRecipAddrtype 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginallyIntendedRecipAddrtype
api_type:
- COM
ms.assetid: dcfb6bd5-bff5-4a50-aec7-4bdfdabf7631
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a826f1bdf150b42b61a61b2f53870e9f170e0777
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416088"
---
# <a name="pidtagoriginallyintendedrecipaddrtype-canonical-property"></a><span data-ttu-id="96e54-103">PidTagOriginallyIntendedRecipAddrtype 规范属性</span><span class="sxs-lookup"><span data-stu-id="96e54-103">PidTagOriginallyIntendedRecipAddrtype Canonical Property</span></span>

  
  
<span data-ttu-id="96e54-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96e54-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96e54-105">包含 autoforwarded 邮件最初预期收件人的地址类型。</span><span class="sxs-lookup"><span data-stu-id="96e54-105">Contains the address type of the originally intended recipient of an autoforwarded message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="96e54-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="96e54-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="96e54-107">PR_ORIGINALLY_INTENDED_RECIP_ADDRTYPE、PR_ORIGINALLY_INTENDED_RECIP_ADDRTYPE_A、PR_ORIGINALLY_INTENDED_RECIP_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="96e54-107">PR_ORIGINALLY_INTENDED_RECIP_ADDRTYPE, PR_ORIGINALLY_INTENDED_RECIP_ADDRTYPE_A, PR_ORIGINALLY_INTENDED_RECIP_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="96e54-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="96e54-108">Identifier:</span></span>  <br/> |<span data-ttu-id="96e54-109">0x007B</span><span class="sxs-lookup"><span data-stu-id="96e54-109">0x007B</span></span>  <br/> |
|<span data-ttu-id="96e54-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="96e54-110">Data type:</span></span>  <br/> |<span data-ttu-id="96e54-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="96e54-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="96e54-112">区域：</span><span class="sxs-lookup"><span data-stu-id="96e54-112">Area:</span></span>  <br/> |<span data-ttu-id="96e54-113">服务器</span><span class="sxs-lookup"><span data-stu-id="96e54-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="96e54-114">说明</span><span class="sxs-lookup"><span data-stu-id="96e54-114">Remarks</span></span>

<span data-ttu-id="96e54-115">这些属性是最初预期的邮件收件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="96e54-115">These properties are one of the address properties for the originally intended message recipient.</span></span> <span data-ttu-id="96e54-116">必须由已转发邮件的自动代理进行设置。</span><span class="sxs-lookup"><span data-stu-id="96e54-116">It must be set by the automatic agent that has forwarded the message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="96e54-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="96e54-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="96e54-118">头文件</span><span class="sxs-lookup"><span data-stu-id="96e54-118">Header files</span></span>

<span data-ttu-id="96e54-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="96e54-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="96e54-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="96e54-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="96e54-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="96e54-121">Mapitags.h</span></span>
  
> <span data-ttu-id="96e54-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="96e54-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="96e54-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96e54-123">See also</span></span>



[<span data-ttu-id="96e54-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="96e54-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="96e54-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="96e54-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="96e54-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="96e54-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="96e54-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="96e54-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

