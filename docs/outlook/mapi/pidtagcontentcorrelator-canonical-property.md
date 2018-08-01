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
ms.openlocfilehash: 2290e6751778f17defc8d1007ff62c88f1b75465
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777470"
---
# <a name="pidtagcontentcorrelator-canonical-property"></a><span data-ttu-id="a4667-103">PidTagContentCorrelator 规范属性</span><span class="sxs-lookup"><span data-stu-id="a4667-103">PidTagContentCorrelator Canonical Property</span></span>

  
  
<span data-ttu-id="a4667-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a4667-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a4667-105">包含邮件发件人可用于匹配与原始邮件报告的值。</span><span class="sxs-lookup"><span data-stu-id="a4667-105">Contains a value the message sender can use to match a report with the original message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a4667-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a4667-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a4667-107">PR_CONTENT_CORRELATOR</span><span class="sxs-lookup"><span data-stu-id="a4667-107">PR_CONTENT_CORRELATOR</span></span>  <br/> |
|<span data-ttu-id="a4667-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="a4667-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a4667-109">0x0007</span><span class="sxs-lookup"><span data-stu-id="a4667-109">0x0007</span></span>  <br/> |
|<span data-ttu-id="a4667-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a4667-110">Data type:</span></span>  <br/> |<span data-ttu-id="a4667-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="a4667-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="a4667-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a4667-112">Area:</span></span>  <br/> |<span data-ttu-id="a4667-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="a4667-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a4667-114">说明</span><span class="sxs-lookup"><span data-stu-id="a4667-114">Remarks</span></span>

<span data-ttu-id="a4667-115">由原始邮件发件人定义二进制字符串的内容。</span><span class="sxs-lookup"><span data-stu-id="a4667-115">The contents of the binary string are defined by the message originator.</span></span> <span data-ttu-id="a4667-116">如果对传出邮件，此属性的设置应复制到任何响应消息中生成的报告。</span><span class="sxs-lookup"><span data-stu-id="a4667-116">If set on an outgoing message, this property should be copied onto any reports generated in response to the message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a4667-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="a4667-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="a4667-118">头文件</span><span class="sxs-lookup"><span data-stu-id="a4667-118">Header files</span></span>

<span data-ttu-id="a4667-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a4667-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="a4667-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a4667-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="a4667-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a4667-121">Mapitags.h</span></span>
  
> <span data-ttu-id="a4667-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a4667-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a4667-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4667-123">See also</span></span>



[<span data-ttu-id="a4667-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a4667-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a4667-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a4667-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a4667-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a4667-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a4667-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a4667-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

