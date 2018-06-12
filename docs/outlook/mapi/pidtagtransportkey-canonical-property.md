---
title: PidTagTransportKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTransportKey
api_type:
- COM
ms.assetid: 131211b3-e6f9-4dd4-b6d9-b65361bff775
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 77b302e3c8ae06fb7578fc8fcf9ba8f27d552e18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778515"
---
# <a name="pidtagtransportkey-canonical-property"></a><span data-ttu-id="d8989-103">PidTagTransportKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8989-103">PidTagTransportKey Canonical Property</span></span>

  
  
<span data-ttu-id="d8989-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d8989-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d8989-105">包含由 MAPI 后台处理程序来跟踪进度的出站邮件通过传出传输提供程序的值。</span><span class="sxs-lookup"><span data-stu-id="d8989-105">Contains a value used by the MAPI spooler to track the progress of an outbound message through the outgoing transport providers.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d8989-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="d8989-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d8989-107">PR_TRANSPORT_KEY</span><span class="sxs-lookup"><span data-stu-id="d8989-107">PR_TRANSPORT_KEY</span></span>  <br/> |
|<span data-ttu-id="d8989-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d8989-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d8989-109">0x0E16</span><span class="sxs-lookup"><span data-stu-id="d8989-109">0x0E16</span></span>  <br/> |
|<span data-ttu-id="d8989-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d8989-110">Data type:</span></span>  <br/> |<span data-ttu-id="d8989-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d8989-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d8989-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d8989-112">Area:</span></span>  <br/> |<span data-ttu-id="d8989-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="d8989-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d8989-114">备注</span><span class="sxs-lookup"><span data-stu-id="d8989-114">Remarks</span></span>

<span data-ttu-id="d8989-115">不要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="d8989-115">Do not use this property.</span></span> <span data-ttu-id="d8989-116">它是通过 MAPI 供使用。</span><span class="sxs-lookup"><span data-stu-id="d8989-116">It is reserved for use by MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d8989-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d8989-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d8989-118">头文件</span><span class="sxs-lookup"><span data-stu-id="d8989-118">Header files</span></span>

<span data-ttu-id="d8989-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d8989-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="d8989-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d8989-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="d8989-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d8989-121">Mapitags.h</span></span>
  
> <span data-ttu-id="d8989-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d8989-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d8989-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8989-123">See also</span></span>



[<span data-ttu-id="d8989-124">PidTagTransportProviders 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8989-124">PidTagTransportProviders Canonical Property</span></span>](pidtagtransportproviders-canonical-property.md)


[<span data-ttu-id="d8989-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d8989-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d8989-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8989-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d8989-127">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d8989-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d8989-128">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d8989-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

