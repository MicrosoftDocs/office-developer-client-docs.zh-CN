---
title: PidTagReceiptTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceiptTime
api_type:
- COM
ms.assetid: 9c6cd2f4-e769-4786-b9cc-c02641fecc4f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0d0b8f3a394d2ec2239e8ab186d4021b60b00ea4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778121"
---
# <a name="pidtagreceipttime-canonical-property"></a><span data-ttu-id="b3171-103">PidTagReceiptTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3171-103">PidTagReceiptTime Canonical Property</span></span>

  
  
<span data-ttu-id="b3171-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b3171-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b3171-105">包含的日期和时间生成的送达报告。</span><span class="sxs-lookup"><span data-stu-id="b3171-105">Contains the date and time a delivery report is generated.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b3171-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b3171-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b3171-107">PR_RECEIPT_TIME</span><span class="sxs-lookup"><span data-stu-id="b3171-107">PR_RECEIPT_TIME</span></span>  <br/> |
|<span data-ttu-id="b3171-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b3171-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b3171-109">0x002A</span><span class="sxs-lookup"><span data-stu-id="b3171-109">0x002A</span></span>  <br/> |
|<span data-ttu-id="b3171-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b3171-110">Data type:</span></span>  <br/> |<span data-ttu-id="b3171-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="b3171-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="b3171-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b3171-112">Area:</span></span>  <br/> |<span data-ttu-id="b3171-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="b3171-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b3171-114">说明</span><span class="sxs-lookup"><span data-stu-id="b3171-114">Remarks</span></span>

<span data-ttu-id="b3171-115">此属性必须设置消息存储提供程序接收邮件列表并生成报表。</span><span class="sxs-lookup"><span data-stu-id="b3171-115">This property must be set by the message store provider receiving the original message and generating the report.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b3171-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="b3171-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="b3171-117">头文件</span><span class="sxs-lookup"><span data-stu-id="b3171-117">Header files</span></span>

<span data-ttu-id="b3171-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b3171-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="b3171-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b3171-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="b3171-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b3171-120">Mapitags.h</span></span>
  
> <span data-ttu-id="b3171-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b3171-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b3171-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3171-122">See also</span></span>



[<span data-ttu-id="b3171-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b3171-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b3171-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3171-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b3171-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b3171-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b3171-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b3171-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

