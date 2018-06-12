---
title: PidTagAttachAdditionalInformation 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachAdditionalInformation
api_type:
- HeaderDef
ms.assetid: 75f092f2-ee3f-45c2-a46f-e1dff2e22b2e
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 83de3a4ad7c93b2dfee8063ab63bfbf0724a5f61
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777323"
---
# <a name="pidtagattachadditionalinformation-canonical-property"></a><span data-ttu-id="84931-103">PidTagAttachAdditionalInformation 规范属性</span><span class="sxs-lookup"><span data-stu-id="84931-103">PidTagAttachAdditionalInformation Canonical Property</span></span>

  
  
<span data-ttu-id="84931-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="84931-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="84931-105">提供有关非 Windows 附件的文件类型信息。</span><span class="sxs-lookup"><span data-stu-id="84931-105">Provides file type information for a non-Windows attachment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="84931-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="84931-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="84931-107">PR_ATTACH_ADDITIONAL_INFO</span><span class="sxs-lookup"><span data-stu-id="84931-107">PR_ATTACH_ADDITIONAL_INFO</span></span>  <br/> |
|<span data-ttu-id="84931-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="84931-108">Identifier:</span></span>  <br/> |<span data-ttu-id="84931-109">0x370F</span><span class="sxs-lookup"><span data-stu-id="84931-109">0x370F</span></span>  <br/> |
|<span data-ttu-id="84931-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="84931-110">Data type:</span></span>  <br/> |<span data-ttu-id="84931-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="84931-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="84931-112">区域：</span><span class="sxs-lookup"><span data-stu-id="84931-112">Area:</span></span>  <br/> |<span data-ttu-id="84931-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="84931-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="84931-114">备注</span><span class="sxs-lookup"><span data-stu-id="84931-114">Remarks</span></span>

<span data-ttu-id="84931-115">此属性提供有关基于附件的编码的特定附件元数据。</span><span class="sxs-lookup"><span data-stu-id="84931-115">This property provides metadata about a particular attachment based on the attachment's encoding.</span></span> <span data-ttu-id="84931-116">例如，如果**PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)) 属性包含 MacBinary， **PR_ATTACH_ADDITIONAL_INFO**包含一个字符串，表示 Macintosh 文件创建者和文件类型，格式为":CREA:TYPE"编码 Macintosh 文件。</span><span class="sxs-lookup"><span data-stu-id="84931-116">For example, when the **PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)) property contains MacBinary, **PR_ATTACH_ADDITIONAL_INFO** contains a string that represents the Macintosh file creator and file type, formatted as ":CREA:TYPE" for the encoded Macintosh file.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="84931-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="84931-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="84931-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="84931-118">Protocol specifications</span></span>

<span data-ttu-id="84931-119">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="84931-119">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="84931-120">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="84931-120">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="84931-121">头文件</span><span class="sxs-lookup"><span data-stu-id="84931-121">Header files</span></span>

<span data-ttu-id="84931-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="84931-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="84931-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="84931-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="84931-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="84931-124">Mapitags.h</span></span>
  
> <span data-ttu-id="84931-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="84931-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="84931-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84931-126">See also</span></span>



[<span data-ttu-id="84931-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="84931-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="84931-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="84931-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="84931-129">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="84931-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="84931-130">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="84931-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

