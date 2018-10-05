---
title: PidTagAttachmentLinkId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachmentLinkId
api_type:
- HeaderDef
ms.assetid: 5d0daae7-248d-459f-9d96-cb949b86f590
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 623b4195b7128667b9aaa6bc97d03c21d62c690a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394830"
---
# <a name="pidtagattachmentlinkid-canonical-property"></a><span data-ttu-id="835f4-103">PidTagAttachmentLinkId 规范属性</span><span class="sxs-lookup"><span data-stu-id="835f4-103">PidTagAttachmentLinkId Canonical Property</span></span>

  
  
<span data-ttu-id="835f4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="835f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="835f4-105">指示此附件链接到的消息对象的类型。</span><span class="sxs-lookup"><span data-stu-id="835f4-105">Indicates the type of Message object to which this attachment is linked.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="835f4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="835f4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="835f4-107">PR_ATTACHMENT_LINKID</span><span class="sxs-lookup"><span data-stu-id="835f4-107">PR_ATTACHMENT_LINKID</span></span>  <br/> |
|<span data-ttu-id="835f4-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="835f4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="835f4-109">0x7FFA</span><span class="sxs-lookup"><span data-stu-id="835f4-109">0x7FFA</span></span>  <br/> |
|<span data-ttu-id="835f4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="835f4-110">Data type:</span></span>  <br/> |<span data-ttu-id="835f4-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="835f4-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="835f4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="835f4-112">Area:</span></span>  <br/> |<span data-ttu-id="835f4-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="835f4-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="835f4-114">说明</span><span class="sxs-lookup"><span data-stu-id="835f4-114">Remarks</span></span>

<span data-ttu-id="835f4-115">必须为 0，除非覆盖其他协议的扩展邮件和附件对象协议[[MS OXCMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="835f4-115">Must be 0, unless overridden by other protocols that extend the Message and Attachment Object Protocol as noted in [[MS-OXCMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="835f4-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="835f4-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="835f4-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="835f4-117">Protocol specifications</span></span>

<span data-ttu-id="835f4-118">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="835f4-118">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="835f4-119">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="835f4-119">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="835f4-120">[[MS OXOJRNL]](https://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="835f4-120">[[MS-OXOJRNL]](https://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="835f4-121">指定的属性和操作所允许的日记对象。</span><span class="sxs-lookup"><span data-stu-id="835f4-121">Specifies the properties and operations that are permissible for journal objects.</span></span>
    
<span data-ttu-id="835f4-122">[[MS OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="835f4-122">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="835f4-123">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="835f4-123">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="835f4-124">头文件</span><span class="sxs-lookup"><span data-stu-id="835f4-124">Header files</span></span>

<span data-ttu-id="835f4-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="835f4-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="835f4-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="835f4-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="835f4-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="835f4-127">Mapitags.h</span></span>
  
> <span data-ttu-id="835f4-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="835f4-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="835f4-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="835f4-129">See also</span></span>



[<span data-ttu-id="835f4-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="835f4-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="835f4-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="835f4-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="835f4-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="835f4-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="835f4-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="835f4-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

