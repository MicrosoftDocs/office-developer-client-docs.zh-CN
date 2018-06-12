---
title: PidTagAttachMimeTag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachMimeTag
api_type:
- HeaderDef
ms.assetid: cbc4585d-f970-4b22-ac08-d7fc91bff3d3
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6f65d67903fa9ebb255345f8666cd53de5512cab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777360"
---
# <a name="pidtagattachmimetag-canonical-property"></a><span data-ttu-id="b7322-103">PidTagAttachMimeTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="b7322-103">PidTagAttachMimeTag Canonical Property</span></span>

  
  
<span data-ttu-id="b7322-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b7322-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b7322-105">包含有关多用途 Internet 邮件扩展 (MIME) 附件格式信息。</span><span class="sxs-lookup"><span data-stu-id="b7322-105">Contains formatting information about a Multipurpose Internet Mail Extensions (MIME) attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b7322-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="b7322-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b7322-107">PR_ATTACH_MIME_TAG，PR_ATTACH_MIME_TAG_A，PR_ATTACH_MIME_TAG_W</span><span class="sxs-lookup"><span data-stu-id="b7322-107">PR_ATTACH_MIME_TAG, PR_ATTACH_MIME_TAG_A, PR_ATTACH_MIME_TAG_W</span></span>  <br/> |
|<span data-ttu-id="b7322-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b7322-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b7322-109">0x370E</span><span class="sxs-lookup"><span data-stu-id="b7322-109">0x370E</span></span>  <br/> |
|<span data-ttu-id="b7322-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b7322-110">Data type:</span></span>  <br/> |<span data-ttu-id="b7322-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b7322-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b7322-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b7322-112">Area:</span></span>  <br/> |<span data-ttu-id="b7322-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="b7322-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b7322-114">备注</span><span class="sxs-lookup"><span data-stu-id="b7322-114">Remarks</span></span>

<span data-ttu-id="b7322-115">如果**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 属性包含值**OID_MIMETAG**，这些属性来确定如何设置附件的格式应查看传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="b7322-115">If the **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) property contains the value **OID_MIMETAG**, the transport provider should look at these properties to determine how the attachment is formatted.</span></span> 
  
<span data-ttu-id="b7322-116">入站 MIME 标头的内容类型参数复制这些属性。</span><span class="sxs-lookup"><span data-stu-id="b7322-116">These properties are copied from the Content-type parameter of the inbound MIME header.</span></span> <span data-ttu-id="b7322-117">RFC 1521 文档中定义的字符串组成。</span><span class="sxs-lookup"><span data-stu-id="b7322-117">The composition of the string is defined in the RFC 1521 document.</span></span> <span data-ttu-id="b7322-118">格式为类型/子类型，如应用程序中的二进制或 text/plain。</span><span class="sxs-lookup"><span data-stu-id="b7322-118">The format is type/subtype, such as application/binary or text/plain.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b7322-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="b7322-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b7322-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="b7322-120">Protocol specifications</span></span>

<span data-ttu-id="b7322-121">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b7322-121">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b7322-122">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="b7322-122">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="b7322-123">[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b7322-123">[[MS-OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b7322-124">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="b7322-124">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b7322-125">头文件</span><span class="sxs-lookup"><span data-stu-id="b7322-125">Header files</span></span>

<span data-ttu-id="b7322-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b7322-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="b7322-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b7322-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="b7322-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b7322-128">Mapitags.h</span></span>
  
> <span data-ttu-id="b7322-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b7322-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b7322-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7322-130">See also</span></span>



[<span data-ttu-id="b7322-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b7322-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b7322-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b7322-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b7322-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b7322-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b7322-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b7322-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

