---
title: PidTagContentCorrelator 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentCorrelator
api_type:
- HeaderDef
ms.assetid: 0bf78879-2f9f-4c29-b1f4-2f4882d8464d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96e0e3152a70eb2913c4559afd99e25adff48ca9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438524"
---
# <a name="pidtagcontentcorrelator-canonical-property"></a><span data-ttu-id="975e0-103">PidTagContentCorrelator 规范属性</span><span class="sxs-lookup"><span data-stu-id="975e0-103">PidTagContentCorrelator Canonical Property</span></span>

  
  
<span data-ttu-id="975e0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="975e0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="975e0-105">包含邮件发件人可用于将报告与原始邮件相匹配的值。</span><span class="sxs-lookup"><span data-stu-id="975e0-105">Contains a value the message sender can use to match a report with the original message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="975e0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="975e0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="975e0-107">PR_CONTENT_CORRELATOR</span><span class="sxs-lookup"><span data-stu-id="975e0-107">PR_CONTENT_CORRELATOR</span></span>  <br/> |
|<span data-ttu-id="975e0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="975e0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="975e0-109">0x0007</span><span class="sxs-lookup"><span data-stu-id="975e0-109">0x0007</span></span>  <br/> |
|<span data-ttu-id="975e0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="975e0-110">Data type:</span></span>  <br/> |<span data-ttu-id="975e0-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="975e0-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="975e0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="975e0-112">Area:</span></span>  <br/> |<span data-ttu-id="975e0-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="975e0-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="975e0-114">备注</span><span class="sxs-lookup"><span data-stu-id="975e0-114">Remarks</span></span>

<span data-ttu-id="975e0-115">二进制字符串的内容由邮件发起方定义。</span><span class="sxs-lookup"><span data-stu-id="975e0-115">The contents of the binary string are defined by the message originator.</span></span> <span data-ttu-id="975e0-116">如果对传出邮件进行设置，则此属性应复制到为响应邮件而生成的任何报告中。</span><span class="sxs-lookup"><span data-stu-id="975e0-116">If set on an outgoing message, this property should be copied onto any reports generated in response to the message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="975e0-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="975e0-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="975e0-118">头文件</span><span class="sxs-lookup"><span data-stu-id="975e0-118">Header files</span></span>

<span data-ttu-id="975e0-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="975e0-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="975e0-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="975e0-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="975e0-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="975e0-121">Mapitags.h</span></span>
  
> <span data-ttu-id="975e0-122">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="975e0-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="975e0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="975e0-123">See also</span></span>



[<span data-ttu-id="975e0-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="975e0-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="975e0-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="975e0-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="975e0-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="975e0-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="975e0-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="975e0-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

