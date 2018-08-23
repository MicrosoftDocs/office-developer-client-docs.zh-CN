---
title: PidTagDiscardReason 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDiscardReason
api_type:
- HeaderDef
ms.assetid: 5004dc1f-6bd3-4764-b83c-d04d83161dba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8835b7234a209d5cb80a19593632380f6d83826
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593156"
---
# <a name="pidtagdiscardreason-canonical-property"></a><span data-ttu-id="50bad-103">PidTagDiscardReason 规范属性</span><span class="sxs-lookup"><span data-stu-id="50bad-103">PidTagDiscardReason Canonical Property</span></span>

  
  
<span data-ttu-id="50bad-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="50bad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="50bad-105">包含邮件传输代理 (MTA) 为什么已丢弃的消息的原因。</span><span class="sxs-lookup"><span data-stu-id="50bad-105">Contains a reason why a message transfer agent (MTA) has discarded a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="50bad-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="50bad-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="50bad-107">PR_DISCARD_REASON</span><span class="sxs-lookup"><span data-stu-id="50bad-107">PR_DISCARD_REASON</span></span>  <br/> |
|<span data-ttu-id="50bad-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="50bad-108">Identifier:</span></span>  <br/> |<span data-ttu-id="50bad-109">0x0011</span><span class="sxs-lookup"><span data-stu-id="50bad-109">0x0011</span></span>  <br/> |
|<span data-ttu-id="50bad-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="50bad-110">Data type:</span></span>  <br/> |<span data-ttu-id="50bad-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="50bad-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="50bad-112">区域：</span><span class="sxs-lookup"><span data-stu-id="50bad-112">Area:</span></span>  <br/> |<span data-ttu-id="50bad-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="50bad-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="50bad-114">注解</span><span class="sxs-lookup"><span data-stu-id="50bad-114">Remarks</span></span>

<span data-ttu-id="50bad-115">此属性中包含的原因是原件报表中使用的邮件。</span><span class="sxs-lookup"><span data-stu-id="50bad-115">The reason contained in this property is used in a nondelivery report for the message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="50bad-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="50bad-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="50bad-117">头文件</span><span class="sxs-lookup"><span data-stu-id="50bad-117">Header files</span></span>

<span data-ttu-id="50bad-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="50bad-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="50bad-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="50bad-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="50bad-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="50bad-120">Mapitags.h</span></span>
  
> <span data-ttu-id="50bad-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="50bad-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="50bad-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50bad-122">See also</span></span>



[<span data-ttu-id="50bad-123">PidTagNonDeliveryReportReasonCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="50bad-123">PidTagNonDeliveryReportReasonCode Canonical Property</span></span>](pidtagnondeliveryreportreasoncode-canonical-property.md)


[<span data-ttu-id="50bad-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="50bad-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="50bad-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="50bad-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="50bad-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="50bad-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="50bad-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="50bad-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

