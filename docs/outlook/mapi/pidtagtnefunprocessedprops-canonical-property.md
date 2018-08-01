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
ms.openlocfilehash: ee05f2e539d379e8fe197161fa0f6453add31afb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778507"
---
# <a name="pidtagtnefunprocessedprops-canonical-property"></a><span data-ttu-id="88b78-103">PidTagTnefUnprocessedProps 规范属性</span><span class="sxs-lookup"><span data-stu-id="88b78-103">PidTagTnefUnprocessedProps Canonical Property</span></span>

  
  
<span data-ttu-id="88b78-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="88b78-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="88b78-105">筛选传输中性封装格式 (TNEF) 时，序列化属性。</span><span class="sxs-lookup"><span data-stu-id="88b78-105">Serializes properties when filtering Transport Neutral Encapsulation Format (TNEF).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="88b78-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="88b78-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="88b78-107">PR_TNEF_UNPROCESSED_PROPS</span><span class="sxs-lookup"><span data-stu-id="88b78-107">PR_TNEF_UNPROCESSED_PROPS</span></span>  <br/> |
|<span data-ttu-id="88b78-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="88b78-108">Identifier:</span></span>  <br/> |<span data-ttu-id="88b78-109">0x0E9C</span><span class="sxs-lookup"><span data-stu-id="88b78-109">0x0E9C</span></span>  <br/> |
|<span data-ttu-id="88b78-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="88b78-110">Data type:</span></span>  <br/> |<span data-ttu-id="88b78-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="88b78-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="88b78-112">区域：</span><span class="sxs-lookup"><span data-stu-id="88b78-112">Area:</span></span>  <br/> |<span data-ttu-id="88b78-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="88b78-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="88b78-114">说明</span><span class="sxs-lookup"><span data-stu-id="88b78-114">Remarks</span></span>

<span data-ttu-id="88b78-115">使用的 Microsoft Outlook 和 Outlook Web Access (OWA) 中的 TNEF 包含无法存储中创建的命名的属性的情况下保存原始 TNEF。</span><span class="sxs-lookup"><span data-stu-id="88b78-115">Used by Microsoft Outlook and Outlook Web Access (OWA) for saving the original TNEF in cases where the TNEF contains named properties that cannot be created in the store.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="88b78-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="88b78-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="88b78-117">头文件</span><span class="sxs-lookup"><span data-stu-id="88b78-117">Header files</span></span>

<span data-ttu-id="88b78-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="88b78-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="88b78-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="88b78-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="88b78-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="88b78-120">Mapitags.h</span></span>
  
> <span data-ttu-id="88b78-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="88b78-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="88b78-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88b78-122">See also</span></span>



[<span data-ttu-id="88b78-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="88b78-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="88b78-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="88b78-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="88b78-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="88b78-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="88b78-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="88b78-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

