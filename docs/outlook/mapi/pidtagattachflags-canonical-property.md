---
title: PidTagAttachFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachFlags
api_type:
- HeaderDef
ms.assetid: 47e01131-f399-43cb-9815-aba69638c3fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: efccd75cce04e4e392a7fbd9feecc7c8b49ab57e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339331"
---
# <a name="pidtagattachflags-canonical-property"></a><span data-ttu-id="1a842-103">PidTagAttachFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="1a842-103">PidTagAttachFlags Canonical Property</span></span>

  
  
<span data-ttu-id="1a842-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1a842-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1a842-105">包含附件标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="1a842-105">Contains a bitmask of flags for an attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1a842-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1a842-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1a842-107">PR_ATTACH_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1a842-107">PR_ATTACH_FLAGS</span></span>  <br/> |
|<span data-ttu-id="1a842-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1a842-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1a842-109">0x3714</span><span class="sxs-lookup"><span data-stu-id="1a842-109">0x3714</span></span>  <br/> |
|<span data-ttu-id="1a842-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1a842-110">Data type:</span></span>  <br/> |<span data-ttu-id="1a842-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1a842-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="1a842-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1a842-112">Area:</span></span>  <br/> |<span data-ttu-id="1a842-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="1a842-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1a842-114">备注</span><span class="sxs-lookup"><span data-stu-id="1a842-114">Remarks</span></span>

<span data-ttu-id="1a842-115">此属性用于 MHTML 支持。</span><span class="sxs-lookup"><span data-stu-id="1a842-115">This property is used for MHTML support.</span></span> 
  
<span data-ttu-id="1a842-116">可以针对该位掩码设置以下一个或多个PR_ATTACH_FLAGS标记： </span><span class="sxs-lookup"><span data-stu-id="1a842-116">One or more of the following flags can be set for the **PR_ATTACH_FLAGS** bitmask:</span></span> 
  
<span data-ttu-id="1a842-117">ATT_INVISIBLE_IN_HTML</span><span class="sxs-lookup"><span data-stu-id="1a842-117">ATT_INVISIBLE_IN_HTML</span></span> 
  
> <span data-ttu-id="1a842-118">指示此附件对 HTML 呈现应用程序不可用，应在 MIME 应用程序处理的多用途 Internet 邮件扩展 (忽略) 。</span><span class="sxs-lookup"><span data-stu-id="1a842-118">Indicates that this attachment is not available to HTML rendering applications and should be ignored in Multipurpose Internet Mail Extensions (MIME) processing.</span></span> 
    
<span data-ttu-id="1a842-119">ATT_INVISIBLE_IN_RTF</span><span class="sxs-lookup"><span data-stu-id="1a842-119">ATT_INVISIBLE_IN_RTF</span></span> 
  
> <span data-ttu-id="1a842-120">指示此附件不适用于 RTF 格式的 RTF (格式) MAPI 应忽略此附件。</span><span class="sxs-lookup"><span data-stu-id="1a842-120">Indicates that this attachment is not available to applications rendering in Rich Text Format (RTF) and should be ignored by MAPI.</span></span>
    
<span data-ttu-id="1a842-121">如果 **PR_ATTACH_FLAGS** 属性为零或不存在，则所有应用程序将处理附件。</span><span class="sxs-lookup"><span data-stu-id="1a842-121">If the **PR_ATTACH_FLAGS** property is zero or absent, the attachment is to be processed by all applications.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1a842-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="1a842-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1a842-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="1a842-123">Protocol specifications</span></span>

<span data-ttu-id="1a842-124">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1a842-124">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1a842-125">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="1a842-125">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1a842-126">头文件</span><span class="sxs-lookup"><span data-stu-id="1a842-126">Header files</span></span>

<span data-ttu-id="1a842-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1a842-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="1a842-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1a842-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="1a842-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1a842-129">Mapitags.h</span></span>
  
> <span data-ttu-id="1a842-130">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1a842-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1a842-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a842-131">See also</span></span>



[<span data-ttu-id="1a842-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1a842-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1a842-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1a842-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1a842-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1a842-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1a842-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1a842-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

