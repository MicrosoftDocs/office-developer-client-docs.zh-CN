---
title: PidLidImageAttachmentsCompressionLevel 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidImageAttachmentsCompressionLevel
api_type:
- COM
ms.assetid: cc169ba8-e9b7-42ad-8f0e-77b0843f95ea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 13e2ac93e7e3ba46bf25b26e76bd44c15f2b89e2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776870"
---
# <a name="pidlidimageattachmentscompressionlevel-canonical-property"></a><span data-ttu-id="2ac86-103">PidLidImageAttachmentsCompressionLevel 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ac86-103">PidLidImageAttachmentsCompressionLevel Canonical Property</span></span>

  
  
<span data-ttu-id="2ac86-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2ac86-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2ac86-105">定义对图像附件应用压缩级别。</span><span class="sxs-lookup"><span data-stu-id="2ac86-105">Defines a compression level to apply on image attachments.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ac86-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2ac86-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2ac86-107">dispidImgAttchmtsCompressLevel</span><span class="sxs-lookup"><span data-stu-id="2ac86-107">dispidImgAttchmtsCompressLevel</span></span>  <br/> |
|<span data-ttu-id="2ac86-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="2ac86-108">Property set:</span></span>  <br/> |<span data-ttu-id="2ac86-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="2ac86-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="2ac86-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="2ac86-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2ac86-111">0x00008593</span><span class="sxs-lookup"><span data-stu-id="2ac86-111">0x00008593</span></span>  <br/> |
|<span data-ttu-id="2ac86-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2ac86-112">Data type:</span></span>  <br/> |<span data-ttu-id="2ac86-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="2ac86-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="2ac86-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2ac86-114">Area:</span></span>  <br/> |<span data-ttu-id="2ac86-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="2ac86-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ac86-116">说明</span><span class="sxs-lookup"><span data-stu-id="2ac86-116">Remarks</span></span>

<span data-ttu-id="2ac86-117">以下是有效的压缩级别：</span><span class="sxs-lookup"><span data-stu-id="2ac86-117">The following are valid compression levels:</span></span>
  
```cpp
enum PictureCompressLevel
{
 pclOriginal = 0,
 pclEmail = 1,
 pclWeb = 2,
 pclDocuments = 3,
};
```

## <a name="related-resources"></a><span data-ttu-id="2ac86-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="2ac86-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2ac86-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="2ac86-119">Protocol specifications</span></span>

<span data-ttu-id="2ac86-120">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="2ac86-120">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="2ac86-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2ac86-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2ac86-122">头文件</span><span class="sxs-lookup"><span data-stu-id="2ac86-122">Header files</span></span>

<span data-ttu-id="2ac86-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2ac86-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="2ac86-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2ac86-124">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2ac86-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ac86-125">See also</span></span>



[<span data-ttu-id="2ac86-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2ac86-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2ac86-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ac86-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2ac86-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2ac86-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2ac86-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ac86-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

