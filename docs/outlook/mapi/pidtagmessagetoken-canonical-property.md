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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2d832b3a53f8056c034b5e87f1f309fa3058173d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408185"
---
# <a name="pidtagmessagetoken-canonical-property"></a><span data-ttu-id="c6031-103">PidTagMessageToken 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6031-103">PidTagMessageToken Canonical Property</span></span>

  
  
<span data-ttu-id="c6031-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c6031-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c6031-105">包含一个 ASN. 1 邮件的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="c6031-105">Contains an ASN.1 security token for a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c6031-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c6031-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c6031-107">PR_MESSAGE_TOKEN</span><span class="sxs-lookup"><span data-stu-id="c6031-107">PR_MESSAGE_TOKEN</span></span>  <br/> |
|<span data-ttu-id="c6031-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c6031-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c6031-109">0x0C03</span><span class="sxs-lookup"><span data-stu-id="c6031-109">0x0C03</span></span>  <br/> |
|<span data-ttu-id="c6031-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c6031-110">Data type:</span></span>  <br/> |<span data-ttu-id="c6031-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="c6031-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="c6031-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c6031-112">Area:</span></span>  <br/> |<span data-ttu-id="c6031-113">安全邮件传递属性</span><span class="sxs-lookup"><span data-stu-id="c6031-113">Secure Messaging Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c6031-114">说明</span><span class="sxs-lookup"><span data-stu-id="c6031-114">Remarks</span></span>

<span data-ttu-id="c6031-115">此属性可将受保护的与安全相关的信息从其原始发件人传达给收件人。</span><span class="sxs-lookup"><span data-stu-id="c6031-115">This property conveys protected security-related information from its originator to its recipient.</span></span> <span data-ttu-id="c6031-116">与**PR_MESSAGE_SECURITY_LABEL** ([PidTagMessageSecurityLabel](pidtagmessagesecuritylabel-canonical-property.md)) 属性结合使用时, 它可保证标签与邮件内容的关联。</span><span class="sxs-lookup"><span data-stu-id="c6031-116">In conjunction with the **PR_MESSAGE_SECURITY_LABEL** ([PidTagMessageSecurityLabel](pidtagmessagesecuritylabel-canonical-property.md)) property, it guarantees the label's association with the message content.</span></span> <span data-ttu-id="c6031-117">与**PR_CONTENT_INTEGRITY_CHECK** ([PidTagContentIntegrityCheck](pidtagcontentintegritycheck-canonical-property.md)) 属性结合使用时, 它将验证邮件内容是否保持不变。</span><span class="sxs-lookup"><span data-stu-id="c6031-117">In conjunction with the **PR_CONTENT_INTEGRITY_CHECK** ([PidTagContentIntegrityCheck](pidtagcontentintegritycheck-canonical-property.md)) property, it verifies that the message content is unchanged.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c6031-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="c6031-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c6031-119">头文件</span><span class="sxs-lookup"><span data-stu-id="c6031-119">Header files</span></span>

<span data-ttu-id="c6031-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c6031-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="c6031-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c6031-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="c6031-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c6031-122">Mapitags.h</span></span>
  
> <span data-ttu-id="c6031-123">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c6031-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c6031-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6031-124">See also</span></span>



[<span data-ttu-id="c6031-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c6031-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c6031-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6031-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c6031-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c6031-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c6031-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c6031-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

