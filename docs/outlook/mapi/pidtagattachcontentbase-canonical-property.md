---
title: PidTagAttachContentBase 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachContentBase
api_type:
- HeaderDef
ms.assetid: 35c10264-6998-4c46-8cef-82708c96d9c7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 40e2efbf512265dffeee43d09e85879e8c3a0e56
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582418"
---
# <a name="pidtagattachcontentbase-canonical-property"></a><span data-ttu-id="131d5-103">PidTagAttachContentBase 规范属性</span><span class="sxs-lookup"><span data-stu-id="131d5-103">PidTagAttachContentBase Canonical Property</span></span>

  
  
<span data-ttu-id="131d5-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="131d5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="131d5-105">包含多用途 Internet 邮件扩展 (MIME) 邮件附件的内容的基本标头。</span><span class="sxs-lookup"><span data-stu-id="131d5-105">Contains the content base header of a Multipurpose Internet Mail Extensions (MIME) message attachment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="131d5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="131d5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="131d5-107">PR_ATTACH_CONTENT_BASE，PR_ATTACH_CONTENT_BASE_A，PR_ATTACH_CONTENT_BASE_W</span><span class="sxs-lookup"><span data-stu-id="131d5-107">PR_ATTACH_CONTENT_BASE, PR_ATTACH_CONTENT_BASE_A, PR_ATTACH_CONTENT_BASE_W</span></span>  <br/> |
|<span data-ttu-id="131d5-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="131d5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="131d5-109">0x3711</span><span class="sxs-lookup"><span data-stu-id="131d5-109">0x3711</span></span>  <br/> |
|<span data-ttu-id="131d5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="131d5-110">Data type:</span></span>  <br/> |<span data-ttu-id="131d5-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="131d5-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="131d5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="131d5-112">Area:</span></span>  <br/> |<span data-ttu-id="131d5-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="131d5-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="131d5-114">注解</span><span class="sxs-lookup"><span data-stu-id="131d5-114">Remarks</span></span>

<span data-ttu-id="131d5-115">使用这些属性 MHTML 支持。</span><span class="sxs-lookup"><span data-stu-id="131d5-115">These properties are used for MHTML support.</span></span> <span data-ttu-id="131d5-116">它们表示的适当的 MIME 正文部分内容的基本标头。</span><span class="sxs-lookup"><span data-stu-id="131d5-116">They represent the content base header for the appropriate MIME body part.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="131d5-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="131d5-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="131d5-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="131d5-118">Protocol specifications</span></span>

<span data-ttu-id="131d5-119">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="131d5-119">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="131d5-120">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="131d5-120">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="131d5-121">头文件</span><span class="sxs-lookup"><span data-stu-id="131d5-121">Header files</span></span>

<span data-ttu-id="131d5-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="131d5-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="131d5-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="131d5-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="131d5-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="131d5-124">Mapitags.h</span></span>
  
> <span data-ttu-id="131d5-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="131d5-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="131d5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="131d5-126">See also</span></span>



[<span data-ttu-id="131d5-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="131d5-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="131d5-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="131d5-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="131d5-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="131d5-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="131d5-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="131d5-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

