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
ms.openlocfilehash: ec1db68d9168e7260a32aaf7708897df6124725a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360506"
---
# <a name="pidtagattachcontentbase-canonical-property"></a><span data-ttu-id="efa71-103">PidTagAttachContentBase 规范属性</span><span class="sxs-lookup"><span data-stu-id="efa71-103">PidTagAttachContentBase Canonical Property</span></span>

  
  
<span data-ttu-id="efa71-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="efa71-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="efa71-105">包含多用途 Internet 邮件扩展 (MIME) 邮件附件的内容基标头。</span><span class="sxs-lookup"><span data-stu-id="efa71-105">Contains the content base header of a Multipurpose Internet Mail Extensions (MIME) message attachment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="efa71-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="efa71-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="efa71-107">PR_ATTACH_CONTENT_BASE、PR_ATTACH_CONTENT_BASE_A、PR_ATTACH_CONTENT_BASE_W</span><span class="sxs-lookup"><span data-stu-id="efa71-107">PR_ATTACH_CONTENT_BASE, PR_ATTACH_CONTENT_BASE_A, PR_ATTACH_CONTENT_BASE_W</span></span>  <br/> |
|<span data-ttu-id="efa71-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="efa71-108">Identifier:</span></span>  <br/> |<span data-ttu-id="efa71-109">0x3711</span><span class="sxs-lookup"><span data-stu-id="efa71-109">0x3711</span></span>  <br/> |
|<span data-ttu-id="efa71-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="efa71-110">Data type:</span></span>  <br/> |<span data-ttu-id="efa71-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="efa71-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="efa71-112">区域：</span><span class="sxs-lookup"><span data-stu-id="efa71-112">Area:</span></span>  <br/> |<span data-ttu-id="efa71-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="efa71-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="efa71-114">注解</span><span class="sxs-lookup"><span data-stu-id="efa71-114">Remarks</span></span>

<span data-ttu-id="efa71-115">这些属性用于 MHTML 支持。</span><span class="sxs-lookup"><span data-stu-id="efa71-115">These properties are used for MHTML support.</span></span> <span data-ttu-id="efa71-116">它们表示相应 MIME 正文部分的内容基头。</span><span class="sxs-lookup"><span data-stu-id="efa71-116">They represent the content base header for the appropriate MIME body part.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="efa71-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="efa71-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="efa71-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="efa71-118">Protocol specifications</span></span>

<span data-ttu-id="efa71-119">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="efa71-119">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="efa71-120">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="efa71-120">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="efa71-121">头文件</span><span class="sxs-lookup"><span data-stu-id="efa71-121">Header files</span></span>

<span data-ttu-id="efa71-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="efa71-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="efa71-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="efa71-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="efa71-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="efa71-124">Mapitags.h</span></span>
  
> <span data-ttu-id="efa71-125">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="efa71-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="efa71-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efa71-126">See also</span></span>



[<span data-ttu-id="efa71-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="efa71-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="efa71-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="efa71-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="efa71-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="efa71-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="efa71-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="efa71-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

