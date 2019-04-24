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
ms.openlocfilehash: ea217808a163c7f16bbaa3c5a959fd32c8cbe10c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357916"
---
# <a name="pidtagcorrelate-canonical-property"></a><span data-ttu-id="9cd96-103">PidTagCorrelate 规范属性</span><span class="sxs-lookup"><span data-stu-id="9cd96-103">PidTagCorrelate Canonical Property</span></span>

  
  
<span data-ttu-id="9cd96-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9cd96-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9cd96-105">如果邮件的发件人请求邮件系统的关联功能, 则该参数包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9cd96-105">Contains TRUE if the sender of a message requests the correlation feature of the messaging system.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9cd96-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9cd96-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9cd96-107">PR_CORRELATE</span><span class="sxs-lookup"><span data-stu-id="9cd96-107">PR_CORRELATE</span></span>  <br/> |
|<span data-ttu-id="9cd96-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9cd96-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9cd96-109">0x0E0C</span><span class="sxs-lookup"><span data-stu-id="9cd96-109">0x0E0C</span></span>  <br/> |
|<span data-ttu-id="9cd96-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9cd96-110">Data type:</span></span>  <br/> |<span data-ttu-id="9cd96-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="9cd96-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="9cd96-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9cd96-112">Area:</span></span>  <br/> |<span data-ttu-id="9cd96-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="9cd96-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9cd96-114">注解</span><span class="sxs-lookup"><span data-stu-id="9cd96-114">Remarks</span></span>

<span data-ttu-id="9cd96-115">此属性用于请求与原始已发送邮件的传入报告的关联。</span><span class="sxs-lookup"><span data-stu-id="9cd96-115">This property is used to request the correlation of incoming reports with the original sent message.</span></span> <span data-ttu-id="9cd96-116">当传输提供程序遇到**PR_CORRELATE**设置为 TRUE 的已提交邮件时, 它会将**PR_CORRELATE_MTSID** ([PidTagCorrelateMtsid](pidtagcorrelatemtsid-canonical-property.md)) 属性设置为该邮件的邮件传输系统 (MTS) 标识符。</span><span class="sxs-lookup"><span data-stu-id="9cd96-116">When a transport provider encounters a submitted message with **PR_CORRELATE** set to TRUE, it sets the **PR_CORRELATE_MTSID** ([PidTagCorrelateMtsid](pidtagcorrelatemtsid-canonical-property.md)) property to the message transfer system (MTS) identifier for that message.</span></span>
  
 <span data-ttu-id="9cd96-117">**PR_CORRELATE**应与支持按 MTS 标识符的关联的邮件系统结合使用, 例如, X. 400。</span><span class="sxs-lookup"><span data-stu-id="9cd96-117">**PR_CORRELATE** should be used with messaging systems that support correlation by MTS identifier, such as X.400.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="9cd96-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="9cd96-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9cd96-119">头文件</span><span class="sxs-lookup"><span data-stu-id="9cd96-119">Header files</span></span>

<span data-ttu-id="9cd96-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="9cd96-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="9cd96-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9cd96-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="9cd96-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="9cd96-122">Mapitags.h</span></span>
  
> <span data-ttu-id="9cd96-123">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9cd96-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9cd96-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cd96-124">See also</span></span>



[<span data-ttu-id="9cd96-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9cd96-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9cd96-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9cd96-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9cd96-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9cd96-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9cd96-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9cd96-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

