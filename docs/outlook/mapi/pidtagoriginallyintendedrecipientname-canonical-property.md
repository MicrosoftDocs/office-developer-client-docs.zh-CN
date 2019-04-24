---
title: PidTagOriginallyIntendedRecipientName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginallyIntendedRecipientName
api_type:
- COM
ms.assetid: 56c406fb-8778-4f85-bbdc-4cabfa140248
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8637ef8036ccec79b82bcfff4a9f6d21fd5c2e11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342586"
---
# <a name="pidtagoriginallyintendedrecipientname-canonical-property"></a><span data-ttu-id="53450-103">PidTagOriginallyIntendedRecipientName 规范属性</span><span class="sxs-lookup"><span data-stu-id="53450-103">PidTagOriginallyIntendedRecipientName Canonical Property</span></span>

  
  
<span data-ttu-id="53450-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53450-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53450-105">包含 autoforwarded 邮件最初预期收件人的编码名称。</span><span class="sxs-lookup"><span data-stu-id="53450-105">Contains the encoded name of the originally intended recipient of an autoforwarded message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="53450-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="53450-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="53450-107">PR_ORIGINALLY_INTENDED_RECIPIENT_NAME</span><span class="sxs-lookup"><span data-stu-id="53450-107">PR_ORIGINALLY_INTENDED_RECIPIENT_NAME</span></span>  <br/> |
|<span data-ttu-id="53450-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="53450-108">Identifier:</span></span>  <br/> |<span data-ttu-id="53450-109">0x0020</span><span class="sxs-lookup"><span data-stu-id="53450-109">0x0020</span></span>  <br/> |
|<span data-ttu-id="53450-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="53450-110">Data type:</span></span>  <br/> |<span data-ttu-id="53450-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="53450-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="53450-112">区域：</span><span class="sxs-lookup"><span data-stu-id="53450-112">Area:</span></span>  <br/> |<span data-ttu-id="53450-113">服务器</span><span class="sxs-lookup"><span data-stu-id="53450-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="53450-114">注解</span><span class="sxs-lookup"><span data-stu-id="53450-114">Remarks</span></span>

<span data-ttu-id="53450-115">**PR_ORIGINALLY_INTENDED_RECIPIENT_NAME**属性必须由已转发邮件的自动代理进行设置。</span><span class="sxs-lookup"><span data-stu-id="53450-115">The **PR_ORIGINALLY_INTENDED_RECIPIENT_NAME** property must be set by the automatic agent that has forwarded the message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="53450-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="53450-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="53450-117">头文件</span><span class="sxs-lookup"><span data-stu-id="53450-117">Header files</span></span>

<span data-ttu-id="53450-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="53450-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="53450-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="53450-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="53450-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="53450-120">Mapitags.h</span></span>
  
> <span data-ttu-id="53450-121">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="53450-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="53450-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53450-122">See also</span></span>



[<span data-ttu-id="53450-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="53450-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="53450-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="53450-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="53450-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="53450-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="53450-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="53450-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

