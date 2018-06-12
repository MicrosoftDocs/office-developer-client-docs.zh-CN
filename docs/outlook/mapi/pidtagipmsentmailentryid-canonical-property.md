---
title: PidTagIpmSentMailEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmSentMailEntryId
api_type:
- HeaderDef
ms.assetid: f6877435-6b26-4060-924f-a65591ad9538
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 2bf7665d7867b9c7151f787bbc6b3cfd802bca35
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777768"
---
# <a name="pidtagipmsentmailentryid-canonical-property"></a><span data-ttu-id="4ab30-103">PidTagIpmSentMailEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="4ab30-103">PidTagIpmSentMailEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="4ab30-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4ab30-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4ab30-105">包含标准人际邮件 (IPM) 发送邮件文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4ab30-105">Contains the entry identifier of the standard interpersonal message (IPM) Sent Items folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4ab30-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="4ab30-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4ab30-107">PR_IPM_SENTMAIL_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="4ab30-107">PR_IPM_SENTMAIL_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="4ab30-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4ab30-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4ab30-109">0x35E4</span><span class="sxs-lookup"><span data-stu-id="4ab30-109">0x35E4</span></span>  <br/> |
|<span data-ttu-id="4ab30-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4ab30-110">Data type:</span></span>  <br/> |<span data-ttu-id="4ab30-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="4ab30-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="4ab30-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4ab30-112">Area:</span></span>  <br/> |<span data-ttu-id="4ab30-113">Folder</span><span class="sxs-lookup"><span data-stu-id="4ab30-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4ab30-114">备注</span><span class="sxs-lookup"><span data-stu-id="4ab30-114">Remarks</span></span>

<span data-ttu-id="4ab30-115">已发送人际邮件是通常放置在已发送邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4ab30-115">After being sent, interpersonal messages are usually placed in the Sent Items folder.</span></span> <span data-ttu-id="4ab30-116">客户端可以使用此属性设置已提交的邮件上的**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="4ab30-116">A client can use this property to set the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property on a submitted message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="4ab30-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="4ab30-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="4ab30-118">头文件</span><span class="sxs-lookup"><span data-stu-id="4ab30-118">Header files</span></span>

<span data-ttu-id="4ab30-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4ab30-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="4ab30-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4ab30-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="4ab30-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4ab30-121">Mapitags.h</span></span>
  
> <span data-ttu-id="4ab30-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4ab30-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4ab30-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ab30-123">See also</span></span>



[<span data-ttu-id="4ab30-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4ab30-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4ab30-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4ab30-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4ab30-126">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4ab30-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4ab30-127">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4ab30-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

