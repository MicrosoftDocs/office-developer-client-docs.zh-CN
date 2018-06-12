---
title: PidTagOriginallyIntendedRecipEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginallyIntendedRecipEmailAddress
api_type:
- COM
ms.assetid: 6a85b695-731a-4401-9c9c-fda6bc308558
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: e24ae5f56a043d810eb805720606fd5b44d60cba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777937"
---
# <a name="pidtagoriginallyintendedrecipemailaddress-canonical-property"></a><span data-ttu-id="77ef6-103">PidTagOriginallyIntendedRecipEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="77ef6-103">PidTagOriginallyIntendedRecipEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="77ef6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="77ef6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="77ef6-105">包含自动转发邮件的最初预期接收人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="77ef6-105">Contains the email address of the originally intended recipient of an autoforwarded message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="77ef6-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="77ef6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="77ef6-107">PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS，PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_A，PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="77ef6-107">PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS, PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_A, PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="77ef6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="77ef6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="77ef6-109">0x007C</span><span class="sxs-lookup"><span data-stu-id="77ef6-109">0x007C</span></span>  <br/> |
|<span data-ttu-id="77ef6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="77ef6-110">Data type:</span></span>  <br/> |<span data-ttu-id="77ef6-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="77ef6-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="77ef6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="77ef6-112">Area:</span></span>  <br/> |<span data-ttu-id="77ef6-113">Server</span><span class="sxs-lookup"><span data-stu-id="77ef6-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="77ef6-114">备注</span><span class="sxs-lookup"><span data-stu-id="77ef6-114">Remarks</span></span>

<span data-ttu-id="77ef6-115">这些属性是在最初预期的邮件收件人的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="77ef6-115">These properties are examples of the address properties for the originally intended message recipient.</span></span> <span data-ttu-id="77ef6-116">它们必须已转发邮件的自动代理设置。</span><span class="sxs-lookup"><span data-stu-id="77ef6-116">They must be set by the automatic agent that has forwarded the message.</span></span>
  
<span data-ttu-id="77ef6-117">这些属性对应于 X.400 报告每个收件人属性。</span><span class="sxs-lookup"><span data-stu-id="77ef6-117">These properties correspond to the X.400 report per-recipient attribute.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="77ef6-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="77ef6-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="77ef6-119">头文件</span><span class="sxs-lookup"><span data-stu-id="77ef6-119">Header files</span></span>

<span data-ttu-id="77ef6-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="77ef6-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="77ef6-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="77ef6-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="77ef6-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="77ef6-122">Mapitags.h</span></span>
  
> <span data-ttu-id="77ef6-123">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="77ef6-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="77ef6-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77ef6-124">See also</span></span>



[<span data-ttu-id="77ef6-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="77ef6-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="77ef6-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="77ef6-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="77ef6-127">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="77ef6-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="77ef6-128">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="77ef6-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

