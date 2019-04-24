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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f05fa0816db3b412329372ad392c673c240eb59e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327242"
---
# <a name="pidtagattachmimetag-canonical-property"></a><span data-ttu-id="136d0-103">PidTagAttachMimeTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="136d0-103">PidTagAttachMimeTag Canonical Property</span></span>

  
  
<span data-ttu-id="136d0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="136d0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="136d0-105">包含有关多用途 Internet 邮件扩展 (MIME) 附件的格式信息。</span><span class="sxs-lookup"><span data-stu-id="136d0-105">Contains formatting information about a Multipurpose Internet Mail Extensions (MIME) attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="136d0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="136d0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="136d0-107">PR_ATTACH_MIME_TAG、PR_ATTACH_MIME_TAG_A、PR_ATTACH_MIME_TAG_W</span><span class="sxs-lookup"><span data-stu-id="136d0-107">PR_ATTACH_MIME_TAG, PR_ATTACH_MIME_TAG_A, PR_ATTACH_MIME_TAG_W</span></span>  <br/> |
|<span data-ttu-id="136d0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="136d0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="136d0-109">0x370E</span><span class="sxs-lookup"><span data-stu-id="136d0-109">0x370E</span></span>  <br/> |
|<span data-ttu-id="136d0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="136d0-110">Data type:</span></span>  <br/> |<span data-ttu-id="136d0-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="136d0-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="136d0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="136d0-112">Area:</span></span>  <br/> |<span data-ttu-id="136d0-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="136d0-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="136d0-114">注解</span><span class="sxs-lookup"><span data-stu-id="136d0-114">Remarks</span></span>

<span data-ttu-id="136d0-115">如果**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 属性包含值**OID_MIMETAG**, 则传输提供程序应查看这些属性以确定如何设置附件格式。</span><span class="sxs-lookup"><span data-stu-id="136d0-115">If the **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) property contains the value **OID_MIMETAG**, the transport provider should look at these properties to determine how the attachment is formatted.</span></span> 
  
<span data-ttu-id="136d0-116">这些属性是从入站 MIME 标头的 Content type 参数中复制的。</span><span class="sxs-lookup"><span data-stu-id="136d0-116">These properties are copied from the Content-type parameter of the inbound MIME header.</span></span> <span data-ttu-id="136d0-117">字符串的组成定义在 RFC 1521 文档中。</span><span class="sxs-lookup"><span data-stu-id="136d0-117">The composition of the string is defined in the RFC 1521 document.</span></span> <span data-ttu-id="136d0-118">格式为类型/子类型, 如应用程序/二进制或文本/纯文本。</span><span class="sxs-lookup"><span data-stu-id="136d0-118">The format is type/subtype, such as application/binary or text/plain.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="136d0-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="136d0-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="136d0-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="136d0-120">Protocol specifications</span></span>

<span data-ttu-id="136d0-121">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="136d0-121">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="136d0-122">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="136d0-122">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="136d0-123">[[毫秒-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="136d0-123">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="136d0-124">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="136d0-124">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="136d0-125">头文件</span><span class="sxs-lookup"><span data-stu-id="136d0-125">Header files</span></span>

<span data-ttu-id="136d0-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="136d0-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="136d0-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="136d0-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="136d0-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="136d0-128">Mapitags.h</span></span>
  
> <span data-ttu-id="136d0-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="136d0-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="136d0-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="136d0-130">See also</span></span>



[<span data-ttu-id="136d0-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="136d0-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="136d0-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="136d0-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="136d0-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="136d0-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="136d0-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="136d0-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

