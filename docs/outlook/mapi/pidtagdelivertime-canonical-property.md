---
title: PidTagDeliverTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeliverTime
api_type:
- HeaderDef
ms.assetid: da0ad17b-08ac-4c50-ac1d-13062b890dfd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3e9318e396bf195ad701b92372a3136dee7fd0d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435276"
---
# <a name="pidtagdelivertime-canonical-property"></a><span data-ttu-id="f4460-103">PidTagDeliverTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="f4460-103">PidTagDeliverTime Canonical Property</span></span>

  
  
<span data-ttu-id="f4460-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f4460-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f4460-105">包含原始邮件的送达日期和时间。</span><span class="sxs-lookup"><span data-stu-id="f4460-105">Contains the date and time when the original message was delivered.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f4460-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f4460-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f4460-107">PR_DELIVER_TIME</span><span class="sxs-lookup"><span data-stu-id="f4460-107">PR_DELIVER_TIME</span></span>  <br/> |
|<span data-ttu-id="f4460-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f4460-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f4460-109">0x0010</span><span class="sxs-lookup"><span data-stu-id="f4460-109">0x0010</span></span>  <br/> |
|<span data-ttu-id="f4460-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f4460-110">Data type:</span></span>  <br/> |<span data-ttu-id="f4460-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="f4460-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="f4460-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f4460-112">Area:</span></span>  <br/> |<span data-ttu-id="f4460-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="f4460-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f4460-114">备注</span><span class="sxs-lookup"><span data-stu-id="f4460-114">Remarks</span></span>

<span data-ttu-id="f4460-115">此属性是送达报告上的每个收件人属性，指示原始邮件传递到生成送达报告的邮件用户的时间。</span><span class="sxs-lookup"><span data-stu-id="f4460-115">This property is a per-recipient property on a delivery report that indicates the time the original message was delivered to the messaging user for which the delivery report is being generated.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f4460-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="f4460-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f4460-117">头文件</span><span class="sxs-lookup"><span data-stu-id="f4460-117">Header files</span></span>

<span data-ttu-id="f4460-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f4460-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="f4460-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f4460-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="f4460-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f4460-120">Mapitags.h</span></span>
  
> <span data-ttu-id="f4460-121">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f4460-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f4460-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4460-122">See also</span></span>



[<span data-ttu-id="f4460-123">IMAPISupport::StatusRecips</span><span class="sxs-lookup"><span data-stu-id="f4460-123">IMAPISupport::StatusRecips</span></span>](imapisupport-statusrecips.md)


[<span data-ttu-id="f4460-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f4460-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f4460-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f4460-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f4460-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f4460-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f4460-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f4460-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

