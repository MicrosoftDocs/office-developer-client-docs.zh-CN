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
ms.openlocfilehash: 30ed8053c9c3d77f4831da37ddd2456ad0564a5a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331890"
---
# <a name="pidtagcontentintegritycheck-canonical-property"></a><span data-ttu-id="8ff9c-103">PidTagContentIntegrityCheck 规范属性</span><span class="sxs-lookup"><span data-stu-id="8ff9c-103">PidTagContentIntegrityCheck Canonical Property</span></span>

  
  
<span data-ttu-id="8ff9c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8ff9c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8ff9c-105">包含一个 ASN. 1 内容完整性检查值, 允许邮件发件人将邮件内容泄露给未授权的收件人。</span><span class="sxs-lookup"><span data-stu-id="8ff9c-105">Contains an ASN.1 content integrity check value that allows a message sender to protect message content from disclosure to unauthorized recipients.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8ff9c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8ff9c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8ff9c-107">PR_CONTENT_INTEGRITY_CHECK</span><span class="sxs-lookup"><span data-stu-id="8ff9c-107">PR_CONTENT_INTEGRITY_CHECK</span></span>  <br/> |
|<span data-ttu-id="8ff9c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8ff9c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8ff9c-109">0x0C00</span><span class="sxs-lookup"><span data-stu-id="8ff9c-109">0x0C00</span></span>  <br/> |
|<span data-ttu-id="8ff9c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8ff9c-110">Data type:</span></span>  <br/> |<span data-ttu-id="8ff9c-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8ff9c-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8ff9c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8ff9c-112">Area:</span></span>  <br/> |<span data-ttu-id="8ff9c-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="8ff9c-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8ff9c-114">注解</span><span class="sxs-lookup"><span data-stu-id="8ff9c-114">Remarks</span></span>

<span data-ttu-id="8ff9c-115">此属性提供对邮件内容的不可否认性的提供。</span><span class="sxs-lookup"><span data-stu-id="8ff9c-115">This property provides for non-repudiation of message content.</span></span> <span data-ttu-id="8ff9c-116">与**PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) 结合使用, 可确保邮件的内容在其目标处不变。</span><span class="sxs-lookup"><span data-stu-id="8ff9c-116">In conjunction with **PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)), it ensures that the content of a message arrives at its destination unchanged.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8ff9c-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="8ff9c-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8ff9c-118">头文件</span><span class="sxs-lookup"><span data-stu-id="8ff9c-118">Header files</span></span>

<span data-ttu-id="8ff9c-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8ff9c-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="8ff9c-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8ff9c-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="8ff9c-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8ff9c-121">Mapitags.h</span></span>
  
> <span data-ttu-id="8ff9c-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8ff9c-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8ff9c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ff9c-123">See also</span></span>



[<span data-ttu-id="8ff9c-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8ff9c-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8ff9c-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8ff9c-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8ff9c-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8ff9c-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8ff9c-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8ff9c-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

