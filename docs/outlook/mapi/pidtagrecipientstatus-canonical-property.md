---
title: PidTagRecipientStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientStatus
api_type:
- COM
ms.assetid: b483dd42-92c0-42c2-b6f9-621daeee1659
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 2abf8085ae353ea2b50f647e5cf641708008c47d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778149"
---
# <a name="pidtagrecipientstatus-canonical-property"></a><span data-ttu-id="07054-103">PidTagRecipientStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="07054-103">PidTagRecipientStatus Canonical Property</span></span>

  
  
<span data-ttu-id="07054-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="07054-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="07054-105">包含一个值，它使用 MAPI 后台处理程序中分配传递责任之间传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="07054-105">Contains a value that is used by the MAPI spooler in assigning delivery responsibility among transport providers.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="07054-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="07054-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="07054-107">PR_RECIPIENT_STATUS</span><span class="sxs-lookup"><span data-stu-id="07054-107">PR_RECIPIENT_STATUS</span></span>  <br/> |
|<span data-ttu-id="07054-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="07054-108">Identifier:</span></span>  <br/> |<span data-ttu-id="07054-109">0x0E15</span><span class="sxs-lookup"><span data-stu-id="07054-109">0x0E15</span></span>  <br/> |
|<span data-ttu-id="07054-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="07054-110">Data type:</span></span>  <br/> |<span data-ttu-id="07054-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="07054-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="07054-112">区域：</span><span class="sxs-lookup"><span data-stu-id="07054-112">Area:</span></span>  <br/> |<span data-ttu-id="07054-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="07054-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="07054-114">备注</span><span class="sxs-lookup"><span data-stu-id="07054-114">Remarks</span></span>

<span data-ttu-id="07054-115">不要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="07054-115">Do not use this property.</span></span> <span data-ttu-id="07054-116">它是通过 MAPI 供使用。</span><span class="sxs-lookup"><span data-stu-id="07054-116">It is reserved for use by MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="07054-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="07054-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="07054-118">头文件</span><span class="sxs-lookup"><span data-stu-id="07054-118">Header files</span></span>

<span data-ttu-id="07054-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="07054-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="07054-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="07054-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="07054-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="07054-121">Mapitags.h</span></span>
  
> <span data-ttu-id="07054-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="07054-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="07054-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07054-123">See also</span></span>



[<span data-ttu-id="07054-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="07054-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="07054-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="07054-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="07054-126">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="07054-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="07054-127">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="07054-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

