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
ms.openlocfilehash: 0701bb2cf08c79a69c9cd21e9acf1ce4e8ac4ee1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593072"
---
# <a name="pidtagattachmentflags-canonical-property"></a><span data-ttu-id="2e425-103">PidTagAttachmentFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e425-103">PidTagAttachmentFlags Canonical Property</span></span>

  
  
<span data-ttu-id="2e425-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e425-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e425-105">指示此 Attachment 对象的特殊处理。</span><span class="sxs-lookup"><span data-stu-id="2e425-105">Indicates special handling for this Attachment object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2e425-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2e425-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2e425-107">PR_ATTACHMENT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2e425-107">PR_ATTACHMENT_FLAGS</span></span>  <br/> |
|<span data-ttu-id="2e425-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="2e425-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2e425-109">0x7FFD</span><span class="sxs-lookup"><span data-stu-id="2e425-109">0x7FFD</span></span>  <br/> |
|<span data-ttu-id="2e425-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2e425-110">Data type:</span></span>  <br/> |<span data-ttu-id="2e425-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="2e425-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="2e425-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2e425-112">Area:</span></span>  <br/> |<span data-ttu-id="2e425-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="2e425-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2e425-114">注解</span><span class="sxs-lookup"><span data-stu-id="2e425-114">Remarks</span></span>

<span data-ttu-id="2e425-115">必须 0x00000000，除非由其他协议的扩展邮件和附件对象协议[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)中所述重写</span><span class="sxs-lookup"><span data-stu-id="2e425-115">Must be 0x00000000, unless overridden by other protocols that extend the Message and Attachment Object Protocol as noted in [[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2e425-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="2e425-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2e425-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="2e425-117">Protocol specifications</span></span>

<span data-ttu-id="2e425-118">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e425-118">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e425-119">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="2e425-119">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="2e425-120">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e425-120">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e425-121">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="2e425-121">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2e425-122">头文件</span><span class="sxs-lookup"><span data-stu-id="2e425-122">Header files</span></span>

<span data-ttu-id="2e425-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2e425-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="2e425-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2e425-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="2e425-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2e425-125">Mapitags.h</span></span>
  
> <span data-ttu-id="2e425-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2e425-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2e425-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e425-127">See also</span></span>



[<span data-ttu-id="2e425-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2e425-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2e425-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e425-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2e425-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2e425-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2e425-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2e425-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

