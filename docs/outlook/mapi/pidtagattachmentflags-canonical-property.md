---
title: PidTagAttachmentFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachmentFlags
api_type:
- HeaderDef
ms.assetid: 42981aac-f9e7-45dd-91a2-15d9784f30aa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d494f1f14daff75be55e910da56204ecb3dbcf83
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400710"
---
# <a name="pidtagattachmentflags-canonical-property"></a><span data-ttu-id="15b11-103">PidTagAttachmentFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="15b11-103">PidTagAttachmentFlags Canonical Property</span></span>

  
  
<span data-ttu-id="15b11-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="15b11-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="15b11-105">指示此 Attachment 对象的特殊处理。</span><span class="sxs-lookup"><span data-stu-id="15b11-105">Indicates special handling for this Attachment object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="15b11-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="15b11-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="15b11-107">PR_ATTACHMENT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="15b11-107">PR_ATTACHMENT_FLAGS</span></span>  <br/> |
|<span data-ttu-id="15b11-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="15b11-108">Identifier:</span></span>  <br/> |<span data-ttu-id="15b11-109">0x7FFD</span><span class="sxs-lookup"><span data-stu-id="15b11-109">0x7FFD</span></span>  <br/> |
|<span data-ttu-id="15b11-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="15b11-110">Data type:</span></span>  <br/> |<span data-ttu-id="15b11-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="15b11-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="15b11-112">区域：</span><span class="sxs-lookup"><span data-stu-id="15b11-112">Area:</span></span>  <br/> |<span data-ttu-id="15b11-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="15b11-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="15b11-114">说明</span><span class="sxs-lookup"><span data-stu-id="15b11-114">Remarks</span></span>

<span data-ttu-id="15b11-115">必须 0x00000000，除非由其他协议的扩展邮件和附件对象协议[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)中所述重写</span><span class="sxs-lookup"><span data-stu-id="15b11-115">Must be 0x00000000, unless overridden by other protocols that extend the Message and Attachment Object Protocol as noted in [[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="15b11-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="15b11-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="15b11-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="15b11-117">Protocol specifications</span></span>

<span data-ttu-id="15b11-118">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15b11-118">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15b11-119">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="15b11-119">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="15b11-120">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15b11-120">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15b11-121">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="15b11-121">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="15b11-122">头文件</span><span class="sxs-lookup"><span data-stu-id="15b11-122">Header files</span></span>

<span data-ttu-id="15b11-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="15b11-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="15b11-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="15b11-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="15b11-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="15b11-125">Mapitags.h</span></span>
  
> <span data-ttu-id="15b11-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="15b11-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="15b11-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15b11-127">See also</span></span>



[<span data-ttu-id="15b11-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="15b11-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="15b11-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="15b11-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="15b11-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="15b11-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="15b11-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="15b11-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

