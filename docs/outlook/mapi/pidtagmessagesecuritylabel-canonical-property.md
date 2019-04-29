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
ms.openlocfilehash: b6900cbacc2bea6c5519efdc4281ca98629b23bf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425671"
---
# <a name="pidtagmessagesecuritylabel-canonical-property"></a><span data-ttu-id="5f98e-103">PidTagMessageSecurityLabel 规范属性</span><span class="sxs-lookup"><span data-stu-id="5f98e-103">PidTagMessageSecurityLabel Canonical Property</span></span>

  
  
<span data-ttu-id="5f98e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f98e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f98e-105">包含邮件的安全标签。</span><span class="sxs-lookup"><span data-stu-id="5f98e-105">Contains a security label for a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5f98e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5f98e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5f98e-107">PR_MESSAGE_SECURITY_LABEL</span><span class="sxs-lookup"><span data-stu-id="5f98e-107">PR_MESSAGE_SECURITY_LABEL</span></span>  <br/> |
|<span data-ttu-id="5f98e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5f98e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5f98e-109">0x001E</span><span class="sxs-lookup"><span data-stu-id="5f98e-109">0x001E</span></span>  <br/> |
|<span data-ttu-id="5f98e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5f98e-110">Data type:</span></span>  <br/> |<span data-ttu-id="5f98e-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="5f98e-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="5f98e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5f98e-112">Area:</span></span>  <br/> |<span data-ttu-id="5f98e-113">服务器</span><span class="sxs-lookup"><span data-stu-id="5f98e-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5f98e-114">说明</span><span class="sxs-lookup"><span data-stu-id="5f98e-114">Remarks</span></span>

<span data-ttu-id="5f98e-115">此属性提供**PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) 属性保护邮件的基础。</span><span class="sxs-lookup"><span data-stu-id="5f98e-115">This property provides the basis on which the **PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) property protects a message.</span></span> <span data-ttu-id="5f98e-116">令牌会保证它与邮件内容的关联。</span><span class="sxs-lookup"><span data-stu-id="5f98e-116">Its association with the message content is guaranteed by the token.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5f98e-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="5f98e-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="5f98e-118">头文件</span><span class="sxs-lookup"><span data-stu-id="5f98e-118">Header files</span></span>

<span data-ttu-id="5f98e-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="5f98e-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="5f98e-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5f98e-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="5f98e-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="5f98e-121">Mapitags.h</span></span>
  
> <span data-ttu-id="5f98e-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5f98e-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5f98e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f98e-123">See also</span></span>



[<span data-ttu-id="5f98e-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5f98e-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5f98e-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5f98e-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5f98e-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5f98e-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5f98e-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5f98e-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

