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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9ea9938ca9f8dd0b25cf2de5199178a76e17b6d0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361178"
---
# <a name="pidtagtnefunprocessedprops-canonical-property"></a><span data-ttu-id="c7855-103">PidTagTnefUnprocessedProps 规范属性</span><span class="sxs-lookup"><span data-stu-id="c7855-103">PidTagTnefUnprocessedProps Canonical Property</span></span>

  
  
<span data-ttu-id="c7855-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7855-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7855-105">筛选传输中性封装格式 (TNEF) 时序列化属性。</span><span class="sxs-lookup"><span data-stu-id="c7855-105">Serializes properties when filtering Transport Neutral Encapsulation Format (TNEF).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c7855-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c7855-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c7855-107">PR_TNEF_UNPROCESSED_PROPS</span><span class="sxs-lookup"><span data-stu-id="c7855-107">PR_TNEF_UNPROCESSED_PROPS</span></span>  <br/> |
|<span data-ttu-id="c7855-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c7855-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c7855-109">0x0E9C</span><span class="sxs-lookup"><span data-stu-id="c7855-109">0x0E9C</span></span>  <br/> |
|<span data-ttu-id="c7855-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c7855-110">Data type:</span></span>  <br/> |<span data-ttu-id="c7855-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="c7855-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="c7855-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c7855-112">Area:</span></span>  <br/> |<span data-ttu-id="c7855-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="c7855-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c7855-114">注解</span><span class="sxs-lookup"><span data-stu-id="c7855-114">Remarks</span></span>

<span data-ttu-id="c7855-115">Microsoft outlook 和 Outlook Web Access (OWA) 用于保存原始 tnef, 在 TNEF 中包含无法在存储中创建的命名属性的情况下。</span><span class="sxs-lookup"><span data-stu-id="c7855-115">Used by Microsoft Outlook and Outlook Web Access (OWA) for saving the original TNEF in cases where the TNEF contains named properties that cannot be created in the store.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c7855-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="c7855-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c7855-117">头文件</span><span class="sxs-lookup"><span data-stu-id="c7855-117">Header files</span></span>

<span data-ttu-id="c7855-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c7855-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="c7855-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c7855-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="c7855-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c7855-120">Mapitags.h</span></span>
  
> <span data-ttu-id="c7855-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c7855-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c7855-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7855-122">See also</span></span>



[<span data-ttu-id="c7855-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c7855-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c7855-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c7855-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c7855-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c7855-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c7855-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c7855-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

