---
title: PidTagOriginatorRequestedAlternateRecipient 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginatorRequestedAlternateRecipient
api_type:
- COM
ms.assetid: c85b7862-18bc-4e17-94db-9097e0ac4a02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 45cd0e8a95f908d7ef56d03b3ecab5d5df5bcae1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437859"
---
# <a name="pidtagoriginatorrequestedalternaterecipient-canonical-property"></a><span data-ttu-id="498e5-103">PidTagOriginatorRequestedAlternateRecipient 规范属性</span><span class="sxs-lookup"><span data-stu-id="498e5-103">PidTagOriginatorRequestedAlternateRecipient Canonical Property</span></span>

  
  
<span data-ttu-id="498e5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="498e5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="498e5-105">包含发件人指定的备用收件人的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="498e5-105">Contains an entry identifier for an alternate recipient designated by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="498e5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="498e5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="498e5-107">PR_ORIGINATOR_REQUESTED_ALTERNATE_RECIPIENT</span><span class="sxs-lookup"><span data-stu-id="498e5-107">PR_ORIGINATOR_REQUESTED_ALTERNATE_RECIPIENT</span></span>  <br/> |
|<span data-ttu-id="498e5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="498e5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="498e5-109">0x0C09</span><span class="sxs-lookup"><span data-stu-id="498e5-109">0x0C09</span></span>  <br/> |
|<span data-ttu-id="498e5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="498e5-110">Data type:</span></span>  <br/> |<span data-ttu-id="498e5-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="498e5-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="498e5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="498e5-112">Area:</span></span>  <br/> |<span data-ttu-id="498e5-113">MIME</span><span class="sxs-lookup"><span data-stu-id="498e5-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="498e5-114">备注</span><span class="sxs-lookup"><span data-stu-id="498e5-114">Remarks</span></span>

<span data-ttu-id="498e5-115">此属性用于自动前向邮件。</span><span class="sxs-lookup"><span data-stu-id="498e5-115">This property is used in autoforwarded messages.</span></span> <span data-ttu-id="498e5-116">如果不允许自动前向或尚未指定备用收件人，应生成未送达报告。</span><span class="sxs-lookup"><span data-stu-id="498e5-116">If autoforwarding is not permitted or if no alternate recipient has been designated, a nondelivery report should be generated.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="498e5-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="498e5-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="498e5-118">头文件</span><span class="sxs-lookup"><span data-stu-id="498e5-118">Header files</span></span>

<span data-ttu-id="498e5-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="498e5-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="498e5-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="498e5-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="498e5-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="498e5-121">Mapitags.h</span></span>
  
> <span data-ttu-id="498e5-122">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="498e5-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="498e5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="498e5-123">See also</span></span>



[<span data-ttu-id="498e5-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="498e5-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="498e5-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="498e5-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="498e5-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="498e5-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="498e5-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="498e5-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

