---
title: PidTagAttachContentLocation 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachContentLocation
api_type:
- HeaderDef
ms.assetid: af2f776c-1b77-4942-827a-4363eda3924f
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d886bf1e30eae6b4b26512eed95988516a609c94
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777325"
---
# <a name="pidtagattachcontentlocation-canonical-property"></a><span data-ttu-id="f24a1-103">PidTagAttachContentLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="f24a1-103">PidTagAttachContentLocation Canonical Property</span></span>

  
  
<span data-ttu-id="f24a1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f24a1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f24a1-105">包含多用途 Internet 邮件扩展 (MIME) 邮件附件的内容位置标头。</span><span class="sxs-lookup"><span data-stu-id="f24a1-105">Contains the content location header of a Multipurpose Internet Mail Extensions (MIME) message attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f24a1-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="f24a1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f24a1-107">PR_ATTACH_CONTENT_LOCATION，PR_ATTACH_CONTENT_LOCATION_A，PR_ATTACH_CONTENT_LOCATION_W</span><span class="sxs-lookup"><span data-stu-id="f24a1-107">PR_ATTACH_CONTENT_LOCATION, PR_ATTACH_CONTENT_LOCATION_A, PR_ATTACH_CONTENT_LOCATION_W</span></span>  <br/> |
|<span data-ttu-id="f24a1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f24a1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f24a1-109">0x3713</span><span class="sxs-lookup"><span data-stu-id="f24a1-109">0x3713</span></span>  <br/> |
|<span data-ttu-id="f24a1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f24a1-110">Data type:</span></span>  <br/> |<span data-ttu-id="f24a1-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f24a1-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="f24a1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f24a1-112">Area:</span></span>  <br/> |<span data-ttu-id="f24a1-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="f24a1-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f24a1-114">备注</span><span class="sxs-lookup"><span data-stu-id="f24a1-114">Remarks</span></span>

<span data-ttu-id="f24a1-115">使用这些属性 MHTML 支持。</span><span class="sxs-lookup"><span data-stu-id="f24a1-115">These properties are used for MHTML support.</span></span> <span data-ttu-id="f24a1-116">它们表示的适当的 MIME 正文部分的内容位置标头。</span><span class="sxs-lookup"><span data-stu-id="f24a1-116">They represent the content location header for the appropriate MIME body part.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f24a1-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="f24a1-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f24a1-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="f24a1-118">Protocol specifications</span></span>

<span data-ttu-id="f24a1-119">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f24a1-119">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f24a1-120">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="f24a1-120">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f24a1-121">头文件</span><span class="sxs-lookup"><span data-stu-id="f24a1-121">Header files</span></span>

<span data-ttu-id="f24a1-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f24a1-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="f24a1-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f24a1-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="f24a1-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f24a1-124">Mapitags.h</span></span>
  
> <span data-ttu-id="f24a1-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f24a1-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f24a1-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f24a1-126">See also</span></span>



[<span data-ttu-id="f24a1-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f24a1-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f24a1-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f24a1-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f24a1-129">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f24a1-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f24a1-130">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f24a1-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

