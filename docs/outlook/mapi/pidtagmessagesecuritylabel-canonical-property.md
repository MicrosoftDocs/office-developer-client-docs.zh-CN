---
title: PidTagMessageSecurityLabel 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageSecurityLabel
api_type:
- HeaderDef
ms.assetid: aae41f1b-19bb-40c7-8564-0c87a5a4e47c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a6caa322e1d266be1fe56aecd89736e757067758
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594367"
---
# <a name="pidtagmessagesecuritylabel-canonical-property"></a><span data-ttu-id="db3b2-103">PidTagMessageSecurityLabel 规范属性</span><span class="sxs-lookup"><span data-stu-id="db3b2-103">PidTagMessageSecurityLabel Canonical Property</span></span>

  
  
<span data-ttu-id="db3b2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="db3b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="db3b2-105">包含邮件安全标签。</span><span class="sxs-lookup"><span data-stu-id="db3b2-105">Contains a security label for a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="db3b2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="db3b2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="db3b2-107">PR_MESSAGE_SECURITY_LABEL</span><span class="sxs-lookup"><span data-stu-id="db3b2-107">PR_MESSAGE_SECURITY_LABEL</span></span>  <br/> |
|<span data-ttu-id="db3b2-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="db3b2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="db3b2-109">0x001E</span><span class="sxs-lookup"><span data-stu-id="db3b2-109">0x001E</span></span>  <br/> |
|<span data-ttu-id="db3b2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="db3b2-110">Data type:</span></span>  <br/> |<span data-ttu-id="db3b2-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="db3b2-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="db3b2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="db3b2-112">Area:</span></span>  <br/> |<span data-ttu-id="db3b2-113">Server</span><span class="sxs-lookup"><span data-stu-id="db3b2-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="db3b2-114">注解</span><span class="sxs-lookup"><span data-stu-id="db3b2-114">Remarks</span></span>

<span data-ttu-id="db3b2-115">此属性提供在其**PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) 属性保护邮件的基础。</span><span class="sxs-lookup"><span data-stu-id="db3b2-115">This property provides the basis on which the **PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) property protects a message.</span></span> <span data-ttu-id="db3b2-116">由令牌保证其与邮件内容的关联。</span><span class="sxs-lookup"><span data-stu-id="db3b2-116">Its association with the message content is guaranteed by the token.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="db3b2-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="db3b2-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="db3b2-118">头文件</span><span class="sxs-lookup"><span data-stu-id="db3b2-118">Header files</span></span>

<span data-ttu-id="db3b2-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="db3b2-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="db3b2-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="db3b2-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="db3b2-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="db3b2-121">Mapitags.h</span></span>
  
> <span data-ttu-id="db3b2-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="db3b2-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="db3b2-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db3b2-123">See also</span></span>



[<span data-ttu-id="db3b2-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="db3b2-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="db3b2-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="db3b2-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="db3b2-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="db3b2-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="db3b2-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="db3b2-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

