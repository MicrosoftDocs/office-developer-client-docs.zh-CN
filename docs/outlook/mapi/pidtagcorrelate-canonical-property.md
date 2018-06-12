---
title: PidTagCorrelate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagCorrelate
api_type:
- HeaderDef
ms.assetid: be34993e-ffcc-47f5-b2d4-95ffa707bc5c
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ce8573310e17e26b4e2deb4c0a0f835a6569151e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777530"
---
# <a name="pidtagcorrelate-canonical-property"></a><span data-ttu-id="da50f-103">PidTagCorrelate 规范属性</span><span class="sxs-lookup"><span data-stu-id="da50f-103">PidTagCorrelate Canonical Property</span></span>

  
  
<span data-ttu-id="da50f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="da50f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="da50f-105">包含 TRUE，如果发件人的邮件请求邮件系统的相关功能。</span><span class="sxs-lookup"><span data-stu-id="da50f-105">Contains TRUE if the sender of a message requests the correlation feature of the messaging system.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="da50f-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="da50f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="da50f-107">PR_CORRELATE</span><span class="sxs-lookup"><span data-stu-id="da50f-107">PR_CORRELATE</span></span>  <br/> |
|<span data-ttu-id="da50f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="da50f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="da50f-109">0x0E0C</span><span class="sxs-lookup"><span data-stu-id="da50f-109">0x0E0C</span></span>  <br/> |
|<span data-ttu-id="da50f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="da50f-110">Data type:</span></span>  <br/> |<span data-ttu-id="da50f-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="da50f-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="da50f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="da50f-112">Area:</span></span>  <br/> |<span data-ttu-id="da50f-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="da50f-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="da50f-114">备注</span><span class="sxs-lookup"><span data-stu-id="da50f-114">Remarks</span></span>

<span data-ttu-id="da50f-115">此属性用于请求的传入报告的原始发送邮件的相关性。</span><span class="sxs-lookup"><span data-stu-id="da50f-115">This property is used to request the correlation of incoming reports with the original sent message.</span></span> <span data-ttu-id="da50f-116">当传输提供程序遇到已提交的邮件**PR_CORRELATE**设置为 TRUE 时，它将**PR_CORRELATE_MTSID** ([PidTagCorrelateMtsid](pidtagcorrelatemtsid-canonical-property.md)) 属性设置为该邮件的邮件传输系统 (MTS) 标识符。</span><span class="sxs-lookup"><span data-stu-id="da50f-116">When a transport provider encounters a submitted message with **PR_CORRELATE** set to TRUE, it sets the **PR_CORRELATE_MTSID** ([PidTagCorrelateMtsid](pidtagcorrelatemtsid-canonical-property.md)) property to the message transfer system (MTS) identifier for that message.</span></span>
  
 <span data-ttu-id="da50f-117">通过 MTS 标识符，如 X.400，应使用消息支持相关的系统使用**PR_CORRELATE** 。</span><span class="sxs-lookup"><span data-stu-id="da50f-117">**PR_CORRELATE** should be used with messaging systems that support correlation by MTS identifier, such as X.400.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="da50f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="da50f-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="da50f-119">头文件</span><span class="sxs-lookup"><span data-stu-id="da50f-119">Header files</span></span>

<span data-ttu-id="da50f-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="da50f-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="da50f-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="da50f-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="da50f-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="da50f-122">Mapitags.h</span></span>
  
> <span data-ttu-id="da50f-123">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="da50f-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="da50f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da50f-124">See also</span></span>



[<span data-ttu-id="da50f-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="da50f-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="da50f-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="da50f-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="da50f-127">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="da50f-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="da50f-128">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="da50f-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

