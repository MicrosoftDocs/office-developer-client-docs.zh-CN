---
title: PidTagMessageToken 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageToken
api_type:
- HeaderDef
ms.assetid: fcb93346-db92-44b5-a447-59fd95f98f45
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7357b7b98d90d08f7d14e965458703e4e193f63a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777869"
---
# <a name="pidtagmessagetoken-canonical-property"></a><span data-ttu-id="daecf-103">PidTagMessageToken 规范属性</span><span class="sxs-lookup"><span data-stu-id="daecf-103">PidTagMessageToken Canonical Property</span></span>

  
  
<span data-ttu-id="daecf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="daecf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="daecf-105">包含邮件 ASN.1 安全令牌。</span><span class="sxs-lookup"><span data-stu-id="daecf-105">Contains an ASN.1 security token for a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="daecf-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="daecf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="daecf-107">PR_MESSAGE_TOKEN</span><span class="sxs-lookup"><span data-stu-id="daecf-107">PR_MESSAGE_TOKEN</span></span>  <br/> |
|<span data-ttu-id="daecf-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="daecf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="daecf-109">0x0C03</span><span class="sxs-lookup"><span data-stu-id="daecf-109">0x0C03</span></span>  <br/> |
|<span data-ttu-id="daecf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="daecf-110">Data type:</span></span>  <br/> |<span data-ttu-id="daecf-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="daecf-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="daecf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="daecf-112">Area:</span></span>  <br/> |<span data-ttu-id="daecf-113">安全邮件属性</span><span class="sxs-lookup"><span data-stu-id="daecf-113">Secure Messaging Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="daecf-114">备注</span><span class="sxs-lookup"><span data-stu-id="daecf-114">Remarks</span></span>

<span data-ttu-id="daecf-115">此属性传达受保护与安全相关信息从其原始发件人向其收件人。</span><span class="sxs-lookup"><span data-stu-id="daecf-115">This property conveys protected security-related information from its originator to its recipient.</span></span> <span data-ttu-id="daecf-116">与**PR_MESSAGE_SECURITY_LABEL** ([PidTagMessageSecurityLabel](pidtagmessagesecuritylabel-canonical-property.md)) 属性一起使用，则保证与邮件内容的标签的关联。</span><span class="sxs-lookup"><span data-stu-id="daecf-116">In conjunction with the **PR_MESSAGE_SECURITY_LABEL** ([PidTagMessageSecurityLabel](pidtagmessagesecuritylabel-canonical-property.md)) property, it guarantees the label's association with the message content.</span></span> <span data-ttu-id="daecf-117">在与**PR_CONTENT_INTEGRITY_CHECK** ([PidTagContentIntegrityCheck](pidtagcontentintegritycheck-canonical-property.md)) 属性一起使用，它验证的消息内容未更改。</span><span class="sxs-lookup"><span data-stu-id="daecf-117">In conjunction with the **PR_CONTENT_INTEGRITY_CHECK** ([PidTagContentIntegrityCheck](pidtagcontentintegritycheck-canonical-property.md)) property, it verifies that the message content is unchanged.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="daecf-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="daecf-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="daecf-119">头文件</span><span class="sxs-lookup"><span data-stu-id="daecf-119">Header files</span></span>

<span data-ttu-id="daecf-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="daecf-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="daecf-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="daecf-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="daecf-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="daecf-122">Mapitags.h</span></span>
  
> <span data-ttu-id="daecf-123">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="daecf-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="daecf-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="daecf-124">See also</span></span>



[<span data-ttu-id="daecf-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="daecf-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="daecf-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="daecf-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="daecf-127">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="daecf-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="daecf-128">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="daecf-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

