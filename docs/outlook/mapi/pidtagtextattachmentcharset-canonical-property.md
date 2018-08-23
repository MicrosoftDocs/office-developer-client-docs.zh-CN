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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cec34819cfa2c6e790f8808eb5bab70412f286b5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591427"
---
# <a name="pidtagtextattachmentcharset-canonical-property"></a><span data-ttu-id="ed5e1-103">PidTagTextAttachmentCharset 规范属性</span><span class="sxs-lookup"><span data-stu-id="ed5e1-103">PidTagTextAttachmentCharset Canonical Property</span></span>

  
  
<span data-ttu-id="ed5e1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed5e1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ed5e1-105">包含邮件附件的字符设置值。</span><span class="sxs-lookup"><span data-stu-id="ed5e1-105">Contains a message attachment's character set value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ed5e1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ed5e1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ed5e1-107">无</span><span class="sxs-lookup"><span data-stu-id="ed5e1-107">None</span></span>  <br/> |
|<span data-ttu-id="ed5e1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ed5e1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ed5e1-109">0x371B</span><span class="sxs-lookup"><span data-stu-id="ed5e1-109">0x371B</span></span>  <br/> |
|<span data-ttu-id="ed5e1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ed5e1-110">Data type:</span></span>  <br/> |<span data-ttu-id="ed5e1-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ed5e1-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ed5e1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ed5e1-112">Area:</span></span>  <br/> |<span data-ttu-id="ed5e1-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="ed5e1-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ed5e1-114">注解</span><span class="sxs-lookup"><span data-stu-id="ed5e1-114">Remarks</span></span>

<span data-ttu-id="ed5e1-115">此属性的数据派生开头的内容类型 MIME 标头字段中的"文本 /"、"字符集"参数是否存在。</span><span class="sxs-lookup"><span data-stu-id="ed5e1-115">This property's data is derived from a Content-Type MIME header field that starts with "text/", if a "charset" parameter is present.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ed5e1-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="ed5e1-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ed5e1-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="ed5e1-117">Protocol specifications</span></span>

<span data-ttu-id="ed5e1-118">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ed5e1-118">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ed5e1-119">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="ed5e1-119">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ed5e1-120">头文件</span><span class="sxs-lookup"><span data-stu-id="ed5e1-120">Header files</span></span>

<span data-ttu-id="ed5e1-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ed5e1-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="ed5e1-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ed5e1-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="ed5e1-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ed5e1-123">Mapitags.h</span></span>
  
> <span data-ttu-id="ed5e1-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ed5e1-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ed5e1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed5e1-125">See also</span></span>



[<span data-ttu-id="ed5e1-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ed5e1-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ed5e1-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ed5e1-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ed5e1-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ed5e1-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ed5e1-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ed5e1-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

