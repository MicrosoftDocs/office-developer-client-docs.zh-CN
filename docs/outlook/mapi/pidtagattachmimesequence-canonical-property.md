---
title: PidTagAttachMimeSequence 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachMimeSequence
api_type:
- HeaderDef
ms.assetid: d2a84f24-b4a5-4e16-9219-7a579a31a8f8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ae9b79abea9a1b2b31867b9ed575e16e8f1c4474
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412469"
---
# <a name="pidtagattachmimesequence-canonical-property"></a><span data-ttu-id="1e26f-103">PidTagAttachMimeSequence 规范属性</span><span class="sxs-lookup"><span data-stu-id="1e26f-103">PidTagAttachMimeSequence Canonical Property</span></span>

  
  
<span data-ttu-id="1e26f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1e26f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1e26f-105">包含 mime 邮件附件的 mime 序列号。</span><span class="sxs-lookup"><span data-stu-id="1e26f-105">Contains the MIME sequence number of a MIME message attachment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1e26f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1e26f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1e26f-107">PR_ATTACH_MIME_SEQUENCE</span><span class="sxs-lookup"><span data-stu-id="1e26f-107">PR_ATTACH_MIME_SEQUENCE</span></span>  <br/> |
|<span data-ttu-id="1e26f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1e26f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1e26f-109">0x3710</span><span class="sxs-lookup"><span data-stu-id="1e26f-109">0x3710</span></span>  <br/> |
|<span data-ttu-id="1e26f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1e26f-110">Data type:</span></span>  <br/> |<span data-ttu-id="1e26f-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1e26f-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="1e26f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1e26f-112">Area:</span></span>  <br/> |<span data-ttu-id="1e26f-113">邮件附件属性</span><span class="sxs-lookup"><span data-stu-id="1e26f-113">Message Attachment Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1e26f-114">说明</span><span class="sxs-lookup"><span data-stu-id="1e26f-114">Remarks</span></span>

<span data-ttu-id="1e26f-115">此属性用于 MHTML 支持。</span><span class="sxs-lookup"><span data-stu-id="1e26f-115">This property is used for MHTML support.</span></span> <span data-ttu-id="1e26f-116">它表示 mime 邮件的父 mime 多部分正文部分内附件的序列号。</span><span class="sxs-lookup"><span data-stu-id="1e26f-116">It represents the sequence number of the attachment within the parent MIME multipart body part of the MIME message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1e26f-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="1e26f-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="1e26f-118">头文件</span><span class="sxs-lookup"><span data-stu-id="1e26f-118">Header files</span></span>

<span data-ttu-id="1e26f-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1e26f-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="1e26f-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1e26f-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="1e26f-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="1e26f-121">Mapitags.h</span></span>
  
> <span data-ttu-id="1e26f-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1e26f-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1e26f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e26f-123">See also</span></span>



[<span data-ttu-id="1e26f-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1e26f-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1e26f-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1e26f-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1e26f-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1e26f-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1e26f-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1e26f-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

