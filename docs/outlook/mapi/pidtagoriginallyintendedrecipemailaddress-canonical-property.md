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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4a0e7325618a38addefe562c8207066dfea620f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411370"
---
# <a name="pidtagoriginallyintendedrecipemailaddress-canonical-property"></a><span data-ttu-id="2b139-103">PidTagOriginallyIntendedRecipEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="2b139-103">PidTagOriginallyIntendedRecipEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="2b139-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2b139-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2b139-105">包含 autoforwarded 邮件最初预期收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2b139-105">Contains the email address of the originally intended recipient of an autoforwarded message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2b139-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2b139-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2b139-107">PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS、PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_A、PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="2b139-107">PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS, PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_A, PR_ORIGINALLY_INTENDED_RECIP_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="2b139-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2b139-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2b139-109">0x007C</span><span class="sxs-lookup"><span data-stu-id="2b139-109">0x007C</span></span>  <br/> |
|<span data-ttu-id="2b139-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2b139-110">Data type:</span></span>  <br/> |<span data-ttu-id="2b139-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2b139-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2b139-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2b139-112">Area:</span></span>  <br/> |<span data-ttu-id="2b139-113">服务器</span><span class="sxs-lookup"><span data-stu-id="2b139-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2b139-114">说明</span><span class="sxs-lookup"><span data-stu-id="2b139-114">Remarks</span></span>

<span data-ttu-id="2b139-115">这些属性是最初预期的邮件收件人的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="2b139-115">These properties are examples of the address properties for the originally intended message recipient.</span></span> <span data-ttu-id="2b139-116">它们必须由已转发邮件的自动代理进行设置。</span><span class="sxs-lookup"><span data-stu-id="2b139-116">They must be set by the automatic agent that has forwarded the message.</span></span>
  
<span data-ttu-id="2b139-117">这些属性对应于每个收件人的 X 千位报告属性。</span><span class="sxs-lookup"><span data-stu-id="2b139-117">These properties correspond to the X.400 report per-recipient attribute.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2b139-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="2b139-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="2b139-119">头文件</span><span class="sxs-lookup"><span data-stu-id="2b139-119">Header files</span></span>

<span data-ttu-id="2b139-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="2b139-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="2b139-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2b139-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="2b139-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="2b139-122">Mapitags.h</span></span>
  
> <span data-ttu-id="2b139-123">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2b139-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2b139-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b139-124">See also</span></span>



[<span data-ttu-id="2b139-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2b139-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2b139-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2b139-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2b139-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2b139-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2b139-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2b139-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

