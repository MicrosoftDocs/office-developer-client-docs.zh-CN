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
ms.openlocfilehash: c7abd0ae93c5b38c756ec0915dda6a4cdfcebaa5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777993"
---
# <a name="pidtagoriginatorrequestedalternaterecipient-canonical-property"></a><span data-ttu-id="ac713-103">PidTagOriginatorRequestedAlternateRecipient 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac713-103">PidTagOriginatorRequestedAlternateRecipient Canonical Property</span></span>

  
  
<span data-ttu-id="ac713-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ac713-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ac713-105">包含的发件人指定一个备用收件人的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ac713-105">Contains an entry identifier for an alternate recipient designated by the sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ac713-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ac713-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ac713-107">PR_ORIGINATOR_REQUESTED_ALTERNATE_RECIPIENT</span><span class="sxs-lookup"><span data-stu-id="ac713-107">PR_ORIGINATOR_REQUESTED_ALTERNATE_RECIPIENT</span></span>  <br/> |
|<span data-ttu-id="ac713-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ac713-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ac713-109">0x0C09</span><span class="sxs-lookup"><span data-stu-id="ac713-109">0x0C09</span></span>  <br/> |
|<span data-ttu-id="ac713-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ac713-110">Data type:</span></span>  <br/> |<span data-ttu-id="ac713-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ac713-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ac713-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ac713-112">Area:</span></span>  <br/> |<span data-ttu-id="ac713-113">MIME</span><span class="sxs-lookup"><span data-stu-id="ac713-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ac713-114">说明</span><span class="sxs-lookup"><span data-stu-id="ac713-114">Remarks</span></span>

<span data-ttu-id="ac713-115">自动转发邮件中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="ac713-115">This property is used in autoforwarded messages.</span></span> <span data-ttu-id="ac713-116">如果不允许自动转接，或者如果已不指定任何备用收件人，应生成原件报告。</span><span class="sxs-lookup"><span data-stu-id="ac713-116">If autoforwarding is not permitted or if no alternate recipient has been designated, a nondelivery report should be generated.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ac713-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="ac713-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ac713-118">头文件</span><span class="sxs-lookup"><span data-stu-id="ac713-118">Header files</span></span>

<span data-ttu-id="ac713-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ac713-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="ac713-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ac713-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="ac713-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ac713-121">Mapitags.h</span></span>
  
> <span data-ttu-id="ac713-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ac713-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ac713-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac713-123">See also</span></span>



[<span data-ttu-id="ac713-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ac713-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ac713-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac713-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ac713-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ac713-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ac713-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ac713-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

