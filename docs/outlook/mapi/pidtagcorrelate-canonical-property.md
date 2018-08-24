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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 063e41bf9fe306b3862e302abb4495ca56e3087b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575453"
---
# <a name="pidtagcorrelate-canonical-property"></a><span data-ttu-id="7ffc2-103">PidTagCorrelate 规范属性</span><span class="sxs-lookup"><span data-stu-id="7ffc2-103">PidTagCorrelate Canonical Property</span></span>

  
  
<span data-ttu-id="7ffc2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ffc2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ffc2-105">包含 TRUE，如果发件人的邮件请求邮件系统的相关功能。</span><span class="sxs-lookup"><span data-stu-id="7ffc2-105">Contains TRUE if the sender of a message requests the correlation feature of the messaging system.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7ffc2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7ffc2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7ffc2-107">PR_CORRELATE</span><span class="sxs-lookup"><span data-stu-id="7ffc2-107">PR_CORRELATE</span></span>  <br/> |
|<span data-ttu-id="7ffc2-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="7ffc2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7ffc2-109">0x0E0C</span><span class="sxs-lookup"><span data-stu-id="7ffc2-109">0x0E0C</span></span>  <br/> |
|<span data-ttu-id="7ffc2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7ffc2-110">Data type:</span></span>  <br/> |<span data-ttu-id="7ffc2-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="7ffc2-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="7ffc2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7ffc2-112">Area:</span></span>  <br/> |<span data-ttu-id="7ffc2-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="7ffc2-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7ffc2-114">注解</span><span class="sxs-lookup"><span data-stu-id="7ffc2-114">Remarks</span></span>

<span data-ttu-id="7ffc2-115">此属性用于请求的传入报告的原始发送邮件的相关性。</span><span class="sxs-lookup"><span data-stu-id="7ffc2-115">This property is used to request the correlation of incoming reports with the original sent message.</span></span> <span data-ttu-id="7ffc2-116">当传输提供程序遇到已提交的邮件**PR_CORRELATE**设置为 TRUE 时，它将**PR_CORRELATE_MTSID** ([PidTagCorrelateMtsid](pidtagcorrelatemtsid-canonical-property.md)) 属性设置为该邮件的邮件传输系统 (MTS) 标识符。</span><span class="sxs-lookup"><span data-stu-id="7ffc2-116">When a transport provider encounters a submitted message with **PR_CORRELATE** set to TRUE, it sets the **PR_CORRELATE_MTSID** ([PidTagCorrelateMtsid](pidtagcorrelatemtsid-canonical-property.md)) property to the message transfer system (MTS) identifier for that message.</span></span>
  
 <span data-ttu-id="7ffc2-117">通过 MTS 标识符，如 X.400，应使用消息支持相关的系统使用**PR_CORRELATE** 。</span><span class="sxs-lookup"><span data-stu-id="7ffc2-117">**PR_CORRELATE** should be used with messaging systems that support correlation by MTS identifier, such as X.400.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7ffc2-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7ffc2-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="7ffc2-119">头文件</span><span class="sxs-lookup"><span data-stu-id="7ffc2-119">Header files</span></span>

<span data-ttu-id="7ffc2-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7ffc2-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="7ffc2-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7ffc2-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="7ffc2-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7ffc2-122">Mapitags.h</span></span>
  
> <span data-ttu-id="7ffc2-123">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7ffc2-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7ffc2-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ffc2-124">See also</span></span>



[<span data-ttu-id="7ffc2-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7ffc2-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7ffc2-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7ffc2-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7ffc2-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7ffc2-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7ffc2-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7ffc2-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

