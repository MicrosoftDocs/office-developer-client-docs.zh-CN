---
title: PidTagTnefUnprocessedProps 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTnefUnprocessedProps
api_type:
- COM
ms.assetid: df9cd614-1198-44a2-9bf5-36c57179a9a9
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ee05f2e539d379e8fe197161fa0f6453add31afb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778507"
---
# <a name="pidtagtnefunprocessedprops-canonical-property"></a><span data-ttu-id="6b45f-103">PidTagTnefUnprocessedProps 规范属性</span><span class="sxs-lookup"><span data-stu-id="6b45f-103">PidTagTnefUnprocessedProps Canonical Property</span></span>

  
  
<span data-ttu-id="6b45f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6b45f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6b45f-105">筛选传输中性封装格式 (TNEF) 时，序列化属性。</span><span class="sxs-lookup"><span data-stu-id="6b45f-105">Serializes properties when filtering Transport Neutral Encapsulation Format (TNEF).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6b45f-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="6b45f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6b45f-107">PR_TNEF_UNPROCESSED_PROPS</span><span class="sxs-lookup"><span data-stu-id="6b45f-107">PR_TNEF_UNPROCESSED_PROPS</span></span>  <br/> |
|<span data-ttu-id="6b45f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6b45f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6b45f-109">0x0E9C</span><span class="sxs-lookup"><span data-stu-id="6b45f-109">0x0E9C</span></span>  <br/> |
|<span data-ttu-id="6b45f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6b45f-110">Data type:</span></span>  <br/> |<span data-ttu-id="6b45f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6b45f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6b45f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6b45f-112">Area:</span></span>  <br/> |<span data-ttu-id="6b45f-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="6b45f-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6b45f-114">备注</span><span class="sxs-lookup"><span data-stu-id="6b45f-114">Remarks</span></span>

<span data-ttu-id="6b45f-115">使用的 Microsoft Outlook 和 Outlook Web Access (OWA) 中的 TNEF 包含无法存储中创建的命名的属性的情况下保存原始 TNEF。</span><span class="sxs-lookup"><span data-stu-id="6b45f-115">Used by Microsoft Outlook and Outlook Web Access (OWA) for saving the original TNEF in cases where the TNEF contains named properties that cannot be created in the store.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6b45f-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="6b45f-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="6b45f-117">头文件</span><span class="sxs-lookup"><span data-stu-id="6b45f-117">Header files</span></span>

<span data-ttu-id="6b45f-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6b45f-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="6b45f-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6b45f-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="6b45f-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6b45f-120">Mapitags.h</span></span>
  
> <span data-ttu-id="6b45f-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6b45f-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6b45f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b45f-122">See also</span></span>



[<span data-ttu-id="6b45f-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6b45f-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6b45f-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6b45f-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6b45f-125">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6b45f-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6b45f-126">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6b45f-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

