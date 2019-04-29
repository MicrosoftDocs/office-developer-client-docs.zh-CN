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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5494f95aaf554038f43c34e1e1e388f871a52775
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410712"
---
# <a name="pidtagrecipientstatus-canonical-property"></a><span data-ttu-id="869e3-103">PidTagRecipientStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="869e3-103">PidTagRecipientStatus Canonical Property</span></span>

  
  
<span data-ttu-id="869e3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="869e3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="869e3-105">包含 MAPI 后台处理程序在传输提供程序之间分配传递责任时使用的值。</span><span class="sxs-lookup"><span data-stu-id="869e3-105">Contains a value that is used by the MAPI spooler in assigning delivery responsibility among transport providers.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="869e3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="869e3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="869e3-107">PR_RECIPIENT_STATUS</span><span class="sxs-lookup"><span data-stu-id="869e3-107">PR_RECIPIENT_STATUS</span></span>  <br/> |
|<span data-ttu-id="869e3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="869e3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="869e3-109">0x0E15</span><span class="sxs-lookup"><span data-stu-id="869e3-109">0x0E15</span></span>  <br/> |
|<span data-ttu-id="869e3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="869e3-110">Data type:</span></span>  <br/> |<span data-ttu-id="869e3-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="869e3-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="869e3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="869e3-112">Area:</span></span>  <br/> |<span data-ttu-id="869e3-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="869e3-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="869e3-114">说明</span><span class="sxs-lookup"><span data-stu-id="869e3-114">Remarks</span></span>

<span data-ttu-id="869e3-115">不要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="869e3-115">Do not use this property.</span></span> <span data-ttu-id="869e3-116">它保留供 MAPI 使用。</span><span class="sxs-lookup"><span data-stu-id="869e3-116">It is reserved for use by MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="869e3-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="869e3-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="869e3-118">头文件</span><span class="sxs-lookup"><span data-stu-id="869e3-118">Header files</span></span>

<span data-ttu-id="869e3-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="869e3-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="869e3-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="869e3-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="869e3-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="869e3-121">Mapitags.h</span></span>
  
> <span data-ttu-id="869e3-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="869e3-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="869e3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="869e3-123">See also</span></span>



[<span data-ttu-id="869e3-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="869e3-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="869e3-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="869e3-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="869e3-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="869e3-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="869e3-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="869e3-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

