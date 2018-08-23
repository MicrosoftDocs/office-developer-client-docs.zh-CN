---
title: PidTagContentIntegrityCheck 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentIntegrityCheck
api_type:
- HeaderDef
ms.assetid: c7f10b8a-6b20-44cf-bde6-8d2b711c1c14
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 53226daafd1c0a53f96db5af3432d6f34738fd93
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585806"
---
# <a name="pidtagcontentintegritycheck-canonical-property"></a><span data-ttu-id="9b3df-103">PidTagContentIntegrityCheck 规范属性</span><span class="sxs-lookup"><span data-stu-id="9b3df-103">PidTagContentIntegrityCheck Canonical Property</span></span>

  
  
<span data-ttu-id="9b3df-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9b3df-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9b3df-105">包含允许的邮件发件人，以防止泄露消息内容到未经授权的收件人 ASN.1 内容的完整性检查值。</span><span class="sxs-lookup"><span data-stu-id="9b3df-105">Contains an ASN.1 content integrity check value that allows a message sender to protect message content from disclosure to unauthorized recipients.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9b3df-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9b3df-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9b3df-107">PR_CONTENT_INTEGRITY_CHECK</span><span class="sxs-lookup"><span data-stu-id="9b3df-107">PR_CONTENT_INTEGRITY_CHECK</span></span>  <br/> |
|<span data-ttu-id="9b3df-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="9b3df-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9b3df-109">0x0C00</span><span class="sxs-lookup"><span data-stu-id="9b3df-109">0x0C00</span></span>  <br/> |
|<span data-ttu-id="9b3df-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9b3df-110">Data type:</span></span>  <br/> |<span data-ttu-id="9b3df-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9b3df-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9b3df-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9b3df-112">Area:</span></span>  <br/> |<span data-ttu-id="9b3df-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="9b3df-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9b3df-114">注解</span><span class="sxs-lookup"><span data-stu-id="9b3df-114">Remarks</span></span>

<span data-ttu-id="9b3df-115">此属性提供的不可否认性的消息内容。</span><span class="sxs-lookup"><span data-stu-id="9b3df-115">This property provides for non-repudiation of message content.</span></span> <span data-ttu-id="9b3df-116">与**PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) 一起使用，它可以确保一条消息的内容到达目标不变。</span><span class="sxs-lookup"><span data-stu-id="9b3df-116">In conjunction with **PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)), it ensures that the content of a message arrives at its destination unchanged.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9b3df-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="9b3df-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9b3df-118">头文件</span><span class="sxs-lookup"><span data-stu-id="9b3df-118">Header files</span></span>

<span data-ttu-id="9b3df-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9b3df-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="9b3df-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9b3df-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="9b3df-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9b3df-121">Mapitags.h</span></span>
  
> <span data-ttu-id="9b3df-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9b3df-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9b3df-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b3df-123">See also</span></span>



[<span data-ttu-id="9b3df-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9b3df-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9b3df-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9b3df-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9b3df-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9b3df-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9b3df-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9b3df-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

