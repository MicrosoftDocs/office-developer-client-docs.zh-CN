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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9b16cf3b8d0281ba8995058af6b18dbe22dcf592
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566115"
---
# <a name="pidtagreportdispositionmode-canonical-property"></a><span data-ttu-id="32fe3-103">PidTagReportDispositionMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="32fe3-103">PidTagReportDispositionMode Canonical Property</span></span>

  
  
<span data-ttu-id="32fe3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="32fe3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="32fe3-105">指示对回执请求收款的邮件的处置。</span><span class="sxs-lookup"><span data-stu-id="32fe3-105">Indicates the disposition of the receipt for messages that request receipts.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="32fe3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="32fe3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="32fe3-107">PR_REPORT_DISPOSITION_MODE，PR_REPORT_DISPOSITION_MODE_A，PR_REPORT_DISPOSITION_MODE_W</span><span class="sxs-lookup"><span data-stu-id="32fe3-107">PR_REPORT_DISPOSITION_MODE, PR_REPORT_DISPOSITION_MODE_A, PR_REPORT_DISPOSITION_MODE_W</span></span>  <br/> |
|<span data-ttu-id="32fe3-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="32fe3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="32fe3-109">0x0081</span><span class="sxs-lookup"><span data-stu-id="32fe3-109">0x0081</span></span>  <br/> |
|<span data-ttu-id="32fe3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="32fe3-110">Data type:</span></span>  <br/> |<span data-ttu-id="32fe3-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="32fe3-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="32fe3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="32fe3-112">Area:</span></span>  <br/> |<span data-ttu-id="32fe3-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="32fe3-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="32fe3-114">注解</span><span class="sxs-lookup"><span data-stu-id="32fe3-114">Remarks</span></span>

<span data-ttu-id="32fe3-115">此属性可能的值为"手动-操作/MDN-发送-自动"和"手动-操作/MDN-发送-手动"。</span><span class="sxs-lookup"><span data-stu-id="32fe3-115">The possible values for this property are "manual-action/MDN-sent-automatically" and "manual-action/MDN-sent-manually".</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="32fe3-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="32fe3-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="32fe3-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="32fe3-117">Protocol specifications</span></span>

<span data-ttu-id="32fe3-118">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="32fe3-118">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="32fe3-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="32fe3-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="32fe3-120">头文件</span><span class="sxs-lookup"><span data-stu-id="32fe3-120">Header files</span></span>

<span data-ttu-id="32fe3-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="32fe3-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="32fe3-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="32fe3-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="32fe3-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="32fe3-123">Mapitags.h</span></span>
  
> <span data-ttu-id="32fe3-124">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="32fe3-124">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="32fe3-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32fe3-125">See also</span></span>



[<span data-ttu-id="32fe3-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="32fe3-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="32fe3-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="32fe3-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="32fe3-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="32fe3-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="32fe3-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="32fe3-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

