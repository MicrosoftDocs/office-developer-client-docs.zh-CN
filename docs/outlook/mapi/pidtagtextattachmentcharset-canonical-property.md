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
ms.openlocfilehash: 1db41bc5c7ea71d65d892da520d4258354eb53cf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358812"
---
# <a name="pidtagtextattachmentcharset-canonical-property"></a><span data-ttu-id="ca8c4-103">PidTagTextAttachmentCharset 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca8c4-103">PidTagTextAttachmentCharset Canonical Property</span></span>

  
  
<span data-ttu-id="ca8c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca8c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca8c4-105">包含邮件附件的字符集值。</span><span class="sxs-lookup"><span data-stu-id="ca8c4-105">Contains a message attachment's character set value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ca8c4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ca8c4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ca8c4-107">无</span><span class="sxs-lookup"><span data-stu-id="ca8c4-107">None</span></span>  <br/> |
|<span data-ttu-id="ca8c4-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ca8c4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ca8c4-109">0x371B</span><span class="sxs-lookup"><span data-stu-id="ca8c4-109">0x371B</span></span>  <br/> |
|<span data-ttu-id="ca8c4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ca8c4-110">Data type:</span></span>  <br/> |<span data-ttu-id="ca8c4-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ca8c4-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ca8c4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ca8c4-112">Area:</span></span>  <br/> |<span data-ttu-id="ca8c4-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="ca8c4-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ca8c4-114">备注</span><span class="sxs-lookup"><span data-stu-id="ca8c4-114">Remarks</span></span>

<span data-ttu-id="ca8c4-115">如果存在"charset"参数，则此属性的数据派生自以"text/"开头的 Content-Type MIME 头字段。</span><span class="sxs-lookup"><span data-stu-id="ca8c4-115">This property's data is derived from a Content-Type MIME header field that starts with "text/", if a "charset" parameter is present.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ca8c4-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="ca8c4-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ca8c4-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="ca8c4-117">Protocol specifications</span></span>

<span data-ttu-id="ca8c4-118">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ca8c4-118">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ca8c4-119">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="ca8c4-119">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ca8c4-120">头文件</span><span class="sxs-lookup"><span data-stu-id="ca8c4-120">Header files</span></span>

<span data-ttu-id="ca8c4-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ca8c4-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="ca8c4-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ca8c4-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="ca8c4-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ca8c4-123">Mapitags.h</span></span>
  
> <span data-ttu-id="ca8c4-124">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ca8c4-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ca8c4-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca8c4-125">See also</span></span>



[<span data-ttu-id="ca8c4-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ca8c4-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ca8c4-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca8c4-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ca8c4-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ca8c4-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ca8c4-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ca8c4-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

