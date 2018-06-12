---
title: PidTagReportDispositionMode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 67b3c76a-f6f7-462b-955c-dc7b53e7e7eb
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bc2d577ad6c6b430c2339dfb0567ca56de0a7f8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778209"
---
# <a name="pidtagreportdispositionmode-canonical-property"></a><span data-ttu-id="03343-103">PidTagReportDispositionMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="03343-103">PidTagReportDispositionMode Canonical Property</span></span>

  
  
<span data-ttu-id="03343-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="03343-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="03343-105">指示对回执请求收款的邮件的处置。</span><span class="sxs-lookup"><span data-stu-id="03343-105">Indicates the disposition of the receipt for messages that request receipts.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="03343-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="03343-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="03343-107">PR_REPORT_DISPOSITION_MODE，PR_REPORT_DISPOSITION_MODE_A，PR_REPORT_DISPOSITION_MODE_W</span><span class="sxs-lookup"><span data-stu-id="03343-107">PR_REPORT_DISPOSITION_MODE, PR_REPORT_DISPOSITION_MODE_A, PR_REPORT_DISPOSITION_MODE_W</span></span>  <br/> |
|<span data-ttu-id="03343-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="03343-108">Identifier:</span></span>  <br/> |<span data-ttu-id="03343-109">0x0081</span><span class="sxs-lookup"><span data-stu-id="03343-109">0x0081</span></span>  <br/> |
|<span data-ttu-id="03343-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="03343-110">Data type:</span></span>  <br/> |<span data-ttu-id="03343-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="03343-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="03343-112">区域：</span><span class="sxs-lookup"><span data-stu-id="03343-112">Area:</span></span>  <br/> |<span data-ttu-id="03343-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="03343-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="03343-114">备注</span><span class="sxs-lookup"><span data-stu-id="03343-114">Remarks</span></span>

<span data-ttu-id="03343-115">此属性可能的值为"手动-操作/MDN-发送-自动"和"手动-操作/MDN-发送-手动"。</span><span class="sxs-lookup"><span data-stu-id="03343-115">The possible values for this property are "manual-action/MDN-sent-automatically" and "manual-action/MDN-sent-manually".</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="03343-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="03343-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="03343-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="03343-117">Protocol specifications</span></span>

<span data-ttu-id="03343-118">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="03343-118">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="03343-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="03343-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="03343-120">头文件</span><span class="sxs-lookup"><span data-stu-id="03343-120">Header files</span></span>

<span data-ttu-id="03343-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="03343-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="03343-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="03343-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="03343-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="03343-123">Mapitags.h</span></span>
  
> <span data-ttu-id="03343-124">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="03343-124">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="03343-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03343-125">See also</span></span>



[<span data-ttu-id="03343-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="03343-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="03343-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="03343-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="03343-128">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="03343-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="03343-129">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="03343-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

