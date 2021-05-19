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
ms.openlocfilehash: 32c81474580dbe4948c40390dadd0445776ab825
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434800"
---
# <a name="pidtagdiscardreason-canonical-property"></a><span data-ttu-id="3a49e-103">PidTagDiscardReason 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a49e-103">PidTagDiscardReason Canonical Property</span></span>

  
  
<span data-ttu-id="3a49e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3a49e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3a49e-105">包含邮件传输代理在 MTA (丢弃) 的原因。</span><span class="sxs-lookup"><span data-stu-id="3a49e-105">Contains a reason why a message transfer agent (MTA) has discarded a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3a49e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3a49e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3a49e-107">PR_DISCARD_REASON</span><span class="sxs-lookup"><span data-stu-id="3a49e-107">PR_DISCARD_REASON</span></span>  <br/> |
|<span data-ttu-id="3a49e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3a49e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3a49e-109">0x0011</span><span class="sxs-lookup"><span data-stu-id="3a49e-109">0x0011</span></span>  <br/> |
|<span data-ttu-id="3a49e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3a49e-110">Data type:</span></span>  <br/> |<span data-ttu-id="3a49e-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="3a49e-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="3a49e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3a49e-112">Area:</span></span>  <br/> |<span data-ttu-id="3a49e-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="3a49e-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3a49e-114">备注</span><span class="sxs-lookup"><span data-stu-id="3a49e-114">Remarks</span></span>

<span data-ttu-id="3a49e-115">此属性中包含的原因在邮件的未送达报告中使用。</span><span class="sxs-lookup"><span data-stu-id="3a49e-115">The reason contained in this property is used in a nondelivery report for the message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3a49e-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="3a49e-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="3a49e-117">头文件</span><span class="sxs-lookup"><span data-stu-id="3a49e-117">Header files</span></span>

<span data-ttu-id="3a49e-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3a49e-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="3a49e-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3a49e-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="3a49e-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3a49e-120">Mapitags.h</span></span>
  
> <span data-ttu-id="3a49e-121">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3a49e-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3a49e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a49e-122">See also</span></span>



[<span data-ttu-id="3a49e-123">PidTagNonDeliveryReportReasonCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a49e-123">PidTagNonDeliveryReportReasonCode Canonical Property</span></span>](pidtagnondeliveryreportreasoncode-canonical-property.md)


[<span data-ttu-id="3a49e-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3a49e-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3a49e-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a49e-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3a49e-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3a49e-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3a49e-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3a49e-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

