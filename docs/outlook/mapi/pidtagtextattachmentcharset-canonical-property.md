---
title: PidTagTextAttachmentCharset 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTextAttachmentCharset
api_type:
- COM
ms.assetid: d347c949-d0c3-4a36-8447-3fa01111cdc1
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c728799832b10ad2d4533a9a040582b67054baad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778511"
---
# <a name="pidtagtextattachmentcharset-canonical-property"></a><span data-ttu-id="7b6b7-103">PidTagTextAttachmentCharset 规范属性</span><span class="sxs-lookup"><span data-stu-id="7b6b7-103">PidTagTextAttachmentCharset Canonical Property</span></span>

  
  
<span data-ttu-id="7b6b7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7b6b7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7b6b7-105">包含邮件附件的字符设置值。</span><span class="sxs-lookup"><span data-stu-id="7b6b7-105">Contains a message attachment's character set value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7b6b7-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="7b6b7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7b6b7-107">无</span><span class="sxs-lookup"><span data-stu-id="7b6b7-107">None</span></span>  <br/> |
|<span data-ttu-id="7b6b7-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7b6b7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7b6b7-109">0x371B</span><span class="sxs-lookup"><span data-stu-id="7b6b7-109">0x371B</span></span>  <br/> |
|<span data-ttu-id="7b6b7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7b6b7-110">Data type:</span></span>  <br/> |<span data-ttu-id="7b6b7-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7b6b7-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7b6b7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7b6b7-112">Area:</span></span>  <br/> |<span data-ttu-id="7b6b7-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="7b6b7-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7b6b7-114">备注</span><span class="sxs-lookup"><span data-stu-id="7b6b7-114">Remarks</span></span>

<span data-ttu-id="7b6b7-115">此属性的数据派生开头的内容类型 MIME 标头字段中的"文本 /"、"字符集"参数是否存在。</span><span class="sxs-lookup"><span data-stu-id="7b6b7-115">This property's data is derived from a Content-Type MIME header field that starts with "text/", if a "charset" parameter is present.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7b6b7-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="7b6b7-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7b6b7-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="7b6b7-117">Protocol specifications</span></span>

<span data-ttu-id="7b6b7-118">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7b6b7-118">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7b6b7-119">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="7b6b7-119">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7b6b7-120">头文件</span><span class="sxs-lookup"><span data-stu-id="7b6b7-120">Header files</span></span>

<span data-ttu-id="7b6b7-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7b6b7-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="7b6b7-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7b6b7-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="7b6b7-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7b6b7-123">Mapitags.h</span></span>
  
> <span data-ttu-id="7b6b7-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7b6b7-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7b6b7-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b6b7-125">See also</span></span>



[<span data-ttu-id="7b6b7-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7b6b7-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7b6b7-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7b6b7-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7b6b7-128">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7b6b7-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7b6b7-129">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7b6b7-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

