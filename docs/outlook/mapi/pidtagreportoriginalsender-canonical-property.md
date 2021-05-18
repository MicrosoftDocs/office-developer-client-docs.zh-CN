---
title: PidTagReportOriginalSender 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 429811c4-73fe-4a05-9c42-e5ac8e974f29
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4fc3d2751841cb2fb119e7b1695c93260758dcea
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413904"
---
# <a name="pidtagreportoriginalsender-canonical-property"></a><span data-ttu-id="b3132-103">PidTagReportOriginalSender 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3132-103">PidTagReportOriginalSender Canonical Property</span></span>

  
  
<span data-ttu-id="b3132-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b3132-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b3132-105">指示请求接收的邮件的原始发件人。</span><span class="sxs-lookup"><span data-stu-id="b3132-105">Indicates the original sender of the message for messages that request receipts.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b3132-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b3132-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b3132-107">PR_REPORT_ORIGINAL_SENDER、PR_REPORT_ORIGINAL_SENDER_A、PR_REPORT_ORIGINAL_SENDER_W</span><span class="sxs-lookup"><span data-stu-id="b3132-107">PR_REPORT_ORIGINAL_SENDER, PR_REPORT_ORIGINAL_SENDER_A, PR_REPORT_ORIGINAL_SENDER_W</span></span>  <br/> |
|<span data-ttu-id="b3132-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b3132-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b3132-109">0x0082</span><span class="sxs-lookup"><span data-stu-id="b3132-109">0x0082</span></span>  <br/> |
|<span data-ttu-id="b3132-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b3132-110">Data type:</span></span>  <br/> |<span data-ttu-id="b3132-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b3132-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b3132-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b3132-112">Area:</span></span>  <br/> |<span data-ttu-id="b3132-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="b3132-113">MAPI envelope</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="b3132-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="b3132-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b3132-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="b3132-115">Protocol specifications</span></span>

<span data-ttu-id="b3132-116">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="b3132-116">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="b3132-117">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="b3132-117">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b3132-118">头文件</span><span class="sxs-lookup"><span data-stu-id="b3132-118">Header files</span></span>

<span data-ttu-id="b3132-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b3132-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="b3132-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b3132-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="b3132-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b3132-121">Mapitags.h</span></span>
  
> <span data-ttu-id="b3132-122">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b3132-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b3132-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3132-123">See also</span></span>



[<span data-ttu-id="b3132-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b3132-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b3132-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3132-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b3132-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b3132-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b3132-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b3132-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

